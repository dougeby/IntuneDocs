---
# required metadata

title: Choose how to enroll iOS devices in Intune
titleSuffix: "Intune Azure preview"
description: "Intune Azure preview: Learn how to set up enrollment of iOS devices in Microsoft Intune."
keywords:
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 05/24/2017
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

# Choose how to enroll iOS devices

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

This topic describes the methods you can use to enroll iOS devices and the prerequisites for enrollment.

Use the following information to decide which method to use for enrolling iOS devices. All of the following methods, except BYOD, are for enrolling corporate-owned devices.

**Prerequisite:** An [Apple Push Notification service  certificate](apple-mdm-push-certificate-get.md) is required.

## User-owned iOS devices (BYOD)

If users want to enroll their personal, BYOD (bring your own device) devices, the only available enrollment method is for users to download the Company Portal app for iOS from the App Store, and follow the enrollment instructions in the app. Once enrolled, users can connect to the company network, join the domain or Azure Active Directory, and get access to corporate resources. You can block enrollment of personally owned iOS devices. See [Set device type restrictions](enrollment-restrictions-set.md#set-device-type-restrictions) for instructions.

## Enrollment program with Apple
Apple offers device purchasing programs that include device enrollment and management infrastructure. Device purchased through one of these programs can bulk-enrolled "over the air" by assigning device serial numbers to Intune management.

- **Device Enrollment Program (DEM)** - Apple's device enrollment program for organizations and enterprises. For more information, see [Enroll iOS devices using Device Enrollment Program](device-enrollment-program-enroll-ios.md).
- **Apple School Manager (ASM)** - Apple's device enrollment program for schools. For more information see [Enable iOS device enrollment with Apple School Manager](apple-school-manager-set-up-ios.md)

## Apple Configurator

You can enroll iOS devices by exporting a Corporate Enrollment profile and then connecting those mobile devices to a Mac that is running [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017). Apple Configurator supports two forms of enrollment:

- **Setup Assistant enrollment**: Resets the device to factory settings and prepares it for setup by the device's new user. This method requires the admin to connect the iOS device through USB to a Mac computer running Apple Configurator to preconfigure the enrollment. Devices are then delivered to their users, who run the Setup Assistant process. This process configures the device with users' work or school credentials and completes the enrollment process. For more information, see [Enroll iOS devices with Apple Configurator and Setup Assistant](apple-configurator-setup-assistant-enroll-ios.md).

- **Direct enrollment**: Creates an Apple Configurator–compliant file for use during device preparation. The enrolled device isn’t factory reset, and it has no user affiliation. To enroll devices, the admin is required to connect the iOS device through USB to a Mac computer running Apple Configurator. For more information, see [Enroll iOS devices using Apple Configurator Direct Enrollment](apple-configurator-direct-enroll-ios.md).

## Use the device enrollment manager (DEM)
Device enrollment manager is a type of user account that can enroll and manage up to 1,000 devices. You add existing users to the DEM account to give them these capabilities. Each device that the DEM user enrolls uses a single Intune license. For more information, see [Enroll devices using device enrollment manager](device-enrollment-manager-enroll.md).
