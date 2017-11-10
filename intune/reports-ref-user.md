---
# required metadata
title: User - Intune Data Warehouse | Microsoft Docs 
description: Reference topic for the User category of entity collections in the Intune Data Warehouse API.
keywords: Intune Data Warehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 11/9/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: C29A6EEA-72B7-427E-9601-E05B408F3BB0

# optional metadata
#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic
---

# Reference for user entity

The **User** category contains the **User** entity that defines user and agent properties in the data model.

**User**

The **User** entity lists all the Azure Active Directory (Azure AD) users with assigned licenses in your enterprise.

The **Users** entity collection contains data from the last month. These records include user states during the data collection period, even if the user has been removed. For example, a user may be added to Intune and then removed during the course of the last month. While this user  is not present at the time of the report, the user and state are present in the data from the prior month. You could create a report that would show the duration of the user's historic presence in your data.

You can use the **Current Users** entity collection to limit the user data to users who are currently active. For more information, see [Reference for current user entity](reports-ref-current-user.md).

| Property  | Description | Example |
|---------|------------|--------|
| UserKey |Unique identifier of the user in the data warehouse - surrogate key. |123 |
| UserId |Unique identifier of the user  - similar to UserKey, but is a natural key. |b66bc706-ffff-7437-0340-032819502773 |
| UserEmail |Email address of the user. |John@constoso.com |
| DisplayName |Display name of the user. |John |
| IntuneLicensed |Specifies if this user is Intune licensed or not. |True/False |
| IsDeleted |Indicates whether this user record has been updated.  True- this user has a new record with updated fields in this table. False- the latest record for this user. |True/False |
| StartDateInclusiveUTC |Date and time in UTC when this user was created in the data warehouse. |11/23/2016 12:00:00 AM |
| EndDateExclusiveUTC |Date and time in UTC when IsDeleted changed to True. |11/23/2016 12:00:00 AM |
| IsCurrent |Indicates whether this user record is current or not in the data warehouse. |True/False |
| RowLastModifiedDateTimeUTC |Date and time in UTC when this user was last modified in the data warehouse. |11/23/2016 12:00:00 AM |

