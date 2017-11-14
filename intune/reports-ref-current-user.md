---
# required metadata
title: User - Intune Data Warehouse | Microsoft Docs 
description: Reference topic for the User category of entity collections in the Intune Data Warehouse API.
keywords: Intune Data Warehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 11/14/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: C10E6752-E925-40AD-ABBF-6B621FB7AFC4

# optional metadata
#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic
---

# Reference for current user entity

The **Current User** category contains user and agent properties in the data model. The **Current User** entity collection is limited to currently active users. The entity contains all the Azure Active Directory Users that are currently assigned a license. The license could be an Intune license, a Hybrid license or a Microsoft Office 3065 license. If a user has been removed, they will not be represented for the data collection period. For a collection that contains a history of changes in user state, see [Reference for user entity](reports-ref-user.md).


**User**

The **User** entity lists all the Azure Active Directory (Azure AD) users with assigned licenses in your enterprise.

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