---
title: Control what admins can see in the Microsoft Intune admin console
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: e0783eaa-67dc-410e-9e80-4d3aa72f36d8
author: robstackmsft
---
# Control what admins can see in the Microsoft Intune admin console
[!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] provides the ability to filter the admin console view to allow users to access only the items you want them to see. For example, you might want to allow only admin console operators to be able to update malware definitions, or reset the passcode on devices. This is accomplished by using preset **designations** that you assign to specific users. When these users access the admin console, they only see items specific to their designation.

Use this feature to help you assign administration tasks to staff while still ensuring the security of your [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] data.

## How to assign a designation to a user

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Admin** &gt; **Service Administrators**.

2.  From the list of service administrators, choose the user whose designation you want to change, and then click **Manage Access**.

3.  In the **Manage Access** dialog box, choose the level of access that you want to give the selected user. You can choose from:

    -   **Full access**

    -   **Read only access**

    Additionally, the **Helpdesk - Groups Node** allows users to choose from one of the following designations that provide custom levels of access to the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] admin console:

    -   See lists of users and devices (the user cannot use filters to modify the view. However, you can use group filtering to modify what the user can see). For more information, see [Use groups to manage users and devices with Microsoft Intune](../Topic/Use-groups-to-manage-users-and-devices-with-Microsoft-Intune.md).

    -   Print the list of users and devices.

    -   Export the list of users and devices

    -   View the properties of a user or device.

    -   Perform the following remote tasks:

        -   Run a full malware scan

        -   Run a quick malware scan

        -   Restart a computer

        -   Update malware definitions

        -   Refresh policies

        -   Refresh inventory

        -   Remote lock a device

        -   Passcode reset

When the user you configured next opens the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] admin console, they will be given the level of access you specified.

## See Also
[Technical reference for Microsoft Intune](../Topic/Technical-reference-for-Microsoft-Intune.md)

