---
# required metadata

title: How to monitor app information and assignments
titlesuffix: Microsoft Intune
description: After you've assigned an app to users or devices, use this information to help you monitor its status.
keywords:
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/09/2018
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
2. Choose **All services** > **Intune**. Intune is located in the **Monitoring + Management** group.
3. Choose **Mobile Apps**, then choose **Apps** in the **Manage** group.
5. In the list of apps, choose an app you want to monitor. You'll then see the app blade with an overview of the device status and the user status.

## App overview blade

You can use the specific app blade to review details about the status of an app in your environment.

### Essentials
The **Essentials** section contains the following information about the app:

 | **App Details**            | **Description**                                                      |
|------------------------|------------------------------------------------------------------|
| **Publisher**          | Publisher of the app.                                            |
| **Operating system**   | The operating system of the app (Windows, iOS, Android, etc.) |
| **Created**             | The date and time when this revision was created.                         |
| **Assigned**           | **Yes** or **No** if the app has been assigned.                  |

### Device and user status graphs
The graphs shows the number for the following status:

| **Device Status**       | **Description**                                       |
|-----------------------|-------------------------------------------------------|
| **Installed**         | The number of apps installed.                         |
| **Not Installed**     | The number of apps not installed.                     |
| **Failed**            | The number of failed installations.                   |
| **Install Pending**   | The number of apps in the process of being installed. |
| **Not Applicable**           | The number of apps where status is not applicable.            |

### Device install status

A device status list is displayed when you select **Device install status** in the **Monitor** section. The details table includes the following columns:

| **Device Column**      | **Description**                                                                                                                                                                                                                                            |
|----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Device name**      | Name of the device on platforms that allow naming a device. On other   platforms, Intune creates a name from other properties. This attribute cannot   be available for all devices.                                                                       |
| **User name**        | The name of the user.                                                                                                                                                                                                                                      |
| **Platform**         | The operating system of the device (Windows, iOS, Android, etc.)                                                                                                                                                                                           |
| **Version**          | The version number of the app. For line-of-business apps the full version   number of the app is displayed. The full version number identifies a specific   release of the app. The number appears as _Version_(_Build_). For example,   2.2(2.2.17560800) |
| **Status**           | The status of the app.                                                                                                                                                                                                                                     |
| **Status details**   | Details of the status.                                                                                                                                                                                                                                     |
| **Last check-in**    | Date of the device last sync with Intune.                                                                                                                                                                                                                  |


### User install status

A user status list is displayed when you select **User install status** in the **Monitor** section. The details table includes the following columns:

| **User Column**     | **Description**                           |
|---------------------|-------------------------------------------|
| **Name**            | The name of the user in Azure AD.         |
| **User name**       | The unique name of the user.              |
| **Installations**   | Number of apps installs used by the user. |
| **Failures**        | Number of failed install by the user.     |
| **Not installed**   | Number of apps not installed by the user. |


## Next steps

- To learn more about working with your Intune data, see the [Use the Intune Data Warehouse](reports-nav-create-intune-reports.md).
- To learn about app configuration policies, see [App configuration policies for Intune](app-configuration-policies-overview.md).