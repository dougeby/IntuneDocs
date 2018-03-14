---
# required metadata

title: View your devices with Microsoft Intune - Azure | Microsoft Docs
description: View your device details, including operating systems, storage space, manufacturer, and model. Get a list of installed apps, check compliance policies, and set up TeamViewer with Microsoft Intune in Azure. Similar to viewing inventory of the devices you manage.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2018
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

# See device details in Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

The **Devices** feature provides additional details into the devices you manage, including their hardware and the apps installed. 

This article shows you how to view all your devices, and their properties in the Azure portal.

## View your device details

1. Sign in to the [Azure portal](https://portal.azure.com).
2. Select **All services**, filter on **Intune**, and select **Microsoft Intune**.
3. Select **Devices**. Within Devices, you have several options:

   - **Overview**: Get information about devices you've enrolled, and the operating system each device runs.
   - **Manage**: To see a list of all the devices you manage, choose **All devices** or **Azure AD devices**.
    Select one of the devices in the list. This step opens the <*device name*> **Overview**, where you can select the following:
     - **Overview**: See the device name, the owner, whether it's a bring-your-own-device (BYOD) device, when it checked in, and more details.
	 - **Hardware**: See free storage space, the model and manufacturer, and more details about the device.
	 - **Discovered apps**: See a list of all the apps that Intune found installed on the device.
	 - **Device compliance**: Displays the state of all compliance policies that have been assigned to the device.
	 - **Device configuration**: Displays the compliance state of all device configuration policies that are assigned to the device.
   - **Monitor**: Choose **Device actions** to see a list of actions that are done on devices you manage, and their current state. **Audit logs** show the status of different tasks.
   - **Setup** > **TeamViewer Connector**: Configure remote administration on devices by using the TeamViewer software. For details, see [Provide remote assistance for Intune managed Android devices](device-profile-android-teamviewer.md).

Intune collects an app list only on corporate-owned devices. Apps aren't checked on personal devices. For Windows 10 PCs, only modern apps are listed for corporate-owned devices. Intune doesn't collect information about Win32 apps on the device. Depending on the carrier used by the devices, not all apps may be collected.

## Next steps
See what else you can do to [manage your devices](device-management.md) with Intune.
