---
# required metadata

title: Protect devices with Microsoft Intune | Microsoft Intune
description:
keywords:
author: Robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 71e0cbf3-2bfb-412e-8a12-8503df08b4cf

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Protect devices with Microsoft Intune
Once you have your devices managed by Intune, you'll want to make sure that they are protected against unauthorized access and other threats. Here are some of the capabilities of Intune that help accomplish these aims.

> [!TIP]
> This topic does not contain all the ways in which Intune can help to secure your devices. For example, you can use Intune policies to configure many security settings for your devices like configuring passwords, encryption settings, and hardware features such as Bluetooth and the device camera. See [Manage settings and features on your devices with Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) to learn more about these settings.

## Reset passcodes when users are locked out of their devices
Since the first step in protecting company data on mobile devices is to require a passcode to use the device, sometimes you have to [reset a passcode](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) or help an employee do so, either by removing the passcode or setting a temporary passcode remotely. You can also [lock a device remotely](use-remote-lock-or-passcode-reset-in-microsoft-intune.md) if it is lost or stolen.

## Add an additional layer of protection to Windows devices
[Multi-factor authentication (MFA)](protect-windows-devices-with-multi-factor-authentication.md) is a more secure way of authenticating the users of Windows and Windows Phone devices on the network.  With MFA, users need to confirm their identity beyond username and password, through a phone call, or text message.

## Control Microsoft Passport settings on Windows devices
Intune lets you integrate with [Microsoft Passport for Work](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md) which is an alternative sign-in method for Windows 10 and later that uses Active Directory, or an Azure Active Directory account to replace a password, smart card, or virtual smart card.

## Protect Windows PCs managed with the Intune client
Intune continues to support security policies for Windows PCs that you don't enroll, but manage with the Intune computer client software. To find out how these policies can help you secure your Windows PCs, see [Use policies to help protect Windows PCs that run the Intune client software](policies-to-protect-windows-pcs-in-microsoft-intune.md).
