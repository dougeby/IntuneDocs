---
# required metadata

title: Reset and remove device passcodes with Intune 
titlesuffix: "Azure portal"
description: Learn how to reset and remove the passcode on devices you manage with Intune.
keywords:
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
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

# Reset and remove the passcode on Intune-managed devices


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

The terms *remove* and *reset* are used interchangeably in this article.

The **Remove passcode** action generates a new passcode for the device, which is displayed on the <*device name*> **Overview** blade.

## Supported platforms

- Windows - Not supported
- Windows Phone - Supported on Windows Phone 8.1 to Windows 10 Creators update not Azure AD joined, Windows 10 Creators Update and later
- iOS - Supported
- macOS - Not supported
- Android - Supported on Android versions earlier than Android 7. Android for Work is not supported.

## How to reset a passcode

1. Sign into the [Azure portal](https://portal.azure.com).
2. Choose **All services** > **Intune**. Intune is located in the **Monitoring + Management** section.
3. On the **Intune** blade, choose **Devices**.
4. On the **Devices** blade, choose **All devices**.
5. From the list of devices you manage, select a device, choose **...More**, and then choose the **Remove passcode** device remote action.

## Next steps

To see the status of the action you just took, on the **Devices** blade, choose **Device actions**.
