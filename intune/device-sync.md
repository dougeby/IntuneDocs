---
# required metadata

title: Sync devices with Intune 
titlesuffix: "Azure portal"
description: Learn how to synchronize devices with Intune to get the latest policies and actions."
keywords:
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 02ad249e-f098-421f-861f-6b2ff733ac7c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: ilwu
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Sync devices with Intune to get the latest policies and actions


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

The **Sync** device action forces the selected device to immediately check in with Intune. When a device checks in, it immediately receives any pending actions or policies that have been assigned to it.  This action can help you to immediately validate and troubleshoot policies you’ve assigned, without waiting for the next scheduled check-in.

## Supported platforms

- Windows - Supported
- Windows Phone - Supported
- iOS - Supported
- macOS - Supported
- Android - Supported

## How to sync a device

1. Sign into the Azure portal.
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Devices**.
4. On the **Devices and groups** blade, choose **All devices**.
5. From the list of devices you manage, choose a device, and then choose the **Sync** remote action.
7. Choose **Yes** to confirm the action.

## Next steps

Choose **Device Actions** to see the status of the sync action. 
