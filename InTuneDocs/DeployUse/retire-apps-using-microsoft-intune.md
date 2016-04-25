---
# required metadata

title: Retire apps | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 6fbf0805-1144-4e08-bafd-4f181d932bf2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Retire apps using Microsoft Intune

To retire an app, you simply uninstall it. When you deploy and manage apps with Intune, the process to uninstall the app is the same for both mobile devices and Windows PCs. The app must support being uninstalled for this procedure to succeed.

## Uninstall an app

1.  In the [Microsoft Intune administrator console](https://manage.microsoft.com), choose **Apps** &gt; **Apps**.

2.  Select the app you want to uninstall (which you have previously deployed), and then choose **Manage Deployment**.

3.  On the **Deployment Action** page, select **Uninstall** from the **Approval** column.

When the device or computer next checks for apps, the app will be uninstalled.

### See also
[Add apps in Microsoft Intune](add-apps.md)
