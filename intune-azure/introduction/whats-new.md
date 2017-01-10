---
# required metadata
title: "What's new in the Microsoft Intune Preview | Intune Azure preview | Microsoft Docs"
description: "Intune Azure preview: Find out what's new in the Intune Azure preview"
keywords:
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 01/09/2017
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# What's new in the Microsoft Intune preview


[!INCLUDE[azure_preview](../includes/azure_preview.md)]


As the public preview progresses, and more features are added, we'll let you know about them here.

## December 2016 (initial release)

- Deploy and manage apps from a store to iOS, Android, and Windows devices
- Deploy and manage line of business (LOB) apps to iOS, Android, and Windows devices
- Deploy and manage volume-purchased apps to iOS, and Windows devices
- Deploy and manage web apps for Android, iOS, and Windows devices
- iOS managed app configuration profiles
- Configure app protection policies, and deploy line of business apps to devices that are not enrolled with Intune
- VPN profiles, per-app VPN, Wi-Fi, email, and certificate profiles
- Compliance policies
- Conditional access for Azure AD
- Conditional access for On-Premises Exchange
- Device enrollment
- Role-based access control

## Deprecated features in the Azure portal

### Support for row-by-row review of hardware identifiers
The Azure portal does not support row-by-row review of hardware identifiers for IMEI numbers and Apple serial numbers. In the classic Intune console, you can import details from a comma-separated-values (.csv) file and overwrite the existing details for individual hardware identifiers. The Azure portal features a single, streamlined option that automatically overwrites details for all hardware identifiers or ignores new details for existing identifiers.

#### How this affects you
In the Azure portal, you will not be able to decide, row by row, which International Mobile Equipment Identity (IMEI) devices to update. The classic Intune console will continue to support this functionality.

#### How to get ready for this change
We are providing this information in advance so, if it affects you, you can make your support admins aware of this change. This change will coincide with the move to the Azure portal, anticipated for the first half of 2017.


### Support for default Corporate Device Enrollment profiles in Apple DEP
The Azure portal does not support the “default” Corporate Device Enrollment profile for Apple Device Enrollment Program (DEP) device serial numbers. This functionality, available in the classic Intune console, is being discontinued to prevent unintentionally assigned profiles. In the Azure portal, serial numbers synchronized from an Apple DEP account will initially have no Corporate Device Enrollment profile assigned.

#### How this affects you
In the Azure portal, you will not be able to set a default profile policy across all Apple devices. The classic Intune console will continue to support this functionality.

#### How to get ready for this change
We are providing this information in advance so, if it affects you, you can make your support admins aware of this change. This will coincide with the move to the Azure portal, anticipated for the first half of 2017.
