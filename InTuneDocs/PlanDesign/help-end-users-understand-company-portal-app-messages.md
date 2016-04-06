---
# required metadata

title: Help end users understand Company Portal app messages | Microsoft Intune
description:
keywords:
author: staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 3df993aa-48c5-4799-b68d-c85fe4f7b02c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Help end users understand Company Portal app messages

The following information applies only on Android 6.0 and above devices. During device enrollment, end users see two messages, which appear during the enrollment process:

- Allow Company Portal to make and manage phone calls?
- Allow Company Portal to access photos, media, and files on your device?

See the following paragraphs for details about these messages and for information that you can share with your end users about them.

## Allow Company Portal to make and manage phone calls?

### Message text and where it appears
The message text is **Allow Company Portal to make and manage phone calls?**, and it appears when users sign in to the Company Portal app for the first time to start enrolling their device.

### What the message means
The message is prompting users to allow their device phone number and IMEI to be sent to the Intune service and to appear in the Admin console on the Hardware page. 

[!NOTE] **The Company Portal app never makes or manages phone calls!** The message text is controlled by Google and cannot be changed. 

To see the **Hardware** page, go to **Groups** > **All mobile devices** > **Device**s. Select the user's device, and go to **View Properties** > **Hardware**.

### What happens if users allow or deny access
If users allow access, the device's phone number and IMEI will appear on the Hardware page in the Admin console.

If users deny access, they can continue to use the Company Portal app and enroll their device, but the users's device phone number and IMEI will be blank on the Hardware page in the Admin console. The second time that users sign in to the Company Portal app after denying access, the message displays a **Never ask again** check box that users can select so that the message never shows again.

If users allow, but then later deny access, the message appears the next time users sign in to the Company Portal app after enrollment.</br></br>If users later decide to allow access, they can go to **Settings** > **Apps** > **Company Portal** > **Permissions** > **Phone**, and then turn on the permission.

### Where to send your users for more information
[Sign in to the Company Portal app](/Intune/EndUser/sign-in-to-the-company-portal-app-android)

## Allow Company Portal to access photos, media, and files on your device?

### Message text and where it appears
The message text is **Allow Company Portal to access photos, media, and files on your device?**, and it appears when users tap **Send Data** to send data logs to their IT admin.

### What the message means
The message is prompting users to allow their device to write data logs to the device's SD card and to enable those logs to be moved by using a USB cable.   

[!NOTE] **The Company Portal app never accesses users' photos, media, and files!** The message text is controlled by Google and cannot be changed.

### What happens if users allow or deny access
If users allow access, the logs will be copied to the SD card.

If users deny access, they can still send data logs, but the logs won't be copied to the device's SD card. 

The second time that users sign in to the Company Portal app after denying access, the message displays a **Never ask again** check box that users can select so that the message never shows again. If users allow, but then later deny access, the message appears the next time users try to send logs. If users later decide to allow access, they can go to **Settings** > **Apps** > **Company Portal** > **Permissions** > **Storage**, and then turn on the permission.

### Where to send your users for more information
[Send diagnostic data logs to your IT admin using email](/Intune/EndUser/send-diagnostic-data-logs-to-your-it-administrator-using-email-android)


### See also
[What to tell your end users about using Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)
