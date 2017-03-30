---
# required metadata

title: Special migration considerations | Microsoft Docs
description: The purpose of this article is give customer provide special migration considerations before they start a migration campaign.
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: dagerrit
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Phase 1: Special migration considerations

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

There are special migration considerations which may be applicable depending on your existing MDM provider environment.

## Factory reset for Apple’s Device Enrollment Program (DEP)

The Apple Device Enrollment Program (DEP) sets device configurations that cannot be removed by the end user. To retain the advanced management features of DEP, the device must be returned to the out-of-box (new) state via factory reset to enroll to Intune.

To continue using DEP to manage the devices in Intune:

1.  Onboard [DEP in Intune](https://docs.microsoft.com/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune)

2.  Go your Apple DEP account and [re-assign the DEP device serial numbers](https://help.apple.com/deployment/business/#/tesf9562af26) from your existing MDM provider to Intune.

3.  [Synchronize](https://docs.microsoft.com/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) your DEP account with Intune

4.  [Create and assign](https://docs.microsoft.com/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) appropriate DEP enrollment profiles to the serial numbers in Intune.

5.  Factory reset the devices (either remotely via your current MDM provider or manually on each device)

6.  Distribute the devices to end-users.

## Next steps 

[Phase 2: Migration campaign](https://docs.microsoft.com/intune/plan-design/migration-phase2-migration-campaign)
