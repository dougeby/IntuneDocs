---
title: Windows 10 configuration policy settings in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855
author: robstackmsft
---
# Windows 10 configuration policy settings in Microsoft Intune
Use the [!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)] **general configuration policy** for Windows 10 to configure settings for enrolled Windows 10 desktop, and Windows 10 Mobile devices:



## Security settings

### Password

|Setting name|Details|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Require a password to unlock devices**|Require a password on supported devices.|Yes|Yes|
|**Required password type**|Specifies the type of password that will be required, such as numeric only, or alphanumeric|Yes|Yes|
|**Required password type** - **Minimum number of character sets**|There are four character sets, lowercase letters, uppercase letters, numbers, and symbols. This setting specifies how many different character sets must be included in the password.|Yes|Yes|
|**Minimum password length (Windows 10 Desktop only)**|This setting is no longer supported and will be removed in the future. You can use the setting for Windows 10 Mobile below for desktop computers.|Yes|No|
|**Minimum password length (Windows 10 Mobile only)**|-|No|Yes|
|**Number of repeated sign-in failures to allow before the device is wiped**|Wipes the device if this number of login attempts fail.|Yes|Yes|
|**Minutes of inactivity before screen turns off**|Yes|Yes|
|**Password expiration (days)**|Yes|Yes|
|**Remember password history**|-|Yes|Yes|
|**Remember password history** - **Prevent reuse of previous passwords**|Yes|Yes|
|**Allow picture password and PIN**|Lets you use simple gestures on a picture, or a simple PIN to login.|Yes|No|
|**Require a password when the device returns from an idle state**|No|Yes|

### Encryption

|Setting name|Details|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Require encryption on mobile device**|-|No|Yes|

### System

|Setting name|Details|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Allow screen capture**|Let's the user capture the device screen as an image.|No|Yes|
|**Allow manual unenrollment**|Lets the user manually delete the workplace account from the device.|Yes|Yes|
|**Allow manual root certificate installation**|Specifies whether the user can manually install root certificates|No|Yes|
|**Allow diagnostic and usage data to be sent to Microsoft**|Yes|Yes|

## Cloud settings

### Account and synchronization

|Setting name|Details|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Allow Microsoft account**|Yes|Yes|
|**Allow adding non-Microsoft accounts manually**|Yes|Yes|
|**Allow settings synchronization for Microsoft accounts**|Yes|Yes|

## Email settings

|Setting name|Details|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Make Microsoft account optional in Windows Mail application**|Configure this to remove the requirement for a Microsoft account in Windows Mail.|Yes|No|

## Application settings

### Microsoft Edge

|Setting name|Details|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Allow web browser**|Allow the use of the Edge web browser on the device.|No|Yes|
|**Allow search suggestions in address bar**|Lets your search engine suggest sites as you type search phrases.|Yes|Yes|
|**Allow sending intranet traffic to Internet Explorer**|Yes|No|
|**Allow do not track**|Yes|Yes|
|**Enable SmartScreen**|Yes|Yes|
|**Allow active scripting**|-|Yes|Yes|
|**Allow pop-ups**|Enables or disables the browser pop-up blocker.|Yes|No|
|**Allow cookies**|Allow or disable cookies.|Yes|Yes|
|**Allow Autofill**|Allow users to change autocomplete settings in the browser.|Yes|No|
|**Allow Password Manager**|Yes|Yes|
|**Enterprise Mode site list location**|Specifies where to find the list of web sites that will open in Enterprise mode. Users cannot edit this list.|Yes|No|

### Apps

|Setting name|Details|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Allow application store**|-|No|Yes|

## Device capability settings

### Cellular

|Setting name|Details|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Allow data roaming**|Allow roaming between networks when accessing data.|Yes|Yes|
|**Allow VPN over cellular**|Yes|Yes|
|**Allow VPN roaming over cellular**|Yes|Yes|

### Hardware

|Setting name|Details|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Allow camera**|Specifies whether the device camera can be used.|Yes|Yes|
|**Allow removable storage**|Specifies whether external storage devices such as an SD card can be used with the device.|Yes|Yes|
|**Allow Wi-Fi**|Allows the use of the devices Wi-Fi capability.|No|Yes|
|**Allow internet sharing**|Allow the use of Internet connection sharing on the device.|Yes|Yes|
|**Allow manual Wi-Fi configuration**|Controls whether the user can configure their own Wi-Fi connections, or whether they can only use connections configured by a Wi-Fi profile.|No|Yes|
|**Allow automatic connection to free Wi-Fi hotspots**|Yes|Yes|
|**Allow geolocation**<br /><br />Specifies whether the device can use location services information.|Yes|Yes|
|**Allow NFC**|Yes|Yes|
|**Allow Bluetooth**|Yes|Yes|
|**Allow Bluetooth discoverable mode**|Yes|Yes|
|**Allow Bluetooth advertising**<br /><br />Allows devices to receive advertisements over Bluetooth.|Yes|Yes|
|**Allow Bluetooth connectable mode** **Important:** |This setting is no longer supported by Windows 10 and will be removed in the future.|Yes|Yes|
|**Allow phone reset**|Yes|Yes|
|**Allow USB connection**|Yes|Yes|
|**Allow AntiTheft mode**|Configure whether Windows Antitheft mode is enabled.|Yes|Yes|

### Features

|Setting name|Details|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Allow copy and paste**|No|Yes|
|**Allow voice recording**|No|Yes|
|**Allow Cortana**|-|Yes|Yes|
|**Allow action center notifications**|-|No|Yes|

## Updates settings

|Setting name|Details|Windows 10 Desktop|Windows 10 Mobile|
|----------------|---------------|----------------------|---------------------|
|**Allow automatic updates**|Enable this setting to allow automatic updates. Then, configure one of the following settings to control update behavior:<br /><br />**Notify download**<br /><br />**Auto install at maintenance time**<br /><br />**Auto install and reboot at maintenance time**<br /><br />**Auto install and reboot at scheduled time** **Note:** When this option is selected, you can also configure the following settings:  **Suppress notification to end user** and **Define install day for scheduled updates**.|Yes|No|



### See Also
[Use policies to manage computers and mobile devices with Microsoft Intune](use-policies-to-manage-computers-and-mobile-devices-with-microsoft-intune.md)

