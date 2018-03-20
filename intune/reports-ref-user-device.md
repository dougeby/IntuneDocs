---
# required metadata
title: User Device Association - Intune Data Warehouse
titlesuffix: Microsoft Intune 
description: A list of changes in the Intune Data Warehouse API.
keywords: Intune Data Warehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/02/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 777484A7-09CE-4409-987F-76B3F87DFE93

# optional metadata
#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: aanavath
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic
---
# User Device Association

The **UserDeviceAssociation** entity contains user device associations in your organization.

| Name               | Description                                                                                      | Example                |
|--------------------|--------------------------------------------------------------------------------------------------|------------------------|
| UserKey            | Unique identifier of the user in the data warehouse. (Surrogate key).                              | 123                    |
| DeviceKey          | Unique identifier of the device in the data warehouse.                                            | 123                    |
| CreatedDateTimeUTC | Date and time when the user device association was created. Uses UTC format.                                | 11/23/2016 12:00:00 AM |
| IsDeleted          | Indicates that the user unenrolled that device, and that the association is not current anymore. | True/False             |
| EndedDateTimeUTC   | Date and time in UTC when IsDeleted changed to **True**.                                              | 06/23/2017 12:00:00 AM |
