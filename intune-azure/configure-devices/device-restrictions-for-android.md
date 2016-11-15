---
# required metadata

title: Intune device restriction settings for Android devices | Microsoft Docs
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
- 	**Camera** - 	
- 	**Copy and paste** - 	
- 	**Clipboard sharing between apps** - 	
- 	**Diagnostic data submission** - 	
- 	**Factory reset** - 	
- 	**Geolocation** - Allows the device to utilize location information (Samsung KNOX Standard only).	
- 	**Power off** - 	
- 	**Screen capture** - 	
- 	**Voice assistant** - 	
- 	**YouTube** - 	
		
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

- 	**Google Play store** - 	
		
## Restricted Apps		
		
## Browser	
- 	**Web browser** - 	
- 	**Autofill** - 	
- 	**Cookies** - 	
- 	**Javascript** - 	
- 	**Pop-ups** - 	
 		
## Cloud and Storage	
- 	**Google backup** - 	
- 	**Google account auto sync** - 	
- 	**Removable storage** - 	
- 	**Encryption on storage cards** - 	
		
## Cellular and Connectivity	
- 	**Data roaming** - 	
- 	**SMS/MMS messaging** - 	
- 	**Voice dialing** - 	
- 	**Voice roaming** - 	
- 	**Bluetooth** - Allows the use of Bluetooth on the device (Samsung KNOX Standard only).	
- 	**NFC** - Allows operations that use near field communication if the device supports it (Samsung KNOX Standard only).	
- 	**Wi-Fi** - Allows the use of the Wi-Fi capabilities of the device (Samsung KNOX Standard only).	
- 	**Wi-Fi tethering** - Allows the use of Wi-Fi tethering on the device (Samsung KNOX Standard only).	
		
## Kiosk	
- 	**Select a managed app** - 	
- 	**Screen sleep button**	- 
- 	**Volume buttons** - 	
