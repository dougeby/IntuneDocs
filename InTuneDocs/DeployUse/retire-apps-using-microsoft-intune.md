---
title: Retire apps using Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 6fbf0805-1144-4e08-bafd-4f181d932bf2
author: robstackmsft
---
# Retire apps using Microsoft Intune

To retire an app, you simply uninstall it. When you deploy and manage apps with Intune, the process to uninstall the app is the same for both mobile devices and computers. The app must support being uninstalled for this procedure to succeed.

## Uninstall an app

1.  In the [Microsoft Intune administrator console](https://manage.microsoft.com), choose **Apps** &gt; **Apps**.

2.  Select the app you want to uninstall (which you have previously deployed), and then choose **Manage Deployment**.

3.  On the **Deployment Action** page, select **Uninstall** from the **Approval** column.

When the device or computer next checks for apps, the app will be uninstalled.

### See also
[Add and deploy apps](add-apps-for-mobile-devices-in-microsoft-intune.md)
