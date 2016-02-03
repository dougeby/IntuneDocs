---
title: MD Conversion - Help protect your data with remote wipe, remote lock, or passcode reset using Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: fbccc270-1eb9-4c3c-b787-b66de8763676
---
# MD Conversion - Help protect your data with remote wipe, remote lock, or passcode reset using Microsoft Intune
[!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] provides selective wipe, full wipe, remote lock, and passcode reset capabilities. Because mobile devices can store sensitive corporate data and provide access to many corporate resources, you can issue a remote device wipe command from the [!INCLUDE[wit_adminconsole](../Token/wit_adminconsole_md.md)] to wipe a lost or stolen device. Also, users can issue a remote device wipe command from the [!INCLUDE[wit_iwportal_1](../Token/wit_iwportal_1_md.md)] on privately owned devices enrolled in Intune.

> [!NOTE]
> This topic is only about wiping devices managed by Intune. You can also use [the Azure preview portal](https://portal.azure.com) to [wipe company data from apps](https://technet.microsoft.com/en-us/library/mt627826.aspx).

## <a name="bkmk_wipe"></a>Use Retire/Wipe to help secure a lost device or to retire a device from active use
**Full wipe** restores a device to its factory default settings, removing all company and user data and settings.     The device is removed from Intune. **Be careful about selecting full wipe; your data cannot be recovered**.

**Selective wipe** removes company data from a device.   The device is removed from Intune. The following tables describe by platform what data is removed and the effect on data that remains on the device after a selective wipe.

**iOS**

|Data type|iOS|
|-------------|-------|
|Company apps and associated data installed by [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)].|Apps are uninstalled. Company app data is removed.<br /><br />App data from Microsoft apps that use mobile app management is removed. The app is not removed.|
|Settings|Configurations that were set by [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] policy are no longer enforced and users can change the settings.|
|Wi-Fi and VPN profile settings|Removed|
|Certificate profile settings|Certificates removed and revoked.|
|Management Agent|Management profile is removed.|
|Email|Email profiles that are provisioned through [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] are removed and cached email on the device is deleted.|
|Azure Active Directory (AAD) Unjoin|AAD Record removed|
**Android**

|Data type|Android|Android Samsung KNOX|
|-------------|-----------|------------------------|
|Web links|Removed.|Removed|
|Unmanaged Google Play apps|Apps and data remain installed|Apps and data remain installed|
|Unmanaged line of business apps|Apps and data remain installed|Apps are uninstalled and data local to app is removed as a result. No data outside the app (SD card, etc.) is removed.|
|Managed Google Play apps|App data is removed. App is not removed. Data protected by MAM encryption outside the app (SD card, etc.) remain encrypted but aren't removed.|App data is removed. App is not removed. Data protected by MAM encryption outside the app (SD card, etc.) remain encrypted but aren't removed.|
|Managed line of business apps|App data is removed. App is not removed. Data protected by MAM encryption outside the app (SD card, etc.) remain encrypted but aren't removed.|App data is removed. App is not removed. Data protected by MAM encryption outside the app (SD card, etc.) remain encrypted but aren't removed.|
|Settings|Configurations that were set by [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] policy are no longer enforced and users can change the settings.|Configurations that were set by [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] policy are no longer enforced and users can change the settings.|
|Wi-Fi and VPN profile settings|Removed|Removed|
|Certificate profile settings|Certificates revoked, but not removed.|Certificates removed and revoked.|
|Management Agent|Device Administrator privilege is revoked.|Device Administrator privilege is revoked.|
|Email|Email  received by the Microsoft Outlook app for Android  app is removed.|Email profiles that are provisioned through [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] are removed and cached email on the device is deleted.|
|Azure Active Directory (AAD) Unjoin|AAD Record removed|AAD Record removed|
**Windows**

|Data type|Windows 8.1 (enrolled as a mobile device) and Windows RT 8.1|Windows RT|Windows Phone 8 and Windows Phone 8.1|
|-------------|----------------------------------------------------------------|--------------|-----------------------------------------|
|Company apps and associated data installed by [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)].|Files protected by EFS will have their key revoked and the user will not be able to open the files.|Will not remove company apps.|Apps originally installed through the company portal are uninstalled. Company app data is removed.|
|Settings|Configurations that were set by [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] policy are no longer enforced and users can change the settings.|Configurations that were set by [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] policy are no longer enforced and users can change the settings.|Configurations that were set by [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] policy are no longer enforced and users can change the settings.|
|Wi-Fi and VPN profile settings|Removed|Removed|Not supported|
|Certificate profile settings|Certificates removed and revoked.|Certificates removed and revoked.|Not supported|
|Management Agent|Not applicable. Management agent is built-in.|Not applicable. Management agent is built-in.|Not applicable. Management agent is built-in.|
|Email|Removes email that is EFS enabled which includes the Mail app for Windows email and attachments.|Not supported|Email profiles that are provisioned through [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] are removed and cached email on the device is deleted.|
|Azure Active Directory (AAD) Unjoin|No|No|AAD Record removed|

#### To remotely wipe a device from the Intune administrator console

