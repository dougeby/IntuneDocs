---
# required metadata

title: Reset Windows 10 devices with Microsoft Intune - Azure | Microsoft Docs
description: Use Fresh Start to remove or uninstall apps on Windows 10 PCs using Microsoft Intune, including pre-installed apps from OEMs. Can also keep contents of Home folder using the if user data is retained setting. 
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
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

The **Fresh Start** device action removes any apps that are installed on a Windows 10 PC running the Creators Update. Then, it automatically updates the PC to the latest version of Windows.

This action helps remove pre-installed (OEM) apps that are typically installed with a new PC. To keep the contents of the user's Home folder, and only remove apps and settings, use the `if user data is retained` setting.

> [!IMPORTANT]
> Fresh Start unenrolls the device from Intune, but the device is still joined in Azure Active Directory.

## Use Fresh Start

1. Sign in to the [Azure portal](https://portal.azure.com).
2. Choose **All services**, filter on **Intune**, and select **Microsoft Intune**.
3. Select **Devices**, and then select **All devices**.
4. From the list of devices you manage, choose a Windows 10 desktop device, and then select **Fresh Start**.

## Next steps

To see the status of this action, select **Device actions** (**Microsoft Intune** > **Devices**).