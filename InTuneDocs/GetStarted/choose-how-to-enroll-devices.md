---
# required metadata

title: Choose how to enroll mobile devices | Microsoft Intune
description: Decide how to enroll mobile devices in Intune by answering a few simple questions
keywords:
author: NathBarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: cac62b64-3f8b-47ae-aa66-970c7ba15466

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: dagerrit
#ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Choose how to enroll mobile devices

Your answers to the following questions will help determine the best enrollment method for the devices you manage.

## **Do employees bring their own devices or are devices provided by your organization?**

  - **Users-owned devices** - "Bring your own device" (BYOD) enrollment
  - **Company-owned devices** - COD enrollment

> [!div class="button"]
[BYOD Enrollment >](#what-byod-devices-can-your-users-enroll)   
> [!div class="button"]
[COD Enrollment >](#are-your-company-owned-devices-shared-or-do-they-have-dedicated-users)

## **What BYOD devices can your users enroll?**

> [!div class="button"]
[Android](/intune/deploy-use/set-up-android-management-with-microsoft-intune) [iOS and Mac](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) [Windows 10 Mobile & Window Phone](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune) [Windows PCs](/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune)

## **Are your company-owned devices shared or do they have dedicated users?**

> [!div class="button"]
[Shared >](#what-operating-system-are-your-shared-devices-running)   [Dedicated >](#how-will-you-manage-dedicated-ios-devices)


## **What operating system are your shared devices running?**

  > [!div class="button"]
  [Windows >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [Android >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [iOS >](#how-will-you-manage-shared-ios-devices)

## **How will you manage shared iOS devices?**

  > [!div class="button"]
  [iOS DEP Enrollment >](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [iOS Direct enrollment >](/intune/deploy-use/ios-direct-enrollment-in-microsoft-intune)  [DEM enrollment >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

  - **Apple’s Device Enrollment Program (DEP)** - iOS devices purchased or managed with DEP can be targeted with an enrollment profile. When users power on their devices for the first time, the device downloads the DEP profile and enrolls with the profile DEP.

  - **Apple Configurator on a Mac** - Apple Configurator is an Apple application that runs on a Mac PC. You can connect your iOS devices to the Mac with a USB cable to install an enrollment profile on the device. If you can factory reset devices to enroll them use Setup Assistant enrollment. If you don't want to factory reset devices, use Direct enrollment.

  - **Device Enrollment Manager** - Intune's device enrollment manager (DEM) allows a manager or administrator to enroll many mobile devices with a single user account. These devices cannot have user affinity (i.e. dedicated users) and must enroll by installing and signing in to the Company Portal app.

## **How will you manage dedicated iOS devices?**

  > [!div class="button"]
  [Tag with IMEI >](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers) [iOS DEP](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [iOS Setup Assistant](/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [Tag with IMEI](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  You can enroll corporate-owned devices with dedicated users in the following ways:

  - **Apple’s Device Enrollment Program (DEP)** - iOS devices purchased or managed with DEP can be targeted with an enrollment profile. When users power on their devices for the first time, the device downloads the DEP profile and enrolls with Intune.

  - **Apple Configurator on a Mac** - Apple Configurator is an Apple application that runs on a Mac PC. You can connect your iOS devices to the Mac with a USB cable to install an enrollment profile on the device. If you can factory reset devices to enroll them use Setup Assistant enrollment.

  - **Tag with IMEI number** - By importing the international mobile equipment identity (IMEI) numbers of company-owned devices you can tag them as company-owned devices in Intune. Users can then enroll their devices as a personal devices by installing the Company Portal to access company resources such as email, apps, and data.
