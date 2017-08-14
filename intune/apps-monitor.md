---
# required metadata

title: How to monitor app information and assignments 
titleSuffix: "Intune on Azure"
description: After you've assigned an app to users or devices, use this information to help you monitor its status."
keywords:
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 05/05/2017
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

1. In the **Mobile Apps** workload, choose **Manage** > **Apps**.
2. In the list of apps blade, choose the app you want to see information for. You'll then see the <*app name*> **Device install status** blade:
![App install status blade.](./media/monitor-apps.png)

Then, take one of the following actions to learn more about your apps, and their assignments.

## General

- **Overview** - Provides a basic overview of the app, and information about the status of any assignments for that app. You can choose one of the charts to open the **Device install status** or **User install status** blades to get more detailed information.

## Manage

- **Properties** - Let's you view and change information about the selected app. For more information about app properties, see [How to add an app to Microsoft Intune](apps-add.md).
- **Assignments** - Provides information about assignments for this app. For more information, see [How to assign apps to groups with Microsoft Intune](apps-deploy.md).

## Monitor

- **Device install status** - Provides detailed information for each device you assigned the selected app to including the device name, operating system, when the device last checked-in to Intune, and the status of the app installation.
- **User install status** - Provides detailed information fro user to you assigned the selected app to including the number of installations of the app the user has on all their devices, and information about any installation failures.