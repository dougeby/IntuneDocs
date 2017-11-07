---
# required metadata
title: Data Warehouse data model | Microsoft Docs 
description: The Intune Data Warehouse samples data daily to provide a historical view of your continually changing mobile environment.
keywords: Intune Data Warehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 4D04D3D9-4B6C-41CD-AAF8-466AF8FA6032

# optional metadata
#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic
---

# Data Warehouse data model

The Intune Data Warehouse samples data daily to provide a historical view of your continually changing mobile environment.

The data pulled from your tenant is added into a data warehouse. The warehouse is a set of entities and relationships that are meaningful to the type of questions you  want to ask. For example, you can review the number of installations of an in-house developed Android application per day over the last week to assess if there is an increasing trend of installations. The structure of the data warehouse enables you to gain insight into your mobile environment. In turn, analytics tools, such as Microsoft Power BI, can use the Data Warehouse data model to create visualizations and dynamic dashboards.

The Intune Data Warehouse structure uses a star-schema model. A star-schema organizes facts over the dimension of time. A *fact* in the context of the model is a quantitative measurement such as the number of devices, number of apps, or time of enrollment. A *dimension* in the context of the model is a set of categories and their hierarchical relationship. For example, days are grouped into months and months are grouped into years. A star-schema model is optimized for flexibility and data analysis so that you can create the reports needed to understand your evolving mobile environment.

The warehouse exposes data in the following high-level categories:
  -  App protection enabled apps and usage
  -  Enrolled devices, properties, and inventory
  -  Apps and software inventory
  -  Device configuration and compliance policies

**Data model entity sets**

Entity sets are named collections of entities in the data model. These sets contain entities that define the data collected in the model. Each entity set provide an access point into the Data Warehouse data model. You find details about the following categories of entities:

  -  [Application](reports-ref-application.md)
  -  [Date](reports-ref-date.md)
  -  [Devices](reports-ref-devices.md)
  -  [Intune Management Extension](reports-ref-intunemanagementextension.md)
  -  [Policy](reports-ref-policy.md)
  -  [Mobile App Management (MAM)](reports-ref-mobile-app-management.md)
  -  [User](reports-ref-user.md)
  -  [User Device Associations](reports-ref-user-device.md)