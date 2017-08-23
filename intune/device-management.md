---
# required metadata

title: Manage devices with Intune
titleSuffix: "Intune on Azure"
description: Learn how to see the devices you manage with Intune, and perform various operations on them."
keywords:
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/23/2017
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: angrobe
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# What is Microsoft Intune device management?


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

The **Devices** workload gives you insights into the devices you manage, and lets you perform remote tasks on those devices. To access the workload:

1. Sign into the Azure portal.
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Devices**.
4. You can view information about devices and perform the remote device actions listed.

## Available device actions
The actions available depend on the device platform, and the configuration of the device.

- [View device inventory](device-inventory.md)
- Perform remote device actions:
	- [Remove company data](devices-wipe.md#remove-company-data)
	- [Factory reset](devices-wipe.md#factory-reset)
	- [Remote lock](device-remote-lock.md) 
	- [Reset passcode](device-passcode-reset.md)
	- [Bypass Activation Lock](device-activation-lock-bypass.md) (iOS only)
	- [Fresh Start](device-fresh-start.md) (Windows only)
	- [Lost mode](device-lost-mode.md) (iOS only)
	- [Locate device](device-locate.md) (iOS only)
	- [Restart](device-restart.md) (Windows only)
	- [Windows 10 PIN reset](device-windows-pin-reset.md)
	- [Remote control for Android](device-profile-android-teamviewer.md)
	- [Synchronize device](device-sync.md)


## Next steps

- Choose **Device Actions** to see the status of actions taken on devices you manage.
![Monitor device actions](./media/monitor-device-actions.png)
