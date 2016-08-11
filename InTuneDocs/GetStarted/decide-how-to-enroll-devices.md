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
ms.assetid: 178df739-d3b9-43cb-8440-c5c110b1276b

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

Mobile device enrollment is the process that brings smartphones, tablets and PCs into management by Microsoft Intune. As an administrator, you need to determine how best to enroll devices based on the following:

 - 	Ownership (personal v. company-owned)
 -	Usage (shared v. personal)
 - 	Platform (iOS, Android, Windows Phone, Windows PC, Mac PC)

Your answers to the following questions will help determine the best enrollment method for the devices you manage.

## **Do employees bring their own devices or are devices provided by your organization?**

  - **Users-owned devices** - "BYOD” (Bring your own device) enrollment – Users can install the Intune Company Portal app on their device and then enroll it, gaining access to company resources like email, company apps, company data, and support.  

  - **Company-owned devices** - Company-owned devices (COD) can be enrolled in a variety of ways, depending upon the needs of the organization and the types of devices being managed.

> [!div class="button"]
[BYOD Enrollment >](#what-byod-devices-can-your-users-enroll)   [COD Enrollment >](#are-your-company-owned-devices-shared-or-do-they-have-dedicated-users)

## **What BYOD devices can your users enroll?**

> [!div class="button"]
[Android](/intune/deploy-use/set-up-android-management-with-microsoft-intune) [iOS and Mac](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) [Windows 10 Mobile & Window Phone](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune) [Windows PCs](/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune)

## **Are your company-owned devices shared or do they have dedicated users?**

- **Shared company-owned devices** - These devices don’t have a single user and usually aren’t configured to access email. Examples include kiosk devices or task-oriented devices users draw from a pool as needed and then return. Recommended enrollment methods depend upon the devices' platform.

- **Dedicated Users** - Company-owned devices that are issued to individual users need to be tracked as company assets while allowing users to access email and data as personal devices. Recommended enrollment methods depend upon the devices' platform.

> [!div class="button"]
[Shared >](#what-operating-system-are-your-shared-devices-running)   [Dedicated >](#how-will-you-manage-dedicated-ios-devices)


## **What operating system are your shared devices running?**

  > [!div class="button"]
  [Windows >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [Android >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [iOS >](#how-will-you-manage-shared-ios-devices)

## **How will you manage shared iOS devices?**

- **Apple’s Device Enrollment Program (DEP)** - iOS devices purchased or managed with DEP can be targeted with an enrollment profile. When users power on their devices for the first time, the device downloads the DEP profile and enrolls with the profile DEP

- **Apple Configurator on a Mac** - Apple Configurator is an Apple application that runs on a Mac PC. You can connect your iOS devices to the Mac with a USB cable to install an enrollment profile on the device. If you can factory reset devices to enroll them use Setup Assistant enrollment. If you don't want to factory reset devices, use Direct enrollment.

- **Device Enrollment Manager** - Intune's device enrollment manager (DEM) allows a manager or administrator to enroll many mobile devices with a single user account. These devices cannot have user affinity (i.e. dedicated users) and must enroll by installing and signing in to the Company Portal app.

  > [!div class="button"]
  [iOS DEP Enrollment >](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [iOS Direct enrollment >](/intune/deploy-use/ios-direct-enrollment-in-microsoft-intune)  [DEM enrollment >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).

## **How will you manage dedicated iOS devices?**

You can enroll corporate-owned devices with dedicated users in the following ways:

- **Apple’s Device Enrollment Program (DEP)** - iOS devices purchased or managed with DEP can be targeted with an enrollment profile. When users power on their devices for the first time, the device downloads the DEP profile and enrolls with Intune.

- **Apple Configurator on a Mac** - Apple Configurator is an Apple application that runs on a Mac PC. You can connect your iOS devices to the Mac with a USB cable to install an enrollment profile on the device. If you can factory reset devices to enroll them use Setup Assistant enrollment.

- **Tag with IMEI number** - By importing the international mobile equipment identity (IMEI) numbers of company-owned devices you can tag them as company-owned devices in Intune. Users can then enroll their devices as a personal devices by installing the Company Portal to access company resources such as email, apps, and data.

  > [!div class="button"]
  [Tag with IMEI >](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers) [iOS DEP](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [iOS Setup Assistant](/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [Tag with IMEI](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)
