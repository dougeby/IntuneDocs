---
# required metadata

title: Manage corporate-owned devices 
description: Enroll corporate-owned devices in a variety of ways, based on the type of device, how it was purchased, and the needs of the organization.
keywords:
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 01/29/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 2b60bbff-25e6-489b-9621-c71b4275fa06
ROBOTS: NOINDEX,NOFOLLOW

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: dagerrit
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Enroll corporate-owned devices by using Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

You can enroll organization-owned or corporate-owned devices to manage with Intune in a variety of ways, depending on the type of device, how the device was purchased, and the needs of the organization. You also can install the Company Portal app to enroll and manage corporate-owned devices, like in a "bring your own device" (BYOD) scenario.

By default, devices for all platforms are allowed to enroll in Intune. To block devices from enrolling, sign to the [Microsoft Intune admin portal](https://manage.microsoft.com) with your admin credentials. Choose **Admin** > **Mobile Device Management** > **Enrollment Rules** and then clear the applicable check boxes for the platforms that you want to block.

## Enroll corporate-owned iOS devices

Corporate-owned device enrollment methods are a good choice for "choose your own device" (CYOD) scenarios. In a CYOD environment, the organization pays for a device that the user selects, and the organization manages the device.

If you offer users iOS devices to choose from, you can preconfigure enrollment so that the device is managed with Intune from the first time the user turns it on. Intune supports enrollment via the [Apple Device Enrollment Program (DEP)](ios-device-enrollment-program-in-microsoft-intune.md), or by using the Apple Configurator tool on a Mac computer for [direct](ios-direct-enrollment-in-microsoft-intune.md) or [Setup Assistant](ios-setup-assistant-enrollment-in-microsoft-intune.md) enrollment.

Learn how to [enroll corporate-owned iOS devices](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

## Create a device enrollment manager account

You can create a single-user device enrollment manager (DEM) account in Intune to manage a large number of mobile devices for your organization. After you create a DEM account, a designated account manager can enroll more than the 15 devices that a standard user can enroll.

You can use a DEM account to enroll only devices that aren't used by a single, specific user. Those types of devices are good for point-of-sale or utility apps, for example, but not for users who need to access email or company resources.

Learn how to [enroll corporate-owned devices by using a DEM account](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md).

## Enroll corporate-owned Windows 10 Enterprise devices

If you use Azure Active Directory Premium or Microsoft Enterprise Mobility Suite in your organization, you can [enroll Windows 10 Enterprise devices](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview). When a user adds a work or school account on a device, the device is automatically tagged as "corporate-owned."

## Import IMEI numbers

Many mobile device manufacturers use a unique number called an International Mobile Equipment Identity (IMEI) on their devices. You can import IMEI numbers for devices that your organization owns. When the device becomes managed by Intune, it's tagged as a corporate-owned device.

Learn how to [tag corporate-owned devices by using IMEI numbers](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md).

## Identify a device as corporate-owned

Intune recognizes a device as "corporate" when any of the following conditions are true:

 - The device was [enrolled by using a DEM account](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) (all platforms).
 - The device was enrolled by using the [Apple DEP](ios-device-enrollment-program-in-microsoft-intune.md) or [Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md) (iOS only).
 - The device manufacturer [predeclared the device by using IMEI numbers](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md) (all platforms with IMEI numbers).
 - The device is registered in [Azure Active Directory or Enterprise Mobility Suite as a Windows 10 Enterprise device](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview) (Windows 10 only).

When a device is tagged as corporate, you see **Corporate** in the **Ownership** column for that device record in the administrator console. 
