---
# required metadata

title: Remove a user from an iOS device with Intune 
titlesuffix: "Azure portal"
description: Learn how to remove a user from a shared iOS device with Intune."
keywords:
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 2ea5941c-a69b-4e1c-b42c-a1fc0c3a7de7

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: ilwu
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Remove a user from a shared iOS device with Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

The **Remove user** action deletes a user you choose from the local cache on a shared iPad device that has been configured to manage the iOS Classroom app with an [iOS education profile](education-settings-configure-ios.md). 

## Supported platforms

- Windows - Not supported
- Windows Phone - Not supported
- iOS - Supported on iOS 9.3 and later (shared iPad devices only)
- macOS - Not supported
- Android - Not supported

## How to remove a user

1. Sign into the Azure portal.
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Devices**.
4. On the **Devices** blade, choose **All devices**.
5. From the list of devices you manage, choose an iOS device.
6. On the blade for that device, choose **Users**.
7. From the list, right-click the user you want to remove, and then choose **Remove user**.

## Next steps

To see the status of the action you just took, on the **Devices and groups** blade, choose **Device Actions**.
