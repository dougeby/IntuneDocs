---
title: Passcode reset and remote lock
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 2c1e0dd3-23de-4182-9f68-007bc9e62363
author: Lindavr
---
# Passcode reset and remote lock
Insert introduction here.

## Passcode Reset
If a user forgets their passcode, you can help them by removing the passcode from a device or by forcing a new temporary passcode on a device. The table below lists how passcode reset works on different mobile platforms.

|Platform|Passcode Reset|
|------------|------------------|
|iOS|Supported for clearing the passcode from a device. Does not create a new temporary passcode.|
|Android|Supported and a temporary passcode is created.|
|Windows Phone 8 and Windows Phone 8.1|Supported|
|[!INCLUDE[winblue_winrt_2](../Token/winblue_winrt_2_md.md)] and [!INCLUDE[win8RT_client_1](../Token/win8RT_client_1_md.md)]|Not Supported|
|Windows 8.1|Not Supported|

#### To reset the passcode on a mobile device remotely through the Microsoft Intune Console

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com/), click **Groups** &gt; **All Devices** &gt; **All Mobile Devices**.

2.  Click **All Direct Managed Devices** for devices enrolled to [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] or **All Exchange ActiveSync Managed Devices**.

    > [!TIP]
    > You can also navigate to a device by user. Click **All Users** and on the properties page for the user, click the **Devices** tab, and then click the name of the mobile device that you want to wipe.

3.  In the list, click the device or devices that you want to lock, and then on the taskbar click **Remote Tasks** and select **Passcode Reset**.

### Remote Lock
If a user loses their device you can lock the device remotely. The table below lists how remote lock works on different mobile platforms.

|Platform|Remote Lock|
|------------|---------------|
|iOS|Supported|
|Android|Supported|
|Windows Phone 8 and Windows Phone 8.1|Supported|
|[!INCLUDE[winblue_winrt_2](../Token/winblue_winrt_2_md.md)] and [!INCLUDE[win8RT_client_1](../Token/win8RT_client_1_md.md)]|Supported if the current user of the device is the same user who enrolled the device.|
|Windows 8.1|Supported if the current user of the device is the same user who enrolled the device.|

##### To lock a mobile device remotely through the Microsoft Intune Console

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com/), click **Groups** &gt; **All Devices** &gt; **All Mobile Devices**.

2.  Click **All Direct Managed Devices** for devices enrolled to [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] or **All Exchange ActiveSync Managed Devices**.

    > [!TIP]
    > You can also navigate to a device by user. Click **All Users** and on the properties page for the user, click the **Devices** tab, and then click the name of the mobile device that you want to wipe.

3.  In the list, click the device or devices that you want to lock, and then on the taskbar click **Remote Tasks** and select **Remote Lock**.

