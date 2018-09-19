---
title: Quickstart - Create and assign a custom role in Intune
description: Quickstart - Create and assign a custom role for a remote device manager.
services: microsoft-intune
author: ErikjeMS

ms.service: microsoft-intune
ms.topic: quickstart
ms.date: 09/15/2018
ms.author: erikje
---

# Quickstart: Create and assign a custom role

In this Intune quickstart, you'll create a custom role with specific permissions for a security operations department. Then you'll assign the role to a group of such operators. There are several default roles that you can use right away. But by creating custom roles like this one, you have precise access control to all parts of your mobile device management system.

If you don’t have an Intune subscription, [sign up for a free trial account](free-trial-sign-up.md).

## Sign in to Intune

Sign in to [Intune](https://aka.ms/intuneportal) as a Global Administrator or an Intune Service Administrator.

## Create a custom role

When you create a custom role, you can set permissions for a wide range of actions. For the security operations role, we'll set a few Read permissions so that the operator can review a device's configurations and policies.

1. In Intune, choose **Roles** > **All roles** > **Add**.
![Browser](media/quickstart-create-custom-role/add-custom-role.png)
2. Under **Add custom role**, in the **Name** box, enter *Security operations*.
3. In the **Description** box, enter *This role lets a security operator monitor device configuration and compliance information.*
4. Choose **Configure** > **Corporate device identifiers** > **Yes** next to **Read** > **OK**.
![Browser](media/quickstart-create-custom-role/corp-device-id-read.png)
5. Choose **Device compliance policies** > **Yes** next to **Read** > **OK**.
6. Choose **Device configurations** > **Yes** next to **Read** > **OK**.
7. Choose **Organization** > **Yes** next to **Read** > **OK**.
8. Choose **OK** > **Create**.

## Assign the role to a group

Before your security operator can use the new permissions, you must assign the role to a group that contains the security user.

1. In Intune, choose **Roles** > **All roles** > **Remote device helpdesk**.
2. Under **Intune roles**, choose **Assignments** > **Assign**.
3. In the **Assignment name** box, enter *Sec ops*.
4. Choose **Member (Groups)** > **Add**.
5. Choose a group that contains your helpdesk operators who will handle remote devices.
6. Choose **Select** > **OK**.
7. Choose **Scope (Groups)** > **Select groups to include** > choose a group that includes all employees normally assigned security policies or profiles.
8. Choose **Select** > **OK** > **OK**.

Now everyone in the group is a member of the *Security operations* role and can review the following information about a device: corporate device identifiers, device compliance policies, device configurations, and organization information.

## Clean up resources

If you don't want to use the new custom role any more, you can delete it. Choose **Roles** > **All roles** > choose the ellipses next to the role > **Delete**.

## Next steps

In this quickstart, you created a custom security operations role and assigned it to a group. You can learn more about security issues in the following article.

> [!div class="nextstepaction"]
> [Get started with device compliance policies](device-compliance-get-started.md)
