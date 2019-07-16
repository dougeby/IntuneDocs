---
# required metadata

title: Create certificates profile in Microsoft Intune - Azure | Microsoft Docs
description: For your devices, add or create a certificate profile by configuring SCEP or PKCS certificate environment, export the public certificate, create the profile in the Azure portal, and then assign SCEP or PKCS to the certificate profiles in Microsoft Intune in the Azure portal
keywords:
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology:
ms.assetid: 5eccfa11-52ab-49eb-afef-a185b4dccde1

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure
ms.collection: M365-identity-device-management
---

# Use certificates for authentication in Microsoft Intune  

Use certificates with Intune to authenticate your users' access to corporate resources through VPN, Wi-Fi, or email profiles. When you use certificates to authenticate these connections, your end users won't need to enter usernames and passwords, which helps to make their access seamless.  

Intune supports the following certificate types:  

- Simple Certificate Enrollment Protocol (SCEP)  
- PKCS#12 (or PFX)  

To deploy these certificates, you’ll create and assign certificate profiles to devices.  

Each individual certificate profile you create supports a single platform. For example, if you use PKCS certificates, you’ll create PKCS certificate profile for Android and a separate PKCS certificate profile for iOS. If you also use SCEP certificates for those two platforms, you’ll create a SCEP certificate profile for Android, and another for iOS.  

**General considerations**:  
- If you don't have an Enterprise Certification Authority (CA), you must create one.  
- If you use SCEP certificate profiles, you’ll configure a Network Device Enrollment Service (NDES) server.  
- Both SCEP and PKCS certificate profiles require you to download, install, and configure the Microsoft Intune Certificate Connector.  
- For a device to use SCEP and PCKS certificate profiles, that device must trust your root Certification Authority. You use a *trusted certificate profile* to deploy your Trusted Root CA certificate to devices.  

## Supported platforms and certificate profiles  
| Platform              | Trusted certificate profile | PKCS certificate profile | SCEP certificate profile | PKCS imported certificate profile  |
|--|--|--|--|---|
| Android               | ![Supported](./media/certificates-configure/green_check.png) | ![Supported](./media/certificates-configure/green_check.png) | ![Supported](./media/certificates-configure/green_check.png)|  ![Supported](./media/certificates-configure/green_check.png) |
| Android enterprise    | ![Supported](./media/certificates-configure/green_check.png) | ![Supported](./media/certificates-configure/green_check.png) | ![Supported](./media/certificates-configure/green_check.png) | ![Supported](./media/certificates-configure/green_check.png) |
| iOS                   | ![Supported](./media/certificates-configure/green_check.png) | ![Supported](./media/certificates-configure/green_check.png) | ![Supported](./media/certificates-configure/green_check.png) | ![Supported](./media/certificates-configure/green_check.png) |
| macOS                 | ![Supported](./media/certificates-configure/green_check.png) |   |![Supported](./media/certificates-configure/green_check.png)|![Supported](./media/certificates-configure/green_check.png)|
| Windows Phone 8.1     |![Supported](./media/certificates-configure/green_check.png)  |  | ![Supported](./media/certificates-configure/green_check.png)| ![Supported](./media/certificates-configure/green_check.png) |
| Windows 8.1 and later |![Supported](./media/certificates-configure/green_check.png)  |  |![Supported](./media/certificates-configure/green_check.png) |   |
| Windows 10 and later  | ![Supported](./media/certificates-configure/green_check.png) | ![Supported](./media/certificates-configure/green_check.png) | ![Supported](./media/certificates-configure/green_check.png) | ![Supported](./media/certificates-configure/green_check.png) |

## Export the trusted root CA certificate  
To use PKCS and SCEP certificates, devices must trust your root Certification Authority. To establish this trust, you export the Trusted Root Certification Authority (CA) certificate as a public certificate (.cer). You can get this certificate from the issuing CA, or from any device that trusts your issuing CA.  

To export the certificate, refer to the documentation for your Certification Authority. You’ll need to export the public certificate as a .cer file.  Don't export the private key, a .pfx file.  

You’ll use this .cer file when you [create trusted certificate profiles](#create-trusted-certificate-profiles) to deploy that certificate to your devices.  

## Create trusted certificate profiles  
Create a trusted certificate profile before you can create a SCEP or PKCS certificate profile. Deploying a trusted certificate profile ensures each device recognizes the legitimacy of your CA. SCEP certificate profiles directly reference a trusted certificate profile. PKCS certificate profiles don’t directly reference the trusted certificate profile but do directly reference the server that hosts your CA. Deploying a trusted certificate profile to devices ensures this trust is established. When a device doesn’t trust the root CA, the SCEP or PKCS certificate profile policy will fail.  

Create a separate trusted certificate profile for each device platform you want to support, just as you'll do for SCEP and PCKS certificate profiles.  


### To create a trusted certificate profile  

1. Sign in to the [Intune portal](https://aka.ms/intuneportal).  
2. Select **Device configuration** > **Manage** > **Profiles** > **Create profile**.  
3. Enter a **Name and Description** for the trusted certificate profile.  
4. From the **Platform** drop-down list, select the device platform for this trusted certificate.  
5. From the **Profile type** drop-down list, choose **Trusted certificate**.  
6. Browse to the trusted root CA certificate .cer file you exported for use with this certificate profile, and then select **OK**.  
7. For Windows 8.1 and Windows 10 devices only, select the **Destination Store** for the trusted certificate from:  
   - **Computer certificate store - Root**
   - **Computer certificate store - Intermediate**
   - **User certificate store - Intermediate**
8. When you're done, choose **OK**, go back to the **Create profile** pane, and select **Create**.
The profile appears in the list of profiles on the *Device configuration – Profiles* view pane, with a profile type of **Trusted certificate**.  Be sure to assign this profile to devices that will use SCEP or PCKS certificates. To assign the profile to groups, see [assign device profiles](device-profile-assign.md).

> [!NOTE]  
> Android devices might display a message that a third party has installed a trusted certificate.  

## Additional resources  
- [Assign device profiles](device-profile-assign.md)  
- [Use S/MIME to sign and encrypt emails](certificates-s-mime-encryption-sign.md)  
- [Use third-party certification authority](certificate-authority-add-scep-overview.md)  

## Next steps  
After you create and assign trusted certificate profiles, create SCEP or PKCS certificate profiles for each platform you want to use. To continue, see the following articles:  
- [Configure infrastructure to support SCEP certificates with Intune](certificates-scep-configure.md)  
- [Configure and manage PKCS certificates with Intune](certficates-pfx-configure.md)  


