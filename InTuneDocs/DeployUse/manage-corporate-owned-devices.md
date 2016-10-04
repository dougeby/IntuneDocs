---
# required metadata

title: Manage corporate-owned devices | Microsoft Intune
description: Enroll corporate-owned devices in a variety of ways, based on the type of device, how it was purchased, and the needs of the organization.
keywords:
author: NathBarn
manager: angrobe
ms.date: 07/20/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 2b60bbff-25e6-489b-9621-c71b4275fa06

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: dagerrit
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Enroll corporate-owned devices with Microsoft Intune

You can enroll organization-owned or corporate-owned devices to manage by using Intune in a variety of ways, depending on the type of device, how the device was purchased, and the needs of the organization. You also can install the Company Portal app to enroll and manage corporate-owned devices, like in a "bring your own device" (BYOD) scenario.

## Corporate-owned iOS devices

Corporate-owned device enrollment methods are a good choice for "choose your own device" (CYOD) scenarios. In this scenario, the organization purchases the device for a user, but chooses to manage the device. If your organization purchases iOS devices, you can preconfigure enrollment so that the device is managed from the first time the user turns it on. Intune supports enrollment via [Apple's Device Enrollment Program (DEP)](ios-device-enrollment-program-in-microsoft-intune.md), or by using the Apple Configurator tool running on a Mac computer for [direct](ios-direct-enrollment-in-microsoft-intune.md) or [Setup Assistant](ios-setup-assistant-enrollment-in-microsoft-intune.md) enrollment.

Learn how to [enroll corporate-owned iOS devices](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

## Device enrollment manager

Your organization can use a single user account called a device enrollment manager account in Intune to manage a large number of mobile devices. After you create a device enrollment manager account, a manager can use that account to enroll more than the default five devices that a standard user can enroll. You can use a device enrollment manager to enroll only devices that aren't used by a specific user. These kinds of devices are good for point-of-sale or utility apps, for example. We do not recommend them for users who need access to email or company resources.

Learn how to [enroll corporate-owned devices by using the device enrollment manager](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md).

## Enroll corporate-owned Windows 10 desktops

If your organization uses Azure Active Directory Premium or Microsoft Enterprise Mobility Suite, you can [enroll Windows 10 Enterprise devices](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview). Devices are automatically tagged as "corporate-owned" when a user adds a work or school account.

## Identify a device as corporate-owned

In a list of devices, under **Ownership**, a corporate-owned device is listed as **Corporate**. A corporate-owned device has one of these characteristics:

 - The device was [enrolled with device enrollment manager (DEM)](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)
 - The device was enrolled with Apple's [device enrollment program (DEP)](ios-device-enrollment-program-in-microsoft-intune.md) or [Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md)
 - The device is [predeclared with IMEI numbers](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md)
 - The device has an [Azure Active Directory/Enterprise Mobility Suite registration of a Windows 10 device](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview)

### IMEI

Many mobile device manufacturers use a unique International Mobile Equipment Identity (IMEI) number on their devices. Intune administrators can import IMEI numbers for devices that the company owns. When the device becomes managed by Intune, it's tagged as a corporate-owned device.

Learn how to [specify corporate-owned devices with international mobile equipment identity (IMEI) numbers](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md).
