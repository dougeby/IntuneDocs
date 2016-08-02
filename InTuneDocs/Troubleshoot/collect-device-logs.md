---
# required metadata

title: Collect device logs| Microsoft Intune
description:
keywords:
author: Nbigman
manager: angrobe
ms.date: 06/01/2016
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

### Android log location
Android logs are located in *<Android Device>\Phone\Android\data\com.microsoft.windowsintune.companyportal\files*. The user can also send you log files in email, as described in [Send Android diagnostic data logs to your IT administrator using email](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-email-android).

### iOS logs

The user can send you enrollment errors as described in [Send iOS enrollment errors to your IT administrator](/intune/enduser/send-errors-to-your-it-admin-ios)

### Mac OS X devices

1. Open the **Console** app.
2. Under **FILES** choose **system.log**.
3. In the menu bar on the top, choose **File** > **Save a Copy As…** and save the file.

### Windows phone

In the **Windows Phone Company Portal**, the user will have to choose the **…** to access the menu and then choose **Send Logs**. This option is available both before and after signing in to the portal.

### Windows

For the Windows Company Portal the logs are located in *%localappdata%\Packages\Microsoft.CompanyPortal_8wekyb3d8bbwe\LocalState*.
