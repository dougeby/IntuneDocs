---
# required metadata

title: Bypass iOS Activation Lock with Intune
titlesuffix: "Azure portal"
description: Learn how to use Intune to bypass iOS Activation Lock to access locked devices."
keywords:
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 08/22/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 9ca3b0ba-e41c-45fb-af28-119dff47c59f

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: ilwu
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Bypass Activation Lock on Supervised iOS devices with Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Microsoft Intune can help you manage iOS Activation Lock, a feature of the Find My iPhone app for iOS 8.0 and later devices. Activation Lock is enabled automatically when a user opens the Find My iPhone app on a device. After it is enabled, the user's Apple ID and password must be entered before anyone can:

- Turn off Find My iPhone
- Erase the device
- Reactivate the device

## How Activation Lock affects you

While Activation Lock helps secure iOS devices and improves the chances of recovering a lost or stolen device, this capability can present you, as an IT admin, with a number of challenges. For example:

- A user sets up Activation Lock on a device. The user then leaves the company and returns the device. Without the user's Apple ID and password, there is no way to reactivate the device.
- You need a report of all devices that have Activation Lock enabled.
- You want to reassign some devices to a different department during a device refresh in your organization. You can only reassign devices that do not have Activation Lock enabled.

To help solve these problems, Apple introduced Activation Lock bypass in iOS 7.1. Activation Lock bypass lets you remove the Activation Lock from supervised devices without the user's Apple ID and password. Supervised devices can generate a device-specific Activation Lock bypass code, which is stored on Apple's activation server.

>[!TIP]
>Supervised mode for iOS devices lets you use Apple Configurator to lock down a device and limit functionality to specific business purposes. Supervised mode is used only for corporate-owned devices.

You can read more about Activation Lock on [Apple's web site](https://support.apple.com/HT201365).

## How Intune helps you manage Activation Lock
Intune can request the Activation Lock status of supervised devices that run iOS 8.0 and later. For supervised devices only, Intune can retrieve the Activation Lock bypass code and directly issue it to the device. If the device has been wiped, you can directly access the device by using a blank user name and the code as the password.

**The business benefits of using Intune to manage Activation Lock are:**

- The user gets the security benefits of the Find My iPhone app.
- You can enable users to do their work and know that when a device needs to be repurposed, you can retire or unlock it.

## Before you start
Before you can bypass Activation Lock on devices, you must enable it by following these instructions:

1. Configure an Intune device restriction profile for iOS using the information in [How to configure device restriction settings](/intune-azure/configure-devices/how-to-configure-device-restrictions).
2. In the [device restriction settings for iOS](device-restrictions-ios.md), under the **General** settings, enable the option **Activation Lock**.
3. Save the profile, and then [assign it](device-profile-assign.md) to the devices on which you want to manage Activation Lock bypass.


## How to use Activation Lock bypass

>[!IMPORTANT]
>After you bypass the Activation Lock on a device, if the Find My iPhone app is opened, a new Activation Lock is automatically applied. Because of this, **you should be in physical possession of the device before you follow this procedure**.

The Intune **Bypass Activation Lock** remote device action removes the activation lock from an iOS device without the user’s Apple ID and password. Once you bypass the activation lock, the device turns on activation lock again when the Find My iPhone app launches. Only bypass the activation lock if you have physical access to the device.

1. Sign into the Azure portal.
2. Choose **All services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Devices**.
4. On the **Devices** blade, choose **All devices**.
5. From the list of devices you manage, choose a supervised iOS device, choose **...More**, and then choose the **Bypass Activation Lock** device remote action.

## Next steps

You can examine the status of the unlock request on the details page for the device in the **Manage devices** workload.
