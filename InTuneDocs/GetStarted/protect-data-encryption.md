---
# required metadata

title: Protecting company data with data encryption | Microsoft Intune
description: This guide can help you protect your company from data loss by forcing a passcode and data encryption using a policy on the mobile apps.
keywords: encyrption, PIN, data
author: arob98
manager: angrobe
ms.date: 10/14/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: b1e84ef8-a260-4e3d-aaf1-8b3facfecafa

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: pchacon
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Quick Start Guide: Protect company data with data encryption
Microsoft Intune can help you prevent data loss from Office mobile apps in a variety of ways, including:
- On iOS and Android devices, by encrypting corporate data with the highest encryption level provided by iOS and Android.
- On iOS and Android devices that, because of privacy or legal requriements, cannot be enrolled in a mobile device management solution.

In addition, Microsoft Intune can help you prevent data loss from Office mobile apps and secure O365 data without having to enroll iOS or Android mobile devices to mobile device management , even if you use a non-Microsoft mobile device management solution to managed mobile devices. 

## Is this quick start guide right for me?
This quick start guide is a good resource if you meet the following prerequisites:
- You use or have licenses that you want to use for O365, if managing Office mobile apps.
- You are planning to use Office mobile apps on iOS or Android. (Windows is not yet a supported platform.)
- You use a mobile device management solution (Microsoft or non-Microsoft). If you cannot use a mobile device management solution because of statutory rules, this guide is something that you can use.
- Mobile application management without enrollment is not yet compatible with Exchange or SharePoint on-prem. You can only protect data hosted in online versions.

This guide can help you protect your company from data loss by forcing a passcode and data encryption using a policy on the mobile apps accessing your company's sensitive data without requiring enrollment in a device management solution. Microsoft Intune allows you to set mobile application management (MAM) policies over Office mobile apps on iOS and Android, giving you control over enabling and disabling features like PIN to access the app and encryption. 

This approach protects Office 365 data without requiring users to enroll their devices into a mobile device management solution while also maintaining a great en-user experience with Office mobile apps. Intune enrollment is not required. 

## How do I do it?
1.	[Review how you can protect app data](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) 
2.	[Get ready to configure mobile app management policies](/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) 
3.	[Create and deploy mobile app management policies](/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) 

## Additional information:
- [Find out about the end user experience for MAM enabled apps with Microsoft Intune.](/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune)
- [Decide how to prepare apps for mobile application management with Microsoft Intune.](/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune)
- <a href="https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners" target="_blank"> View the list of Microsoft Intune application partners &rarr;</a>