---
title: Enable access to company resources using certificate profiles with Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 8cbb8499-611d-4217-a7b4-e9b864785dd0
author: Nbigman
---
# Enable access to company resources using certificate profiles with Microsoft Intune
When you enable access to corporate resources through VPN, Wi-Fi, or email profiles, you have the option of securing that access with a certificate installed on each user device. Here's how it works:

 
1.   First, you install a root certificate (or intermediate CA certificate) on each device so that the device recognizes the legitimacy of your Certification Authority. You do this with by creating and deploying a **Trusted Certificate Profile**. When you deploy this profile, the devices that you manage with Intune will request and receive the root certificate. The **Trusted Certificate Profile** is available for devices running iOS 7.1 and later, Mac OS X 10.9 and later, Android 4.0 and later, and Windows Phone 8.1 and later. You have to create a separate profile for each platform.

2.   Next, you make each device request a certificate to be used for authentication of email, VPN, and Wi-Fi access. For Android 4.0 and later, and Windows 10 (desktop and mobile) and later, create and deploy the **PKCS #12 (.PFX) Certificate Profile**. Use the **SCEP Certificate Profile** for iOS 7.1 and later, Mac OS X 10.9 and later, Android 4.0 and later, and Windows Phone 8.1 and later. You have to create a separate profile for each platform. When you create the profile you associate it with the **Trusted Root Certificate profile** that you already created.

## Next steps
- [Configure certificate infrastructure](Configure-certificate-infrastructure.md)
- [Configure Intune certificate profiles](Configure-Intune-certificate-profiles.md)
> [!NOTE]           
> -    If you don't have an enterprise certification authority, you have to create one. 
>- If you decide, based on your device platforms, to use the Simplified Certificate Enrollment Protocol (SCEP) profile, you also need to configure a Network Device Enrollment Service (NDES) server.
>-  Whether you plan to use SCEP or or .PFX profiles, you have to download and configure the Microsoft Intune Certificate Connector.
> Configuration of all of these is described in the topic [Configure certificate infrastructure](Configure-certificate-infrastructure.md).