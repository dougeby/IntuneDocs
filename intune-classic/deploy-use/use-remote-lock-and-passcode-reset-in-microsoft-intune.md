---
title: Remote lock and passcode reset 
description: Intune provides both remote lock and passcode reset capabilities.
keywords:
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 03/06/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 970f8c81-7c7f-4789-9ed4-2133d50b9db6
ROBOTS: NOINDEX,NOFOLLOW

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: chrisgre
#ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic
---
# Help protect your devices with remote lock and passcode reset

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune provides both remote lock and passcode reset capabilities.

## Lock a device remotely
If a user loses a device, you can lock the device remotely. The device must already have a PIN or passcode set on it before you can use remote lock.

The following table lists how remote lock works on different mobile platforms.

|Platform|Remote lock|
|------------|---------------|
|macOS|Not supported|
|iOS|Supported|
|Android|Supported|
|Android for Work|Supported|
|Windows 10 (mobile)|Supported|
|Windows 10 (desktop)|Not supported|
|Windows Phone 8 and Windows Phone 8.1|Supported|
|Windows RT 8.1 and Windows RT|Supported if the current user of the device is the same user who enrolled the device.|
|Windows 8.1|Supported if the current user of the device is the same user who enrolled the device.|

Remote lock is not supported for Windows PCs enrolled with the Intune software client.

### Lock a mobile device remotely through the Intune console

1.  In the [Intune administrator console](https://manage.microsoft.com/), choose **Groups** &gt; **All Devices** &gt; **All Mobile Devices**.

2.  Choose **All Direct Managed Devices** for devices enrolled in Intune or **All Exchange ActiveSync Managed Devices**.

    > [!TIP]
    > You can also navigate to a device by user. Choose **All Users**. On the user's properties page, choose **Devices**, and then choose the name of the mobile device you want to lock.

3.  In the list, choose the device or devices that you want to lock. On the taskbar, choose **Remote Tasks** and select **Remote Lock**.

## Reset the passcode on a device
If a user forgets a passcode, you can help by removing the passcode from a device or by forcing a new temporary passcode on a device. The following table lists how passcode reset works on different mobile platforms.

|Platform|Passcode reset|
|------------|------------------|
|macOS|Not supported|
|iOS|Supported for clearing the passcode from a device. Does not create a new temporary passcode.|
|Android|Supported on versions earlier than Android 7.0. Creates a temporary passcode.|
|Android for Work|Not supported|
|Windows 10 mobile|Supported for Windows 10 Creator version and later mobile devices that are Azure AD joined.|
|Windows Phone 8 and Windows Phone 8.1|Supported|
|Windows RT 8.1|Not Supported|
|Windows 8.1|Not Supported|
|Windows 10 desktop|Not Supported|

Passcode reset is not supported for Windows PCs enrolled with the Intune software client.

### Reset a passcode

1.  In the [Intune administrator console](https://manage.microsoft.com/), choose **Groups** &gt; **All Devices** &gt; **All Mobile Devices**.

2.  Choose **All Direct Managed Devices** for devices enrolled in Intune or **All Exchange ActiveSync Managed Devices**.

    > [!TIP]
    > You can also navigate to a device by user. Click **All Users**. On the user's properties page, click **Devices**, and then click the name of the mobile device you want to wipe.

3.  In the list, choose the device or devices that you want to lock. On the taskbar, choose **Remote Tasks** and select **Passcode Reset**.


### See also
[Retire devices](retire-devices-from-microsoft-intune-management.md) and
[Windows Selective Wipe for Device Data Management](http://technet.microsoft.com/library/dn486874.aspx)
