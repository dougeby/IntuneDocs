---
# required metadata
title: Current User - Intune Data Warehouse
titlesuffix: Microsoft Intune 
description: Reference topic for the User category of entity collections in the Intune Data Warehouse API.
keywords: Intune Data Warehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/02/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: C10E6752-E925-40AD-ABBF-6B621FB7AFC4

# optional metadata
#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: aanavath
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic
---

# Reference for Current User entity

The **Current User** category contains user properties in the data model. The **Current User** entity collection is limited to currently active users. The entity contains all the Azure Active Directory users that are currently assigned a license. The license could be an Intune license, a Hybrid license, or a Microsoft Office 365 license. If a user has been removed, they will not be represented in the Current User collection. For a collection that contains a history of changes in user state, see [Reference for user entity](reports-ref-user.md).


## Current User

The **Current User** entity lists all the Azure Active Directory (Azure AD) users with assigned licenses in your enterprise.

| Property  | Description | Example |
|---------|------------|--------|
| UserKey |Unique identifier of the user in the data warehouse - surrogate key. |123 |
| UserId |Unique identifier of the user  - similar to UserKey, but is a natural key. |b66bc706-ffff-7437-0340-032819502773 |
| UserEmail |Email address of the user. |John@constoso.com |
| UPN | User principal name of the user. | John@constoso.com |
| DisplayName |Display name of the user. |John |
| IntuneLicensed |Specifies if this user is Intune licensed or not. |True/False |
| StartDateInclusiveUTC |Date and time in UTC when this user was created in the data warehouse. |11/23/2016 12:00:00 AM |
| RowLastModifiedDateTimeUTC |Date and time in UTC when this user was last modified in the data warehouse. |11/23/2016 12:00:00 AM |

## Next steps
 - You can use the **Users** entity collection to expand the user data to users who are not currently active. For more information, see [Reference for user entity](reports-ref-user.md).
 - Learn more about how the data warehouse tracks a user's lifetime in Intune, see [User lifetime representation in the Intune Data Warehouse](reports-ref-user-timeline.md).
