---
# required metadata
title: Data Warehouse data model | Microsoft Docs 
description: The Intune Data Warehouse samples data daily to provide a historical view of your continually changing mobile environment.
keywords: Intune Data Warehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 11/10/2017
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

The Intune Data Warehouse samples data daily to provide a historical view of your continually changing environment of mobile devices. The view is composed of related things in time.

## Things: entity sets

The warehouse exposes data in the following high-level areas:

  -  App protection enabled apps and usage
  -  Enrolled devices, properties, and inventory
  -  Apps and software inventory
  -  Device configuration and compliance policies

These areas contain the entities, or things, that are meaningful to your Intune environment. You find details about the entity sets in the following topics:

  -  [Application](reports-ref-application.md)
  -  [Date](reports-ref-date.md)
  -  [Devices](reports-ref-devices.md)
  -  [Intune Management Extension](reports-ref-intunemanagementextension.md)
  -  [Policy](reports-ref-policy.md)
  -  [Mobile App Management (MAM)](reports-ref-mobile-app-management.md)
  -  [User](reports-ref-user.md)
  -  [Current User](reports-ref-current-user.md)
  -  [User Device Associations](reports-ref-user-device.md)

## Relationships: star-schema model

The warehouse organizes the entities in relationships that are meaningful to the type of questions you want to ask. For example, you can review the number of installations of an in-house developed Android application. The structure of the data warehouse enables you to gain insight into your mobile environment. In turn, analytics tools, such as Microsoft Power BI, can use the Data Warehouse data model to create visualizations and dynamic dashboards.

The entities and relationships use a star-schema model. A star-schema correlates facts over the dimension of time. A *fact* in the context of the model is a quantitative measurement such as the number of devices, number of apps, or time of enrollment. A *dimension* in the context of the model is a set of categories and their hierarchical relationship. For example, days are grouped into months and months are grouped into years. A star-schema model is optimized for flexibility and data analysis so that you can create the reports needed to understand your evolving mobile environment.

## Time: daily snapshots

The warehouse is downstream from your Intune data. Intune takes a daily snapshot at Midnight UTC and stores the snapshot in the warehouse. The warehouse keeps a month of snapshots representing your Intune data.

## Entity lifetime representation in the warehouse

You can use the month of data snapshots to answer questions about time-based trends. For example, you can look at the number of users being added over a month. You might also ask about the number of users who have been removed from the system.

To provide this insight, the data warehouse stores historical information. This means it tracks the lifetimes of entities. The warehouse records when an entity was created when the state of the entity changes, and when an entity is deleted. With the history captured with daily snapshots of quantitative measurements, you can compare one day to the previous day and so on.

Working with entity lifetimes can be confusing since your entities are changing state. That means if you look at a snapshot on day 30, a user record may not exist in an active state in the data. On day 29-28 the entity record may exist as active. And then before day 28, the user did not exist at all.

This may be clearer if we walk through the lifetime of an entity.

Assume a user, **John Smith**, gets assigned a license on 06/01/2017, then the **User** table would have the following entry: 
 
| DisplayName | IsDeleted | StartDateInclusiveUTC | EndDateExclusiveUTC | IsCurrent 
| -- | -- | -- | -- | -- |
| John Smith | FALSE | 06/01/2017 | 12/31/9999 | TRUE
 
John Smith gives up his license on 07/25/2017. The **User** table has the following entries. Changes in existing records are `marked`. 

| DisplayName | IsDeleted | StartDateInclusiveUTC | EndDateExclusiveUTC | IsCurrent 
| -- | -- | -- | -- | -- |
| John Smith | FALSE | 06/01/2017 | `07/26/2017` | `FALSE` 
| John Smith | TRUE | 07/26/2017 | 12/31/9999 | TRUE 

The first row indicates John Smith existed in Intune from 06/01/2017 to 07/25/2017. The second record indicates that the user was deleted on 07/25/2017 and is no longer present in Intune.

Now let assume John Smith gets a new license assigned on 08/31/2017, then the User table would have the following entries:
 
| DisplayName | IsDeleted | StartDateInclusiveUTC | EndDateExclusiveUTC | IsCurrent 
| -- | -- | -- | -- | -- |
| John Smith | FALSE | 06/01/2017 | 07/26/2017 | FALSE 
| John Smith | TRUE | 07/26/2017 | `08/31/2017` | `FALSE` 
| John Smith | FALSE | 08/31/2017 | 12/31/9999 | TRUE 
 
A person wanting to see the current state of all users would want to apply a filter where `IsCurrent = TRUE`. 
 
A person wanting to see only existing users would want to apply a filter where `IsCurrent = TRUE AND IsDeleted = FALSE`.

## Dimension tables in the entity lifetime

In order to store the history of state changes in entities, Intune doesn't delete records. Instead it marks the record as deleted. This is called a soft-delete. The dimension tables use various metadata columns to track the lifetime of records. 

The most commonly used metadata columns are: 

| Metadata Property Name  | Interpretation of Values |
|--|--|
| IsDeleted | Indicates whether the entity was deleted in Intune. |
| StartDateInclusiveUTC  | The UTC date the entity was loaded into the Intune Data Warehouse. The entity may have been created before it was imported into the Intune Data Warehouse. |
| DeletedDateUTC  | The UTC date that the entity was deleted in Intune. |  

Any metadata column starting with the prefix **Row**, such as **RowLastModifiedDateTimeUTC**, indicates when a record was created or modified in the Intune Data Warehouse. The warehouse is downstream from the data in Intune. This value has no relationship to the lifetime of the entity in Intune.  
 
Any person wanting to see only those dimension entities that currently exist would want to apply a filter where **IsDeleted = FALSE**.

## Next Steps

 - Learn more about working with data warehouses in the [Create First Data WareHouse](https://www.codeproject.com/Articles/652108/Create-First-Data-WareHouse).
 - Learn about working with Power BI and a data warehouse in [Create a new Power BI report by importing a dataset](https://powerbi.microsoft.com/documentation/powerbi-service-create-a-new-report/). 
