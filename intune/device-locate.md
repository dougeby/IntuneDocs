---
# required metadata

title: Find lost iOS devices with Microsoft Intune - Azure | Microsoft Docs
description: Find or locate lost or stolen iOS devices using Locate Device feature in Microsoft Intune; and get details on the security and privacy information when using the Locate Device action.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
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

To get the location of a lost or stolen iOS device on a map, use the **Locate Device** action. The device must be a corporate-owned iOS device, enrolled through the device enrollment program (DEP), and be in supervised mode. Before you use this action, be sure the device is in [lost mode](device-lost-mode.md).

## Supported platforms

- iOS 9.3 and later

This feature is **not** supported for the following: 
- Windows
- Windows Phone
- macOS
- Android

## Locate a lost or stolen device

1. Sign in to the [Azure portal](https://portal.azure.com).
2. Select **All services**, filter on **Intune**, and select **Microsoft Intune**.
3. Select **Devices**, and then select **All devices**.
4. From the list of devices you manage, choose an iOS device, choose **...More**, and then choose the **Locate device** remote action.
5. After the device is located, it's location is displayed on the **Locate device** blade.
	![Locate device using Intune in Azure](./media/locate-device.png)

>[!NOTE]
>For privacy purposes, the distance you can zoom into the map is limited.

## Security and privacy information for lost mode and locate device actions
- No device location information is sent to Intune until you turn this action on.
- When you use the locate device action, the latitude and longitude coordinates of the device are sent to Intune, and displayed in the Azure portal.
- The data is stored for 24 hours, then removed. You cannot manually remove the location data.
- Location data is encrypted, both while stored, and while being transmitted.
- When you configure lost mode, you can customize a message that displays on the lock screen. In this message, to help the person that finds the device, be sure to include specific details to return the lost device.

## Next steps

To see the status of enabling Locate Device, open **Devices**, and select **Device actions**.