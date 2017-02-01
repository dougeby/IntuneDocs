---
# required metadata

title: How to reset your  passcode from the Company Portal website | Microsoft Docs
description:
keywords:
author: barlanmsftms.author: barlan
manager: angrobe
ms.date: 01/23/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 4fa3255b-9d1e-42d5-bd8b-70963dcf2d86searchScope: - Company Portal

# optional metadata

ROBOTS: NOINDEX,NOFOLLOW
#audience:
#ms.devlang:
ms.reviewer: mamoriss
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# How to reset your device passcode from the Company Portal website

If you lose your device PIN or password for a device that you have enrolled in Intune, you can use the [Company Portal website](http://portal.manage.microsoft.com) to reset it. You can use the Company Portal website to manage computers and devices that you have enrolled in Intune and to do most of the same tasks that you can do when you use your Company Portal app.

> [!NOTE]
> It's possible that you won't see the **Reset Passcode** button on the Company Portal website. If you do not, you'll need to contact your IT admin for support through the Company Portal website.

To reset your passcode:

1.  Open the [Company Portal website](http://portal.manage.microsoft.com) and choose the device whose passcode you want to reset.

2.  Choose **Reset Passcode**.

    ![Device details with Reset Passcode button](./media/iwp-screen-with-all-options.png)

3.  Choose **Sign out**, and then sign back in with your work or school credentials. You have to sign back in within five minutes.

    ![Reset message with sign-out button](./media/iwp-2-sign-out.png)

4.  Choose **Reset Passcode**.

    ![Message that explains what happens when you reset the passcode](./media/iwp-3-tap-reset-passcode-after-signin.png)

    Check the table to see how **Reset Passcode** works on your device.

    |Device Type|What Happens When You Reset|
    |------------|-----------|
    |Android|Removes the existing passcode and creates a temporary passcode with both letters and numbers|
    |iOS|Removes the existing passcode and does not create a temporary passcode. If you're using the Touch ID fingerprint scanner for opening your device or making purchases, you'll need to set it up again.|
    |Windows 10 Mobile|Removes the existing passcode and creates a temporary passcode with both letters and numbers. If you're using Windows Hello facial recognition to log in, it will still be supported.|
    |Windows Phone 8.1|Removes the existing passcode and creates a temporary passcode with numbers.|

    5.  Unlock your device and set a new passcode, or change the temporary passcode by going to your device **Settings**.

    To see a notification confirming that your password was reset successfully, click the notification flag at the top right of the Company Portal website.

Still need help? Contact your IT admin. For contact information, check the [Company Portal website](http://portal.manage.microsoft.com).
