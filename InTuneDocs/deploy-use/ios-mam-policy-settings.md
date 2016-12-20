---
# required metadata

title: iOS MAM policy settings | Microsoft Docs
description: This topic describes the mobile app management policy settings for iOS devices.
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 09/30/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 673ff872-943c-4076-931c-0be90363aea9

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: andcerat
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

#  iOS mobile app management policy settings
The policy settings described in this topic can be [configured](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) for a mobile app management (MAM) policy on the **Settings** blade in the Azure portal.

There are two categories of policy settings: data relocation settings and access settings. In this topic, the term *policy-managed apps* refers to apps that are configured with MAM policies.

##  Data relocation settings

| Setting | How to use | Default value |
|------|------|------|
| **Prevent iTunes and iCloud backups** | Choose **Yes** to disable, or choose **No** to allow backup of company data from policy-managed apps. | Yes |
| **Allow app to transfer data to other apps** | Specify what apps can receive data from policy-managed apps: <ul><li> **Policy managed apps**: Allow transfer only to other policy-managed apps.</li> <li>**All apps**: Allow transfer to any app. </li> <li>**None**: Do not allow data transfer to any app, including other policy-managed apps.</li></ul> Additionally, if you set this option to **Policy managed apps** or **None**, the iOS 9 feature that allows Spotlight Search to search data within apps will be blocked. <br><br> | All apps |
| **Allow app to receive data from other apps** | Specify what apps can transfer data to policy-managed apps: <ul><li>**Policy managed apps**: Allow transfer only from other policy-managed apps.</li><li>**All apps**: Allow data transfer from any app.</li><li>**None**: Do not allow data transfer from any app, including other policy-managed apps. | All apps |
| **Prevent "Save As"** | Choose **Yes** to disable the use of the Save As option in any app that uses this policy. Choose **No** if you want to allow the use of Save As. | No |
| **Restrict cut, copy and paste with other apps** | Specify when cut, copy, and paste actions can be used with the app. Choose from: <ul><li>**Blocked**:  Do not allow cut, copy, and paste actions between this app and any other app.</li><li>**Policy managed apps**: Allow cut, copy, and paste actions between this app and other policy-managed apps.</li><li>**Policy managed with paste in**: Allow cut or copy between this app and other policy-managed apps. Allow data from any app to be pasted into this app.</li><li>**Any app**: No restrictions for cut, copy, and paste to and from this app. | Any app |
|**Restrict web content to display in the Managed Browser** | Choose **Yes** to enforce web links in the app to be opened in the Managed Browser app. <br><br> For devices not enrolled in Intune, the web links in policy-managed apps can open only in the Managed Browser app. <br><br> If you are using Intune to manage your devices, see [Manage Internet access using managed browser policies with Microsoft Intune](manage-internet-access-using-managed-browser-policies.md). | No |
| **Encrypt app data** | For policy-managed apps, data is encrypted at rest using the device-level encryption scheme provided by iOS. When a PIN is required, the data is encrypted according to the settings in the app protection policy. <br><br> Go to the official Apple documentation [here](https://support.apple.com/HT202739) to see which iOS encryption modules are FIPS 140-2 certified or pending FIPS 140-2 certification. <br><br> Specify when data is encrypted. Choose from: <ul><li>**When device is locked**: All app data that is associated with this policy is encrypted while the device is locked.</li><li>**When device is locked and there are open files**: All app data associated with this policy is encrypted while the device is locked, except for data in the files that are currently open in the app.</li><li>**After device restart**:All app data associated with this policy is encrypted when the device is restarted, until the device is unlocked for the first time.</li><li>**Use device settings**: App data is encrypted based on the default settings on the device. <br><br> When you enable this setting, the user is required to set up and use a PIN to access their device.  If there is no PIN, the apps will not open and the user will be prompted to set a PIN with the message “Your organization has required you to first enable a device PIN to access this app.” </li> | When device is locked | 




  > [!NOTE]
  > None of the data relocation settings controls the Apple managed open-in feature on iOS devices. To use manage Apple open-in, see [Manage data transfer between iOS apps with Microsoft Intune](manage-data-transfer-between-ios-apps-with-microsoft-intune.md).






- **Disable contact sync**: Choose **Yes** to prevent contact information from syncing to the native address book app on the device. If you choose **No**, the app will save the contact information to the native address book app on the device.

  When you do a selective wipe to remove company data, contacts synced directly from the app to the native address book are removed. Any contacts synced from the native address book to another external source cannot be wiped. Currently this applies only to the Microsoft Outlook app.

  Default value = **No**

- **Disable printing**: Choose **Yes** to prevent printing company data from apps that are associated with the MAM policy.

    Default value = **No**

##  Access settings

- **Require PIN for access**: Choose **Yes** to require a PIN to use policy-managed apps. The user is prompted to set this up the first time they run the app in a work context.

  Default value = **Yes**.
    -  **Allow simple PIN**: Specify whether to let users use simple PIN sequences like 1234 or 1111. Default value = **Yes**.
    - **PIN Length**: Specify the minimum number of digits in a PIN. Default value = **4**.
    - **Number of attempts before PIN reset**: Specify the number of PIN entry attempts that can be made before the user must reset the PIN. There is no default value for this setting.

- **Require fingerprint instead of PIN (iOS 8.0+)**: Choose **Yes** to require a fingerprint identity instead of a PIN for app access.
On iOS devices, you can let the user identify themselves by using a fingerprint on iOS devices instead of a PIN. When the user tries to open this app by using their work account, they are prompted to provide their fingerprint identity instead of entering a PIN.

  Default value = **Yes**.
- **Require corporate credentials for access**: Choose **Yes** to require corporate credentials instead of a PIN for app access. If you set this to **Yes**, this overrides the requirements for PIN or Touch ID. The user will be prompted to provide their corporate credentials.

  Default value = **No**.
- **Block managed apps from running on jailbroken or rooted devices**: Choose **Yes** to block apps from running on jailbroken or rooted devices. The user will continue to be able to use the apps for personal tasks, but will have to use a different device for work.

  Default value = **Yes**.
- **Recheck the access requirements after (minutes)**
  -   **Timeout**: Specify the time (in minutes) before the access requirements for the app are rechecked.
  -   **Offline grace period**: If the device is offline, specify the time (in minutes) before the access requirements for the app are rechecked.

  Default values = **30**-minute timeout and **720**-minute offline grace period.
- **Offline interval before app data is wiped (days)**: You can choose to wipe the company data if a device has been offline for a certain period. Specify the number of days a device can be offline before the company data is removed from the device.

  >[!TIP]
  >Entering a value of **0** turns off this setting.

  Default value = **90** days.
