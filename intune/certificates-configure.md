---
# required metadata

title: Create certificates profile in Microsoft Intune - Azure | Microsoft Docs
description: For your devices, add or create a certificate profile by configuring SCEP or PKCS certificate environment, export the public certificate, create the profile in the Azure portal, and then assign SCEP or PKCS to the certificate profiles in Microsoft Intune in the Azure portal
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/01/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 5eccfa11-52ab-49eb-afef-a185b4dccde1

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Configure a certificate profile for your devices in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

When you give users access to corporate resources through VPN, Wi-Fi, or email profiles, you can authenticate these connections by using certificates. When you use certificates, you don't need to enter user names and passwords to authenticate connections

You can use Intune to assign these certificates to devices you manage. Intune supports assigning and managing the following certificate types:

- Simple Certificate Enrollment Protocol (SCEP)
- PKCS#12 (or PFX)

Each of these certificate types has its own prerequisites and infrastructure requirements.

## Overview

1. Ensure you have the correct certificate infrastructure in place. You can use [SCEP certificates](certificates-scep-configure.md), and [PKCS certificates](certficates-pfx-configure.md).

2. Install a root certificate or an intermediate Certification Authority (CA) certificate on each device so that the device recognizes the legitimacy of your CA. To do this, create and assign a **trusted certificate profile**. When you assign this profile, the devices that you manage with Intune request and receive the root certificate. You must create a separate profile for each platform. Trusted certificate profiles are available for the following platforms:

	- iOS 8.0 and later
	- macOS 10.9 and later
	- Android 4.0 and later
	- Android for Work
	- Windows 8.1 and later
	- Windows Phone 8.1 and later
	- Windows 10 and later

3. Create certificate profiles so that devices request a certificate to be used for authentication of VPN, Wi-Fi, and email access. You can create and assign a **PKCS** or **SCEP** certificate profile for devices running the following platforms:

   - iOS 8.0 and later
   - Android 4.0 and later
   - Android for Work
   - Windows 10 (desktop and mobile) and later

   You can only use a **SCEP** certificate profile for devices running the following platforms:

   - macOS 10.9 and later
   - Windows Phone 8.1 and later

Be sure to create a separate profile for each device platform. When you create the profile, associate it with the trusted root certificate profile that you've already created.

### Further considerations

- If you don't have an Enterprise Certification Authority, you must create one
- If you use SCEP profiles, configure a Network Device Enrollment Service (NDES) server
- Whether you plan to use SCEP or PKCS profiles, download and configure the Microsoft Intune Certificate Connector


## Step 1: Configure your certificate infrastructure

See one of the following topics for help configuring the infrastructure for each type of certificate profile:

- [Configure and manage SCEP certificates with Intune](certificates-scep-configure.md)
- [Configure and manage PKCS certificates with Intune](certficates-pfx-configure.md)


## Step 2: Export your trusted root CA certificate

Export the Trusted Root Certification Authorities (CA) certificate as a public certificate (.cer) from the issuing CA, or from any device that trusts your issuing CA. Do not export the private key (.pfx).

You import this certificate when you set up a trusted certificate profile.

## Step 3: Create trusted certificate profiles
Create a trusted certificate profile before you can create a SCEP or PKCS certificate profile. A trusted certificate profile and a SCEP or PKCS profile are needed for each device platform. The steps to create trusted certificates is similar for each device platform.

1. Sign into the [Azure portal](https://portal.azure.com).
2. Choose **All services** > **Intune**. Intune is located in the **Monitoring + Management** section.
3. On the **Intune** pane, choose **Device configuration**.
2. On the **Device configuration** pane, choose **Manage** > **Profiles**.
3. On the profiles pane, choose **Create profile**.
4. On the **Create profile** pane, enter a **Name** and **Description** for the trusted certificate profile.
5. From the **Platform** drop-down list, select the device platform for this trusted certificate. Currently, you can choose one of the following platforms for certificate settings:

	- **Android**
	- **Android for Work**
	- **iOS**
	- **macOS**
	- **Windows Phone 8.1**
	- **Windows 8.1 and later**
	- **Windows 10 and later**

6. From the **Profile type** drop-down list, choose **Trusted certificate**.
7. Browse to the certificate you saved in task 1, then click **OK**.
8. For Windows 8.1 and Windows 10 devices only, select the **Destination Store** for the trusted certificate from:
	- **Computer certificate store - Root**
	- **Computer certificate store - Intermediate**
	- **User certificate store - Intermediate**
8. When you're done, choose **OK**, go back to the **Create profile** pane, and select **Create**.

The profile is created and appears on the list. To assign this profile to groups, see [assign device profiles](device-profile-assign.md).

Android devices may display a message that a third party has installed a trusted certificate.

## Step 4: Create SCEP or PKCS certificate profiles

See one of the following topics for help configuring and assigning each type of certificate profile:

- [Configure and manage SCEP certificates with Intune](certificates-scep-configure.md)
- [Configure and manage PKCS certificates with Intune](certficates-pfx-configure.md)

After you create a trusted certificate profile, create SCEP or PKCS certificate profiles for each platform you want to use. When you create a SCEP certificate profile, enter a trusted certificate profile for that same platform. This step links the two certificate profiles, but you still must assign each profile separately.

## Next steps
See [How to assign device profiles](device-profile-assign.md) for general information about how to assign device profiles.
