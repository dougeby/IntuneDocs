---
# required metadata

title: Reset Windows 10 devices with Intune 
titlesuffix: "Azure portal"
description: Learn how to use Fresh Start to reset Windows 10 PCs running Intune."
keywords:
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 08/09/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: ilwu
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Use Fresh Start to reset Windows 10 devices with Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

The **Fresh Start** device action removes any apps that were installed on a Windows 10 PC running the Creators Update, then automatically updates the PC to the latest version of Windows.
This action can be used to help remove pre-installed (OEM) apps that are often delivered with a new PC. You can configure if user data is retained when this device action is issued. In this case, apps and settings are removed, but the contents of the users Home folder are retained.

## How to use Fresh Start

1. Sign into the [Azure portal](https://portal.azure.com).
2. Choose **All services** > **Intune**. Intune is located in the **Monitoring + Management** section.
3. On the **Intune** pane, choose **Devices**.
4. On the **Devices** pane, choose **All devices**.
5. From the list of devices you manage, choose a Windows 10 desktop device, and then choose the **Fresh Start** device remote action.

## Next steps

To see the status of the action you just took, on the **Devices** pane, choose **Device actions**.

