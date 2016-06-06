---
# required metadata

title: Choose how to enroll mobile devices | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 06/06/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: cac62b64-3f8b-47ae-aa66-970c7ba15466

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: damionw
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

## Do employees bring their own devices or are they provided by your organization?

  **Users-owned devices** - "BYOD” (Bring your own device) enrollment – Users can install the Intune Company Portal app on their device and then enroll it, gaining access to company resources like email, company apps, company data, and support.  
  > [!div class="button"]
  [BYOD Enrollment >](..deploy-use/get-ready-to-enroll-devices-in-microsoft-intune)

  **Company-owned devices** - Company-owned devices (COD) can be enrolled in a variety of ways, depending upon the needs of the organization and the types of devices being managed. Next question...

## Are your company-owned devices shared or do they have individual users?

**Shared company-owned devices** - These devices don’t have a single user and usually aren’t configured to access email. Examples include kiosk devices or task-oriented devices users draw from a pool as needed and then return. Recommended enrollment methods depend upon the devices' platform.

  - **Windows and Android devices** - A *device enrollment manager* is an Intune account that can be used to enroll many shared devices using the Company Portal app.
  > [!div class="button"]
  [Device enrollment manager >](../deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

  - **iOS devices** - Shared iOS devices can be managed in three ways.  **How will you enroll your shared iOS devices?**

    - **Apple’s Device Enrollment Program (DEP)** - iOS devices purchased or managed with DEP can be targeted with an enrollment profile. When users power on their devices for the first time, the device downloads the DEP profile and enrolls with the profile DEP
    > [!div class="button"]
    [DEP Enrollment >](../deploy-use/ios-device-enrollment-program-in-microsoft-intune)

    - **Apple Configurator on a Mac** - Apple Configurator is an Apple application that runs on a Mac PC. You can connect your iOS devices to the Mac with a USB cable to install an enrollment profile on the device. If you can factory reset devices to enroll them use Setup Assistant enrollment. If you don't want to factory reset devices, use Direct enrollment.

    > [!div class="button"]
    [Setup Assistant enrollment >](../deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) or [Direct enrollment >](../deploy-use/ios-direct-enrollment-in-microsoft-intune)

    - **None of the above** - If you cannot or do not want to use Apple's DEP or Apple Configurator enrollment methods, use Intune's device enrollment manager.
    > [!div class="button"]
    [DEM enrollment >](../deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).

**Individual Users** - Company-owned devices that are issued to individual users need to be tracked as company assets while allowing users to access email and data as personal devices. Recommended enrollment methods depend upon the devices' platform.

  - **Windows and Android devices** - By importing the international mobile equipment identity (IMEI) numbers of company-owned devices you can tag them as company-owned devices in Intune. Users can then enroll their devices as a personal devices by installing the Company Portal to access company resources such as email, apps, and data.
  > [!div class="button"]
  [Tag with IMEI >](../deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  - **iOS devices** - Shared iOS devices can be managed in three ways.  **How will you enroll your shared iOS devices?**

    - **Apple’s Device Enrollment Program (DEP)** - iOS devices purchased or managed with DEP can be targeted with an enrollment profile. When users power on their devices for the first time, the device downloads the DEP profile and is enrolled according to the profile.
    > [!div class="button"]
    [DEP Enrollment](../deploy-use/ios-device-enrollment-program-in-microsoft-intune).

    - **Apple Configurator on a Mac** - Apple Configurator is an Apple application that runs on a Mac PC. You can connect your iOS devices to the Mac with a USB cable to install an enrollment profile on the device. If you can factory reset devices to enroll them use Setup Assistant enrollment.

    If you don't want to factory reset devices, use Direct enrollment.
    If you can factory reset devices to enroll them, use Setup Assistant enrollment.
    > [!div class="button"][iOS Setup Assistant enrollment](../deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune)
    > [!div class="button"][iOS direct enrollment](../deploy-use/ios-direct-enrollment-in-microsoft-intune).

    - **None of the above** - If you cannot or do not want to use Apple's DEP or Apple Configurator enrollment methods, by importing the international mobile equipment identity (IMEI) numbers of company-owned devices you can tag them as company-owned devices in Intune. Users can then enroll their devices as a personal devices by installing the Company Portal to access company resources such as email, apps, and data. > [!div class="button"][Tag devices with IMEI numbers](../deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)
