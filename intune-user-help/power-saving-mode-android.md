---
# required metadata

title: An existing company email account was found | Microsoft Docs
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

# Power saving mode may cause some issues

> [!IMPORTANT]
> This issue is documented here because we have been receiving an increased number of customer reports about it. If you continue to experience this issue after you have taken these steps, please reach out to [your IT admin](https://portal.manage.microsoft.com) for additional help.

Enrolling your device in Intune lets you get access to company resources. One of the most common resources is email access. An issue that we have seen with accessing email on Android devices has been when battery optimization is turned on. Battery optimization saves power whenever your phone or tablet battery gets low. It may turn on automatically to try and help your device stay turned on for as long as possible. Battery optimization is partially able to do this because it tries to stop automatic email downloads.  

The Microsoft Intune team is actively working on a solution for this issue. If you are encountering it now, you should remove the Company Portal and Outlook apps from the list of apps that are affected when battery saver is turned on. Since there are many Android devices made by a variety of manufacturers, you may need to do this only once (in your system settings) or twice (in system settings and in separate, manufacturer-specific settings).

For example, on a Google Pixel device, you would follow these steps to remove these apps from battery optimization:

1. Open **Settings**.
2. Tap **Battery** > **More** > **Battery optimization**.
3. Tap the down arrow, then **Not optimized**.
4. Select the Company Portal and Outlook apps, and turn off battery optimization.

Still need help? Contact your IT admin. For their contact information, check the [Company Portal website](http://portal.manage.microsoft.com).
