---
title: Overview of the device lifecycle | Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid:
author: robstackmsft
---
# Overview of the mobile device management (MDM) lifecycle

The Intune device lifecycle begins with initially enrolling a device and then moves through several steps concluding when the device is no longer required.

![The device lifecycle](./media/devicelifecycle_nobg.png "the Intune device lifecycle")

## Enroll
Today's mobile device management (MDM) strategies deal with variety of phones, tablets, and PCs (iOS, Android, Windows, and Mac OS X). If you need to be able to manage the device, which is commonly the case for corporate owned devices, the first step is to [set up device enrollment](enroll-devices-in-microsoft-intune.md). You can also manage Windows PCs either by enrolling them with Intune (MDM) or by [installing the Intune client software](manage-windows-pcs-with-microsoft-intune.md).

## Configure
Getting your devices enrolled is just the first step. To take advantage of all that Intune offers and to ensure your devices are secure and compliant with company standards, you can choose from a wide range of **policies** which let you configure almost every aspect of how managed devices operate. For example, should users have passwords on devices that have company data? You can require one. Do you have corporate Wifi? You can automatically configure it. Here are the types of configuration options available:

- [**Configuration policies**](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) - These policies let you configure how the features and capabilities of device you manage work. For example, you could require the use of a password on Windows Phone's, or disable the use of the camera on iPhones.
- [**Company resource access policies**](enable-access-to-company-resources-with-microsoft-intune.md) - To let your users access their work on their personal device can present you with challenges. For example, how do you ensure that all devices that need to access company email are configured correctly? How can you ensure that users can access the company network with a VPN connection without having to know the often complex settings required? Intune can help to reduce this burden by automatically configuring devices you manage to access common company resources.
- [**Windows PC management policies (with the Intune client software)**](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md) - While enrolling Windows PCs with Intune gives you the most device management capabilities, Intune continues to support managing Windows PCs with the Intune client software. If you need information about some of the tasks you can perform with PCs, start here.

## Protect
In the modern IT world, protecting devices from unauthorized access is one of the most important tasks you'll perform. In addition to the items in the **Configure** step of the device lifecycle, Intune provides further capabilities that help protect devices that you manage from unauthorized access, or malicious attacks:
- [**Multi-factor authentication**](protect-windows-devices-with-multi-factor-authentication.md) - Adding an extra layer of authentication to user logons can help make devices even more secure. Windows, Windows Phone, and Windows Mobile devices offer multi-factor authentication which requires a second level of authentication such as a phone call or text message before users can gain access.
- [**Microsoft Passport settings**](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md) - Microsoft Passport is an alternative sign-on method that lets users use a *gesture*, such as a fingerprint, or Windows Hello to sign on without needing a password.
- [**Policies to protect Windows PCs (with the Intune client software)**](policies-to-protect-windows-pcs-in-microsoft-intune.md) - When you manage Windows PCs using the Intune client software, policies are available that let you control settings for Endpoint Protection, software updates, and Windows Firewall on PCs you manage.

## Retire
When a device gets lost or stolen, needs to be replaced, or when users move to another position, it's usually time to [retire or wipe](help-protect-your-data-with-remote-wipe-remote-lock-or-passcode-reset-using-microsoft-intune.md) the device. There are a number of ways you can do this ranging from resetting the device, removing it from management, or wiping the corporate data on it.
