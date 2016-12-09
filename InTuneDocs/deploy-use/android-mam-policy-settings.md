---
# required metadata

title: Android MAM policy settings | Microsoft Intune
description: This topic describes the mobile app management policy settings for Android devices.
keywords:
author: NathBarnms.author: nathbarn
manager: angrobe
ms.date: 09/30/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 5dbb702a-1df5-4637-95c9-77a5f0b1a0e3

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: andcerat
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Android mobile app management policy settings in Microsoft Intune
The policy settings that are described in this topic can be [configured](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) for a mobile app management (MAM) policy on the **Settings** blade in the Azure portal.
There are two categories of policy settings: data relocation settings and access settings. In this topic, the term *policy-managed apps* refers to apps that are configured with MAM policies.

##  Data relocation settings

- **Prevent Android backups**: Choose **Yes** to disable or  **No** to enable the backup of company data from policy-managed apps.

  Default value = **Yes**
- **Allow app to transfer data to other apps**: Choose one of the options to indicate which type of apps can receive company data from policy-managed apps:
  -   **Policy managed apps**: Enables transfer to apps that have the MAM policy only.
  -   **All apps**: Enables transfer to any app.
  -   **None**: Does not allow data transfer to any app.

 Default value = **All apps**.
- **Allow app to receive data from other apps**: Specify which apps can transfer data to the policy-managed apps:
  -   **Policy managed apps**: Enables data transfers from other policy-managed apps only.
  -   **All apps**: Enables data transfer from any app.
  -   **None**: Does not allow data transfer from any app.

  Default value = **All apps**

-   **Prevent Save As**: Choose **Yes** to disable the use of the Save As option in any app that uses this policy. Choose **No** if you want to enables the use of Save As.

  Default value = **No**
- **Restrict cut, copy, and paste with other apps**: Specify when cut, copy, and paste actions should be restricted. Choose from:
  -   **Blocked**: Does not allow cut, copy, and paste actions between policy-managed apps.
  -   **Policy Managed apps**: Enables cut, copy, and paste actions only between policy-managed apps.
  -   **Policy Managed apps with paste in**: Enables cut or copy between policy-managed apps. Enables cut or copied data from any app to be pasted into this app.
  -   **Any app**: There are no restrictions for cut, copy, and paste actions between any apps.

  Default value = **Any app**
-   **Restrict web content to display in the Managed Browser**: Choose **yes** to specify that all links in the app will be opened in the Managed Browser app.

  For devices that are not enrolled in Intune, links in policy-managed apps can only open in the Managed Browser app if you use the MAM policy.

  If you are using Intune to manage your devices, see [Manage Internet access using managed browser policies with Microsoft Intune](manage-internet-access-using-managed-browser-policies.md).

  Default value = **No**
- **Encrypt app data**: Choose **Yes** to enable encryption. When this setting is enabled, Microsoft provides encryption for apps that are associated with a MAM policy. Data is encrypted synchronously during file I/O tasks. Content on the device storage is always encrypted.
  >[!NOTE]
  >The encryption method is not FIPS 140-2 certified.

  Default value = **Yes**

- **Disable contact sync**: Choose **Yes** to prevent contact information from syncing with the native address book app on the device. If you choose **No**, the app saves the contact information to the native address book app on the device.

  When you do a selective wipe to remove company data, contacts that are synced directly between the app and the native address book are removed. Any contacts that are synced between the native address book to another external source cannot be wiped. Currently this applies only to the Microsoft Outlook app.

  Default value = **No**
- **Disable printing**: Choose **Yes** to prevent the printing of company data from apps that are associated with the MAM policy.

  Default value = **No**

##  Access settings

- **Require PIN for access**: Choose **Yes** to require a PIN to use policy-managed apps. The user is prompted to set this up the first time they run the app in a work context.

 Default value = **Yes**

 -  **Allow simple PIN**: Specify whether to let users use simple PIN sequences like 1234 or 1111. Default value = **Yes**.
 - **PIN Length**: Specify the minimum number of digits in a PIN. Default value = **4**.
 - **Number of attempts before PIN reset**: Specify the number of PIN entry attempts that can be made before the user must reset the PIN. There is no default value for this setting.
 - **Require fingerprint instead of PIN (Android 6.0+):** Choose **Yes** to require a fingerprint identity instead of a numbered PIN for app access.
 On Android devices, you can enable the user to identify themselves by using fingerprint instead of a numbered PIN. When they try to access this app by using their work account, they are prompted to provide their fingerprint identity instead of entering a PIN.
 - **Require corporate credentials for access**: Choose **Yes** to require corporate credentials instead of a PIN or fingerprint for app access. If you set this to **Yes**, this setting overrides the requirements for a PIN or Touch ID. The user will be prompted to provide their corporate credentials. Default value = **No**.


- **Block managed apps from running on jailbroken or rooted devices**: Choose **Yes** to block apps from running on jailbroken or rooted devices. The user can continue to use the apps for personal tasks, but must use a different device for work.

  Default value = **Yes**
- **Recheck the access requirements after (minutes)**
  -   **Timeout**: Specify the time (in minutes) before the access requirements for the app are rechecked.
  -   **Offline grace period**: If the device is offline, specify the time (in minutes) before the access requirements for the app are rechecked.

  Default values = **30**-minute timeout and **720**-minute offline grace period

-   **Offline interval before app data is wiped (days)**: Choose to wipe the company data if a device has been offline for a certain period.  Specify the number of days a device can be offline before the company data is removed from the device.

    >[!TIP]
    >Entering a value of **0** turns off this setting.

  Default value = **90** days
- **Block screen capture and Android Assistant (Android 6 Marshmallow or later)**: Choose **Yes** to block screen capture and the **Android Assistant** capabilities of the device when using this app.

  Default values = **No**
