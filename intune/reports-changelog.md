---
# required metadata
title: Intune Data Warehouse Change log | Microsoft Docs 
description: A list of changes in the Intune Data Warehouse API.
keywords: Intune Data Warehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/19/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: E85DBB2D-67BB-4E10-82D6-E43046B9C43C

# optional metadata
#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic
---

# Change log for the Intune Data Warehouse API

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Keep current on updates to the Intune Data Warehouse.

## 1710
_Released November, 2017_

### User entity contains latest user data in Data Warehouse data model <!-- 1544273 -->

The first version of the Intune Data Warehouse data model only contained recent, historical Intune data. Report makers could not capture the current state of a user. In this update, the [**User entity**](reports-ref-user.md) will be populated ith the latest user data.

### New entities in the in Data Warehouse data model <!-- 1479526 --><!-- -->

 - The entity, [**UserDeviceAssociation**](reports-ref-user-device.md), added. **UserDeviceAssociation** contains user device associations in your organization.
 - The entity, [**IntuneManagementExtension**](reports-ref-intunemanagementextension.md), added. **IntuneManagementExtension** contains entities for mobile devices that track information such as version and installation status.

## Next steps
 - Learn [what’s new each week in Intune](whats-new.md). You can also find out about upcoming changes, important notices about the service, and information about past releases. 
 - Read the [Microsoft Intune Blog](http://go.microsoft.com/fwlink/?LinkID=273882).