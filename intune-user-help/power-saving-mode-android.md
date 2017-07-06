---
# required metadata

title: Power optimization is preventing email access | Microsoft Docs
description:
keywords:
author: barlanmsftms.author: barlan
manager: angrobe
ms.date: 07/06/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: ad713f18-40a9-421f-aa2b-f8c21028d57csearchScope: - User help

# optional metadata

ROBOTS:   
#audience:
#ms.devlang:
ms.reviewer: maxles
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-enduser

---

# I can't get my email because of power optimization

> [!IMPORTANT]
> This issue is documented here because we have been receiving an increased number of customer reports about it. If you continue to experience this issue after you have taken these steps, contact [your IT admin](https://portal.manage.microsoft.com) for additional help.

Enrolling your device in Intune lets you get access to company resources. One of the most common resources is email access. An issue that we have seen with accessing email on Android devices has been when battery optimization is turned on. Battery optimization saves power whenever your phone or tablet battery gets low. It may turn on automatically to try to help your device stay turned on for as long as possible. Battery optimization is partially able to help you this way because it tries to stop automatic email downloads.  

The Microsoft Intune team is actively working on a solution for this issue. You should remove the Company Portal and Outlook apps from the list of apps that are affected when battery saver is turned on.

There are many Android devices that are made by many manufacturers. We cannot document the exact steps you need to take for every device. You may need to take this action in just your system settings or also in certain manufacturer-specific settings. For example, on a Google Pixel device with Android 7.0+, you would follow these steps to remove these apps from battery optimization:

1. Open **Settings**.
2. Tap **Battery** > **More** > **Battery optimization**.
3. Tap the down arrow, then **Not optimized**.
4. Select the Company Portal and Outlook apps, and turn off battery optimization.

Still need help? Contact your IT admin. For their contact information, check the [Company Portal website](http://portal.manage.microsoft.com).
