---
# required metadata

title: Intune device restriction settings for Android
titleSuffix: "Intune on Azure"
description: Learn the Intune settings you can use to control device settings and functionality on Android devices."
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/15/2017
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
ms.custom: intune-azure

---

# Android and Samsung KNOX Standard device restriction settings in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Use these settings with an Android device restriction policy to configure devices in your organization.

## General

|||||
|-|-|-|-|
|Setting name|Details|Android 4.0+|Samsung KNOX Standard|
|**Camera**|Allows the use of the device camera.|Yes|Yes|
|**Copy and paste**|Allows copy and paste functions on the device.|No|Yes|
|**Clipboard sharing between apps**|Allows use of the clipboard to copy and paste between apps.|No|Yes|
|**Diagnostic data submission**|Stops the user from submitting diagnostic data from the device.|No|Yes|
|**Factory reset**|Allows the user to perform a factory reset on the device.|No|Yes|
|**Geolocation**|Allows the device to utilize location information (Samsung KNOX Standard only).|No|Yes|
|**Power off**|Allows the user to power off the device.<br>If disabled, **Number of sign-in failures before wiping device** cannot be set.|No|Yes|
|**Screen capture**|Lets the user capture the screen contents as an image.|No|Yes|
|**Voice assistant**|Allows the use of voice assistant software on the device.|No|Yes|
|**YouTube**|Allows the use of the YouTube app on the device.|No|Yes|
|**Shared devices**|Configure a managed Samsung KNOX Standard device as shared. In this mode, end users can sign in and out of the device with their Azure AD credentials. The device remains managed whether it’s in use or not.<br>When end-users sign-in, they have access to apps and additionally get any policies applied to them. When users sign out, all app data is cleared.|No|Yes|

## Password

|||||
|-|-|-|-|
|Setting name|Details|Android 4.0+|Samsung KNOX Standard|
|**Password**|Require the end user to enter a password to access the device.|Yes|Yes|
|**Minimum password length**|Enter the minimum length of password a user must configure (between 4 and 16 characters).|Yes|Yes|
|**Maximum minutes of inactivity until screen locks**|Specifies the number of minutes of inactivity before the device automatically locks.|Yes|Yes|
|**Number of sign-in failures before wiping device**|Specifies the number of sign-in failures to allow before the device is wiped.|Yes|Yes|
|**Password expiration (days)**|Specifies the number of days before the device password must be changed.|Yes|Yes|
|**Required password type**|Specifies the required password complexity level, and whether biometric devices can be used. Choose from:<br><br>    -     **Device default**<br>-     **Low security biometric**<br>    -     **At least numeric**<br>    -     **Numeric complex** (repeating, or consecutive numbers like '1111' or '1234' are not allowed)<sup>1</sup><br>    -     **At least alphabetic**<br>    -     **At least alphanumeric**<br>    -     **At least alphanumeric with symbols**|Yes|Yes|
|**Prevent reuse of previous passwords**|Stops the end user from creating a password they have used before.|Yes|Yes|
|**Fingerprint unlock**|Allows the use of a fingerprint to unlock supported devices.|No|Yes|
|**Smart Lock and other trust agents**|Lets you control the Smart Lock feature on compatible Android devices (Samsung KNOX Standard 5.0 and later). This phone capability, sometimes known as a trust agent, lets you disable or bypass the device lock screen password if the device is in a trusted location. For example, this could be used when the device is connected to a specific Bluetooth device, or when it's close to an NFC tag. You can use this setting to prevent users from configuring Smart Lock.|Yes (5.0 and later)|Yes|
|**Encryption**|Requires that files on the device are encrypted.|Yes|Yes|

<sup>1</sup> Before you assign this setting to devices, ensure to update the Company Portal app to the latest version on those devices.

If you configure the **Numeric complex** setting, and then assign it to a device running a version of Android earlier than 5.0, the following behavior applies.
- If the Company Portal app is running a version earlier than 1704, no PIN policy is applied to the device and an error is displayed in the Intune portal.
- If the Company Portal app runs the 1704 version or later, only a simple PIN can be applied. Versions of Android earlier than 5.0 do not support this setting. No error is displayed in the Intune portal.


