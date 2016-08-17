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
ms.assetid: 40262e47-1ab4-437d-8ca5-c89b5022f91f

# optional metadata

ROBOTS: NOINDEX,NOFOLLOW
#audience:
#ms.devlang:
ms.reviewer: dagerrit
#ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom: EXPIERIMENT

---
# Choose how to enroll mobile devices

Your answers to this series of questions will help determine the best enrollment method for the devices you manage.

## **How will you manage dedicated iOS devices?**

  > [!div class="button"]
[iOS DEP >](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune)   [iOS Setup Assistant >](/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [Tag with IMEI >](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  You can enroll corporate-owned devices with dedicated users in the following ways:

  - **Apple’s Device Enrollment Program (DEP)** - iOS devices purchased or managed with DEP can be targeted with an enrollment profile. When users power on their devices for the first time, the device downloads the DEP profile and enrolls with Intune.

  - **Apple Configurator on a Mac** - Apple Configurator is an Apple application that runs on a Mac PC. You can connect your iOS devices to the Mac with a USB cable to install an enrollment profile on the device. If you can factory reset devices to enroll them use Setup Assistant enrollment.

  - **Tag with IMEI number** - By importing the international mobile equipment identity (IMEI) numbers of company-owned devices you can tag them as company-owned devices in Intune. Users can then enroll their devices as a personal devices by installing the Company Portal to access company resources such as email, apps, and data.

  > [!div class="button"]
  [< Back](choose-how-to-enroll-devices3.md)
