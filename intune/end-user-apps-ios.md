---
# required metadata

title: How your iOS users get their apps 
description: Methods for making iOS apps available to end users
keywords:
author: barlanmsft
ms.author: barlan
manager: dougeby
ms.date: 10/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 7e3135c1-df26-48c9-aa4c-cdab6168897a

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: aanavath
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---


# How your iOS users get their apps

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Use this information to understand how and where your end users get the apps that you distribute through Microsoft Intune.

**Required apps**--Apps that are required by the admin and that are installed on the device with minimal user involvement, depending on the platform.

**Available apps**--Apps that are provided in the Company Portal app list and that a user may optionally choose to install.

**Managed apps**--Apps that can be managed through policies and that have been "wrapped" by Intune or have been built with the Intune App Software Development Kit (SDK). These apps can be managed by Intune, and app protection policies can be applied to them.

**Unmanaged apps**--Apps that can be managed through policies and that have not been wrapped by Intune or that do not incorporate the Intune App SDK. Application policies cannot be applied to these apps.

Apple restrictions prohibit line-of-business and managed App Store apps from being listed in the Company Portal app. To get around this issue, the tiles in the Company Portal app for iOS point users to different views in a single location (the Company Portal website) for all of their apps.

Enrolled users get their apps by tapping on the following tiles on the Apps screen of the Company Portal app:

- **All Apps** points to a list of all apps in the ALL tab of the [Company Portal website](https://portal.manage.microsoft.com).

- **Featured Apps** take users to the FEATURED tab of the Company Portal website.

- **Categories** points to the CATEGORIES tab of the Company Portal website.


![iOS Company Portal apps screen](./media/ios-cp-app-main-apps-screen.png)

For information on how to add apps and put them in these tiles, see [Add apps for enrolled devices to Intune](/intune-classic/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune.md).

### See also
[How your Android users get their apps](end-user-apps-android.md)

[How your Windows users get their apps](end-user-apps-windows.md)
