---
# required metadata

title: Use remote wipe to help protect data
description: Intune provides selective wipe and full wipe capabilities to remove sensitive corporate data and remove access to many corporate resources.
keywords:
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/21/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8519e411-3d48-44eb-9b41-3e4fd6a93112
ROBOTS: NOINDEX,NOFOLLOW

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: lancecra
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Help protect your data with full or selective wipe using Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

You can wipe apps and data from Intune-managed devices that are no longer needed, are being repurposed, or have gone missing. To do this, Intune provides selective wipe and full wipe capabilities. Users can also issue a remote device wipe command from the Intune Company Portal app on privately owned devices enrolled in Intune.

  > [!NOTE]
  > This topic is only about wiping devices managed by Intune mobile device management. You can also use the [Azure portal](https://portal.azure.com) to [wipe company data from apps](wipe-managed-company-app-data-with-microsoft-intune.md). You can also [retire computers managed with the Intune client software](retire-a-windows-pc-with-microsoft-intune.md).

## Full wipe

**Full wipe** restores a device to its factory default settings, removing all company and user data and settings. The device is removed from Intune. Full wipe is useful for resetting a device before giving it to a new user, or for instances where the device has been lost or stolen.  **Be careful about selecting full wipe. Data on the device cannot be recovered**.


> [!Warning]
> Windows 10 RTM devices (devices earlier than the Windows 10 version 1511) with less than 4 GB of RAM might become inaccessible if wiped. To access a Windows 10 device that has become unresponsive, you can boot the device from a USB drive.

### Remotely wipe a device from the Intune administrator console

1.  Select devices to be wiped. You can find them either by user or by device.

    -   **By user:**

        1.  In the [Intune administrator console](https://manage.microsoft.com/), choose **Groups** &gt; **All Users**.

        2.  Choose the name of the user whose mobile device you want to wipe. Choose **View Properties**.

        3.  On the user's **Properties**  page, choose **Devices**, and then choose the name of the mobile device you want to wipe. To select multiple devices, use Ctrl+click.

    -   **By device:**

        1.  In the [Intune administrator console](https://manage.microsoft.com/), choose **Groups** &gt; **All Mobile Devices**.

         ![Starting a retire or wipe operation](../media/dev-sa-wipe.png)

        2.  Choose **Devices**, and then choose the name of the mobile device you want to wipe. To select multiple devices, use Ctrl+click.

2.  Choose **Retire/Wipe**.

3.  A confirmation message appears, asking you whether you want to retire the device.

    -   To perform a **Selective wipe** that only removes company apps and data, choose **Yes**.

    -   To perform a **Full wipe** that erases all apps and data and returns the device to factory default settings, choose **Wipe the device before retiring**. This action applies to all platforms except Windows 8.1. **You cannot recover data removed by a full wipe**.

If the device is on and connected, it takes less than 15 minutes for a wipe command to propagate across all device types.

#### To delete devices in the Azure Active Directory portal

1.  Browse to [http://aka.ms/accessaad](http://aka.ms/accessaad) or choose **Admin** &gt; **Azure AD** from [https://portal.office.com](https://portal.office.com).

2.  Login with your Org ID using the link on the left side of the page.

3.  Create an Azure Subscription if you don’t have one. This should not require a credit card or payment if you have a paid account (choose the **Register your free Azure Active Directory** subscription link).

4.  Select **Active Directory** and then select your organization.

5.  Select the **Users** tab.

6.  Select the user whose devices you want to delete.

7.  Choose **Devices**.

8.  Remove devices as appropriate, such as those that are no longer in use, or those that have inaccurate definitions.


## Selective wipe

**Selective wipe** removes company data, including mobile app management (MAM) data (where applicable), settings, and email profiles from a device. Selective wipe leaves the user's personal data on the device. The device is removed from Intune. The following tables describe what data is removed, and the effect on data that remains on the device after a selective wipe. (The tables are organized by platform.)

**iOS**

|Data type|iOS|
|-------------|-------|
|Company apps and associated data installed by Intune|Apps are uninstalled. Company app data is removed.<br /><br />App data from Microsoft apps that use mobile app management is removed. The app is not removed.|
|Settings|Configurations that were set by Intune policy are no longer enforced, and users can change the settings.|
|Wi-Fi and VPN profile settings|Removed.|
|Certificate profile settings|Certificates are removed and revoked.|
|Management Agent|Management profile is removed.|
|Email|Email profiles that are provisioned through Intune are removed, and cached email on the device is deleted.|
|Outlook|Email received by the Microsoft Outlook app for iOS is removed.|
|Azure Active Directory (AAD) Unjoin|AAD Record is removed.|
|Contacts | Contacts synced directly from the app to the native address book are removed.  Any contacts synced from the native address book to another external source cannot be wiped. <br /> <br />Currently, only Outlook app is supported.

**Android**

|Data type|Android|Android Samsung KNOX Standard|
|-------------|-----------|------------------------|
|Web links|Removed.|Removed.|
|Unmanaged Google Play apps|Apps and data remain installed.|Apps and data remain installed.|
|Unmanaged line of business apps|Apps and data remain installed.|Apps are uninstalled and data local to the app is removed as a result. No data outside the app (for example, on an SD card) is removed.|
|Managed Google Play apps|App data is removed. App is not removed. Data protected by MAM encryption outside the app (for example, an SD card) remain encrypted and unusable, but aren't removed.|App data is removed. App is not removed. Data protected by MAM encryption outside the app (for example, an SD card) remain encrypted, but aren't removed.|
|Managed line of business apps|App data is removed. App is not removed. Data protected by MAM encryption outside the app (for example, an SD card) remain encrypted and unusable, but aren't removed.|App data is removed. App is not removed. Data protected by MAM encryption outside the app (for example, an SD card) remain encrypted and unusable, but aren't removed.|
|Settings|Configurations that were set by Intune policy are no longer enforced, and users can change the settings.|Configurations that were set by Intune policy are no longer enforced, and users can change the settings.|
|Wi-Fi and VPN profile settings|Removed.|Removed.|
|Certificate profile settings|Certificates revoked, but not removed.|Certificates removed and revoked.|
|Management Agent|Device Administrator privilege is revoked.|Device Administrator privilege is revoked.|
|Email|N/A. See the Outlook item.|Email profiles that are provisioned through Intune are removed, and cached email on the device is deleted.|
|Outlook|Email received by the Microsoft Outlook app for Android is removed, but only if Outlook is protected by MAM policies. Otherwise, Outlook is not wiped on unenrollment.|Email received by the Microsoft Outlook app for Android is removed, but only if Outlook is protected by MAM policies. Otherwise, Outlook is not wiped on unenrollment.|
|Azure Active Directory (AAD) Unjoin|AAD Record removed.|AAD Record removed.|
|Contacts | Contacts synced directly from the app to the native address book are removed.  Any contacts synced from the native address book to another external source cannot be wiped. <br /> <br />Currently, only Outlook app is supported.|Contacts synced directly from the app to the native address book are removed.  Any contacts synced from the native address book to another external source cannot be wiped. <br /> <br />Currently, only Outlook app is supported.

**Android for Work**

Performing selective wipe on an Android for Work device removes all data, apps, and settings in the work profile on that device. This retires the device from management with Intune. Full wipe is not supported for Android for Work.

**Windows**

|Data type|Windows 8.1 (MDM) and Windows RT 8.1|Windows RT|Windows Phone 8 and Windows Phone 8.1|Windows 10|
|-------------|----------------------------------------------------------------|--------------|-----------------------------------------|--------|
|Company apps and associated data installed by Intune|Files protected by EFS will have their key revoked and the user will not be able to open the files.|Will not remove company apps.|Apps originally installed through the company portal are uninstalled. Company app data is removed.|Apps are uninstalled and sideloading keys are removed.|
|Settings|Configurations that were set by Intune policy are no longer enforced, and users can change the settings.|Configurations that were set by Intune policy are no longer enforced, and users can change the settings.|Configurations that were set by Intune policy are no longer enforced, and users can change the settings.|Configurations that were set by Intune policy are no longer enforced, and users can change the settings.|
|Wi-Fi and VPN profile settings|Removed.|Removed.|Not supported.|Removed.|
|Certificate profile settings|Certificates removed and revoked.|Certificates removed and revoked.|Not supported.|Certificates removed and revoked.|
|Email|Removes email that is EFS enabled, which includes the Mail app for Windows email and attachments.|Not supported.|Email profiles that are provisioned through Intune are removed, and cached email on the device is deleted.|Removes email that is EFS enabled, which includes the Mail app for Windows email and attachments. Removes mail accounts that were provisioned by Intune.|
|Azure Active Directory (AAD) Unjoin|No.|No.|AAD Record removed.|Not applicable. Windows 10 does not support selective wipe for Azure Active Directory joined devices.|

## Wipe encryption file system (EFS)-enabled content
Selective wipe of EFS-encrypted content is supported by Windows 8.1 and Windows RT 8.1. The following points apply to a selective wipe of EFS-enabled content:

-   Only apps and data that are protected by EFS using the same Internet domain as the Intune account are selectively wiped. For more information, see [Windows Selective Wipe for Device Data Management](http://technet.microsoft.com/library/dn486874.aspx).

-   If there are any changes are made to the domain associated with EFS, the changes can take up to 48 hours before apps and data using the new domain can be selectively wiped.

-   Each domain that is registered with Intune will be wiped.

The data and apps that are currently supported by EFS selective wipe are:

-   Mail app for Windows

-   Work folders

-   Files and folders encrypted by EFS. For more information, see [Best practices for the Encrypting File System](http://support.microsoft.com/kb/223316).

-   If your organization maintains its identity in Active Directory, it must use the Directory Sync (DirSync) tool to sync information into AAD for EFS selective wipe to work correctly.  For more information on DirSync, see [Directory Sync Scenario](http://technet.microsoft.com/library/dn441212.aspx) in the Azure Active Directory documentation.

## Monitor retire, wipe, and delete actions
To get a report of devices that have been retired, wiped, or deleted:

1.  In the [Intune administrator  console](https://manage.microsoft.com/), choose **Reports** &gt; **Device History Reports**.

2.  Provide a start and end date for the report, and then choose **View Report**.

This report also shows who performed the action.

### See also
[Retire devices](retire-devices-from-microsoft-intune-management.md)

[Windows Selective Wipe for Device Data Management](http://technet.microsoft.com/library/dn486874.aspx)
