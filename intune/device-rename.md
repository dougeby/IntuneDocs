---
# required metadata

title: Rename a Windows device with Microsoft Intune - Azure | Microsoft Docs
description: Rename a Windows device by using Microsoft Intune.
keywords:
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/26/2019
ms.topic: conceptual
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: ilwu
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure
ms.collection: M365-identity-device-management
---

# Rename a Windows device in Intune


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

The **Rename device** action lets you rename a corporate-owned Windows device that is enrolled in Intune. This changes the device's name in Intune as well as on the device. 


## Rename a device

1. Sign in to the [Azure portal](https://portal.azure.com).
2. Choose **All services**, filter on **Intune**, and choose **Microsoft Intune**.
3. Choose **Devices** > **All devices** > choose a Windows device > **More** > **Rename device**.
4. In the **Rename device** blade, type the new name in the text box. You can use letters, numbers, and hyphens. The name must contain at least one letter or hyphen.
5. If you want to restart the device after renaming it, choose **Yes** next to **Resart after rename**.
6. Choose **Rename**.



## Next steps

To see the status of the **Rename** device action, check the **Overview** page for the device.
