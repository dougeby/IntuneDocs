---
# required metadata

title: Customize console views for admin roles 
description: Use this topic to help you filter the Intune admin console view to allow your admins to see only the items they need for their role.
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e0783eaa-67dc-410e-9e80-4d3aa72f36d8ROBOTS: NOINDEX,NOFOLLOW

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Customize Intune console views according to admin roles

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

You can filter the Microsoft Intune administration console view to allow your admins to see only the items they need to see for their role. For example, you can allow only admin console operators to update malware definitions or reset the passcode on devices. You do this by using preset **designations** that you assign to specific users. When these users access the admin console, they can only see items that are specific to their designation.

## To create a custom view

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Admin** &gt; **Service Administrators**.

2.  From the list of service administrators, choose the user whose designation you want to change, and then choose **Manage Access**.

3.  In the **Manage Access** dialog box, choose the level of access that you want to give the selected user. You can choose from:

    -   **Full access**
    -   **Read-only access**
    -   **Helpdesk - Groups node**

    Full access and read-only access are self-explanatory. <!--- **Helpdesk - Groups Node** allows users to choose from one of the following designations that provide custom levels of access to the Intune admin console:--->

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

        -   Lock a device remotely

        -   Reset a passcode

When the admin that you configured next opens the Intune admin console, they will be given the level of access that you designated.
