---
# required metadata

title: Choose iOS device enrollment method for Intune | Intune Azure preview | Microsoft Docs
description: "Intune Azure preview: Learn how to set up enrollment of iOS devices in Microsoft Intune."
keywords:
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 12/13/2016
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
#ms.custom:

---

# Choose iOS device enrollment method for Intune Azure preview

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

This topic describes the methods you can use to enroll iOS devices and the prerequisites for enrollment.

Use the following information to decide which method to use for enrolling iOS devices. All of the following methods, except BYOD, are for enrolling corporate-owned devices.

## User-owned iOS devices (BYOD)

If users want to enroll their personal, BYOD (bring your own device) devices, the only available enrollment method is for users to download the Company Portal app for iOS from the App Store, and follow the enrollment instructions in the app. Once enrolled, users can connect to the company network, join the domain or Azure Active Directory, and get access to corporate resources.

## Apple Configurator

You can enroll iOS devices by exporting a Corporate Enrollment profile and then connecting those mobile devices to a Mac that is running Apple Configurator. Apple Configurator supports two forms of enrollment:

- **Setup Assistant enrollment**: Resets the device to factory settings and prepares it for setup by the device's new user. This method requires the admin to connect the iOS device through USB to a Mac computer running [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) to preconfigure the enrollment. Devices are then delivered to their users, who run the Setup Assistant process. This process configures the device with users' work or school credentials and completes the enrollment process. For more information, see [Enroll iOS devices with Apple Configurator and Setup Assistant](enroll-ios-devices-with-apple-configurator-and-setup-assistant.md).

- **Direct enrollment**: Creates an [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)–compliant file for use during device preparation. The enrolled device isn’t factory reset, and it has no user affiliation. To enroll devices, the admin is required to connect the iOS device through USB to a Mac computer running Apple Configurator. For more information, see [Enroll iOS devices using Apple Configurator Direct Enrollment](enroll-ios-devices-with-apple-configurator-and-direct-enrollment.md).

## Use the Device Enrollment Program (DEP)

DEP deploys an enrollment profile “over the air” to devices that are purchased through DEP. When a user runs Setup Assistant on the device, the device is enrolled in Intune. Devices enrolled through DEP cannot be unenrolled by users. For more information, see [Enroll iOS devices using Device Enrollment Program](enroll-ios-devices-using-device-enrollment-program.md).

## Use the device enrollment manager (DEM)
Device enrollment manager is a type of user account that can enroll and manage up to 1,000 devices. You add existing users to the DEM account to give them these capabilities. Each device that the DEM user enrolls uses a single Intune license. For more information, see [Enroll devices using device enrollment manager](enroll-devices-using-device-enrollment-manager.md).
