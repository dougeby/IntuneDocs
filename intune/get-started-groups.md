---
# required metadata

title: Get started with groupstitleSuffix: "Intune on Azure"
description:
keywords:
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 06/27/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 39a93fb5-d318-4997-a409-b64549a00e7a

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---

# Get started with groups

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

[](./media/generic-users-groups.png)

Microsoft Intune uses Azure Active Directory (Azure AD) to [manage access to company resources](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups). This access is controlled using roles in the directory. Intune then manages this access for mobile devices, which allows members of that group to access resources.

## How do I create a group?

1. Sign in to the [Azure portal](https://portal.azure.com).
2. Using **Search resources**, search for **Users and groups**.
3. Once you've opened the **Users and groups** blade, select **All groups**.
4. On the **Users and groups – All groups** blade, select the **New group** command.
5. On the **Group** blade, add a **Name** and **Description** for the group.
6. Set the **Membership type** as **Assigned**. Do not **Enable Office features** for the test group.
7. Click **Create**.

If you've successfully created a group, it should appear in the list of **All groups**. If it doesn't appear there, try to create another group.
