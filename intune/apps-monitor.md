---
# required metadata

title: How to monitor app information and assignments 
titlesuffix: "Azure portal"
description: After you've assigned an app to users or devices, use this information to help you monitor its status."
keywords:
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/20/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 64e5133d-1e23-4ee6-b556-f5d32c0e95da

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---

# How to monitor app information and assignments with Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune provides a number of ways in which you can monitor the properties of apps you manage, as well as their assignment status.

1. Sign in to the Azure portal.
2. Choose **More Services** > **Monitoring + Management** + **Intune**.
3. In the **Mobile Apps** workload, choose **Apps** in the **Manage** group.
     
    ![App install status blade.](./media/monitor-apps.png)
5. In the list of apps blade, choose an app you. You'll then see the <*app name*> **Device install status** blade.

The device install status report contains the following columns:

1.  **Device Name** 
      The name of the type of device.
2.  **User Name** 
      The name of the user.
3.   **Platform** 
       The operating system installed on the device.
4.  **Version** 
      The version number of the application.
5.   **Status** 
       The possible statuses for the apps are: **Installed**, **Not Installed**, **Install Pending** and **Error**.
6. **Status Details** 
    A readable description of the app's status on the device.
7. **Last Check-In** 
     When the device last checked-in to Intune.

Then, take one of the following actions to learn more about your apps, and their assignments.

## General

- **Overview** - Provides a basic overview of the app, and information about the status of any assignments for that app. You can choose one of the charts to open the **Device install status** or **User install status** blades to get more detailed information.

## Manage

- **Properties** - Let's you view and change information about the selected app. For more information about app properties, see [How to add an app to Microsoft Intune](apps-add.md).
- **Assignments** - Provides information about assignments for this app. For more information, see [How to assign apps to groups with Microsoft Intune](apps-deploy.md).

## Monitor

- **Device install status** - Provides detailed information for each device you assigned the selected app to including the device name, operating system, when the device last checked-in to Intune, and the status of the app installation.
- **User install status** - Provides detailed information for user you assigned the selected app to, including the number of installations of the app the user has on all their devices, and information about any installation failures.