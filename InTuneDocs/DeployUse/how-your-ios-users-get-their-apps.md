---
# required metadata

title: How your iOS users get their apps | Microsoft Intune
description: Methods for making iOS apps available to end users
keywords:
author: Staciebarker
manager: angrobe
ms.date: 08/24/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 7e3135c1-df26-48c9-aa4c-cdab6168897a

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# How your iOS users get their apps

Use this information to understand how and where your end users get the apps that you distribute through Microsoft Intune.

**Required apps** - Apps that are required by the administrator and that are installed on the device with minimal user involvement, depending on the platform.

**Available apps** - Apps that are provided in the Company Portal app list and that a user may optionally choose to install.

**Managed apps** - Apps that can be managed through policies and that have been "wrapped" by Intune or have been built with the Intune Mobile Application Management (MAM) Software Development Kit (SDK). These apps can be managed by Intune, and application policies can be applied to them.

**Unmanaged apps** - Apps that can be managed through policies and that have not been wrapped by Intune or that do not incorporate the Intune MAM SDK. Application policies cannot be applied to these apps.

Apple restrictions prohibit line-of-business and managed app store apps from being listed in the Company Portal app, so that means that users have to visit different views to find all of their apps. Apps for each tile shown on the Company Portal app Apps page are available as follows:

- The **Company Apps** tile points to a list of all apps in the **ALL** tab of the [Company Portal website](http://portal.manage.microsoft.com).

- The **Other Apps** tile currently points to a view, inside the Company Portal app, that lists all apps that Apple allows the Company Portal app to show. This includes all apps except line-of-business and managed app store apps.

- The **Categories** tile currently points to a view, inside the Company Portal app, that lists categories of apps.

	![ios-how-to-sync-device-with-intune](./media/ios-sync-comp-portal-apps.png)


###See also
[How your Android users get their apps](how-your-android-users-get-their-apps.md)</br>
[How your Windows users get their apps](how-your-windows-users-get-their-apps.md)
