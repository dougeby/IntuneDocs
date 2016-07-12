---
# required metadata

title: Windows policy settings | Microsoft Intune
description: Use the Intune Windows general configuration policy (Windows 8.1 and later) to configure settings for enrolled Windows 8, and Windows 8.1 devices.
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 6982a2bc-aafa-475a-9236-4840b709e5a1

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Windows policy settings in Microsoft Intune
Use the Microsoft Intune **Windows general configuration policy (Windows 8.1 and later)** to configure the following settings for enrolled Windows 8, and Windows 8.1 devices:

## Applicability settings

|Setting name|Details|
|----------------|----------------------------------|
|**Apply all configurations to Windows 10**|Allows settings in this policy to be applied to Windows 10 devices in addition to Windows 8, and Windows 8.1 devices.|

## Security settings

|Setting name|Details|Windows 8.1 and Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Required password type**|Specifies the type of password that will be required, such as numeric only, or alphanumeric.|Yes|Yes|
|**Required password type – Minimum number of character sets**|There are four character sets, lowercase letters, uppercase letters, numbers, and symbols. This setting specifies how many different character sets must be included in the password. However, for iOS devices, this specifies the number of symbol characters must be included in the password.|Yes|Yes|
|**Minimum password length**<sup>1</sup>|Configures the minimum required length (in characters) for the password on devices.|Yes|Yes|
|**Number of repeated sign-in failures to allow before the device is wiped**|Wipes the device if the login fails this number of times.|Yes|Yes|
|**Minutes of inactivity before screen turns off**|Choose the number of minutes a device must be idle before a password is required to unlock it.| Yes|Yes|
|**Password expiration (days)**|Specifies the number of days before the device password must be changed.|Yes|Yes|
|**Remember password history**|Specifies whether the user can configure previously used passwords.|Yes|Yes|
|**Remember password history** – **Prevent reuse of previous passwords**|Specifies the number of previously used passwords that are remembered by the device.|Yes|Yes|
|**Allow picture password and PIN**|Allows the use of a picture password and PIN on the device. A picture password lets the user log in with gestures on a picture. A PIN lets the users quickly sign in with a 4 digit code.|Yes|Yes|
<sup>1</sup> When you set deploy a password length policy to devices that run Windows RT, users will be forced to reset their password, even if their current password complies with the policy requirements.

## Encryption settings

|Setting name|Details|Windows 8.1 and Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Require encryption on mobile device**<sup>1</sup>|Requires that files on the device are encrypted.<br>For Windows Phone 8 devices, you must set this to **Yes**.|Yes|No|
<sup>1</sup> Additional information for devices that run Windows 8.1

-   To enforce encryption on devices that run Windows 8.1, you must install the [December 2014 MDM client update for Windows](http://support.microsoft.com/kb/3013816) on each device.

-   If you enable this setting for Windows 8.1 devices, all users of the device must have a Microsoft Account.

-   For encryption to work, the device must meet the Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) hardware certification requirements.

-   When you enforce encryption on a device, the recovery key is only accessible from the users Microsoft Account, accessed from their OneDrive account. You cannot recover this key on behalf of a user.

## Malware settings

|Setting name|Details|Windows 8.1 and Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Require network firewall**|Require that the Windows Firewall is turned on.|Yes|No|
|**Enable SmartScreen**|Require the use of Windows SmartScreen on devices.|Yes|No|

## System settings

|Setting name|Details|Windows 8.1 and Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Require automatic updates**|Turn on the automatic updates setting on devices.|Yes|No|
|**Require automatic updates – Minimum classification of updates to install automatically**|Choose the classification of updates that will be installed automatically:<br /><br />-   **Important** – Installs all updates classified as important.<br />-   **Recommended** – Installs all updates classified as important or recommended.|Yes|No|
|**User Account Control**|Require the use of User Account Control (UAC) on devices.|Yes|No|
|**Allow diagnostic data submission**|Allow the device to submit diagnostic information to Microsoft.|Yes|No|


## Cloud settings – documents and data

|Setting name|Details|Windows 8.1 and Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Work Folders URL**|Sets the URL of the work folder to allow documents to be synchronized across devices)|Yes|No|

## Email settings

|Setting name|Details|Windows 8.1 and Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Make Microsoft account optional in Windows Mail application**|Allows access to the Windows Mail application without a Microsoft account.|Yes|No|

## Application settings - browser

|Setting name|Details|Windows 8.1 and Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Allow autofill**|User can change autocomplete settings in the browser.|Yes|No|
|**Allow pop-up blocker**|Enables or disables the browser pop-up blocker.|Yes|No|
|**Allow plug-ins**|User can add plug-ins to Internet Explorer.|Yes|No|
|**Allow active scripting**|Browser can run scripts, such as Active X scripts.|Yes|No|
|**Allow fraud warning**|Enable or disable warnings of potential fraudulent websites.|Yes|No|
|**Allow intranet site for single word entry**|Allows use of a single word to direct Internet Explorer to a web site, such as Bing.|Yes|No|
|**Allow automatic detection of intranet network**|Helps configure security for intranet sites in Internet Explorer.|Yes|No|
|**Security level for Internet**|Set the Internet Explorer security level for Internet sites.|Yes|No|
|**Security level for intranet**|Set the Internet Explorer security level for intranet sites.|Yes|No|
|**Security level for trusted sites**|Configure the security level for the trusted sites zone.|Yes|No|
|**Security level for restricted sites**|Configure the security level for the restricted sites zone.|Yes|No|
|**Send Do Not Track header**|In Internet Explorer, send a do not track header to visited sites.|Yes|No|
|**Allow Enterprise Mode menu access**|Lets users access the Enterprise Mode menu options from Internet Explorer.<br>If selected, you can also specify a **Logging report location** which contains a URL to a report which shows websites for which users have turned on Enterprise Mode access.|Yes|No|
|**Enterprise Mode site list location**|Specify the location of the list of websites that will use Enterprise Mode when it is active.|Yes|No|

## Device capabilities settings - cellular

|Setting name|Details|Windows 8.1 and Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Allow data roaming**|Allow data roaming when the device is on a cellular network.|Yes|No|



### See also
[Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)

