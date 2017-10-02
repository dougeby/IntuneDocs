---

# required metadata

title: Android for Work policy settings 
description: Create policies that control settings and features on Android for Work devices that you manage with Intune.
keywords:
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 02/03/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 35a53076-74d6-486d-b201-e0da2e170008

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: chrisbal
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Android for Work policy settings in Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune supplies a range of built-in general settings that you can configure on [Android for Work devices](android-for-work.md).

## General configuration policy

Use the Intune **Android for Work general configuration policy** to configure security and work profile settings for your Android for Work devices.

If the setting you are looking for does not appear in this topic, you might be able to create it by using an Android custom policy that lets you use OMA-URI settings to control the device. For more information, go to [Custom policy settings](#custom-policy-settings) later in this topic.

> [!TIP]
> Devices are automatically encrypted when you provision a work profile. You cannot change this setting.

### Password settings

|Setting name|Details|
|----------------|-|
|**Require a password to unlock mobile devices**|Specifies whether a password is required on managed devices. Choose from:<br><br>- **Complex** – requires at least one letter, number, and symbol<br>- **Alphanumeric** – requires at least one number and one alphabetic character<br>- **Alphabetic** – requires at least letters or symbols<br>- **Numeric complex** – Requires numeric characters that are not repeating or consecutive<br>- **Numeric**<br><br>If this setting is not enabled, there are no complexity requirements.|
|**Minimum password length**|Specifies the minimum number of characters or numbers in the password.|
|**Minutes of inactivity before device locks**|Specifies the number of minutes without user activity before the device automatically locks.|
|**Allow Smart Lock and other trust agents**<br>(Android 6 and later)|Lets you control the Smart Lock feature on compatible Android devices. This phone capability, sometimes known as a trust agent, lets you disable or bypass the device lock screen password if the device is in a trusted location (for example, when it's connected to a specific Bluetooth device, or when it's close to an NFC tag.) You can use this setting to prevent users from configuring Smart Lock.|
|**Number of repeated sign-in failures before the work profile is removed**|Specifies the number of sign-in failures allowed before the work profile on the device is removed. This does not perform a full device wipe.|
|**Remember password history**|Prevents the reuse of previously used passwords.|
|**Remember password history** - **Prevent reuse of previous passwords**|Specifies the number of previously used passwords to remember.|
|**Password expiration (days)**|Specifies the number of days before the device password must be changed.|
|**Allow fingerprint unlock**<br>(Android 6 and later)|Lets you use a fingerprint to unlock devices with this capability.|


### Work profile settings

|Setting name|Details|
|----------------|-|
|**Allow data sharing between work and personal profiles**|Lets apps in the work profile share data with apps in the users personal profile. Choose from:<br><br>- **Prevent any sharing across boundaries**<br>- **Apps in work profile can handle sharing request from personal profile**<br>- **No restrictions on sharing**|
|**Hide work profile notifications when the device is locked**<br>(Android 6 and later)|Control whether to show any notifications from the work profile when the device is locked.|
|**Set default app permission policy**<br>(Android 6 and later)|Sets the default permission policy for all apps in the work profile. Starting in Android 6, some permissions required by apps are prompted to the end user at runtime.  This policy setting allows IT to decide how or if users are prompted to grant permissions for apps in the work profile. <br/><br/>For example, IT may push an app to the work profile that requires location access.  Normally that app would pop up a dialog to the user asking if they wanted to grant location access to the app, and the user could approve it or deny it.  This policy allows IT to decide whether all permissions should be auto-granted without a prompt, auto-denied without a prompt, or let the end user decide.|


## Custom policy settings
Use the Microsoft Intune **Android for Work custom configuration policy** to deploy OMA-URI settings that can be used to control features on Android for Work devices. These are standard settings that many mobile device manufacturers use to control device features.

This capability is intended to allow you to deploy Android settings that are not configurable with Intune policies.
Intune supports a limited number of Android custom policies at present. See the examples in this topic to find out which policies you can configure.

### General settings

|Setting name|Details|
    |----------------|--------------------|
    |**Name**|Enter a unique name for the Android custom policy to help you identify it in the Intune console.|
    |**Description**|Provide a description that gives an overview of the Android custom policy and other relevant information that helps you to locate it.|

### OMA-URI settings

   |Setting name|Details|
    |--------|--------------------|
    |**Setting name**|Enter a unique name for the OMA-URI setting to help you identify it in the list of settings.|
    |**Setting description**|Provide a description that gives an overview of the setting and other relevant information to help you locate it.|
    |**Data type**|Select the data type in which you will specify this OMA-URI setting. Choose from **String, String (XML), Date and time, Integer, Floating point**, or **Boolean**.|
    |**OMA-URI (case sensitive)**|Specify the OMA-URI you want to supply a setting for.|
    |**Value**|Specify the value to associate with the OMA-URI that you specified previously.|

### Examples

- [Create a Wi-Fi profile with a pre-shared key](pre-shared-key-wi-fi-profile.md)
- [Use a custom policy to create a per-app VPN profile for Android devices](per-app-vpn-for-android-pulse-secure.md)

### See also
[Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
