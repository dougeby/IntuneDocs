---
title: Manage corporate-owned devices with Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid:
author: NathBarn
robots:
---
# Manage corporate-owned devices with Microsoft Intune
Organization or corporate-owned devices (COD) can be brought into management in a variety of ways depending upon the device and how it was purchased.

## Corporate-owned iOS devices
These enrollment methods are good for "Choose your own device" (CYOD) scenarios where the organization purchases the devices for users, but wants to retain management of the device. If your organization has purchased iOS devices, you can pre-configure enrollment so that the device is managed from the first time its user turns it on. Intune supports enrollment via [Apple's Device Enrollment Program (DEP)](ios-device-enrollment-program-in-microsoft-intune.md) or using the Apple Configurator tool running on a Mac computer for [direct](ios-direct-enrollment-in-microsoft-intune.md) or [Setup Assistant](ios-setup-assistant-enrollment-in-microsoft-intune.md) enrollment. 

[Enroll corporate-owned iOS devices](enroll-corporate-owned-ios-devices-in-microsoft-intune.md)

## Device enrollment manager
Organizations can use Intune to manage large numbers of mobile devices with a single user account called a device enrollment manager account. After creating a device enrollment manager account, that account can be used by a manager to enroll more than the standard five devices allowed by default to normal users. Enrolling devices with a device enrollment manager only works for devices that aren't used by a specific user. These devices are good for point-of-sale or utility apps, for example, but bad for users who need access to email or company resources.

[Enroll corporate-owned devices with the device enrollment manager](ios-device-enrollment-program.md)

## Specify corporate-owned devices with international mobile equipment identity (IMEI)
Unique international mobile equipment identity (IMEI) numbers are a common device property for many mobile device manufacturers. Intune administrators can import IMEI numbers for devices the company owns. When the device becomes managed by Intune, it can be tagged as a corporate-owned device and targeted with appropriate policy.

[Specify corporate-owned devices with international mobile equipment identity (IMEI) numbers](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md)
