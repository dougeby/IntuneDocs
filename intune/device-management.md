---
# required metadata

title: Manage devices with Intune
titleSuffix: "Intune on Azure"
description: Learn how to see the devices you manage with Intune, and perform various operations on them."
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/02/2017
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

Now, you can perform the following actions:

- [View device inventory](device-inventory.md)
- Perform remote device actions:
	- [Remove company data](device-company-data-remove.md) 
	- [Factory reset](device-factory-reset.md)
	- [Remote lock](device-remote-lock.md)
	- [Reset passcode](device-passcode-reset.md)
	- [Bypass Activation Lock](device-activation-lock-bypass.md)
	- [Fresh Start](device-fresh-start.md)
	- [Lost mode](device-lost-mode.md)
	- [Locate device](device-locate.md)
	- [Restart](device-restart.md)
	- [Windows 10 PIN reset](device-windows-pin-reset.md)
	- [Remote control for Android](device-profile-android-teamviewer.md)
	- [Synchronize device](device-sync.md)


## Support for each device action

Use the following table to understand the device platforms that are supported by each action.

|||||||
|-|-|-|-|-|-|
|Device action|Windows|Windows Phone|iOS|macOS|Android|
|**Remove company data**|Yes|Yes|Yes|Yes|Yes|
|**Factory reset**|Windows 8.1 and later (not EAS managed devices)|Yes|Yes|No|Android for Work not supported|
|**Delete**|Yes|Yes|Yes|Yes|Yes|
|**Remote lock**|No|Windows Phone 8.1 and later|Yes|No|Yes|
|**Reset passcode**|No|Windows Phone 8.1 to Windows 10 Creators update not Azure AD joined, Windows 10 Creators Update and later - all|Yes|No|Earlier than Android 7, Android for Work not supported|
|**New passcode** (for Windows 10 devices)|No|Windows 10 Creators Update and later (Azure AD joined)|No|No|Android for Work not supported|
|**Bypass Activation Lock**|No|No|Only corporate owned devices|No|No|
|**Lost mode**|No|No|iOS 9.3 and later, supervised, and corp owned|No|No|
|**Locate device**|No|No|Lost mode iOS 9.3 and later, supervised, and corp owned|No|No|
|**Logout current user**|No|No|iOS 9.3 and later (shared iPad devices only)|No|No|
|**Restart**|Windows 8.1 and later|Windows Phone 8.1 and later|No|No|No|
|**Fresh Start**|Windows 10 Creators update and later|No|No|No|No|
|**New Remote Assistance session**|No|No|No|No|Yes|
|**Remove user**|No|No|iOS 9.3 and later (shared iPad devices only)|No|No|
|**Synchronize device**|Yes|Yes|Yes|Yes|Yes|

## Next steps

- Choose **Device Actions** to see the status of actions taken on devices you manage. 
![Monitor device actions](./media/monitor-device-actions.png)
