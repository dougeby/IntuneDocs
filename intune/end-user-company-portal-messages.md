---
# required metadata

title: Company Portal messages users may see on Android 
description: Describes Company Portal app messages that Intune end users might see.
keywords:
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 03/09/2017
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

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

> [!NOTE]
> The following information applies only on devices with Android 6.0+.

At different points in the enrollment process, end users will see two different messages that could be cause for concern.

- __Allow Company Portal to make and manage phone calls?__
- __Allow Company Portal to access photos, media, and files on your device?__

## Allow Company Portal to make and manage phone calls?

### Where it appears
The message **Allow Company Portal to make and manage phone calls?** appears when users tap **Enroll** in the Company Portal app while they are enrolling their device.

### What it means
By accepting this prompt, users allow their device's phone and IMEI numbers to be sent to the Intune service. These will appear on the admin console on the __Hardware__ page.

> [!NOTE]
> **The Company Portal app never makes or manages phone calls!** The message text is controlled by Google and cannot be changed.

To see the **Hardware** page, go to **Groups** > **All mobile devices** > **Devices**. Select the user's device, and go to **View Properties** > **Hardware**.

### What happens if users deny access
If users deny access, they can continue to use the Company Portal app and enroll their device. However, the device phone number and IMEI number will be blank on the __Hardware__ page in the admin console. The second time that users sign in to the Company Portal app after denying access, the message displays a **Never ask again** check box that users can select to stop the prompt.

If users allow, but then later deny access, the message appears the next time users sign in to the Company Portal app after enrollment.

If users later decide to allow access, they can go to **Settings** > **Apps** > **Company Portal** > **Permissions** > **Phone**, and turn it on.

### How to explain this to your users
Send your users to [Enroll your Android device in Intune](/intune-user-help/enroll-your-device-in-intune-android) for more information.

## Allow Company Portal to access your contacts?

### Where it appears
The message **Allow Company Portal to access your contacts?** appears when users tap **Enroll** in the Company Portal app while they are enrolling their device.

### What it means
By accepting this prompt, users allow Intune to create their work account and manage the Azure Active Directory identity that is registered for the user on that device.

> [!NOTE]
> **Microsoft never accesses your contacts!** The message text is controlled by Google and cannot be changed.

### What happens if users deny access
If users deny access, their device will not be enrolled in Intune and cannot be managed. The second time that users sign in to the Company Portal app after denying access, the message displays a **Never ask again** check box that users can select to stop the prompt.

If users allow, but then later deny access, the message appears the next time users sign in to the Company Portal app after enrollment.

If users later decide to allow access, they can go to **Settings** > **Apps** > **Company Portal** > **Permissions** > **Phone**, and turn it on.

### How to explain this to your users
Send your users to [Enroll your Android device in Intune](/intune-user-help/enroll-your-device-in-intune-android) for more information.

## Allow Company Portal to access photos, media, and files on your device?

### Where it appears
The message **Allow Company Portal to access photos, media, and files on your device?** appears when users tap **Send Data** to send logs to their IT admin.

### What it means
By accepting this prompt, users allow their device to write data logs to the device's SD card and enable those logs to be moved using a USB cable.   

> [!NOTE]
> **The Company Portal app never accesses users' photos, media, and files!** The message text is controlled by Google and cannot be changed.

### What happens if users deny access
If users deny access, they can still send data logs via email, but the logs won't be copied to the device's SD card.

The second time that users sign in to the Company Portal app after denying access, the message displays a **Never ask again** check box that users can select so that the message never shows again. If users allow, but then later deny access, the message appears the next time users try to send logs. If users later decide to allow access, they can go to **Settings** > **Apps** > **Company Portal** > **Permissions** > **Storage**, and then turn on the permission.


### How to explain this to your users
Send your users to [Send logs to your IT admin by email](/intune-user-help/send-logs-to-your-it-admin-by-email-android). You can also send them to [Send logs to your IT admin by cable](/intune-user-help/send-logs-to-your-it-admin-by-cable-android) if you want to let them compare the two methods.


### See also
[What to tell your end users about using Intune](/intune-classic/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune)
