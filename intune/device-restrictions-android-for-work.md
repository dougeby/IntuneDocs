---
# required metadata

title: Microsoft Intune device restriction settings for Android for Work 
titlesuffix:
description: Learn the Intune settings you can use to control device settings and functionality on devices running Android for Work.
keywords:
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/2/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Microsoft Intune Android for Work device restriction settings

This article shows you all the Microsoft Intune device restrictions settings that you can configure for devices running Android for Work.

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## Work profile settings

### General Settings

- 	**Copy and paste between work and personal profiles** - Controls copy and paste between work and personal apps. Choose **Block** to enabling blocking. Choose **Not configured** to disable blocking.
- **Data sharing between work and personal profiles** - Use this setting to control whether apps in the work profile can share with apps in the personal profile. This setting controls sharing actions within applications (for example, the **Share…** option in the Chrome browser app) and does not apply to copy/paste clipboard behavior. Unlike [app protection policy settings](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune), device restriction settings are managed from the Intune portal and use the Android for Work work profile partition to isolate managed apps. Choose from:
	- **Default sharing restrictions** - This setting is the default sharing behavior of the device, which varies depending on the version of Android it is running. By default, sharing from the personal profile to the work profile is allowed. Also by default, sharing from the work profile to the personal profile is blocked. This setting prevents sharing of data from the work to the personal profile. Google does not provide a way to block sharing from the personal profile to work profile on devices running versions 6.0 and later.   
	- **Apps in work profile can handle sharing request from personal profile** - Use this option to enable the built-in Android feature that allows sharing from the personal to work profile. When enabled, a sharing request from an app in the personal profile can share with apps in the work profile. This setting is the default behavior for Android devices running versions earlier than 6.0.
	- **Allow sharing across boundaries** - Enables sharing across the work profile boundary in both directions. When you select this setting, apps in the work profile can share data with unbadged apps in the personal profile. Use this setting with care as it allows managed apps in the work profile to share with apps on the unmanaged side of the device.

- 	**Work profile notifications while device locked** - Controls whether apps in the work profile can display data in notifications when the device is locked.
- 	**Default app permissions** - Sets the default permission policy for all apps in the work profile. Starting with Android 6, the user is prompted to grant certain permissions required by apps when the app is launched. This policy setting lets you decide whether users are prompted to grant permissions for all apps in the work profile. For example, you assign an app to the work profile that requires location access. Normally that app prompts the user to approve or deny location access to the app. This policy lets you decide whether all permissions should be auto-granted without a prompt, auto-denied without a prompt, or let the end user decide. Choose from:
	- 	**Device default**
	- 	**Prompt**
	- 	**Auto grant**
	- 	**Auto deny**

	The grant state for permissions can be further defined for specific apps by defining an App Configuration policy for an individual app (under **Mobile Apps** > **App configuration policies**).

- **Add and remove accounts**

   Prevents end users from manually adding or removing accounts in the work profile.

   For example, when you deploy the Gmail app into an Android for Work profile, you can prevent end users from adding or removing accounts in this work profile.

### Work profile password
- **Require Work Profile Password** - (Android 7.0 and above with work profile enabled) Define a passcode policy that applies just to the apps in the work profile. By default, the end user has the option to use the two separately defined PINs or they can elect to combine them into the stronger of the two.
- **Minimum password length** - Enter the minimum number of characters the user's password must contain (from **4**-**16**)
- **Maximum minutes of inactivity until work profile locks** - Select the amount of time before the work profile locks. The user must then enter their credentials to regain access.
- **Number of sign-in failures before wiping device** - Enter the number of times an incorrect password can be entered before the work profile is wiped from the device.
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
- **Smart Lock and other trust agents** - Lets you control the Smart Lock feature on compatible devices. This phone capability, sometimes known as a trust agent, lets you disable or bypass the work profile password if the device is in a trusted location (for example, when it's connected to a specific Bluetooth device, or when it's close to an NFC tag). You can use this setting to prevent users from configuring Smart Lock.

## Device password

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
- **Smart Lock and other trust agents** - Lets you control the Smart Lock feature on compatible devices. This phone capability, sometimes known as a trust agent, lets you disable or bypass the device lock screen password if the device is in a trusted location (for example, when it's connected to a specific Bluetooth device, or when it's close to an NFC tag). You can use this setting to prevent users from configuring Smart Lock.

## System security

 - **Threat scan on apps** - Enforce that the **Verify Apps** setting is on for work and personal profiles.

   > [!Note]  
   > This setting only works for devices that are Android O and above. 

## Next steps

Use the information in [How to configure device restriction settings](device-restrictions-configure.md) to save and assign the profile to users and devices.
