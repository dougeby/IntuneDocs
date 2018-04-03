---
# required metadata

title: View device details with Microsoft Intune - Azure | Microsoft Docs
description: View your device details, including operating systems, storage space, manufacturer, and model. Get a list of installed apps, check compliance policies, and set up TeamViewer with Microsoft Intune in Azure. Similar to viewing inventory of the devices you manage.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/02/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: dougeby
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# See device details in Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

The **Devices** feature provides additional details into the devices you manage, including their hardware and the apps installed.

This article shows you how to view all your devices, and their properties in the Azure portal.

## View the device details

1. Sign in to the [Azure portal](https://portal.azure.com).
2. Select **All services**, filter on **Intune**, and select **Microsoft Intune**.
3. Select **Devices** > **All devices** > select one of your listed devices.
4. Within Devices, you have several options:

  - **Overview** shows the device name, and lists some key properties of the device, including whether it's a bring-your-own-device (BYOD) device, when it checked in, and more. Select **More** to also:
    - Remove company data
    - Delete the device
    - Remote lock the device
    - Erase
    - Start a remote assistance session
  - Use **Properties** to assign a [device category you create](device-group-mapping.md), and change ownership of the device to a personal device, or a corporate device.
  - **Hardware** includes a lot of details about the device, including the device ID, the operating system and version, storage space, the model and manufacturer, conditional access settings, and more details about the device.
  - **Discovered apps** shows a list of all the apps that Intune found installed on the device, and the app version. You can also **Export** the app list into a .csv file.
  - **Device compliance** lists all assigned compliance policies, and if the device is compliant or not compliant.
  - **Device configuration** shows all device configuration policies assigned to the device, and if the policy succeeded or failed.

Intune collects an app list only on corporate-owned devices. Apps aren't checked on personal devices. For Windows 10 PCs, only modern apps are listed for corporate-owned devices. Intune doesn't collect information about Win32 apps on the device. Depending on the carrier used by the devices, not all apps might be collected.

## Next steps
See what else you can do to [manage your devices](device-management.md) with Intune.