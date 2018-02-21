---
# required metadata

title: Remotely restart devices with Intune 
titlesuffix: "Azure portal"
description: Learn how to remotely restart devices using the restart device action."
keywords:
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 11/21/2017
ms.topic: article
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
- iOS - Supported

    > [!Note]  
    > This command requires a supervised devices and the **Device Lock** access right. The device restarts immediately. Passcode-locked iOS devices will not rejoin a Wi-Fi network after restart; after restart, they may not be able to communicate with the server.
- macOS - Not supported
- Android - Not supported

## How to restart a device

1. Sign into the [Azure portal](https://portal.azure.com).
2. Choose **All services** > **Intune**. Intune is located in the **Monitoring + Management** section.
3. On the **Intune** blade, choose **Devices**.
4. On the **Devices** blade, choose **All devices**.
5. From the list of devices you manage, choose a device, choose **...More**, and then choose the **Restart** device remote action.

## Next steps

To see the status of the action you just took, on the **Devices** blade, choose **Device actions**.
