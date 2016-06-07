---
# required metadata

title: Enable access to company resources using certificate profiles |Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8cbb8499-611d-4217-a7b4-e9b864785dd0

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: kmyrup
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Secure resource access with certificate profiles in Microsoft Intune
When you enable access to corporate resources through VPN, Wi-Fi, or email profiles, you have the option of securing that access with a certificate installed on each user device. Here's how it works:

1. Make sure you have the right certificate infrastructure in place, as described in [Configure certificate infrastructure](configure-certificate-infrastructure.md).

2. Install a root certificate (or intermediate CA certificate) on each device so that the device recognizes the legitimacy of your Certification Authority. You do this with by creating and deploying a **Trusted Certificate Profile**. When you deploy this profile, the devices that you manage with Intune will request and receive the root certificate. You have to create a separate profile for each platform. The **Trusted Certificate Profile** is available for these platforms:
 -  iOS 7.1 and later
 -  Mac OS X 10.9 and later
 -  Android 4.0 and later
 -  Windows 8.1 and later
 -  Windows Phone 8.1 and later

3. Make each device request a certificate to be used for authentication of email, VPN, and Wi-Fi access, as described in [Configure intune certificate profiles](configure-intune-certificate-profiles.md). You can create and deploy a **PKCS #12 (.PFX) Certificate Profile**, or a **SCEP Certificate Profile** for devices on these platforms:
 
-  Android 4.0 and later
-  iOS 7.1 and later
-  Windows 10 (desktop and mobile) and later 

Use the **SCEP Certificate Profile** for:
-   Mac OS X 10.9 and later
-   Windows Phone 8.1 and later

You have to create a separate profile for each platform. When you create the profile you associate it with the **Trusted Root Certificate profile** that you already created.

> [!NOTE]           
> -    If you don't have an enterprise certification authority, you have to create one. 
>- If you decide, based on your device platforms, to use the Simplified Certificate Enrollment Protocol (SCEP) profile, you also need to configure a Network Device Enrollment Service (NDES) server.
>-  Whether you plan to use SCEP or or .PFX profiles, you have to download and configure the Microsoft Intune Certificate Connector.
> Configuration of all of these is described in the topic [Configure certificate infrastructure](configure-certificate-infrastructure.md).

### Next steps
- [Configure certificate infrastructure](configure-certificate-infrastructure.md)
- [Configure Intune certificate profiles](configure-intune-certificate-profiles.md)

