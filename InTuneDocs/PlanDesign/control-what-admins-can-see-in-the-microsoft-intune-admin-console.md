---
title: Customize console views for admin roles | Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: e0783eaa-67dc-410e-9e80-4d3aa72f36d8
author: robstackmsft
---
# Customize Intune console views according to admin roles
You can filter the [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] admin console view to allow your admins to see only the items they need to see for their role. For example, you can allow only admin console operators to update malware definitions or reset the passcode on devices. You can do this by using preset **designations** that you assign to specific users. When these users access the admin console, they only see items specific to their designation.

<!--- Use this feature to help you assign administration tasks to staff while still ensuring the security of your [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] data. --->

## How to create a custom view

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Admin** &gt; **Service Administrators**.

2.  From the list of service administrators, choose the user whose designation you want to change, and then choose **Manage Access**.

3.  In the **Manage Access** dialog box, choose the level of access that you want to give the selected user. You can choose from:

    -   **Full access**
    -   **Read-only access**
    -   **Helpdesk - Groups node**

    Full access and read-only access are self explanatory. <!--- **Helpdesk - Groups Node** allows users to choose from one of the following designations that provide custom levels of access to the [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] admin console:--->

    **Helpdesk - Groups Node** restricts what the admin can see and do to the following:

    -   See lists of users and devices. The admin cannot use filters to modify the view. However, you can use group filtering to modify what the admin can see. For more information, see [Use groups to manage users and devices with Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).

    -   Print the list of users and devices

    -   Export the list of users and devices

    -   View the properties of a user or device

    -   Perform the following remote tasks:

        -   Run a full malware scan

        -   Run a quick malware scan

        -   Restart a computer

        -   Update malware definitions

        -   Refresh policies

        -   Refresh inventory

        -   Remote lock a device

        -   Passcode reset

When the admin you configured next opens the [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] admin console, they will be given the level of access you specified.

<blockquote>
  <p>
    Unless someone like you<br>
    Cares a whole awful lot,<br>
    Nothing is going to get better.<br>
    It’s not.
  </p>
  <footer>— <cite title="Dr. Seuss">Dr. Seuss</cite></footer>
</blockquote>
