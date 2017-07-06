---
# required metadata

title: Special migration considerations 
description: The purpose of this article is give customer provide special migration considerations before they start a migration campaign.
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
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

# Special migration considerations

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

There are special migration considerations which may be applicable depending on your existing MDM provider environment.

## Factory reset for Apple’s Device Enrollment Program (DEP)

The Apple Device Enrollment Program (DEP) sets device configurations that cannot be removed by the end user. To retain the advanced management features of DEP, the device must be returned to the out-of-box (new) state via factory reset to enroll to Intune.

To continue using DEP to manage the devices in Intune, [set up iOS device enrollment with Device Enrollment Program](/intune/device-enrollment-program-enroll-ios).


## Next steps 

[Phase 2: Migration campaign](migration-guide-campaign.md)
