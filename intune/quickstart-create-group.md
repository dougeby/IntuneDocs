---
# required metadata

title: Quickstart - Create a group to manage users
titlesuffix: Microsoft Intune
description: In this quickstart you will use Microsoft Intune to create a group based on existing users.
keywords:
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/19/2018
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

# Quickstart: Create a group to manage users

In this quickstart, you will use Intune to create a group based on an existing user. Groups are used to manage your users and control your employees' access to your company resources. These resources can be part of your company's intranet or can be external resources, such as SharePoint sites, SaaS apps, or web apps.

>[!NOTE]
>Intune provides pre-created **All Users** and **All Devices** groups in the console with built-in optimizations for your convenience.

## Prerequisites

- If you don’t have an Intune subscription, [sign up for a free trial account](free-trial-sign-up.md).
- Before starting this quickstart, complete the [create a user](quickstart-create-user.md) quickstart.

## Sign in to Intune

Sign in to the [Intune](https://aka.ms/intuneportal) as a Global Administrator or an Intune Service Administrator. Intune is located in the Azure portal by choosing **All services** > **Intune**. Intune is located in the **Monitoring + Management** section.

## Create a group
1. Once you've opened the **Microsoft Intune** pane, select **Groups** > **New group**.
2. On the **Group** pane, select **Group type** > **Security**.
3. Set the **Name** to "Contoso Testers" and add a **Description** for the group.
4. Set the **Membership type** as **Assigned**. 
5. Click **Members** and select **Members** for the group from the existing list.

    ![Screenshot of creating a group in Microsoft Intune](./media/quickstart-use-groups-01.png)

6. Click **Select**.
7. Click **Create**.

If you've successfully created the group, it will appear in the list of **All groups**. 

## Next steps

In this quickstart, you used Intune to created a group based on an existing user.

> [!div class="nextstepaction"]
> [Quickstart - Set up automatic enrollment](quickstart-setup-auto-enrollment.md)
