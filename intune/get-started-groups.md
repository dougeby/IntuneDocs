---
# required metadata

title: Get started with groups

titleSuffix: "Azure portal"
description: Organize users into groups to make it easier to manage the policies and apps that they can access.
keywords:
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
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

Groups are used to manage your users, and control your employees' access to your company resources. These resources can be part of your directory or can be external resources, like SaaS apps or SharePoint sites.

Microsoft Intune uses Azure Active Directory (Azure AD) to manage access to company resources. This access is controlled using roles in the directory. Intune then manages this access for mobile devices, which allows members of that group to access resources.

## How do I create a group?

1. Sign in to the [Azure portal](https://portal.azure.com).
2. Using **Search resources**, search for **Intune**.
3. Once you've opened the **Microsoft Intune** blade, select **Groups**.
4. On the **Users and groups – All groups** blade, select the **New group** command.
5. On the **Group** blade, add a **Name** and **Description** for the group.
6. Set the **Membership type** as **Assigned**. Do not **Enable Office features** for the test group.
7. Click **Create**.

If you've successfully created a group, it should appear in the list of **All groups**. If it doesn't appear there, try to create another group.

## Next steps

[Get started with policies](get-started-policies.md) - Create policies to prevent users from doing unauthorized things with their devices.

## Learn more

* [Set enrollment restrictions using groups in Intune](groups-add.md)
* [Manage access to company resources using groups in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
