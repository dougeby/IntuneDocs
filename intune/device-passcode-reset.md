---
# required metadata

title: Reset a device passcode with Intune 
titlesuffix: "Azure portal"
description: Learn how to reset the passcode on devices you manage with Intune."
keywords:
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: ilwu
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Reset the passcode on Intune-managed devices


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

The **Remove passcode** action generates a new passcode for the device, which is displayed on the <*device name*> **Overview** blade.

## Supported platforms

- Windows - Not supported
- Windows Phone - Supported on Windows Phone 8.1 to Windows 10 Creators update not Azure AD joined, Windows 10 Creators Update and later
- iOS - Supported
- macOS - Not supported
- Android - Supported on Android versions earlier than Android 7. Android for Work is not supported.

## How to reset a passcode

1. Sign into the Azure portal.
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Devices**.
4. On the **Devices and groups** blade, choose **All devices**.
5. From the list of devices you manage, choose a device, and then choose the **Remove passcode** device remote action.

## Next steps

To see the status of the action you just took, on the **Devices and groups** blade, choose **Device Actions**.
