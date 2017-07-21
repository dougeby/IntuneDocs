---
# required metadata

title: Full or selective wipe on devices using IntunetitleSuffix: "Intune on Azure"
description: Learn how to do a selective wipe of company data on a device or to do a full wipe to factory reset the device."
keywords:
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/21/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 4fdb787e-084f-4507-9c63-c96b13bfcdf9

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Use full or selective wipe

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

You can wipe apps and data from Intune-managed devices that are no longer needed, are being repurposed, or have gone missing. To do this, Intune provides selective wipe and full wipe capabilities. Users can also issue a remote device wipe command from the Intune Company Portal app on privately owned devices enrolled in Intune.

  > [!NOTE]
  > This topic is only about wiping devices managed by Intune mobile device management. You can also use the [Azure portal](https://portal.azure.com) to [wipe company data from apps](https://docs.microsoft.com/intune-classic/deploy-use/wipe-managed-company-app-data-with-microsoft-intune). You can also [retire computers managed with the Intune client software](https://docs.microsoft.com/intune-classic/deploy-use/retire-a-windows-pc-with-microsoft-intune).

## Full wipe

**Full wipe** restores a device to its factory default settings, removing all company and user data and settings. The device is removed from Intune. Full wipe is useful for resetting a device before giving it to a new user, or for instances where the device has been lost or stolen.  **Be careful about selecting full wipe. Data on the device cannot be recovered**.


> [!Warning]
> Windows 10 RTM devices (devices earlier than the Windows 10 version 1511) with less than 4 GB of RAM might become inaccessible if wiped. To access a Windows 10 device that has become unresponsive, you can boot the device from a USB drive.


**To do a full wipe (factory reset) of a device**:

1.  On the **Devices and groups** blade, choose **All devices**.

2.  Choose the name of the device you want to wipe.

3.  On the blade showing the device's name, choose **Factory reset**, and then choose **Yes** to confirm the wipe.

If the device is on and connected, it takes less than 15 minutes for a wipe command to propagate across all device types.

### To delete devices in the Azure Active Directory portal

1.  Browse to [http://aka.ms/accessaad](http://aka.ms/accessaad) or choose **Admin** &gt; **Azure AD** from [https://portal.office.com](https://portal.office.com).

2.  Log in with your Org ID using the link on the left side of the page.

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
|Email|n/a (email profiles are not supported by Android devices)|Email profiles that are provisioned through Intune are removed, and cached email on the device is deleted.|
|Outlook|Email received by the Microsoft Outlook app for Android is removed.|Email received by the Microsoft Outlook app for Android is removed.|
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

**To do a selective wipe**:

1.  On the **Devices and groups** blade, choose **All devices**.

2.  Choose the name of the device you want to wipe.

3.  On the blade showing the device's name, choose **Remove comp...** (stands for Remove company data), and then choose **Yes** to confirm the wipe.

If the device is on and connected, it takes less than 15 minutes for a wipe command to propagate across all device types.
