---
# required metadata

title: Windows policy settings 
description: Use the Intune Windows general configuration policy (Windows 8.1 and later) to configure settings for enrolled Windows 8, and Windows 8.1 devices.
keywords:
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 10/11/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 6982a2bc-aafa-475a-9236-4840b709e5a1
ROBOTS: NOINDEX,NOFOLLOW

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Windows policy settings in Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Use the Microsoft Intune **Windows general configuration policy (Windows 8.1 and later)** to configure the following settings for enrolled Windows 8, Windows 8.1, and Windows RT 8.1 devices:

## Applicability settings

|Setting name|Details|
|----------------|----------------------------------|
|**Apply all configurations to Windows 10**|Enables settings in this policy to be applied to Windows 10 devices, in addition to Windows 8 and Windows 8.1 devices.|

## Security settings

|Setting name|Details|
|----------------|------|
|**Required password type**|Specifies the type of password that's required, such as alphanumeric or numeric only.|
|**Required password type – Minimum number of character sets**|Specifies how many different character sets must be included in the password. There are four character sets: lowercase letters, uppercase letters, numbers, and symbols. However, for iOS devices, this setting specifies the number of symbols that must be included in the password.|
|**Minimum password length**|Configures the minimum required length (in characters) for the password.|
|**Number of repeated sign-in failures to allow before the device is wiped**|Wipes the device if the sign-in attempts fail this number of times.|
|**Minutes of inactivity before screen turns off**|Specifies the number of minutes a device must be idle before a password is required to unlock it.|
|**Password expiration (days)**|Specifies the number of days before the device password must be changed.|
|**Remember password history**|Specifies whether the user can configure previously used passwords.|
|**Remember password history** – **Prevent reuse of previous passwords**|Specifies the number of previously used passwords that are remembered by the device.|
|**Allow picture password and PIN**|Enables the use of a picture password and PIN. A picture password lets the user sign in with gestures on a picture. A PIN lets users quickly sign in with a four-digit code.|

## Encryption settings

|Setting name|Details|
|----------------|-----|
|**Require encryption on mobile device**<sup>1</sup>|Requires that files on the device are encrypted.|
<sup>1</sup> Additional information for devices that run Windows 8.1

-   To enforce encryption on devices that run Windows 8.1, you must install the [December 2014 MDM client update for Windows](http://support.microsoft.com/kb/3013816) on each device.

-   If you enable this setting for Windows 8.1 devices, all users of the device must have a Microsoft account.

-   For encryption to work, the device must meet the Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) hardware certification requirements.

-   When you enforce encryption on a device, the recovery key is only accessible from the user's Microsoft account, which is accessed from their OneDrive account. You cannot recover this key on behalf of a user.

## Malware settings

|Setting name|Details|
|----------------|-----|
|**Require network firewall**|Requires that the Windows Firewall is turned on.|
|**Enable SmartScreen**|Requires the use of Windows SmartScreen.|

## System settings

|Setting name|Details|
|----------------|-------|
|**Require automatic updates**|Turns on the automatic updates setting on devices.|
|**Require automatic updates – Minimum classification of updates to install automatically**|Chooses the classification of updates that will be installed automatically:<br /><br />-   **Important** – Installs all updates that are classified as important.<br />-   **Recommended** – Installs all updates that are classified as important or recommended.|
|**User Account Control**|Requires the use of User Account Control (UAC) on devices.|
|**Allow diagnostic data submission**|Enables the device to submit diagnostic information to Microsoft.|


## Cloud settings – documents and data

|Setting name|Details|
|----------------|------|
|**Work Folders URL**|Sets the URL of the work folder to allow documents to be synchronized across devices.|

## Email settings

|Setting name|Details|
|----------------|-----|
|**Make Microsoft account optional in Windows Mail application**|Enables access to the Windows Mail application without a Microsoft account.|

## Application settings - browser

|Setting name|Details|
|----------------|-----|
|**Allow autofill**|Enables users to change autocomplete settings in the browser.|
|**Allow pop-up blocker**|Enables or disables the browser pop-up blocker.|
|**Allow plug-ins**|Enables users to add plug-ins to Internet Explorer.|
|**Allow active scripting**|Enables the browser to run scripts, such as Active X scripts.|
|**Allow fraud warning**|Enables or disables warnings for potential fraudulent websites.|
|**Allow intranet site for single word entry**|Enables use of a single word to direct Internet Explorer to a web site, such as Bing.|
|**Allow automatic detection of intranet network**|Helps configure security for intranet sites in Internet Explorer.|
|**Security level for Internet**|Sets the Internet Explorer security level for Internet sites.|
|**Security level for intranet**|Sets the Internet Explorer security level for intranet sites.|
|**Security level for trusted sites**|Configures the security level for the trusted sites zone.|
|**Security level for restricted sites**|Configures the security level for the restricted sites zone.|
|**Send Do Not Track header**|Sends  a do not track header to visited sites in Internet Explorer.|
|**Allow Enterprise Mode menu access**|Lets users access the Enterprise Mode menu options from Internet Explorer.<br>If you select this setting, you can also specify a **Logging report location**, which contains a URL to a report that shows websites for which users have turned on Enterprise Mode access.|
|**Enterprise Mode site list location**|Specifies the location of the list of websites that will use Enterprise Mode when it is active.|

## Device capabilities settings - cellular

|Setting name|Details|
|----------------|----|
|**Allow data roaming**|Enables data roaming when the device is on a cellular network.|



### See also
[Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
