---
# required metadata

title: Intune device restrictions settings for iOS devices | Microsoft Docs
description: Description.
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/03/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 73590192-54ca-4833-9f1d-83e1b654399f

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# iOS device restriction settings

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## General	
- 	**Camera** - Select whether the camera on the device can be used. 	
- 	**Diagnostic data submission** - Allow or block the device from submitting diagnostic data to Apple.	
- 	**FaceTime** - Allow the FaceTime app to be used on the device.	
- 	**Screen capture** - Allow the user to capture the contents of the screen as an image.	
- 	**Siri** - Allow use of the Siri voice assistant on the device.	
- 	**Siri while device is locked** - Allow use of the Siri voice assistant on the device while it is locked.	
- 	**Siri profanity filter (supervised only)** - Prevents Siri from dictating, or speaking profane language.	
- 	**Siri to query user-generated content from the internet (supervised only)** - 	
- 	**Untrusted TLS certificates** - Allow untrusted Transport Layer Security certificates on the device.	
- 	**Control Center access while device locked** - 	
- 	**Notifications while device locked** - 	
- 	**Passbook while device locked** - Allow the user to access the Passbook app while the device is locked.	
- 	**Today view while device locked** - Allow the user to see the Today view when the device is locked.	
- 	**Enterprise app trust** - Lets the user select to trust apps that were not downloaded from the app store.	
- 	**AirDrop (supervised only)** - 	
- 	**Spotlight search to return results from internet (supervised only)** - Let Spotlight search connect to the Internet to provide further results.	
- 	**Word definition lookup (supervised only)** - Allow the iOS feature that lets you highlight a word and look up it's definition.	
- 	**Predictive keyboards (supervised only)** - Allow the use of predictive keyboards that suggest words the user might want.	
- 	**Auto-correction (supervised only)** - Lets the device automatically correct misspelled words.	
- 	**Keyboard spell-check (supervised only)** - 	
- 	**Keyboard shortcuts (supervised only)** - 	
- 	**Wrist detection for paired Apple watch** - When enabled, the Apple Watch won't display notifications when it is not being worn.	
		
