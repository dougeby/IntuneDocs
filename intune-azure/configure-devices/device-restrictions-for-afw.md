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
	- 	**Device default**
	- 	**Data sharing between work and personal profiles**
	- 	**Apps in work profile can handle sharing request from personal profile**
	- 	**No restrictions on sharing**
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
	- **Numeric complex**
	- **At least alphabetic**
	- **At least alphanumeric**
	- **At least alphanumeric with symbols**
- **Prevent reuse of previous passwords** - Enter the number of new passwords that must have been used before an old one can be reused (from **1**-**24**).
- **Fingerprint unlock** - Blocks an end user from using the device fingerprint scanner to unlock it.
- **Smart Lock and other trust agents** - Lets you control the Smart Lock feature on compatible devices. This phone capability, sometimes known as a trust agent, lets you disable or bypass the device lock screen password if the device is in a trusted location (for example, when it's connected to a specific Bluetooth device, or when it's close to an NFC tag) You can use this setting to prevent users from configuring Smart Lock.

