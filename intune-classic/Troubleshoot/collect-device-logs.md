---
# required metadata

title: Collect device logs
description: Learn how to collect logs from your managed devices.
keywords:
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 02/07/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: d97fb610-9d88-40e5-bb06-447eec533630ROBOTS: NOINDEX,NOFOLLOW

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: esmich
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Device logs

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

As part of your troubleshooting efforts you might want to collect logs from user devices. Instructions for collecting those logs are described here. Typically you need to access to the device to get these logs or request from the user that they collect the logs and send them to you.

### Android logs
Android logs are located in *<Android Device>\Phone\Android\data\com.microsoft.windowsintune.companyportal\files*.

Sometimes the files don't appear, especially on newer Android devices. If this happens, have your users open the Company Portal app for Android. Then they should choose **Settings**>**Copy Logs** and reboot their device.

For more information about how your users can send you data logs, see the following articles:

- [Use Verbose Logging to help your IT admin fix device issues](/intune-user-help/use-verbose-logging-to-help-your-it-administrator-fix-device-issues-android): Describes how users turn on Verbose Logging, which sends you all of their data logs automatically. By default, Verbose Logging is turned on.

- [Send Android diagnostic data logs to your IT admin using email](/intune-user-help/send-logs-to-your-it-admin-by-email-android)

- [Send diagnostic data logs to your IT admin using a USB cable](/intune-user-help/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)

### iOS logs

Users can send you enrollment errors, as described in [Send iOS enrollment errors to your IT administrator](/intune-user-help/send-errors-to-your-it-admin-ios).

Users can send device logs, as described in [Send iOS Device Logs](/intune-user-help/send-logs-to-microsoft-ios).

### Mac OS X logs

1. Open the **Console** app.
2. Under **FILES**, choose **system.log**.
3. On the menu bar on the top, choose **File** > **Save a Copy As…**. Then save the file.

### Windows Phone

In the Windows Phone Company Portal app, users choose the three dots (**…**) to access the menu, and then choose **Send Logs**. This option is available both before and after signing in to the Company Portal app.

### Windows

For the Windows Company Portal, the logs are located in *%localappdata%\Packages\Microsoft.CompanyPortal_8wekyb3d8bbwe\LocalState*.
