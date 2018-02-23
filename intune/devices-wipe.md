---
# required metadata

title: Use factory reset or remove company data on devices using Intune
titlesuffix: "Azure portal"
description: Learn how to remove company data on a device or to factory reset the device.
keywords:
author: nathbarn
ms.author: nathbarn
manager: dougeby
ms.date: 02/22/2018
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

# Remove devices by using factory reset or remove company data

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

You can remove devices from Intune that are no longer needed, are being repurposed, or have gone missing. You can do this by issuing a **remove company data** or **factory reset** command. Users can also issue a remote command from the Intune Company Portal to personally owned devices enrolled in Intune.

> [!NOTE]
> Before you remove a user from Azure Active Directory, issue a **Factory reset** or **Remove company data** command to all devices associated with that user. If you remove users with managed devices from Azure Active Directory, Intune can no longer issue factory reset or remove company data to those devices.

## Factory reset

**Factory reset** restores a device to its factory default settings, removing all company and user data and settings. The device is removed from Intune management. Factory reset is useful for resetting a device before giving it to a new user, or for instances where the device has been lost or stolen. Be careful about selecting factory reset. Data on the device cannot be recovered.

### To factory reset a device

1. Sign into the [Azure portal](https://portal.azure.com).
2. Choose **All services** > **Intune**. Intune is located in the **Monitoring + Management** section.
3. On the **Devices** blade, choose **All devices**.
4. Choose the name of the device you want to factory reset.
5. On the blade showing the device's name, choose **Factory reset**
6. For Windows 10 version 1709 or higher, there is an additional option to "Retain enrollment state and user account". 
    
    |Retained through a factory reset|Not retained|
    | -------------|------------|
    |User accounts associated with the device|User files|
    |Machine state \(domain join, Azure Active Directory-joined)| User installed apps \(store and Win32 apps)|
    |MDM enrollment|Non-default device settings|
    |OEM installed apps \(store and Win32 apps)||
    |User profile||
    |User data outside of user profile||
    |User autologon|| 
    
         
7. Choose **Yes** to confirm the factory reset.

If the device is on and connected, it takes less than 15 minutes for a factory reset command to propagate across all device types.

## Remove company data

The **remove company data** command removes managed app data (where applicable), settings, and email profiles that were assigned by using Intune. Remove company data leaves the user's personal data on the device. The device is removed from Intune management. The following tables describe what data is removed, and the effect on data that remains on the device after company data is removed.

### iOS

|Data type|iOS|
|-------------|-------|
|Company apps and associated data installed by Intune|Apps are uninstalled. Company app data is removed.<br /><br />App data from Microsoft apps that use mobile app management is removed. The app is not removed.|
|Settings|Configurations that were set by Intune policy are no longer enforced, and users can change the settings.|
|Wi-Fi and VPN profile settings|Removed.|
|Certificate profile settings|Certificates are removed and revoked.|
|Management Agent|Management profile is removed.|
|Email|Email profiles that are provisioned through Intune are removed, and cached email on the device is deleted.|
|Outlook|Email received by the Microsoft Outlook app for iOS is removed.|
|Azure Active Directory (AD) Unjoin|Azure AD record is removed.|
|Contacts | Contacts synced directly from the app to the native address book are removed.  Any contacts synced from the native address book to another external source cannot be removed. <br /> <br />Currently, only Outlook app is supported.

### Android

|Data type|Android|Android Samsung Knox Standard|
|-------------|-----------|------------------------|
|Web links|Removed.|Removed.|
|Unmanaged Google Play apps|Apps and data remain installed.|Apps and data remain installed.|
|Unmanaged line-of-business apps|Apps and data remain installed.|Apps are uninstalled and data local to the app is removed as a result. No data outside the app (for example, on an SD card) is removed.|
|Managed Google Play apps|App data is removed. App is not removed. Data protected by MAM encryption outside the app (for example, an SD card) remain encrypted and unusable, but aren't removed.|App data is removed. App is not removed. Data protected by MAM encryption outside the app (for example, an SD card) remain encrypted, but aren't removed.|
|Managed line-of-business apps|App data is removed. App is not removed. Data protected by MAM encryption outside the app (for example, an SD card) remain encrypted and unusable, but aren't removed.|App data is removed. App is not removed. Data protected by MAM encryption outside the app (for example, an SD card) remain encrypted and unusable, but aren't removed.|
|Settings|Configurations that were set by Intune policy are no longer enforced, and users can change the settings.|Configurations that were set by Intune policy are no longer enforced, and users can change the settings.|
|Wi-Fi and VPN profile settings|Removed.|Removed.|
|Certificate profile settings|Certificates revoked, but not removed.|Certificates removed and revoked.|
|Management Agent|Device Administrator privilege is revoked.|Device Administrator privilege is revoked.|
|Email|n/a (email profiles are not supported by Android devices)|Email profiles that are provisioned through Intune are removed, and cached email on the device is deleted.|
|Outlook|Email received by the Microsoft Outlook app for Android is removed, but only if Outlook is protected by MAM policies. Otherwise, Outlook is not wiped on unenrollment.|Email received by the Microsoft Outlook app for Android is removed, but only if Outlook is protected by MAM policies. Otherwise, Outlook is not wiped on unenrollment.|
|Azure Active Directory (AD) Unjoin|Azure AD Record removed.|Azure AD Record removed.|
|Contacts | Contacts synced directly from the app to the native address book are removed.  Any contacts synced from the native address book to another external source cannot be removed. <br /> <br />Currently, only Outlook app is supported.|Contacts synced directly from the app to the native address book are removed.  Any contacts synced from the native address book to another external source cannot be removed. <br /> <br />Currently, only Outlook app is supported.

### Android for Work

Removing company data from an Android for Work device removes all data, apps, and settings in the work profile on that device. This retires the device from management with Intune. Factory reset is not supported for Android for Work.


### macOS

|Data type|macOS|
|-------------|-------|
|Settings|Configurations that were set by Intune policy are no longer enforced, and users can change the settings.|
|Wi-Fi and VPN profile settings|Removed.|
|Certificate profile settings|Certificates that were deployed through MDM are removed and revoked.|
|Management Agent|Management profile is removed.|
|Outlook|If conditional access is enabled, no new mail will be received by the device.|
|Azure Active Directory (AD) Unjoin|Azure AD record is removed.|

### Windows

|Data type|Windows 8.1 (MDM) and Windows RT 8.1|Windows RT|Windows Phone 8 and Windows Phone 8.1|Windows 10|
|-------------|----------------------------------------------------------------|--------------|-----------------------------------------|--------|
|Company apps and associated data installed by Intune|Files protected by EFS will have their key revoked and the user will not be able to open the files.|Will not remove company apps.|Apps originally installed through the company portal are uninstalled. Company app data is removed.|Apps are uninstalled and sideloading keys are removed.<br>For Windows 10 version 1703 (Creator Update) and later, Office 365 ProPlus apps are not removed.|
|Settings|Configurations that were set by Intune policy are no longer enforced, and users can change the settings.|Configurations that were set by Intune policy are no longer enforced, and users can change the settings.|Configurations that were set by Intune policy are no longer enforced, and users can change the settings.|Configurations that were set by Intune policy are no longer enforced, and users can change the settings.|
|Wi-Fi and VPN profile settings|Removed.|Removed.|Not supported.|Removed.|
|Certificate profile settings|Certificates removed and revoked.|Certificates removed and revoked.|Not supported.|Certificates removed and revoked.|
|Email|Removes email that is EFS enabled, which includes the Mail app for Windows email and attachments.|Not supported.|Email profiles that are provisioned through Intune are removed, and cached email on the device is deleted.|Removes email that is EFS enabled, which includes the Mail app for Windows email and attachments. Removes mail accounts that were provisioned by Intune.|
|Azure Active Directory (AD) Unjoin|No.|No.|Azure AD Record removed.|Not applicable. Windows 10 does not support remove company data for Azure Active Directory joined devices.|

### To remove company data

1. Sign into the [Azure portal](https://portal.azure.com).
2. Choose **All services** > **Intune**. Intune is located in the **Monitoring + Management** section.
3. On the **Devices** blade, choose **All devices**.
4. Choose the name of the device from which you want to remove company data.
5. On the blade showing the device's name, choose **Remove company data**, and then choose **Yes** to confirm.

If the device is on and connected, it takes less than 15 minutes for a remove data command to propagate across all device types.

## Delete devices from the Azure Active Directory portal

Due to communication issues or missing devices, you might need to delete devices from Azure Active Directory (AD). The delete command does not remove a device from management but you can use **Delete** to remove device records from the Azure portal that you know are unreachable and unlikely to communicate with Azure again.

1.  Sign in to the [Azure Active Directory in the Azure portal](http://aka.ms/accessaad) with your admin credentials. You can also sign in to the [Office 365 portal](https://portal.office.com) and then choose **Admin centers** &gt; **Azure AD** from using the link on the left side of the page.
3.  Create an Azure subscription if you don’t have one. This should not require a credit card or payment if you have a paid account (choose the **Register your free Azure Active Directory** subscription link).
4.  Select **Azure Active Directory** and then select your organization.
5.  Select the **Users** tab.
6.  Select the user whose devices you want to delete.
7.  Choose **Devices**.
8.  Remove devices as appropriate, such as those that are no longer in use, or those that have inaccurate definitions.
