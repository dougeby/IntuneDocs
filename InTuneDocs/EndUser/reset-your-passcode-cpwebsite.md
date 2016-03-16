---
title: Reset your passcode
ms.reviewer: na
ms.custom: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid:

# Reset your passcode

If you lose your device PIN or password for a device that you have enrolled in Intune, you can use the [Company Portal website](http://portal.manage.microsoft.com) to reset it. The Company Portal website is a web page that you can use to manage computers and devices that you have enrolled in Intune and to do most of the same tasks that you can do when using your Company Portal app.

> [!NOTE]
> You may not see the Reset Password button on the Company Portal website, depending on how your IT admin has configured Intune. Passcode Reset is not supported on Windows 8.1 and Windows RT devices.

To reset your passcode:

1.  Open the [Company Portal website](http://portal.manage.microsoft.com) and tap the device whose passcode you want to reset.

2.  Tap **Reset Passcode**.

    ![](./media/IW-Help-pics/iwp-1-tap-reset-passcode.png)

3.  Tap **Sign out**, and then sign back in with your work or school credentials. You have to sign back in within five minutes.

    ![](./media/IW-Help-pics/iwp-2-sign-out.png)

4.  Tap **Reset Passcode**.

    ![](./media/IW-Help-pics/iwp-3-tap-reset-passcode-after-signin.png)

    Check the table to see how Reset Passcode works on your device.

    |Platform|Support|
    |------------|-----------|
    |Android|Creates a new, temporary, alphanumeric passcode.|
    |iOS|Removes the passcode from the device and does not create a new temporary passcode. If you're using Touch ID, you'll need to set it up again on your device, because it gets removed when you reset your passcode.|
    |Windows 10 (mobile devices only)|Creates a new, temporary, alphanumeric passcode. Windows Hello is supported.|
    |Windows Phone 8.1|Creates a new,  temporary, numeric passcode.|
    After you unlock your device, you can set a new passcode by going to **Settings** on your device.

5.  Unlock your device and then set a new passcode, or change the temporary passcode by going to **Settings** on your device.

    To see a notification confirming that your password was reset successfully, click the notification flag at the top right of the Company Portal website.

### See also
[Using the Intune Company Portal website](using-the-intune-company-portal-website.md)