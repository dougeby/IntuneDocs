---
# required metadata

title: How your Android users get their apps | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f33d1684-b1b5-44f7-9aac-c6d5186a5d7c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# How your Android users get their apps
Use this information to understand how and where your end users get the apps that you distribute through Microsoft Intune. 

**Required apps** - Apps that are required by the administrator and that are installed on the device with minimal user involvement, depending on the platform.
 
- **Samsung Knox devices**: if you deploy a required app to Samsung Knox devices, it is automatically and silently installed on their device.
- **Native (non-Samsung Knox devices)**: if you deploy a required app to non-Samsung Knox devices, it is not automatically installed on users' devices. Instead, users are prompted to install the app. After they accept the prompts, the app is downloaded, and users then receive a notification indicating that they need to install it. If users choose not to install the app, you can prevent them from accessing company or school resources.

**Available apps** - Apps that are provided in the Company Portal app list and that a user may optionally choose to install.

**Managed apps** - Apps that can be managed through policies and that have been "wrapped" by Intune or have been built with the Intune Mobile Application Management (MAM) Software Development Kit (SDK). These apps can be managed by Intune, and application policies can be applied to them.

**Unmanaged apps** - Apps that can be managed through policies and that have not been wrapped by Intune or that do not incorporate the Intune MAM SDK. Application policies cannot be applied to these apps.

###See also
[Add apps with Microsoft Intune](/intune/deploy-use/add-apps)
[How your iOS users get their apps](how-your-ios-users-get-their-apps.md)
[How your Windows users get their apps](how-your-windows-users-get-their-apps.md)