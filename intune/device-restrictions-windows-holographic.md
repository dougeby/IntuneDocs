---
# required metadata

title: Intune device restriction settings for Windows Holographic for Business
titlesuffix: "Azure portal"
description: Learn the Intune settings you can use to control device settings and functionality on Windows Holographic for Business devices."
keywords:
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 1/19/2018
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

# Windows Holographic for Business device restriction settings in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

The following device restriction settings are supported on devices running Windows Holographic for Business, such as Microsoft Hololens.

## General

- **Manual unenrollment** - Lets the user manually delete the workplace account from the device.
- **Cortana** - Enable or disable the Cortana voice assistant.
- **Geolocation** - Specifies whether the device can use location services information.



## Password
- 	**Password** - Require the end user to enter a password to access the device.
	- 	**Require password when device returns from idle state** - Specifies that the user must enter a password to unlock the device.



## App Store

- 	**App store** - Enable or block use of the app store on devices.
- 	**Auto-update apps from store** - Allows apps installed from the Microsoft Store to be automatically updated.
- 	**Trusted app installation** - Allows apps signed with a trusted certificate to be sideloaded.
- 	**Developer unlock** - Allow Windows developer settings, such as allowing sideloaded apps to be modified by the end user.

## Edge Browser

- 	**Microsoft Edge browser** - Allow the use of the Edge web browser on the device.
- 	**Cookies** - Lets the browser save internet cookies to the device.
- 	**Pop-ups** - Blocks pop-up windows in the browser (applies to Windows 10 desktop only).
- 	**Search suggestions** - Lets your search engine suggest sites as you type search phrases.
- 	**Password Manager** - Enable or disable the Edge Password Manager feature.
- **Send do-not-track headers** - Configures the Edge browser to send do not track headers to websites that users visit.

## Windows Defender Smart Screen

- **SmartScreen for Microsoft Edge** - Enable Edge SmartScreen for accessing site and file downloads.

## Search
- **Search location** -Specify if search can use location. information


## Cloud and Storage
- 	**Microsoft account** - Lets the user associate a Microsoft account with the device.

## Cellular and Connectivity

- 	**Bluetooth** - Controls whether the user can enable and configure Bluetooth on the device.
- 	**Bluetooth discoverability** - Lets the device be discovered by other Bluetooth-enabled devices.
- 	**Bluetooth advertising** - Lets the device receive advertisements over Bluetooth.

## Control Panel and Settings

- **System Time modification** - Prevents the end user from changing the device date and time.

## Reporting and Telemetry

- **Share usage data** - Select level of diagnostic data submission.