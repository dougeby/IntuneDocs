---

# required metadata

title: Android for Work policy settings | Microsoft Intune
description: Create policies that control settings and features on Android for Work devices that you manage with Intune.
keywords:
author: robstackmsft
manager: angrobe
ms.date: 10/11/2016
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
#ms.custom:

---

# Android for Work policy settings in Microsoft Intune

Intune supplies a range of built-in general settings that you can configure on Android for Work devices. Additionally, you can specify Open Mobile Alliance Uniform Resource Identifier (OMA-URI) values to create custom settings that are not available from Intune.

## General configuration policy

Use the Intune **Android for Work general configuration policy** to configure security and work profile settings for your Android for Work devices.

If the setting you are looking for does not appear in this topic, you might be able to create it by using an Android custom policy that lets you use OMA-URI settings to control the device. For more information, go to [Custom policy settings](#custom-policy-settings) later in this topic.

> [!TIP]
> Devices are automatically encrypted when you provision a work profile. You cannot change this setting.

### Password settings

|Setting name|Details|
|----------------|-|
|**Require a password to unlock mobile devices**|Specifies whether a password is required on managed devices.|
|**Minimum password length**|Specifies the minimum number of characters or numbers in the password.|
|**Number of repeated sign-in failures to allow before the work profile is removed**|Specifies the number of sign-in failures to allow before the work profile on the device is removed. This does not perform a full device wipe.|
|**Minutes of inactivity before device locks**|Specifies the number of minutes of inactivity before the device automatically locks.|
|**Password expiration (days)**|Specifies the number of days before the password must be changed.|
|**Remember password history**|Prevents the reuse of previously used passwords.|
|**Remember password history** - **Prevent reuse of previous passwords**|Specifies the number of previously used passwords to remember.|
|**Password quality**|Specifies the password complexity level that's required and whether biometric devices can be used.|
|**Allow fingerprint unlock**<br>(Android 6 and later)|Lets you use a fingerprint to unlock devices with this capability.|
|**Allow Smart Lock and other trust agents**<br>(Android 6 and later)|Lets you control the Smart Lock feature on compatible Android devices. This phone capability, sometimes known as a trust agent, lets you disable or bypass the device lock screen password if the device is in a trusted location (for example, when it's connected to a specific Bluetooth device, or when it's close to an NFC tag.) You can use this setting to prevent users from configuring Smart Lock.|

### Work profile settings

|Setting name|Details|
|----------------|-|
|**Allow data sharing between work and personal profiles**|Lets apps in the work profile share data with apps in the users personal profile.|
|**Hide work profile notifications when the device is locked**<br>(Android 6 and later)|Don't show any notifications from the work profile when the device is locked.|
|**Set default app permission policy**|Sets the default permission policy for all apps in the work profile. Choose from<br>-**Prompt** - Ask the user to grant permissions to apps that require them.<br>-**Auto grant** - Automatically grant apps in the work profile any permissions they need.<br>-**Auto deny** - Automatically deny apps in the work profile any permissions they need.|



## Custom policy settings
Use the Microsoft Intune **Android for Work custom configuration policy** to deploy OMA-URI settings that can be used to control features on Android for Work devices. These are standard settings that many mobile device manufacturers use to control device features.

This capability is intended to allow you to deploy Android settings that are not configurable with Intune policies.

> [!NOTE]
> Currently, Android custom policies only support configuring Wi-Fi settings for Android devices that include a pre-shared key.

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