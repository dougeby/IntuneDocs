---
# required metadata

title: Filter policies with scope tags in Microsoft Intune - Azure | Microsoft Docs
description: Use scope tags to filter configuration profiles to specific roles.
keywords:
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/29/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer:
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Use scope tags to filter policies

Scope tags let you filter policies with custom tags that you create.

For example, create a scope tag called “Engineering Department” and assign it to configuration profiles related to the engineering department. Assign that same tag to an “Engineering Administrators” role. They'll only see the policies with the “Engineering Department” tag.

## To create a scope tag

Choose **Roles** > **Scope (tags)** > **Create**.

## To add a scope tag to a configuration profile

Choose **Device configuration** > **Profiles** > choose a profile > **Properties** > **Scope (Tags)**.

## To assign a scope tag to a role

Choose **Roles** > **All roles** > **Policy and Profile Manager** > **Assignments** > **Scope (Tags)**.

## Next steps

Manage your [roles](role-based-access-control.md) and [profiles](device-profile-assign.md).

