---
# required metadata
title: User Device Association | Microsoft Docs  
description: Reference topic for the User Device Association category of entity collection in the Intune Data Warehouse API.
keywords: Intune Data Warehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 09/15/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: BCDBABCB-A7B1-42F2-BDD1-D055E33F2239

# optional metadata
#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic
---

# Reference for User Device Association entity

The **User Device Association** category contains the **User Device Association** entity used to define device associations in the organization.

**User Device Association**

The **User Device Association** entity represents the define device associations in the organization.

| Name               | Description                                                                                      | Example                |
|--------------------|--------------------------------------------------------------------------------------------------|------------------------|
| UserKey            | Unique identifier of the user in the data warehouse – surrogate key.                             | 123                    |
| DeviceKey          | Unique identifier of the device in the data warehouse.                                           | 123                    |
| CreatedDateTimeUTC | Date and time in UTC when the user device association was created.                               | 11/23/2016 12:00:00 AM |
| IsDeleted          | Indicates that the user unenrolled that device, and that the association is not current anymore. | True                   |
| EndedDateTimeUTC   | Date and time in UTC when IsDeleted changed to **True**.                                             | 06/23/2017 12:00:00 AM |