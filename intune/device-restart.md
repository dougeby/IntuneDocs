---
# required metadata

title: Remotely restart devices with Intune 
titleSuffix: "Intune on Azure"
description: Learn how to remotely restart devices using the restart device action."
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/27/2017
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: c707e0c4-391a-4bad-9dfd-9a7799c48dd5

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: ilwu
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Remotely restart devices with Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

The **Restart** device action causes the device you choose to be restarted. The device owner is not automatically notified of the restart, therefore might lose work.

## Supported platforms

- Windows - Supported on Windows 8.1 and later
- Windows Phone - Supported on Windows Phone 8.1 and later
- iOS - Not supported
- macOS - Not supported
- Android - Not supported

## How to restart a device

1. Sign into the Azure portal.
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Devices**.
4. on the **Devices and groups** blade, choose **All devices**.
5. From the list of devices you manage, choose a device, and then choose the **Restart** device remote action.

## Next steps

To see the status of the action you just took, on the **Devices and groups** blade, choose **Device Actions**.
