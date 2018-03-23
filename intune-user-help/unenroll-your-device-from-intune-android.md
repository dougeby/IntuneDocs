---
# required metadata

title: How to remove your Android device from Intune | Microsoft Docs
description: Describes how to unenroll an Android device from Intune
keywords:
author: barlanmsft
ms.author: barlan
manager: dougeby
ms.date: 03/23/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f40aab26-7613-48cc-a74e-de83df9465a4
searchScope:
 - User help

# optional metadata

ROBOTS:   
#audience:
#ms.devlang:
ms.reviewer: arnab
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-enduser

---


# How to remove your Android device from Intune

When you remove your Android device from Intune, your device can no longer access company resources.  For more about what happens when you remove your device from management, see [What happens if you unenroll your device from Intune?](what-happens-if-you-unenroll-your-device-from-intune-android.md)

## Removing the device from the Company Portal app

To remove your device from Intune and the Company Portal app, follow these steps:

1. Open the **action menu** by tapping the three vertical dots at the top right corner of the Company Portal app.

  ![An image of the Android Company Portal app, with the action menu opened in the top right corner. The new "remove company portal" option is available as the third option, underneath "my profile" and "settings", and above "terms and conditions", "help and feedback", and "about".](./media/android_remove_cp_menu_action_after_1705.png)

2. Tap **Remove Company Portal**.

3. A confirmation will pop up, asking you if you're sure that you want to remove the Company Portal. It will provide some information about what happens when you unenroll your device. After reading over this message, tap **OK** to remove the app.

  ![An image of the confirmation dialog, that is available after selecting the new "remove company portal" option from the action menu. The dialog informs the user that "by removing company portal, your device will no longer be managed by your company support and may remove access to company data, company apps, and company email." It then asks the user to confirm that they want to remove the Company Portal app by selecting "Yes".](./media/android_remove_cp_menu_confirmation_after_1705.png)

## Removing your personal information after removing the Company Portal

To remove all data that the Company Portal app for Android stores on your device:

-	Clear app data in Applications -> Click on app -> button "Clear data"
-	Delete the folder '\storage\internal storage\Android\data\com.microsoft.windowsintune.companyportal'

Still need help? Contact your company support. For contact information, check the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).
