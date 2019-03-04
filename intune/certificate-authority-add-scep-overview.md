---
title: Use third-party CA with SCEP in Microsoft Intune - Azure | Microsoft Docs
description: In Microsoft Intune, you can add a vendor or 3rd party certificate authority (CA) to issue certificates to mobile devices using the SCEP protocol. In this overview, an Azure Active Directory (Azure AD) application gives Microsoft Intune permissions to validate certificates. Then, use the application ID, authentication key, and tenant ID of the AAD application in the setup of your SCEP server to issue certificates. 
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 07/26/2018
ms.topic: conceptual
ms.prod:
ms.service: microsoft-intune
ms.technology:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure
ms.collection: M365-identity-device-management
---

# Add partner certification authority in Intune using SCEP

In Microsoft Intune, third-party certification authorities (CA) can be added. These CAs can deliver certificates to mobile devices using the Simple Certificate Enrollment Protocol (SCEP). This feature can issue new certificates and renew certificates on Windows, iOS, Android, and macOS devices.

There are two parts to using this feature: open-source API, and the Intune administrator tasks.

**Part 1 - Use an open-source API**  
Microsoft created an API that integrates with Intune to validate certificates, send success or failure notifications, and use SSL, specifically SSL socket factory, to communicate with Intune.

The API is available on the [Intune SCEP API public GitHub repository](http://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation) for you to download, and use in your solutions. Use this API with third-party SCEP servers to run custom challenge validation against Intune before delivering a certificate to a device.

[Integrate with Intune SCEP management solution](scep-libraries-apis.md) provides more details on using the API, its methods, and testing the solution you build.

**Part 2 - Create the application and profile**  
Using an Azure Active Directory (Azure AD) application, you can delegate rights to Intune to handle SCEP requests coming from devices. The Azure AD application includes application ID and authentication key values that are used within the API solution the developer creates. Administrators can then create and deploy SCEP certificates profiles using Intune. You can also view reports on the deployment status on the devices.

This article provides an overview of this feature from an Administrator-perspective, including creating the Azure AD application.

## Overview

The following steps provide an overview of issuing SCEP certificates in Intune:

1. In Intune, an administrator creates a SCEP certificate profile, and then targets the profile to users or devices.
2. The device checks in to Intune.
3. Intune creates a unique SCEP challenge. It also adds additional integrity-check information, such as what the expected subject and SAN should be.
4. Intune encrypts and signs both the challenge and integrity-check information, and then sends this information to the device with the SCEP request.
5. The device generates a certificate signing request (CSR) and public/private key pair on the device based on the SCEP certificate profile that's pushed from Intune.
6. The CSR and encrypted/signed challenge are sent to the third-party SCEP server endpoint.
7. The SCEP server sends the CSR and the challenge to Intune. Intune then validates the signature, decrypts the payload, and compares the CSR to the integrity-check information.
8. Intune sends back a response to the SCEP server, and states whether the challenge validation is successful or not.  
9. If the challenge is successfully verified, then the SCEP server issues the certificate to the device.

The following diagram shows a detailed flow of third-party SCEP integration with Intune:

![How third-party certification authority SCEP integrates with Microsoft Intune](./media/scep-certificate-vendor-integration.png)

## Set up third-party CA integration

### Validate third-party certification authority

Before integrating third-party certification authorities with Intune, confirm that the CA you're using supports Intune. [Third-party CA partners](#third-party-certification-authority-partners) (in this article) includes a list. You can also check your certification authority's guidance for more information. The CA may include setup instructions specific to their implementation.

### Authorize communication between CA and Intune

To allow a third-party SCEP server to run custom challenge validation with Intune, create an app in Azure AD. This app gives delegated rights to Intune to validate SCEP requests.

Be sure you have the required permissions to register an Azure AD app. [Required permissions](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal#required-permissions) lists the steps.

**Step 1: Create an Azure AD application**

1. Sign in to the [Azure portal](https://portal.azure.com).
2. Select **Azure Active Directory** > **App registrations** > **New application registration**.
3. Enter a name and sign-on URL. Select **Web app / API** for the application type.
4. Select **Create**.

[Integrate applications with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications) includes some guidance on creating an app, including tips on the URL and name.

**Step 2: Give permissions**

After creating your application, give the Microsoft Intune API the required permissions:

1. In your Azure AD app, open **Settings** > **Required Permissions**.  
2. Select **Add** > **Select an API** > select **Microsoft Intune API** > **Select**.
3. In **Select permissions**, choose **SCEP challenge validation** > **Select**.
4. Select **Done** to save your changes.

**Step 3: Get the application ID and authentication key**

Next, get the ID and key values of your Azure AD application. The following values are needed:

- Application ID
- Authentication Key
- Tenant ID

**To get the application ID and authentication key**:

1. In Azure AD, select your new application (**App registrations**).
2. Copy the **Application ID**, and store it in your application code.
3. Next generate an authentication key. In your Azure AD app, open **Settings** > **Keys**.
4. In **Passwords**, enter a description, and choose the duration of the key. **Save** your changes. Copy and save the value shown.

    > [!IMPORTANT]
    > Copy and save this key immediately, as it's not shown again. This key value is needed with your third-party CA implementation. Be sure to review their guidance on how they want the Application ID, Authentication Key, and Tenant ID configured.

The **Tenant ID** is the domain text after the @ sign in your account. For example, if your account is `admin@name.onmicrosoft.com`, then your tenant ID is **name.onmicrosoft.com**.

[Get application ID and authentication key](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal#get-application-id-and-authentication-key) lists the steps to get these values, and provides more details on Azure AD apps.

### Configure and deploy a SCEP certificate profile
As the administrator, create a SCEP certificate profile to target to users or devices. Then, assign the profile.

- [Create a SCEP certificate profile](certificates-scep-configure.md#create-a-scep-certificate-profile)

- [Assign the certificate profile](certificates-scep-configure.md#assign-the-certificate-profile)

## Removing certificates

When you unenroll or wipe the device, the certificates are removed. The certificates aren't revoked.

## Third-party certification authority partners
The following third-party certification authorities support Intune:

- [Entrust Datacard](http://www.entrustdatacard.com/resource-center/documents/documentation)
- [EJBCA GitHub open-source version](https://github.com/agerbergt/intune-ejbca-connector)
- [EverTrust](https://evertrust.fr/en/products/)

If you're a third-party CA interested in integrating your product with Intune, review the API guidance:

- [Intune SCEP API GitHub repository](http://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation)
- [Intune SCEP API guidance for third party CAs](scep-libraries-apis.md)

## See also

- [Configure certificate profiles](certificates-scep-configure.md)
- [Intune SCEP API GitHub repository](http://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation)
- [Intune SCEP API guidance for third party CAs](scep-libraries-apis.md)
