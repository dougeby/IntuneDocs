---
# required metadata

title: Remove company data from devices with Intune 
titleSuffix: "Intune on Azure"
description: Learn how to remove only company data from devices you manage with Intune."
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f021e95f-157f-4e8a-9253-1cff03d6ee3e

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: ilwu
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Remove company data from Intune-managed devices


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

The **Remove company data** removes only company data from devices managed by Intune. Does not remove personal data from the device. The device will no longer be managed by Intune, and will no longer be able to access corporate resources (not supported for Windows devices that are joined to Azure Active Directory).

## Supported platforms

- Windows - Supported
- Windows Phone - Supported
- iOS - Supported
- macOS - Supported
- Android - Supported

## How to remove company data

1. Sign into the Azure portal.
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Devices**.
4. On the **Devices and groups** blade, choose **All devices**.
5. From the list of devices you manage, choose a device, and then choose the **Remove company data** device remote action.

## Next steps

To see the status of the action you just took, on the **Devices and groups** blade, choose **Device Actions**.