## Google Play Store

|||||
|-|-|-|-|
|Setting name|Details|Android 4.0+|Samsung KNOX Standard|
|**Google Play store**|Allows the user to access the Google Play store on the device|No|Yes|

## Restricted apps

In the restricted apps list, you can configure one of the following lists for both Android, and Samsung KNOX Standard devices:

A **Prohibited apps** list - List the apps (not managed by Intune) that users are not allowed to install and run.
An **Approved apps** list - List the apps that users are allowed to install. To remain compliant, users must not install other apps. Apps that are managed by Intune are automatically allowed.
Device profiles that contain restricted app settings must be assigned to groups of users.

To configure the list, click **Add**, then specify a name of your choice, optionally the app publisher, and the URL to the app in the app store.

### How to specify the URL to an app in the store

To specify an app URL in the compliant and noncompliant apps list, take the following steps:

In the [Apps section of Google Play](https://play.google.com/store/apps), search for the app you want to use.

Open the installation page for the app, and then copy the URL to the clipboard. You can now use this URL in either the compliant or noncompliant apps list.

Example: Search Google Play for Microsoft Office Mobile. Use the URL: **https://play.google.com/store/apps/details?id=com.microsoft.office.officehub**.

### Additional options

You can also click **Import** to get the list from a csv file. Use the format <*app url*>, <*app name*>, <*app publisher*> or click **Export** in the csv file containing the contents of the restricted apps list in the same format.		

## Browser
|||||
|-|-|-|-|
|Setting name|Details|Android 4.0+|Samsung KNOX Standard|
|**Web browser**|Specifies whether the device's default web browser can be used.|No|Yes|
|**Autofill**|Allows the autofill function of the web browser to be used.|No|Yes|
|**Cookies**|Allows the device web browser to use cookies.|No|Yes|
|**Javascript**|Allows the device web browser to run Java scripts.|No|Yes|
|**Pop-ups**|Allows the use of the pop-up blocker in the web browser.|No|Yes|

## Cloud and Storage
|||||
|-|-|-|-|
|Setting name|Details|Android 4.0+|Samsung KNOX Standard|
|**Google backup**|Allows the use of Google backup.|No|Yes|
|**Google account auto sync**|Allows Google account settings to be automatically synchronized.|No|Yes|
|**Removable storage**|Allows the device to use removable storage, like an SD card.|No|Yes|
|**Encryption on storage cards**|Specifies whether the device storage card must be encrypted.|No|Yes|

## Cellular and Connectivity
|||||
|-|-|-|-|
|Setting name|Details|Android 4.0+|Samsung KNOX Standard|
|**Data roaming**|Allows data roaming when the device is on a cellular network).|No|Yes|
|**SMS/MMS messaging**|Allows the use of SMS and MMS messaging on the device.|No|Yes|
|**Voice dialing**|Enables or disables the voice dialing feature on the device.|No|Yes|
|**Voice roaming**|Allows voice roaming when the device is on a cellular network.|No|Yes|
|**Bluetooth**|Allows the use of Bluetooth on the device.|No|Yes|
|**NFC**|Allows operations that use near field communication on supported devices.|No|Yes|
|**Wi-Fi**|Allows the use of the Wi-Fi capabilities of the device.|No|Yes|
|**Wi-Fi tethering**|Allows the use of Wi-Fi tethering on the device.|No|Yes|

## Kiosk
|||||
|-|-|-|-|
|Setting name|Details|Android 4.0+|Samsung KNOX Standard|
|**Select a managed app**|Choose one of the following options to add one or more apps that can run when the device is in kiosk mode. No other apps are allowed to run on the device.<br><br>- **Add apps by package name**<br>- **Add apps by URL**<br>- **Add managed apps**|No|Yes|
|**Screen sleep button**|Enables or disables the screen sleep wake button on the device.|No|Yes|
|**Volume buttons**|Enables or disables the use of the volume buttons on the device.|No|Yes|
