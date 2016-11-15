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
- 	**Camera** - 	
- 	**Diagnostic data submission** - 	
- 	**FaceTime** - 	
- 	**Screen capture** - Allow the user to capture the contents of the screen as an image.	
- 	**Siri** - 	
- 	**Siri while device is locked** - 	
- 	**Siri profanity filter (supervised only)** - Prevents Siri from dictating, or speaking profane language.	
- 	**Siri to query user-generated content from the internet (supervised only)** - 	
- 	**Untrusted TLS certificates** - Allow untrusted Transport Layer Security certificates on the device.	
- 	**Control Center access while device locked** - 	
- 	**Notifications while device locked** - 	
- 	**Passbook while device locked** - 	
- 	**Today view while device locked** - 	
- 	**Enterprise app trust** - 	
- 	**AirDrop (supervised only)** - 	
- 	**Spotlight search to return results from internet (supervised only)** - 	
- 	**Word definition lookup (supervised only)** - 	
- 	**Predictive keyboards (supervised only)** - 	
- 	**Auto-correction (supervised only)** - 	
- 	**Keyboard spell-check (supervised only)** - 	
- 	**Keyboard shortcuts (supervised only)** - 	
- 	**Wrist detection for paired Apple watch** - When enabled, the Apple Watch won't display notifications when it is not being worn.	
		
## Password	
- 	**Password required** - Require the end user to enter a password to access the device.	
- 	**Simple passwords** - Allow simple passwords like 0000 and 1234.	
- 	**Required password type** - 	
- 	**Number of non-alphanumeric characters in password** - 	
- 	**Minimum password length** - 
- 	**Number of sign-in failures before wiping device** - 	
- 	**Maximum minutes after screen lock before password is required** - 	
- 	**Maximum minutes of inactivity until screen locks**	
- 	**Password expiration (days)**	
- 	**Prevent reuse of previous passwords** - 	
- 	**Fingerprint unlock** - 	
		
## App Store, 
- 	**Doc Viewing, Gaming, App store (supervised only)** - 	
- 	**Password to access app store** - 	
- 	**In-app purchases** - 	
- 	**Explicit iTunes music, podcast, or news content (supervised only)** - 	
- 	**Download content from iBook store flagged as 'Erotica'** - 	
- 	**Viewing corporate documents in unmanaged apps** - 	
- 	**Viewing non-corporate documents in corporate apps** - 	
- 	**Disallow AirDrop from managed apps** - 	
- 	**Adding Game Center friends (supervised only)** - 	
- 	**Multiplayer gaming (supervised only)** - 	
		
## Restricted apps	

In the restricted apps list, you can configure one of the following lists:

A **Prohibited apps** list - List the apps (not managed by Intune) that users are not allowed to install and run.
An **Approved apps** list - List the apps that users are allowed to install. To remain compliant, users must not install apps that are not listed. Apps that are managed by Intune are automatically allowed.

To configure the list, click **Add**, then specify a name of your choice, optionally the app publisher, and the URL to the app in the app store.

### How to specify the URL to an app in the store

To specify an app URL in the compliant and noncompliant apps list, or in the Select a managed app that will be allowed to run when the device is in kiosk mode option (iOS only), use the following format:

Using a search engine, find the app that you want to use in the iTunes App Store and open the page for the app.
Copy the URL of the page and use this as the URL to configure the compliant or noncompliant apps list or the app that you want to run in kiosk mode.

Example: Search for Microsoft Word for iPad. The URL that you use will be https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8.

	> [!Note]
	> You can also use the iTunes software to find the app and then use the **Copy Link** command to get the app URL.



### Additional options

You can also click **Import** to populate the list from a csv file in the format <*app url*>, <*app name*>, <*app publisher*> or click **Export** to create a csv file containing the contents of the restricted apps list in the same format.
		
## Cellular	
- 	**Data roaming** - 	
- 	**Global background fetch while roaming** - 	
- 	**Voice dialing**	
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
- 	**Invert colors** - 	
- 	**Mono audio** - 	
- 	**VoiceOver** - 	
- 	**Zoom** - Enable or disable the Zoom accessibility setting, which lets the user use touch to zoom in to the device display.	
- 	**Auto lock** - 	
- 	**Ringer switch** - 	
- 	**Screen rotation** - Enable or disable changing the screen orientation when the user rotates the device.	
- 	**Screen sleep button** - 	
- 	**Touch** - Enable or disable the touchscreen on the device.	
- 	**Volume buttons** - 	
- 	**Assistive touch control** - Enable or disable assistive touch adjustments, which let the user adjust the assistive touch function.	
- 	**Invert colors control** - 	
- 	**Speak on selected text** - 	
- 	**VoiceOver control** - 	
- 	**Zoom control** - Enable or disable zoom adjustments, which let the user adjust the zoom function.	
		
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
