---
# required metadata

title: Remotely restart devices with Intune 
titlesuffix: Microsoft Intune
description: Learn how to remotely restart devices using the restart device action in Microsoft Intune.
keywords:
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 02/22/2018
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

The **Restart** device action causes the device you choose to be restarted. The device owner isn't automatically notified of the restart, and they might lose work.

## Supported platforms

- Windows - Supported on Windows 8.1 and later
- Windows Phone - Supported on Windows Phone 8.1 and later
- iOS - Supported

    > [!Note]  
    > This command requires a supervised device and the **Device Lock** access right. The device restarts immediately. Passcode-locked iOS devices don't rejoin a Wi-Fi network after restart. After restart, the device might not be able to communicate with the server.
- macOS - Not supported
- Android - Not supported

## Restart a device

1. Sign in to the [Azure portal](https://portal.azure.com).
2. Select **All services** > **Intune**. Intune is located in the **Monitoring + Management** section.
3. In the **Intune** pane, select **Devices**.
4. In the **Devices** pane, select **All devices**.
5. In the list of devices that you manage, select a device, select **More**, and then select the **Restart** device remote action.

## Next steps

- To see the status of the **Restart** device action, select **Devices** > **Device actions**.
