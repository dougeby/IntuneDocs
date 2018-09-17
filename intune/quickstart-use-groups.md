---
# required metadata

title: Quickstart - Use a group to manage users
titlesuffix: 
description: In this quickstart you will use Intune to create a group based on existing users.
keywords:
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/17/2018
ms.topic: quickstart
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 723f4b4e-3090-4811-84ff-6af652abea5a

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Quickstart: Use groups to manage users

In this quickstart, you will use Intune to create a group based on existing users. Groups are used to manage your users and control your employees' access to your company resources. These resources can be part of your company's intranet or external resources, such as SharePoint sites, SaaS apps, or web apps.

>[!NOTE]
>Intune provides pre-created **All Users** and **All Devices** groups in the console with built-in optimizations for your convenience.

## Prerequisites

- If you don’t have an Intune subscription, [sign up for a free trial account](free-trial-sign-up.md).
- [Quickstart - Create a user in Intune](quickstart-create-user.md) - Before starting this quickstart, you should follow the steps to create a user and assign a license to it using Intune.

## Sign in to Intune

Sign in to the [Intune](https://aka.ms/intuneportal) as a Global Administrator or an Intune Service Administrator. Intune is located in the Azure portal  by choosing **All services** > **Intune**. Intune is located in the **Monitoring + Management** section.

## Create a group
1. Once you've opened the **Microsoft Intune** pane, select **Groups** > **New group**.
2. On the **Group** pane, select **Group type** > **Security**.
3. Set the **Name** to "Contoso Testers" and add a **Description** for the group.
4. Set the **Membership type** as **Assigned**. 
5. Click **Members** and select **Members** for the group from the existing list.
    > [!NOTE]
    > Completing [Quickstart - Create a user in Intune](quickstart-create-user.md) is required before starting this quickstart.
6. Click **Select**.
7. Click **Create**.

If you've successfully created a group, it will appear in the list of **All groups**. If it doesn't appear, look for a message at the top right of the window for details.

## Next steps

In this quickstart, you used Intune to created a group based on existing users.

> [!div class="nextstepaction"]
> [Quickstart - Create and assign a custom role in Intune](quickstart-create-custom-role.md)
