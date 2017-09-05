---
# required metadata

title: Activate iOS lost mode with Intune 
titleSuffix: "Intune on Azure"
description: Learn how to use Intune to activate lost mode on lost or stolen iOS devices."
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 126a7489-fe3e-43fd-a681-defb2fe0bb66

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: ilwu
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Activate lost mode on iOS devices


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

The **Lost mode** device action helps you enable lost mode on lost or stolen iOS devices. This mode lets you specify a message and a phone number that is displayed on the lock screen of the device.

## Supported platforms

- Windows - Not supported
- Windows Phone - Not supported
- iOS - Supported on iOS 9.3 and later, supervised, and corp owned
- macOS - Not supported
- Android - Not supported

## How to activate lost mode

1. Sign into the Azure portal.
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Devices**.
4. On the **Devices and groups** blade, choose **All devices**.
5. From the list of devices you manage, choose an iOS device, and then choose the **Lost mode** remote action.
6. On the **Lost mode** blade, enable lost mode. Then, enter the message to be displayed, and optionally, a contact phone number.
7. Click **OK**.

When you enable lost mode, you block all use of the device. The end user cannot access the device until you disable lost mode. While lost mode is enabled, you can use the **Locate device** action to find out where the device is.
To use lost mode, the device must be a corporate-owned iOS device that is in supervised mode.

## Security and privacy information for the lost mode and locate device actions
- No device location information is sent to Intune until you turn on this action.
- When you use the locate device action, the latitude and longitude coordinates of the device are sent to Intune, and displayed in the Azure portal.
- The data is stored for 24 hours, then removed. You cannot manually remove the location data.
- Location data is encrypted, both while stored, and while being transmitted.
- We recommend that the message you enter to display on the lock screen includes information that helps someone who finds the device to return it.

## Next steps

To see the status of the action you just took, on the **Devices and groups** blade, choose **Device Actions**.

