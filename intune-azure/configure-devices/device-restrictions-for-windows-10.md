---
# required metadata

title: Intune Device restriction settings for Windows 10 devices | Microsoft Docs
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
ms.assetid: 89f2d806-2e97-430c-a9a1-70688269627f

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Windows 10 and later device restriction settings

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## General
- 	**Screen capture** - Let's the user capture the device screen as an image. (Windows 10 Mobile only)	
- 	**Copy and paste (mobile only)**	
- 	**Manual unenrollment** - Lets the user manually delete the workplace account from the device.	
- 	**Manual root certificate installation** - 	
- 	**Diagnostic data submission** - 	
- 	**Camera**	
- 	**Removable storage** - Specifies whether external storage devices such as an SD card can be used with the device.	
- 	**Geolocation**	
- 	**Internet sharing** - Allow the use of Internet connection sharing on the device.	
- 	**Phone reset** - 	
- 	**USB connection** - Controls whether devices can access external storage devices through a USB connection.	
- 	**AntiTheft mode** - 	
- 	**Action center notifications**	
- 	**Cortana** - 	
- 	**Voice recording** - 	
## Password
- 	**Password required** - Require the end user to enter a password to access the device.	
- 	**Required password type** - Specifies whether the password must be numeric only, or alphanumeric.	
- 	**Minimum password length** - 	
- 	**Number of sign-in failures before wiping device**	
- 	**Maximum minutes of inactivity until screen locks** - 	
- 	**Password expiration (days)** - 	
- 	**Prevent reuse of previous passwords** - 	
- 	**Require password when device returns from idle state**	
- 	**Encryption** - 	
## App Store

- 	**App store (mobile only)** - 	
## Edge Browser
- 	**Microsoft Edge browser (mobile only)** - Allow the use of the Edge web browser on the device.	
- 	**SmartScreen** - 	
- 	**Send do-not-track headers** - Configures the Edge browser to send do not track headers to websites that users visit.	
- 	**Cookies** - 	
- 	**JavaScript**	
- 	**Pop-ups**	
- 	**Search suggestions** - 	
- 	**Send intranet traffic to Internet Explorer** - 	
- 	**Autofill** - 	
- 	**Password Manager** - 	
- 	**Enterprise mode site list location** - 	
## Cloud and Storage
- 	**Microsoft account** - 	
- 	**Non-Microsoft account** - 	
- 	**Settings synchronization for Microsoft account** - 	
## Cellular and Connectivity
- 	**Data roaming** - Allow roaming between networks when accessing data.	
- 	**VPN over the cellular network** - Controls whether the device can access VPN connections when connected to a cellular network.
- 	**VPN roaming over the cellular network** - Controls whether the device can access VPN connections when roaming on a cellular network.	
- 	**Bluetooth** - Controls whether the user can enable and configure Bluetooth on the device.	
- 	**Bluetooth discoverability** - Lets the device be discovered by other Bluetooth-enabled devices.	
- 	**Bluetooth advertising** - Lets the device receive advertisements over Bluetooth.	
- 	**NFC**	- Lets the user enable and configure Near Field Communications capabilities on the device.
- 	**Wi-Fi** - Lets the user enable and configure Wi-Fi on the device (Windows 10 Mobile only).
- 	**Automatically connect to Wi-Fi hotspots** - Lets the device automatically connect to free Wi-Fi hotspots and automatically accept any terms and conditions for the connection.
- 	**Manual Wi-Fi configuration** - Controls whether the user can configure their own Wi-Fi connections, or whether they can only use connections configured by a Wi-Fi profile (Windows 10 Mobile only).
## Defender	

- 	**Real-time monitoring** - Enables real-time scanning for malware, spyware, and other unwanted software.	
- 	**Behavior monitoring**	- Lets Defender check for certain known patterns of suspicious activity on devices.
- 	**Network Inspection System (NIS)**	- The Network Inspection System (NIS) helps to protect devices against network-based exploits by using the signatures of known vulnerabilities from the Microsoft Endpoint Protection Center to help detect and block malicious traffic.
- 	**Scan all downloads** - Controls whether Defender scans all files downloaded from the Internet.	
- 	**Scan scripts loaded in Microsoft web browsers** - 
- 	**End user access to Defender**	- 
- 	**Signature update interval (in hours)** - 
- 	**Monitor file and program activity** - 	
- 	**Days before deleting quarantined malware** - 	
- 	**CPU usage limit during a scan** - 
- 	**Scan archive files** - 	
- 	**Scan incoming mail messages**	- 
- 	**Scan removable drives during a full scan** - 	
- 	**Scan mapped network drives during a full scan** - 
- 	**Scan files opened from network folders** - 
- 	**Cloud protection** - 
- 	**Prompt users before sample submission** - 	
- 	**Time to perform a daily quick scan** - 
- 	**Type of system scan to perform** - 	
## Defender Exclusions

- 	**Files and folders to exclude from scans and real-time protection** - 
- 	**File extensions to exclude from scans and real-time protection** - 
- 	**Processes to exclude from scans and real-time protection** - 	
