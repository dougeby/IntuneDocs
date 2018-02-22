---
# required metadata

title: How to monitor app information and assignments 
titlesuffix: Azure portal
description: After you've assigned an app to users or devices, use this information to help you monitor its status.
keywords:
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 11/21/2017
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

1. Sign into the [Azure portal](https://portal.azure.com).
2. Choose **All services** > **Intune**. Intune is located in the **Monitoring + Management** section.
3. Choose **Mobile Apps**, then choose **Apps** in the **Manage** group.
5. In the list of apps blade, choose an app. You'll then see the <*app name*> **Device install status** blade.

## App overview blade

You can use the <*app name*> **Device install status** blade to review details about the status of an app in your environment.

### Essentials

The **Essentials** section contains the following information about the app:

 - **Publisher**  
Publisher of the app.
 - **Operating system**  
The operating system of the app  (Windows, iOS, Android, etc.)
 - **Create**  
The time when this revision was created.
 - **Assigned**  
**Yes** or **No** if the app has been assigned.

### Status
Each graph shows counts for the following status:

 - **Installed**  
The number of apps installed.
 - **Not Installed**  
The number of apps not installed.
 - **Install Pending**  
The number of apps in the process of being installed.
 - **Failed**  
The number of failed installations.
 - **Unknown**  
The number of apps with an unknown status.

### Device status

Device status. A donut chart that displays the install status of the app on devices. Click the graph to open a list of details about the device status. The details table includes the following columns:

 - **Device name**  
Name of the device on platforms that allow naming a device. On other platforms, Intune creates a name from other properties. This attribute cannot be available for all devices.
 - **User name**  
The name of the user.
 - **Platform**  
The operating system of the device (Windows, iOS, Android, etc.)
 - **Version**  
The version number of the app. For line-of-business apps the full version number of the app is displayed. The full version number identifies a specific release of the app. The number appears as _Version_(_Build_). For example, 2.2(2.2.17560800)
 - **Status**  
The status of the app.
 - **Status details**  
Details of the status.
 - **Last check-in**  
Date of the device last sync with Intune.


### User status

User status. A donut chart that displays the install status of the app for users. Click the graph to open a list of details about the device status. The details table includes the following columns:
 - **Name**  
The name of the user in Azure AD.
 - **User name**  
The unique name of the user.
 - **Installations**  
Number of apps installs used by the user.
 - **Failures**  
Number of failed install by the user.
 - **Not installed**  
Number of apps not installed by the user.


## Next steps

To learn more about working with your Intune data, see the [Use the Intune Data Warehouse](reports-nav-create-intune-reports.md).