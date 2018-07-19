
---
# required metadata

title: Protect devices with Microsoft Intune 
titleSuffix: Microsoft Intune
description: Learn about some of the ways that Intune can help you protect your devices against unauthorized access and other threats.
keywords:
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/19/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid:

---

# Protect devices with Microsoft Intune

Microsoft Intune helps you protect the devices you manage, and the data stored on those devices. Read this topic to learn the basics of these capabilities and to find out how to learn more.

## General ways to protect all devices

### Device configuration
Intune [configuration policies](device-profiles.md) help you protect and configure devices by controlling a multitude of settings and features. For example:
- You can restrict use of hardware features on the device such as the camera, or Bluetooth.
- You can configure compliant and noncompliant apps. You will be alerted if a noncompliant app is installed (and some platforms can actually block the install).

### Reset passcodes when users are locked out of their devices
Since the first step in protecting company data on mobile devices is to require a passcode to use the device, sometimes you have to [reset a passcode](device-passcode-reset.md) or help an employee do so, either by removing the passcode or setting a temporary passcode remotely. You can also [lock a device remotely](device-remote-lock.md) if it is lost or stolen.

### Retire devices and remove data
When a device needs to be [removed from Intune management](devices-wipe.md) (for example, a user leaves, or the device is lost or stolen), it's likely that you will want to remove data from that device. Intune provides a range of methods to ensure your company data remains secure.

### Require devices to be compliant
Intune features [device compliance policies](device-compliance-get-started.md) that let you evaluate (and in some cases remediate) devices that are not compliant with rules that you specify. For example, you can report about iOS devices that are jailbroken, whether devices are encrypted, or whether Windows 10 devices are reported as healthy by the Health Attestation Service.

### Protect apps and the data they use
Intune gives you a range of features to help you protect apps and their data. For example, mobile application management (MAM) policies can prevent data from being backed up from a protected app, restrict copy and paste to other apps, require a PIN to access an app, and more. For more details about protecting apps, see [Protect apps and data with Microsoft Intune](app-protection-policy.md)

### Add an additional layer of protection to devices
[Multi-factor authentication (MFA)](multi-factor-authentication.md) is a more secure way of authenticating the users of devices on the network.  With MFA, users need to confirm their identity beyond user name and password, through a phone call, or text message.

## Further capabilities for Windows devices

### Control Windows Hello for Business settings on Windows devices
Intune lets you integrate with [Windows Hello for Business](windows-hello.md) which is an alternative sign-in method for Windows 10 and later that uses Active Directory, or an Azure Active Directory account to replace a password, smart card, or virtual smart card.

## Further capabilities for iOS devices

### Bypass Activation Lock on iOS devices
Activation Lock is a feature that help protect users' devices by requiring their Apple ID and password to be entered before anyone can erase, or reactivate the device. However, this can lead to problems, for example if the user leaves the company without removing the lock. [iOS Activation Lock bypass]( device-activation-lock-bypass.md) can help by removing the lock from supervised iOS devices allowing you to reallocate, or erase them.

## Next steps

Learn about [mobile threat defense](mobile-threat-defense.md)


