---
# required metadata

title: Intune device restriction settings for Android for Work
titleSuffix: "Intune Azure preview"
description: "Intune Azure preview: Learn the Intune settings you can use to control device settings and functionality on Android for Work devices."
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 1830720b-16cb-4f2f-a71a-62967f882563

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Android for Work device restriction settings in Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## Work profile settings
- 	**Data sharing between work and personal profiles** - Use this setting to control whether apps in the work profile can share data with apps in the personal profile. Choose from:
	- **Default sharing restrictions** - This is the default sharing behavior of the device which varies depending on the version of Android it is running. By default, sharing from the personal to the work profile is allowed. Also by default, sharing between the work profile and personal profile is blocked. This prevents leakage of data from the work to the personal profile. Google does not provide a way to block data going from the personal profile to work profile on devices running versions earlier than 6.0.  
	- **Apps in work profile can handle sharing request from personal profile** - Use this option to enable the built-in Android feature that allows sharing from the personal to work profile. When this is enabled, a sharing request initiated from an app in the personal profile will be able to share with apps in the work profile. This is the default behavior for Android devices running versions earlier than 6.0.
	- **Apps in personal profile can handle sharing request from work profile** - Enables sharing across the work profile boundary in both directions. When you select this setting, apps in the work profile can share data with unmanaged apps in the personal profile.  Use this setting with care as this allows managed data in the work profile to be transferred to the unmanaged side of the device.


- 	**Work profile notifications while device locked** - Control whether apps in the work profile can display on-screen notifications when the device is locked.
- 	**Default app permissions** - Sets the default permission policy for all apps in the work profile. Starting in Android 6, some permissions required by apps are prompted to the end user at runtime. This policy setting allows you to decide how or if users are prompted to grant permissions for apps in the work profile.
For example, you push an app to the work profile that requires location access. Normally that app would pop up a dialog to the user asking if they wanted to grant location access to the app, and the user could approve it or deny it. This policy allows you to decide whether all permissions should be auto-granted without a prompt, auto-denied without a prompt, or let the end user decide. Choose from:
	- 	**Device default**
	- 	**Prompt**
	- 	**Auto grant**
	- 	**Auto deny**

## Password

- **Minimum password length** - Enter the minimum number of characters the users password must contain (from **4**-**14**)
- **Maximum minutes of inactivity until screen locks** - Select the amount of time before an inactive device automatically locks.
- **Number of sign-in failures before wiping device** - Enter the number of times an incorrect password can be entered before all data is wiped from the device.
- **Password expiration (days)** - Enter the number of days until an end user's password must be changed (from **1**-**255**).
- **Required password type** - Select the type of password that must be set on the device. Choose from:
	- **Device default**
	- **Low security biometric**
	- **Required**
	- **At least numeric**
	- **Numeric complex** - (repeating, or consecutive numbers like '1111' or '1234' are not allowed)
	- **At least alphabetic**
	- **At least alphanumeric**
	- **At least alphanumeric with symbols**
- **Prevent reuse of previous passwords** - Enter the number of new passwords that must have been used before an old one can be reused (from **1**-**24**).
- **Fingerprint unlock** - Blocks an end user from using the device fingerprint scanner to unlock it.
- **Smart Lock and other trust agents** - Lets you control the Smart Lock feature on compatible devices. This phone capability, sometimes known as a trust agent, lets you disable or bypass the device lock screen password if the device is in a trusted location (for example, when it's connected to a specific Bluetooth device, or when it's close to an NFC tag) You can use this setting to prevent users from configuring Smart Lock.

## Custom policy settings
Use the Microsoft Intune **Android for Work custom configuration policy** to deploy OMA-URI settings that can be used to control features on Android for Work devices. These are standard settings that many mobile device manufacturers use to control device features.

This capability is intended to allow you to deploy Android settings that are not configurable with Intune policies.
Intune supports a limited number of Android custom policies at present. See the examples in this topic to find out which policies you can configure.

### General settings

|Setting name|Details|
    |----------------|--------------------|
    |**Name** |Enter a unique name for the Android custom policy to help you identify it in the Intune console.|
    |**Description** |Provide a description that gives an overview of the Android custom policy and other relevant information that helps you to locate it.|

### OMA-URI settings

  |Setting name|Details|
  |--------|--------------------|
  |**Name** |Enter a unique name for the OMA-URI setting to help you identify it in the list of settings.|
  |**Description** |Provide a description that gives an overview of the setting and other relevant information to help you locate it.|
	|**OMA-URI (case sensitive)** |Specify the OMA-URI you want to supply a setting for.|
  |**Data type** |Select the data type in which you will specify this OMA-URI setting. Choose from **String, String (XML), Date and time, Integer, Floating point**, or **Boolean**.|
  |**Value** |Specify the value to associate with the OMA-URI that you specified previously.|
