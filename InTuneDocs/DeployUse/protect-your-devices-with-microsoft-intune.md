---
# required metadata

title: Protect devices | Microsoft Intune
description: Learn about some of the ways that Intune can help you protect your devices against unauthorized access and other threats.
keywords:
author: Robstackmsft
manager: angrobe
ms.date: 07/13/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 71e0cbf3-2bfb-412e-8a12-8503df08b4cf

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Protect devices with Microsoft Intune
After you have your devices managed by Intune, you'll want to make sure that they are protected against unauthorized access and other threats. Here are some of the capabilities of Intune that help accomplish these aims.

> [!TIP]
> This topic does not contain all the ways that Intune can help to secure your devices. For example, you can use Intune policies to configure many security settings for your devices, such as passwords and encryption settings, and hardware features, such as Bluetooth and the device camera. See [Manage settings and features on your devices with Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) to learn more about these settings.

## Reset passcodes when users are locked out of their devices
The first step in protecting company data on mobile devices is to require a passcode to use the device. Sometimes you have to [reset a passcode](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) or help an employee do so, either by removing the passcode or setting a temporary passcode remotely. You can also [lock a device remotely](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) if it is lost or stolen.

## Add an additional layer of protection to Windows devices
[Multi-factor authentication (MFA)](protect-windows-devices-with-multi-factor-authentication.md) is a more secure way of authenticating the users of Windows and Windows Phone devices on the network. With MFA, users need to confirm their identity beyond user name and password through a phone call or text message.

## Control Microsoft Passport settings on Windows devices
Intune integrates with [Microsoft Passport for Work](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md). which is an alternative sign-in method for Windows 10 and later. Microsoft Passport for Work uses Active Directory or an Azure Active Directory account to replace a password, smart card, or virtual smart card.

## Bypass Activation Lock on iOS devices
Activation Lock is a feature that helps protect users' devices by requiring their Apple ID and password to be entered before anyone can erase or reactivate the device. However, this can lead to problems if, for example, the user leaves the company without removing the lock. [iOS Activation Lock bypass](help-protect-ios-devices-with-activation-lock-bypass-for-microsoft-intune.md) can help by removing the lock from supervised iOS devices so that you can reallocate or erase them.

## Protect Windows PCs managed with the Intune client
Intune continues to support security policies for Windows PCs that you don't enroll but manage with the Intune computer client software. To find out how these policies can help you secure your Windows PCs, see [Use policies to help protect Windows PCs that run the Intune client software](policies-to-protect-windows-pcs-in-microsoft-intune.md).
