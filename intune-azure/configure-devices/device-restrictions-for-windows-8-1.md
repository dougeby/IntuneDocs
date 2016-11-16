---
# required metadata

title: Intune device restriction settings for Windows 8.1 devices | Microsoft Docs
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
ms.assetid: fe5785e9-8d35-4ad7-95e8-d50f8d87154a

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Windows 8.1 and later device restriction settings

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## General	
- 	**Apply all configurations to Windows 10** - Enables settings in this policy to be applied to Windows 10 devices, in addition to Windows 8.1 devices.	
- 	**Diagnostic data submission** - 	
- 	**Firewall** - 	
- 	**User Account Control** - 	
## Password
- 	**Required password type** - Require the end user to enter a password to access the device.	
- 	**Minimum password length** - Configures the minimum required length (in characters) for the password.	
- 	**Number of sign-in failures before wiping device** - Wipes the device if the sign-in attempts fail this number of times.	
- 	**Maximum minutes of inactivity until screen locks** - Specifies the number of minutes a device must be idle before a password is required to unlock it.	
- 	**Password expiration (days)** - Specifies the number of days before the device password must be changed. 
- 	**Prevent reuse of previous passwords** - Specifies whether the user can configure previously used passwords.	
- 	**Picture password and PIN** - Enables the use of a picture password and PIN. A picture password lets the user sign in with gestures on a picture. A PIN lets users quickly sign in with a four-digit code.	
- 	**Encryption** - Requires that files on the device are encrypted.<br>To enforce encryption on devices that run Windows 8.1, you must install the [December 2014 MDM client update for Windows](https://support.microsoft.com/en-us/kb/3013816) on each device.
If you enable this setting for Windows 8.1 devices, all users of the device must have a Microsoft account.
For encryption to work, the device must meet the [Microsoft InstantGo](https://blogs.windows.com/windowsexperience/2014/06/19/instantgo-a-better-way-to-sleep/#IBHULcTfI4PokO8X.97) hardware certification requirements.
When you enforce encryption on a device, the recovery key is only accessible from the user's Microsoft account, which is accessed from their OneDrive account. You cannot recover this key on behalf of a user. 	



## Browser	
- 	**Autofill** - Enables users to change autocomplete settings in the browser.	
- 	**Fraud warnings** - Enables or disables warnings for potential fraudulent websites.	
- 	**SmartScreen** - 	
- 	**JavaScript** - 	
- 	**Pop-ups** - Enables or disables the browser pop-up blocker.	
- 	**Send do-not-track headers** - Sends a do not track header to visited sites in Internet Explorer.	
- 	**Plugins** - 	
- 	**Single word entry on intranet site** - 	
- 	**Auto detect of intranet site** - 	
- 	**Internet security level** - Sets the Internet Explorer security level for Internet sites.
- 	**Intranet security level** - Sets the Internet Explorer security level for intranet sites.	
- 	**Trusted sites security level** - 	
- 	**High security for restricted sites** - 	
- 	**Enterprise mode menu access** - 	
- 	**Logging report location URL** - 	
- 	**Enterprise mode site list location** - 	
## Cellular
- 	**Data roaming** - 	
## Cloud and Storage	
- 	**Work folders URL** - Sets the URL of the work folder to allow documents to be synchronized across devices.
- 	**Access to Windows Mail app without a Microsoft account** - Enables access to the Windows Mail application without a Microsoft account. 	
