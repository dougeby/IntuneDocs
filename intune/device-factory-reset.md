---
# required metadata

title: Reset devices to factory settings with Intune 
titleSuffix: "Intune on Azure"
description: Learn how to reset devices you manage with Intune to their factory settings."
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8eff9b53-eef2-4c50-8aee-556bc49d69f2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: ilwu
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Reset Intune-managed devices to factory settings


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

The **Factory reset** returns a device to its default settings. The device will no longer be managed by Intune and both company and personal data are removed. You cannot undo this action.

## Supported platforms

- Windows - Supported on Windows 8.1 and later (not EAS managed devices)
- Windows Phone - Supported
- iOS - Supported
- macOS - Not supported
- Android - Supported (Android for Work is not supported)

## How to reset a device to factory settings

1. Sign into the Azure portal.
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Devices**.
4. On the **Devices and groups** blade, choose **All devices**.
5. From the list of devices you manage, choose a device, and then choose the **Factory reset** device remote action.

## Next steps

To see the status of the action you just took, on the **Devices and groups** blade, choose **Device Actions**.

