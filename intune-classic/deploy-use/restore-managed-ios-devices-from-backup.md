---
# required metadata

title: Restore Intune managed iOS devices from backup 
description: Provide guidance to end users on how to re-enroll their devices after restoring from backup.
keywords: restore, managed, iOS
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/18/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: a19e5612-8805-4bd7-a86a-b734bde293ae

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: esmich
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Restore Intune managed iOS devices from backup

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

There will be cases when you or your users will need to restore an iOS device from a backup, such as when a user gets a new device. This topic explains additional steps that you might have to take to set up Intune management after restoring the device.

## Restoring backups onto the same device

If the backup is being restored onto the same device, then the enrollment state on that device will also be restored. There is no need for additional action.

## Restoring backups onto different devices

If the backup is being restored onto a different device, then the enrollment state is not automatically restored on the new device. Users need to follow standard enrollment steps in the Company Portal app on app version 2.1.22 or later to [enroll their iOS device into Intune](/intune-user-help/enroll-your-device-in-intune-ios).

> [!NOTE]
> If you’re targeting your end users with conditional access policies, they will not be able to access corporate email until after they re-enroll.

> [!TIP]
> An example communication for your users could be as follows:
To enroll on your new device, make sure that the Company Portal app is on version 2.1.22 or later. To check the version, open the Company Portal app, tap the Menu button in the upper right, and then tap About. If you are on an earlier version, exit the Company Portal app and open the App Store. Tap the Updates button in the bottom right corner, then tap the Update button next to the Company Portal item in the list. Once the update completes, launch the Company Portal app and [enroll your iOS device into Intune](/intune-user-help/enroll-your-device-in-intune-ios).

## Resolving known issues with restores

Users may experience some difficulty if they restored their device and launched the Company Portal app when they still had Company Portal version 2.1.21 or earlier. These difficulties can be addressed by taking the appropriate steps for the user’s situation.

### For users who will only use their new device
Launch the Company Portal app and unenroll by selecting the current device tile and tapping the __Remove__ button. After removing, follow the standard enrollment steps to [enroll an iOS device into Intune](/intune-user-help/enroll-your-device-in-intune-ios).

### For users who will use both their old and new devices
Clear cookies from Safari by tapping __Settings__ > __Safari__ > __Clear History and Website Data__. After clearing,  uninstall and reinstall the Company Portal app, then follow the standard enrollment steps to [enroll an iOS device into Intune](/intune-user-help/enroll-your-device-in-intune-ios).
