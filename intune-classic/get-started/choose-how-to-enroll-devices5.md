---
# required metadata

title: Choose how to enroll mobile devices 
description: Decide how to enroll mobile devices in Intune by answering a few simple questions
keywords:
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/27/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: ed9250aa-e894-4eac-92b8-5f1a3748e255
ROBOTS: NOINDEX,NOFOLLOW

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: dagerrit
#ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic EXPIERIMENT

---
# Choose how to enroll mobile devices

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Your answers to this series of questions will help determine the best enrollment method for the devices you manage.

## **How will you manage shared iOS devices?**

> [!div class="button"]
[iOS DEP Enrollment >](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune)
> [!div class="button"]
[iOS Direct enrollment >](/intune-classic/deploy-use/ios-direct-enrollment-in-microsoft-intune)
> [!div class="button"]
[DEM enrollment >](/intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

  - **Apple’s Device Enrollment Program (DEP)** - iOS devices purchased or managed with DEP can be targeted with an enrollment profile. When users power on their devices for the first time, the device downloads the DEP profile and enrolls with the profile DEP.

  - **Apple Configurator on a Mac** - Apple Configurator is an Apple application that runs on a Mac PC. You can connect your iOS devices to the Mac with a USB cable to install an enrollment profile on the device. If you can factory reset devices to enroll them use Setup Assistant enrollment. If you don't want to factory reset devices, use Direct enrollment.

  - **Device Enrollment Manager** - Intune's device enrollment manager (DEM) allows a manager or administrator to enroll many mobile devices with a single user account. These devices cannot have user affinity (i.e. dedicated users) and must enroll by installing and signing in to the Company Portal app.

> [!div class="button"]
[< Back](choose-how-to-enroll-devices3.md)
