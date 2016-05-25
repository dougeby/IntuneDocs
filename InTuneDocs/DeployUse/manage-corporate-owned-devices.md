---
# required metadata

title: Manage corporate-owned devices | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 2b60bbff-25e6-489b-9621-c71b4275fa06

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Enroll corporate-owned devices with Microsoft Intune
Organization or corporate-owned devices (COD) can be brought into management by Intune in a variety of ways depending upon the device, how it was purchased, and the needs of the organization.

## Corporate-owned iOS devices
These enrollment methods are good for "Choose your own device" (CYOD) scenarios where the organization purchases the devices for users, but wants to retain management of the device. If your organization has purchased iOS devices, you can pre-configure enrollment so that the device is managed from the first time its user turns it on. Intune supports enrollment via [Apple's Device Enrollment Program (DEP)](ios-device-enrollment-program-in-microsoft-intune.md) or using the Apple Configurator tool running on a Mac computer for [direct](ios-direct-enrollment-in-microsoft-intune.md) or [Setup Assistant](ios-setup-assistant-enrollment-in-microsoft-intune.md) enrollment.

[Enroll corporate-owned iOS devices](enroll-corporate-owned-ios-devices-in-microsoft-intune.md)

## Device enrollment manager
Organizations can use Intune to manage large numbers of mobile devices with a single user account called a device enrollment manager account. After creating a device enrollment manager account, that account can be used by a manager to enroll more than the standard five devices allowed by default to normal users. Enrolling devices with a device enrollment manager only works for devices that aren't used by a specific user. These devices are good for point-of-sale or utility apps, for example, but bad for users who need access to email or company resources.

[Enroll corporate-owned devices with the device enrollment manager](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)

## International mobile equipment identity (IMEI)
Unique international mobile equipment identity (IMEI) numbers are a common device property for many mobile device manufacturers. Intune administrators can import IMEI numbers for devices the company owns. When the device becomes managed by Intune, it can be tagged as a corporate-owned device and targeted with appropriate policy.

[Specify corporate-owned devices with international mobile equipment identity (IMEI) numbers](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

## Overview of corporate owned device enrollment methods

The following table shows enrollment methods for corporate-owned device enrollment methods with their benefits.

**iOS Enrollment Methods**

| **Method** |	**[Wipe](#Wipe)** |	**[User](#User)**	|	**[Locked](#Locked)** |
|:---:|:---:|:---:|:---:|
|**[BYOD](#BYOD)** | No|	Yes |	No |
|**[DEM](#DEM)**|	No |No |No	|
|**[DEP](#DEP)**|	Yes |	Opt |	Opt|
|**[USB-SA](#USB-SA)**|	Yes |	Opt |	No|
|**[USB-Direct](#USB-Direct)**|	No |	No	| No|

**Windows and Android Enrollment Methods**

| **Method** |	**[Wipe](#Wipe)** |	**[User](#User)**	|	**[Locked](#Locked)** |
|:---:|:---:|:---:|:---:|
|**[BYOD](#BYOD)** | No|	Yes |	No |
|**[DEM](#DEM)**|	No |No |No	|

**Enrollment methods for corporate-owned devices**

### BYOD
“Bring Your Own Device.” Users install the Company Portal app and enroll their device. Enrolling a device with the Company Portal will work place join the device. Enrolling iOS devices with the Company Portal requires an Apple ID. BYOD does not require additional configuration for corporate-owned devises. See steps to [set up device management](get-ready-to-enroll-devices-in-microsoft-intune#set-up-device-management.md). ([Back to the table](#overview-of corporate-owned-device-enrollment-methods))

### DEM
Device enrollment manager. Admin creates DEM accounts. Managers can then install the Company Portal and enroll many user-less devices. Learn more about [DEM](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md). ([Back to the table](#overview-of corporate-owned-device-enrollment-methods))

### DEP
Apple Device Enrollment Program. Admin creates and deploys policy “over the air” to iOS devices purchased and managed with DEP. The device is enrolled when the user runs the iOS Setup Assistant. This method supports **iOS Supervised** mode which in turn enables:
  -	Locked enrollment
  -	Conditional access
  -	Jailbreak detection
  -	Mobile application management

Learn more about [DEP](ios-device-enrollment-program-in-microsoft-intune.md). ([Back to the table](#overview-of corporate-owned-device-enrollment-methods))

### USB-SA
USB-connected, Setup Assistant enrollment. The admin creates an Intune policy and exports it to Apple Configurator. USB-connected devices are prepared with Intune policy. The admin must enroll each device by hand. Users receive their devices and run Setup Assistant, enrolling their device. This method supports **iOS Supervised** mode which in turn enables:
  -	Locked enrollment
  -	Conditional access
  -	Jailbreak detection
  -	Mobile application management

Learn more about [Setup Assistant enrollment with Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md). ([Back to the table](#overview-of corporate-owned-device-enrollment-methods))

### USB-Direct
Direct enrollment. The admin creates an Intune policy and exports it to Apple Configurator. USB-connected devices are enrolled directly without requiring a factory reset. The admin must enroll each device by hand. Devices are managed as user-less devices. They are not locked or supervised and cannot support conditional access, jailbreak detection, mobile application management. Learn more about [direct enrollment with Apple Configurator](ios-direct-enrollment-in-microsoft-intune.md). ([Back to the table](#overview-of corporate-owned-device-enrollment-methods))

**Behavior for corporate-owned mobile devices**

### Wipe
Specifies whether enrolling the device requires that the device be factory reset, removing all data from the device and returning it to its original state.
([Back to the table](#overview-of corporate-owned-device-enrollment-methods))

### User
Specifies whether the enrollment method supports “User Affinity” which connects a device with a specific user. “Opt” devices can be enrolled with or without user affinity. User affinity is required to support the following:
  - Mobile application management (MAM) apps
  -	Conditional access to email and company data
  -	Company Portal app

([Back to the table](#overview-of corporate-owned-device-enrollment-methods))

### Lock
Specifies whether the device can be locked to prevent the user from removing the Intune policy, effectively removing the device from management. For iOS devices, locking the device requires that it be in Supervised mode.
([Back to the table](#overview-of corporate-owned-device-enrollment-methods)) ([Back to the table](#overview-of corporate-owned-device-enrollment-methods))
