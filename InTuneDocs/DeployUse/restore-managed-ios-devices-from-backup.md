---
# required metadata

title: Restore Intune managed iOS devices from backup | Microsoft Intune
description: Provide guidance to end users on how to re-enroll their devices after restoring from backup.
keywords:
author: barlanmsft
manager: angrobe
ms.date: 10/07/2016
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

There will be cases where you or your users will need to restore iOS devices. Whether you’ve supplied them with a new device or you’re trying to resolve software issues on one their personal device, restores can impact device re-enrollment in ways that may require additional setup.

**If the backup is being restored onto the _same_ device**, then the device will be automatically re-enrolled after the restore is complete. The Company Portal app will work the same way as before without any need for additional changes.

**If the backup is being restored onto a _different_ device**, then the new device will not automatically be re-enrolled after the restore is complete. Users will need to follow standard procedures to [enroll their iOS device into Intune](intune/enduser/enroll-your-device-in-intune-ios.md).

> [!NOTE]:
> If you’re targeting your end users with conditional access policies, they will not be able to access email until after they re-enroll.

To re-enroll their new device, your users must be running Company Portal 2.1.22 or later. An example communication for your users could be as follows:

> [!TIP]:
> To re-enroll on the new device, make sure that the Company Portal app is on version 2.1.22 or later. To check, open the Company Portal app, then tap the Menu button in the upper right, then tap **About**. If you are on an earlier version, exit the Company Portal app and open the App Store. Tap the **Updates** button in the bottom-right corner, then tap the **UPDATE** button next to the Company Portal item in the list, then [re-enroll your iOS device into Intune](intune/enduser/enroll-your-device-in-intune-ios.md). 
