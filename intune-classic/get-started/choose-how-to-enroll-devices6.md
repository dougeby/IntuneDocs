---
# required metadata

title: Choose how to enroll mobile devices 
description: Decide how to enroll mobile devices in Intune by answering a few simple questions
keywords:
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/27/2017
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 40262e47-1ab4-437d-8ca5-c89b5022f91f
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

## **How will you manage dedicated, corporate-owned devices?**

  > [!div class="button"]
[iOS DEP >](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune)  
> [!div class="button"]
[iOS Setup Assistant >](/intune-classic/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune)
> [!div class="button"]
[Tag with IMEI >](/intune-classic/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  You can enroll corporate-owned devices with dedicated users in the following ways:

  - **Apple’s Device Enrollment Program (DEP)** - iOS devices purchased or managed with DEP can be targeted with an enrollment profile. When users power on their devices for the first time, the device downloads the DEP profile and enrolls with Intune.

  - **Apple Configurator on a Mac** - Apple Configurator is an Apple application that runs on a Mac PC. You can connect your iOS devices to the Mac with a USB cable to install an enrollment profile on the device. If you can factory reset devices to enroll them use Setup Assistant enrollment.

  - **Tag with IMEI number** - By importing the international mobile equipment identity (IMEI) numbers of company-owned devices you can tag them as company-owned devices in Intune. This is the only way to identify dedicated ("single-user") Windows and Android devices as corporate-owned. iOS devices that won't be enrolled with Apple's device enrollment program or Apple Configurator can also be tagged with an IMEI number. After predeclaring the device so it will be tagged as "corporate", you can distribute devices to users. Users can then enroll their devices as a dedicated devices by installing the Company Portal to access company resources such as email, apps, and data.

> [!div class="button"]
[< Back](choose-how-to-enroll-devices3.md)
