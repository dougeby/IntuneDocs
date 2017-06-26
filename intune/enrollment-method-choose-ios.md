---
# required metadata

title: Choose how to enroll iOS devices in Intune
titleSuffix: "Intune on Azure"
description: Learn how to set up enrollment of iOS devices in Microsoft Intune."
keywords:
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e6c0a430-1851-4108-812a-87e0fc2623b5

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: damionw
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Choose how to enroll iOS and macOS devices

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

This topic describes the methods an IT admin can use to enable iOS device enrollment in Intune.

Use the following information to decide which method to use for enrolling iOS devices. All of the following methods, except BYOD, are for enrolling corporate-owned devices.

**Prerequisite:** An [Apple Push Notification service  certificate](apple-mdm-push-certificate-get.md) is required.

## User-owned iOS devices (BYOD)

If users want to enroll their personal, BYOD (bring your own device) devices, they can download the Company Portal app for iOS from the App Store, and follow the enrollment instructions in the app. Once enrolled, users can connect to the company network, join the domain or Azure Active Directory, and get access to corporate resources. To enable BYOD, the only reuirement is an [Apple Push Notification service  certificate](apple-mdm-push-certificate-get.md). You can also block enrollment of personally owned iOS devices. See [Set device type restrictions](enrollment-restrictions-set.md) for instructions.

## User-owned macOS devices (BYOD)

You can enable macOS device enrollment. To enable macOS enrollment, the only reuirement is an [Apple Push Notification service  certificate](apple-mdm-push-certificate-get.md). For more information, see [Enroll macOS devices](./macos-enroll.md)

## Enrollment program with Apple
Apple offers device purchasing programs that include device enrollment and management infrastructure. Device purchased through one of these programs can bulk-enrolled "over the air" by assigning device serial numbers to Intune management.

- **Device Enrollment Program (DEM)** - Apple's device enrollment program for organizations and enterprises. For more information, see [Enroll iOS devices using Device Enrollment Program](device-enrollment-program-enroll-ios.md).
- **Apple School Manager (ASM)** - Apple's device enrollment program for schools. For more information see [Enable iOS device enrollment with Apple School Manager](apple-school-manager-set-up-ios.md)

## Apple Configurator

You can enroll iOS devices by exporting a Corporate Enrollment profile and then connecting those mobile devices to a Mac that is running Apple Configurator. Apple Configurator supports two forms of enrollment:

- **Setup Assistant enrollment**: Resets the device to factory settings and prepares it for setup by the device's new user. This method requires the admin to connect the iOS device through USB to a Mac computer running Apple Configurator to preconfigure the enrollment. Devices are then delivered to their users, who run the Setup Assistant when the devices first starts. This process configures the device with users' work or school credentials and completes the enrollment process. For more information, see [Enroll iOS devices with Apple Configurator and Setup Assistant](apple-configurator-setup-assistant-enroll-ios.md).

- **Direct enrollment**: Creates an Apple Configurator–compliant file for use during device preparation. The enrolled device isn’t factory reset, and it has no user affiliation. To enroll devices, the admin is required to connect the iOS device through USB to a Mac computer running Apple Configurator. For more information, see [Enroll iOS devices using Apple Configurator Direct Enrollment](apple-configurator-direct-enroll-ios.md).

## Use the Device Enrollment Program (DEP)

DEP deploys an enrollment profile “over the air” to devices that are purchased through DEP. When a user runs Setup Assistant on the device when it first starts, the device is enrolled in Intune. For more information, see [Enroll iOS devices using Device Enrollment Program](device-enrollment-program-enroll-ios.md).

## Use the device enrollment manager (DEM)
Device enrollment manager is a generic user account that can enroll and manage up to 1,000 devices without. DEM-managed devices cannot have user affinity, so the device never has an owner. You give an Intune users DEM permissions to give them these capabilities. Each device that the DEM user enrolls uses an Intune license. For more information, see [Enroll devices using device enrollment manager](device-enrollment-manager-enroll.md).