1.  Select devices to be wiped. You can find them either by user or by device.

    -   **By user:**

        1.  In the [Intune administrator console](https://manage.microsoft.com/), click **Groups** &gt; **All Users**.

        2.  Click the name of the user whose mobile device you want to wipe. Click **View Properties**.

        3.  On the user's **Properties**  page, click **Devices**, and then click the name of the mobile device you want to wipe. Use Ctrl+click to multi-select devices.

    -   **By device:**

        1.  In the [Intune administrator console](https://manage.microsoft.com/), click **Groups** &gt; **All Mobile Devices**.

        2.  Click **Devices**, and then click the name of the mobile device you want to wipe. Use Ctrl+click to multi-select devices.

2.  Click **Retire/Wipe**.

3.  A message appears, prompting you to confirm whether you want to retire the device.

    -   To perform a **Selective wipe** which only removes company apps and data, click **Yes**.

    -   To perform a **Full wipe** that erases all apps and data and returns the device to factory default settings, select **Wipe the device before retiring**. This action applies to all platforms except Windows 8.1. **You cannot recover data removed by a full wipe**.

It takes less than 15 minutes for a wipe to propagate across all device types.

### Wiping Encryption File System (EFS)-enabled content
Selective wipe of EFS-encrypted content is supported by Windows 8.1 and Windows RT 8.1. The following apply to a selective wipe of EFS-enabled content:

-   Only apps and data that are protected by EFS using the same Internet domain as the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] account are selectively wiped. For more information, see [Windows Selective Wipe for Device Data Management](http://technet.microsoft.com/library/dn486874.aspx).

-   If there are any changes are made to the domain associated with EFS, the changes can take up to 48 hours before apps and data using the new domain can be selectively wiped.

-   Each domain that is registered with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] will be wiped.

The data and apps that are currently supported by EFS selective wipe are:

-   Mail app for Windows

-   Work Folders

-   Files and folders encrypted by EFS. For more information, see [Best practices for the Encrypting File System](http://support.microsoft.com/kb/223316).

-   If your organization maintains its identity in Active Directory, it must use the Directory Sync (DirSync) tool to sync information into AAD for EFS selective wipe to work correctly.  For more information on DirSync, see [Directory Sync Scenario](http://technet.microsoft.com/library/dn441212.aspx) in the Azure Active Directory documentation.

### Monitor retire, wipe, and delete actions
To get a report of devices that have been retired, wiped, or deleted, and who performed the action:

1.  In the [Intune administrator  console](https://manage.microsoft.com/), click **Reports** &gt; **Device History Reports**.

2.  Provide a start and end date for the report, then click **View Report**.

### <a name="BKMK_passcode"></a>Reset the passcode on a device
If a user forgets their passcode, you can help them by removing the passcode from a device or by forcing a new temporary passcode on a device. The table below lists how passcode reset works on different mobile platforms.

|Platform|Passcode reset|
|------------|------------------|
|iOS|Supported for clearing the passcode from a device. Does not create a new temporary passcode.|
|Android|Supported and a temporary passcode is created.|
|Windows 10|Not supported at this time.|
|Windows Phone 8 and Windows Phone 8.1|Supported|
|[!INCLUDE[winblue_winrt_2](../Token/winblue_winrt_2_md.md)] and [!INCLUDE[win8RT_client_1](../Token/win8RT_client_1_md.md)]|Not Supported|
|Windows 8.1|Not Supported|

##### To reset the passcode on a mobile device remotely through the Microsoft Intune console

1.  In the [Intue administrator  console](https://manage.microsoft.com/), click **Groups** &gt; **All Devices** &gt; **All Mobile Devices**.

2.  Click **All Direct Managed Devices** for devices enrolled in Intune or **All Exchange ActiveSync Managed Devices**.

    > [!TIP]
    > You can also navigate to a device by user. Click **All Users**. On the user's properties page, click **Devices**, and then click the name of the mobile device you want to wipe.

3.  In the list, click the device or devices that you want to lock. On the taskbar, click **Remote Tasks**, and select **Passcode Reset**.

### Lock a device remotely
If a user loses their device you can lock the device remotely. The table below lists how remote lock works on different mobile platforms.

|Platform|Remote lock|
|------------|---------------|
|iOS|Supported|
|Android|Supported|
|Windows 10|Not supported at this time.|
|Windows Phone 8 and Windows Phone 8.1|Supported|
|[!INCLUDE[winblue_winrt_2](../Token/winblue_winrt_2_md.md)] and [!INCLUDE[win8RT_client_1](../Token/win8RT_client_1_md.md)]|Supported if the current user of the device is the same user who enrolled the device.|
|Windows 8.1|Supported if the current user of the device is the same user who enrolled the device.|

##### To lock a mobile device remotely through the Microsoft Intune console

1.  In the [Intune administrator  console](https://manage.microsoft.com/), click **Groups** &gt; **All Devices** &gt; **All Mobile Devices**.

2.  Click **All Direct Managed Devices** for devices enrolled in  Intune  or **All Exchange ActiveSync Managed Devices**.

    > [!TIP]
    > You can also navigate to a device by user. Click **All Users**. On the user's properties page, click **Devices**, and then click the name of the mobile device you want to wipe.

3.  In the list, click the device or devices that you want to lock. On the taskbar, click **Remote Tasks**, and select **Remote Lock**.

## See Also
[Retire data and devices from Microsoft Intune management](../Topic/Retire_data_and_devices_from_Microsoft_Intune_management.md)
[Windows Selective Wipe for Device Data Management](http://technet.microsoft.com/library/dn486874.aspx)

