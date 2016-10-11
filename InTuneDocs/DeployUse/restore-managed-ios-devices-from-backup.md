---
# required metadata

title: Restore Intune managed iOS devices from backup | Microsoft Intune
description: Provide guidance to end users on how to re-enroll their devices after restoring from backup.
keywords:
author: barlanmsft
manager: angrobe
ms.date: 10/11/2016
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
#ms.custom:

---

# Restore Intune managed iOS devices from backup

There will be cases where you or your users will need to restore iOS devices from backup. For example, a device's operating system may need to be reset, or a replacement device is being provided to a user. Both types of restores can impact device enrollment in ways that may require additional setup.

## Restoring backups onto the same device

If the backup is being restored onto the __same__ device, then the enrollment status for that device will also be restored. The Company Portal app will work the same way as before without any need for additional changes.

## Restoring backups onto different devices

If the backup is being restored onto a __different__ device, then the enrollment status will not automatically restored to the new device. Users will need to follow standard enrollment steps to [enroll their iOS device into Intune](/Intune/EndUser/enroll-your-device-in-intune-ios).

> [!NOTE]
> If you’re targeting your end users with conditional access policies, they will not be able to access email until after they re-enroll.

To re-enroll their new device, your users must be running Company Portal app version 2.1.22 or later. An example communication for your users could be as follows:

> [!TIP]
> To re-enroll on the new device, make sure that the Company Portal app is on version 2.1.22 or later. To check, open the Company Portal app, then tap the Menu button in the upper right, then tap **About**. If you are on an earlier version, exit the Company Portal app and open the App Store. Tap the **Updates** button in the bottom-right corner, then tap the **UPDATE** button next to the Company Portal item in the list, then [re-enroll your iOS device into Intune](/Intune/EndUser/enroll-your-device-in-intune-ios).
