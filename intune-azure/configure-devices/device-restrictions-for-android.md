---
# required metadata

title: Intune device restriction settings for Android devices | Intune Azure preview | Microsoft Docs
description: "Intune Azure preview: Learn the Intune settings you can use to control device settings and functionality on Android devices."
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/03/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 6bdf714a-5d93-485c-8b52-513635c60cb6

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Android and Samsung KNOX Standard device restriction settings

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## General	
- 	**Camera** - Allows the use of the device camera.	
- 	**Copy and paste** - Allows copy and paste functions on the device.	
- 	**Clipboard sharing between apps** - Allows use of the clipboard to copy and paste between apps.	
- 	**Diagnostic data submission** - 	
- 	**Factory reset** - Allows the user to perform a factory reset on the device.	
- 	**Geolocation** - Allows the device to utilize location information (Samsung KNOX Standard only).	
- 	**Power off** - Allows the user to power off the device.<br>If this setting is disabled, the setting **Number of sign in failures before wiping device** for Samsung KNOX Standard devices does not function.	
- 	**Screen capture** - Lets the user capture the screen contents as an image.	
- 	**Voice assistant** - Allows the use of voice assistant software on the device.	
- 	**YouTube** - Allows the use of the YouTube app on the device.	
		
## Password	
- 	**Password required** - Require the end user to enter a password to access the device.	
- 	**Minimum password length**	- Enter the minimum length of password a user must configure (between 4 and 16 characters).
- 	**Maximum minutes of inactivity until screen locks** - Specifies the number of minutes of inactivity before the device automatically locks.	
- 	**Number of sign-in failures before wiping device** - Specifies the number of sign-in failures to allow before the device is wiped.	
- 	**Password expiration (days)** - Specifies the number of days before the device password must be changed.	
- 	**Required password type** - Specifies the password complexity level that's required and whether biometric devices can be used.	
- 	**Prevent reuse of previous passwords** - Stops the end user from creating a password they have used before.	
- 	**Fingerprint unlock** - Allows the use of a fingerprint to unlock supported devices.	
- 	**Smart Lock and other trust agents** - Lets you control the Smart Lock feature on compatible Android devices. This phone capability, sometimes known as a trust agent, lets you disable or bypass the device lock screen password if the device is in a trusted location (for example, when it's connected to a specific Bluetooth device, or when it's close to an NFC tag.) You can use this setting to prevent users from configuring Smart Lock.	
- 	**Encryption** - Requires that files on the device are encrypted.	
		
## Google Play Store	

- 	**Google Play store** - Allows the user to access the Google Play store on the device.	
		
## Restricted apps	

In the restricted apps list, you can configure one of the following lists:

A **Prohibited apps** list - List the apps (not managed by Intune) that users are not allowed to install and run.
An **Approved apps** list - List the apps that users are allowed to install. To remain compliant, users must not install apps that are not listed. Apps that are managed by Intune are automatically allowed.

To configure the list, click **Add**, then specify a name of your choice, optionally the app publisher, and the URL to the app in the app store.

### How to specify the URL to an app in the store

To specify an app URL in the compliant and noncompliant apps list, take the following steps:

In the [Apps section of Google Play](https://play.google.com/store/apps), search for the app you want to use.

Open the installation page for the app, and then copy the URL to the clipboard. You can now use this as the URL in either the compliant or noncompliant apps list.

Example: Search Google Play for Microsoft Office Mobile. The URL you use will be **https://play.google.com/store/apps/details?id=com.microsoft.office.officehub**.

### Additional options

You can also click **Import** to populate the list from a csv file in the format <*app url*>, <*app name*>, <*app publisher*> or click **Export** to create a csv file containing the contents of the restricted apps list in the same format.		
		
## Browser	
- 	**Web browser** - Specifies whether the device's default web browser can be used.	
- 	**Autofill** - Allows the autofill function of the web browser to be used.	
- 	**Cookies** - Allows the device web browser to use cookies.	
- 	**Javascript** - Allows the device web browser to run Java scripts.	
- 	**Pop-ups** - Allows the use of the pop-up blocker in the web browser.	
 		
## Cloud and Storage	
- 	**Google backup** - Allows the use of Google backup.	
- 	**Google account auto sync** - Allows Google account settings to be automatically synchronized.	
- 	**Removable storage** - Allows the device to use removable storage, like an SD card.	
- 	**Encryption on storage cards** - Specifies whether the device storage card must be encrypted.	
		
## Cellular and Connectivity	
- 	**Data roaming** - Allows data roaming when the device is on a cellular network.	
- 	**SMS/MMS messaging** - Allows the use of SMS and MMS messaging on the device.	
- 	**Voice dialing** - Enables or disables the voice dialing feature on the device.	
- 	**Voice roaming** - Allows voice roaming when the device is on a cellular network.	
- 	**Bluetooth** - Allows the use of Bluetooth on the device (Samsung KNOX Standard only).	
- 	**NFC** - Allows operations that use near field communication if the device supports it (Samsung KNOX Standard only).	
- 	**Wi-Fi** - Allows the use of the Wi-Fi capabilities of the device (Samsung KNOX Standard only).	
- 	**Wi-Fi tethering** - Allows the use of Wi-Fi tethering on the device (Samsung KNOX Standard only).	
		
## Kiosk	
- 	**Select a managed app** - Browse to, then select a managed app that can run when the device is in kiosk mode (apps specified as a link to the store are not currently supported). No other apps will be allowed to run on the device.	
- 	**Screen sleep button**	- Enables or disables the screen sleep wake button on the device.
- 	**Volume buttons** - Enables or disables the use of the volume buttons on the device.	
