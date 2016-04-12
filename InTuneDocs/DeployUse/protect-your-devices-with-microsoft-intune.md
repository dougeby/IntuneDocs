---
title: Protect your devices with Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 71e0cbf3-2bfb-412e-8a12-8503df08b4cf
author: Robstack
---
# Protect data and devices with Microsoft Intune
Once you have your devices managed by Intune, you'll want to make sure that they are protected against unauthorized access and other threats. Here are some of the capabilities of Intune that help accomplish these aims.

> [!TIP]
> This topic does not contain all the ways in which Intune can help to secure your devices. For example, you can use Intune policies to configure many security settings for your devices like configuring passwords, encryption settings, and hardware features such as Bluetooth and the device camera. See [Manage settings and features on your devices with Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) to learn more about these settings.

## Reset passcodes when users are locked out of their devices
Since the first step in protecting company data on mobile devices is to require a passcode to use the device, sometimes you have to [reset a passcode](use-remote-lock-or-passcode-reset-in-microsoft-intune.md) or help an employee do so, either by removing the passcode or setting a temporary passcode remotely. You can also [lock a device remotely](use-remote-lock-or-passcode-reset-in-microsoft-intune.md) if it is lost or stolen.

## Add an additional layer of protection to Windows devices
[Multi-factor authentication (MFA)](protect-windows-devices-with-multi-factor-authentication.md) is a more secure way of authenticating the users of Windows and Windows Phone devices on the network.  With MFA, users need to confirm their identity beyond username and password, through a phone call, or text message.

## Control Microsoft Passport settings on Windows devices
Intune lets you integrate with [Microsoft Passport for Work](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md) which is an alternative sign-in method for Windows 10 and later that uses Active Directory, or an Azure Active Directory account to replace a password, smart card, or virtual smart card.

## Bypass Activation Lock on iOS devices
When company-owned iOS devices are protected by Activation Lock, and the device is lost or stolen, Activation Lock can keep the device and its data from being used by the wrong people. However, if you are able to recover the device, or if an employee returns the device but forgets to turn off Activation lock, you need to unlock the device. If you don't have the user's Apple ID and password to unlock it, you can use [Intune Activation Lock bypass](help-protect-ios-devices-with-activation-lock-bypass-for-microsoft-intune.md).

## Protect Windows PCs managed with the Intune client
Intune continues to support security policies for Windows PCs that you don't enroll, but manage with the Intune computer client software. To find out how these policies can help you secure your Windows PCs, see [Use policies to help protect Windows PCs that run the Intune client software](policies-to-protect-windows-pcs-in-microsoft-intune.md).
