---
# required metadata

title: View Intune device inventory 
titlesuffix: "Azure portal"
description: Learn how to view the devices you manage with Intune, and understand their hardware and installed apps."
keywords:
author: arob98
ms.author: angrobe
nmanager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: angrobe
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# How to view Intune device inventory


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

The **Devices** workload gives you insights into the devices you manage, including their hardware capabilities, and the apps installed on them. 

To view device inventory:

1. Sign into the [Azure portal](https://portal.azure.com).
2. Choose **All services** > **Intune**. Intune is located in the **Monitoring + Management** section.
3. On the **Intune** blade, choose **Devices**.

Now, choose one of the following options:

- **Overview** Get information about devices you've enrolled, and the operating systems each device runs.
- **Manage** - Choose **All devices** to see a list of all the devices you manage.
	Select one of those devices in the list to open the <*device name*> **Overview** blade where you can select one of:
	- **Overview**  - See general information about the device including its name, owner, whether it is a BYOD device, when it checked-in, and more.
	- **Hardware** - See more detailed information about the device including its free storage space, model and manufacturer, and more.
	- **Discovered apps** - Displays a list of all apps that Intune found installed on the device.
	- **Device compliance** - Displays the compliance state of all compliance policies that have been assigned to the device.
	- **Device configuration** - Displays the compliance state of all device configuration policies that have been assigned to the device.
- **Monitor** - Choose **Device actions** to see a list of device actions that have been performed on devices you manage and their current state.
- **Setup** > **TeamViewer Connector** - Let's you configure remote administration on devices using the TeamViewer software. For details, see [Provide remote assistance for Intune managed Android devices](/intune/device-profile-android-teamviewer).

Intune collects app inventory only on corporate-owned devices. Apps are not inventoried on personal devices. For Windows 10 PCs, only modern app inventory is collected on corporate-owned devices. Intune does not collect information about Win32 apps on the device. Depending on the carrier you use with devices, not all inventory items might be collected.
