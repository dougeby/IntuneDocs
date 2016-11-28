---
# required metadata

title: Collect device logs| Microsoft Intune
description: Learn how to collect logs from your managed devices.
keywords:
author: staciebarkerms.author: staciebarker
manager: angrobe
ms.date: 11/07/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: d97fb610-9d88-40e5-bb06-447eec533630

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: esmich
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Device logs

As part of your troubleshooting efforts you may want to collect logs from user devices. Instructions for collecting those logs are described here. Typically you may need access to the device, or request from the user that they collect the logs and send them to you.

### Android logs
Android logs are located in *<Android Device>\Phone\Android\data\com.microsoft.windowsintune.companyportal\files*. 

Sometimes the files don't appear, especially on newer Android devices. If this happens, have your end users open the Company Portal app for Android, and then go to **Settings**, choose **Copy Logs**, and then reboot their device. 

For more information about how your users can send you data logs, see the following articles:

- [Use Verbose Logging to help your IT admin fix device issues](/intune/enduser/use-verbose-logging-to-help-your-it-administrator-fix-device-issues-android) - Describes how users turn on Verbose Logging, which sends you all of their data logs automatically. By default, Verbose Logging is turned on.

- [Send Android diagnostic data logs to your IT admin using email](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-email-android) 

- [Send diagnostic data logs to your IT admin using a USB cable](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)

### iOS logs

Users can send you enrollment errors, as described in [Send iOS enrollment errors to your IT administrator](/intune/enduser/send-errors-to-your-it-admin-ios).

### Mac OS X logs

1. Open the **Console** app.
2. Under **FILES** choose **system.log**.
3. In the menu bar on the top, choose **File** > **Save a Copy As…** and save the file.

### Windows phone

In the Windows Phone Company Portal app, users choose the **…** to access the menu and then choose **Send Logs**. This option is available both before and after signing in to the Company Portal app.

### Windows

For the Windows Company Portal, the logs are located in *%localappdata%\Packages\Microsoft.CompanyPortal_8wekyb3d8bbwe\LocalState*.
