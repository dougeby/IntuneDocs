---
# required metadata

title: Restart devices with Microsoft Intune - Azure | Microsoft Docs
description: Restart Windows and iOS devices using Microsoft Intune in the Azure portal using the Restart remote action.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/21/2018
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
2. Select **All services**, filter on **Intune**, and select **Microsoft Intune**.
3. Select **Devices** > **All devices**.
4. In the list of devices that you manage, select a device, select **More**, and then select the **Restart** device remote action.

## Next steps

- To see the status of the **Restart** device action, select **Devices** > **Device actions**.
