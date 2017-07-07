---
# required metadata

title: Power optimization is preventing email access | Microsoft Docs
description: Find out how to turn off power optimization for Android to make sure you get your email.
keywords:
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 07/07/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: ad713f18-40a9-421f-aa2b-f8c21028d57c
searchScope:
 - User help

# optional metadata

ROBOTS:   
#audience:
#ms.devlang:
ms.reviewer: maxles
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-enduser

---

# Outlook won't sync managed email when battery optimization for Android is turned on

> [!IMPORTANT]
> This issue is documented here because we have been receiving an increased number of customer reports about it. If you continue to experience this issue after you have taken these steps, contact [your IT admin](https://portal.manage.microsoft.com) for additional help.

Enrolling your device in Intune lets you get access to company resources. One of the most common resources is email access. An issue that we have seen with accessing email on Android devices has been when battery optimization is turned on. Battery optimization may turn on automatically to try to help your device stay powered on for as long as possible. Battery optimization is partially able to help you this way because it tries to stop automatic email downloads.  

The Microsoft Intune team is actively working on a solution for this issue. For now, you must remove the Company Portal and Outlook from the list of apps that are affected by power optimization.

There are many Android devices that are made by many manufacturers. We cannot document the exact steps you need to take for every device. You may need to take this action in just your system settings or also in certain manufacturer-specific settings. We have provided some common examples of how you can resolve this issue on Android devices. 

## "Vanilla" Android devices

For example, on a Google Pixel device with Android 7.0 or higher, you would follow these steps to remove these apps from battery optimization:

1. Open **Settings**.
2. Tap **Battery** > **More** > **Battery optimization**.
3. Tap the down arrow, then **Not optimized**.
4. Select the Company Portal and Outlook apps, and turn off battery optimization.

## Samsung devices

For other types of Android devices, such as Samsung devices with Android 7.0 or higher, you would have to follow different steps to remove the Outlook and Company Portal apps from battery optimization. 

1. Open **Settings**. 
2. Tap **Menu (…)** > **Special access** > **Optimize battery usage**. 
3. Select **All apps** from the dropdown. 
4. Turn **Off** the toggle next to the Company Portal and Outlook apps to turn off battery optimization.

In addition, if you are using a Samsung device that has a lower version of Android, you would need to follow these steps to remove these apps from battery optimization.

1. Open **Settings**. 
2. Tap **Device maintenance** > **Battery** > **Unmonitored apps**. 
3. Tap **Add apps**. 
4. Select the Company Portal and Outlook apps, and tap **Done**. 

## OnePlus devices

On a OnePlus 5 device with Android 7.1.1, you would follow these steps to remove these apps from battery optimization: 

1. Open **Settings**. 
2. Tap **Battery** > **Battery optimization**. 
3. Select the Company Portal and Outlook apps, select **Don’t optimize**, and tap **Done**.

Still need help? Contact your IT admin. For their contact information, check the [Company Portal website](http://portal.manage.microsoft.com).
