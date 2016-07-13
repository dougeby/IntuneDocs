---
# required metadata

title: Send diagnostic data logs to your IT administrator using email | Microsoft Intune
description:
keywords:
author: staciebarker
manager: jeffgilb
ms.date: 05/31/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 85c868e7-8d63-480c-9770-4e99614a5c94

# optional metadata

#ROBOTS: noindex,nofollow
#audience:
#ms.devlang:
ms.reviewer: arnab
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Send diagnostic data logs to your IT administrator using email

If you get an error on your Android device while you're working with your school or company apps or while you're in the Company Portal app, you can send diagnostic data logs  to help your IT admin figure out and fix the error. To include all of the details in the logs, which will make it easier for your IT admin to figure out the issue, turn on Verbose Logging. you can read more about [verbose logging](use-verbose-logging-to-help-your-it-administrator-fix-device-issues-android.md).

To turn on verbose logging:

1.  Open the Company Portal app.

2.  Tap **Menu** &gt;  **Settings**.

	> [!NOTE] 
	> **Menu** could be a software button or a hardware button, depending on the type of Android device you have.

3.  Under **Diagnostic Data**, tap **Send Data**.

	> [!NOTE]
	> **If you're using Android 6.0 or later devices only:**  When you tap **Send Data**, you see the message, **Allow Company Portal to access photos, media, and files on your device?**. 

	This message is misleading, because **Microsoft never accesses the photos, media, or files on your device!** Google controls the message text, so Microsoft cannot change it.  When you allow access, all you're doing is allowing your device to write data logs to the device's SD card, which enables you to move those logs by using a USB cable.

	If you deny access, the message will appear again the next time you tap  **Send Data**, but you can turn off future messages by tapping the **Never ask again** check box.  If you later decide to allow access, go to **Settings** &gt; **Apps** &gt; **Company Portal** &gt; **Permissions** &gt; **Storage**, and then turn on the permission.

4.  Follow the prompts to choose an email app to use for sending the logs to your IT admin. The app will create a pre-addressed email with all the logs attached.


### See also
[Using your Android device with Intune](using-your-android-device-with-intune.md)