## Password	
- 	**Password required** - Require the end user to enter a password to access the device.	
- 	**Simple passwords** - Allow simple passwords like 0000 and 1234.	
- 	**Required password type** - Specify the type of password that will be required, such as numeric only or alphanumeric.	
- 	**Number of non-alphanumeric characters in password** - Specify the number of symbol characters (like **#** or **@**) that must be included in the password.	
- 	**Minimum password length** - Specify the minimum number of characters in the password.
- 	**Number of sign-in failures before wiping device** - Specify the number of failed login attempts before this setting wipes the device.	
- 	**Maximum minutes after screen lock before password is required**<sup>1</sup> - Specify how long the device can remain idle before the user must re-enter their password.	
- 	**Maximum minutes of inactivity until screen locks**<sup>1</sup> - Specify the number of minutes before the device display is turned off.	
- 	**Password expiration (days)** - Specify the number of days before the device password must be changed.	
- 	**Prevent reuse of previous passwords** - Specify the number of previously used passwords that the device remembers.	
- 	**Fingerprint unlock** - Allow using a fingerprint to unlock compatible devices.

<sup>1</sup>When you configure the settings **Maximum minutes of inactivity until screen locks** and **Maximum minutes after screen lock before password is required**, they are applied in sequence. For example, if you set the value for both settings to **5** minutes, the screen will turn off automatically after 5 minutes, and the device will be locked after an additional 5 minutes. However, if the user turns off the screen manually, the second setting is immediately applied. In the same example, after the user turns off the screen, the device will lock 5 minutes later.	
		
## App Store, 
- 	**Doc Viewing, Gaming, App store (supervised only)** - 	
- 	**Password to access app store** - 	
- 	**In-app purchases** - 	
- 	**Explicit iTunes music, podcast, or news content (supervised only)** - Allow the device to access content rated as adult from the store.	
- 	**Download content from iBook store flagged as 'Erotica'** - Allow the user to download books with the "Erotica" category.	
- 	**Viewing corporate documents in unmanaged apps** - 	
- 	**Viewing non-corporate documents in corporate apps** - 	
- 	**Disallow AirDrop from managed apps** - Stops managed apps from being able to send data via. Airdrop.	
- 	**Adding Game Center friends (supervised only)** - Allow the user to add friends in Game Center.	
- 	**Multiplayer gaming (supervised only)** - Allow the user to play multiplayer games on the device.	
		
## Restricted apps	

In the restricted apps list, you can configure one of the following lists:

A **Prohibited apps** list - List the apps (not managed by Intune) that users are not allowed to install and run.
An **Approved apps** list - List the apps that users are allowed to install. To remain compliant, users must not install apps that are not listed. Apps that are managed by Intune are automatically allowed.

To configure the list, click **Add**, then specify a name of your choice, optionally the app publisher, and the URL to the app in the app store.

### How to specify the URL to an app in the store

To specify an app URL in the apps list, use the following format:

Using a search engine, find the app that you want to use in the iTunes App Store and open the page for the app.
Copy the URL of the page and use this as the URL to configure the allowed or prohibited apps list or an app that you want to run in kiosk mode.

Example: Search for Microsoft Word for iPad. The URL that you use will be https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8.

	> [!Note]
	> You can also use the iTunes software to find the app and then use the **Copy Link** command to get the app URL.



### Additional options

You can also click **Import** to populate the list from a csv file in the format <*app url*>, <*app name*>, <*app publisher*> or click **Export** to create a csv file containing the contents of the restricted apps list in the same format.
		
## Cellular	
- 	**Data roaming** - 	
- 	**Global background fetch while roaming** - 	
- 	**Voice dialing** - Allow use of the voice dialing feature on the device.	
- 	**Voice roaming** - 	
		
## Cloud and Storage	
- 	**Backup to iCloud** - 	
- 	**Document sync to iCloud (supervised only)** - 	
- 	**Photo stream syncing to iCloud** - 	
- 	**Encrypted backup** - 	
- 	**iCloud Photo Library** - 	
		
## Kiosk	
- 	**Activation Lock (supervised only)** - Enable Activation Lock on supervised iOS devices.	
- 	**App that runs in kiosk mode** - 	
- 	**Assistive touch** - Enable or disable the **Assistive Touch** accessibility setting, which helps the user perform on-screen gestures that might be difficult for them to perform.	
- 	**Invert colors** - Enable or disable the Invert Colors accessibility setting, which adjusts the display to help users with visual impairments.	
- 	**Mono audio** - 	
- 	**VoiceOver** - Enable or disable the accessibility setting **VoiceOver**, which reads aloud text on the device display.	
- 	**Zoom** - Enable or disable the **Zoom** accessibility setting, which lets the user use touch to zoom in to the device display.	
- 	**Auto lock** - Enable or disable automatic locking of the device.	
- 	**Ringer switch** - 	
- 	**Screen rotation** - Enable or disable changing the screen orientation when the user rotates the device.	
- 	**Screen sleep button** - 	
- 	**Touch** - Enable or disable the touchscreen on the device.	
- 	**Volume buttons** - Enable or disable the use of the volume buttons on the device.	
- 	**Assistive touch control** - Enable or disable assistive touch adjustments, which let the user adjust the assistive touch function.	
- 	**Invert colors control** - Enable or disable invert colors adjustments, which let the user adjust the invert colors function.	
- 	**Speak on selected text** - 	
- 	**VoiceOver control** - Enable or disable voiceover adjustments, which let the user adjust the VoiceOver function (for example, how fast on-screen text is read aloud).	
- 	**Zoom control** - Enable or disable zoom adjustments, which let the user adjust the zoom function.	

>[!NOTE]
> Before you can configure an iOS device for kiosk mode, you must use the Apple Configurator tool or the Apple Device Enrollment Program to put the device into supervised mode. For more information about the Apple Configurator tool, see your Apple documentation.
>If the iOS app that you specify is installed after you deploy the configuration policy, the device will not enter kiosk mode until after it is restarted.
		
## Safari	
- 	**Safari (supervised only)** - 	
- 	**Autofill** - 	
- 	**Cookies** - 	
- 	**JavaScript** - 	
- 	**Fraud warnings** - 	
- 	**Pop-ups** - 	
		
## Domains	
- 	**Unmarked email domain** - 	
- 	**Managed web domains** - 	
- 	**Safari password auto fill domains (supervised only)** - 	
