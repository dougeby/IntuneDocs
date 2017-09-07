---
# required metadata

title: Locate lost iOS devices with Intune 
titlesuffix: "Azure portal"
description: Learn how locate lost or stolen iOS devices with Intune."
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 3e544286-12ad-4a3a-86f8-d2cf16940b1f

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: ilwu
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Locate lost or stolen iOS devices with Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

The **Locate Device** device action displays the location of a lost or stolen iOS device on a map. The device must be a corporate-owned iOS device, enrolled through DEP, that is in supervised mode. Before you use this action, the device must have been placed into [lost mode](/intune-azure/manage-devices/lost-mode.md).

## Supported platforms

- Windows - Not supported
- Windows Phone - Not supported
- iOS - Supported on iOS 9.3 and later (in Lost mode), supervised, and corp owned
- macOS - Not supported
- Android - Not supported

## How to locate a lost or stolen device

1. Sign into the Azure portal.
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Devices**.
4. On the **Devices and groups** blade, choose **All devices**.
5. From the list of devices you manage, choose an iOS device, and then choose the **Locate Device** remote action.
6. After the device has been located, it's location is displayed on the **Locate device** blade.
	![Locate device blade](./media/locate-device.png)

>[!NOTE]
>For privacy purposes, the distance you can zoom into the map is limited.

## Security and privacy information for the lost mode and locate device actions
- No device location information is sent to Intune until you turn this action on.
- When you use the locate device action, the latitude and longitude coordinates of the device are sent to Intune, and displayed in the Azure portal.
- The data is stored for 24 hours, then removed. You cannot manually remove the location data.
- Location data is encrypted, both while stored, and while being transmitted.
- When you configure lost mode, we recommend that the message you enter to display on the lock screen includes information that helps someone who finds the device to return it.


## Next steps

To see the status of the action you just took, on the **Devices and groups** blade, choose **Device Actions**.