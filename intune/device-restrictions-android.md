---
# required metadata

title: Intune device restriction settings for Android
titlesuffix: "Azure portal"
description: Learn the Intune settings you can use to control device settings and functionality on Android devices."
keywords:
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/11/2017
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

# Android and Samsung Knox Standard device restriction settings in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Use these settings with an Android device restriction policy to configure devices in your organization.

>[!TIP]
>If the settings you want are not available, you might be able to configure your devices using a [custom profile](custom-settings-android.md).

## General

- **Camera** - Allows the use of the device camera.
- **Copy and paste (Samsung Knox only)** - Allows copy and paste functions on the device.
- **Clipboard sharing between apps (Samsung Knox only)** - Allows use of the clipboard to copy and paste between apps.
- **Diagnostic data submission (Samsung Knox only)** - Stops the user from submitting diagnostic data from the device.
- **Factory reset (Samsung Knox only)** - Allows the user to perform a factory reset on the device.
- **Geolocation (Samsung Knox only)** - Allows the device to utilize location information.
- **Power off (Samsung Knox only)** - Allows the user to power off the device.<br>If disabled, **Number of sign-in failures before wiping device** cannot be set.
- **Screen capture (Samsung Knox only)** - Lets the user capture the screen contents as an image.
- **Voice assistant (Samsung Knox only)** - Allows the use of voice assistant software on the device.
- **YouTube (Samsung Knox only)** - Allows the use of the YouTube app on the device.
- **Shared devices (Samsung Knox only)** - Configure a managed Samsung Knox Standard device as shared. In this mode, end users can sign in and out of the device with their Azure AD credentials. The device remains managed whether it’s in use or not.<br>When used in conjunction with a SCEP certificate profile, this feature allows end users to share a device with the same set of apps for all users, but with their own SCEP user cert.  When users sign out, all app data is cleared.  This feature is limited to LOB apps only.
- **Block date and time changes (Samsung Knox)** - Prevent the user from changing the date and time settings on the device. 

## Password

- **Password** - Require the end user to enter a password to access the device.|Yes|Yes|
- **Minimum password length** - Enter the minimum length of password a user must configure (between 4 and 16 characters).
- **Maximum minutes of inactivity until screen locks** - Specifies the number of minutes of inactivity before the device automatically locks.
- **Number of sign-in failures before wiping device** - Specifies the number of sign-in failures to allow before the device is wiped.
- **Password expiration (days)** - Specifies the number of days before the device password must be changed.
-  **Required password type** - Specifies the required password complexity level, and whether biometric devices can be used. Choose from:
	- **Device default**
	- **Low security biometric**
	- **At least numeric**
	- **Numeric complex** - Repeating, or consecutive numbers like '1111' or '1234' are not allowed<sup>1</sup>
	- **At least alphabetic**
	- **At least alphanumeric**
	- **At least alphanumeric with symbols**
- **Prevent reuse of previous passwords** - Stops the end user from creating a password they have used before.
- **Fingerprint unlock (Samsung Knox only)** - Allows the use of a fingerprint to unlock supported devices.
- **Smart Lock and other trust agents** - Lets you control the Smart Lock feature on compatible Android devices (Samsung Knox Standard 5.0 and later). This phone capability, sometimes known as a trust agent, lets you disable or bypass the device lock screen password if the device is in a trusted location. For example, this could be used when the device is connected to a specific Bluetooth device, or when it's close to an NFC tag. You can use this setting to prevent users from configuring Smart Lock.
- **Encryption** - Requires that files on the device are encrypted.

<sup>1</sup> Before you assign this setting to devices, ensure to update the Company Portal app to the latest version on those devices.

If you configure the **Numeric complex** setting, and then assign it to a device running a version of Android earlier than 5.0, the following behavior applies.
- If the Company Portal app is running a version earlier than 1704, no PIN policy is applied to the device and an error is displayed in the Azure portal.
- If the Company Portal app runs the 1704 version or later, only a simple PIN can be applied. Versions of Android earlier than 5.0 do not support this setting. No error is displayed in the Azure portal.


## Google Play Store

- **Google Play store (Samsung Knox only)** - Allows the user to access the Google Play store on the device.

## Restricted apps

In the restricted apps list, you can configure one of the following lists for both Android, and Samsung Knox Standard devices:

A **Prohibited apps** list - List the apps (not managed by Intune) that will be reported if users install and run.
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

- **Web browser (Samsung Knox only)** - Specifies whether the device's default web browser can be used.
- **Autofill (Samsung Knox only)** - Allows the autofill function of the web browser to be used.
- **Cookies (Samsung Knox only)** - Allows the device web browser to use cookies.
- **Javascript (Samsung Knox only)** - Allows the device web browser to run Java scripts.
- **Pop-ups (Samsung Knox only)** - Allows the use of the pop-up blocker in the web browser.

## Allow or Block apps

These settings can be used to specify apps that can be installed, or launched on devices that run Samsung Knox Standard only.
Additionally, you can also specify installed apps that will be hidden from the device user. Users cannot run these apps.

- **Apps allowed to be installed (Samsung Knox Standard only)**
- **Apps blocked from launching (Samsung Knox Standard only)**
- **Apps hidden from user (Samsung Knox Standard only)**

For each setting, configure a list of apps using one of the following:

- **Add apps by package name** - Primarily used for line of business apps. Enter the app name, and the name of the app package.
- **Add apps by URL** - Enter the app name, and its URL in the Google Play store.
- **Add managed apps** - From the list of apps you manage with Intune, select the app you require.

## Cloud and Storage

- **Google backup (Samsung Knox only)** - Allows the use of Google backup.
- **Google account auto sync (Samsung Knox only)** - Allows Google account settings to be automatically synchronized.
- **Removable storage (Samsung Knox only)** - Allows the device to use removable storage, like an SD card.
- **Encryption on storage cards (Samsung Knox only)** - Specifies whether the device storage card must be encrypted.

## Cellular and Connectivity

- **Data roaming (Samsung Knox only)** - Allows data roaming when the device is on a cellular network).
- **SMS/MMS messaging (Samsung Knox only)** - Allows the use of SMS and MMS messaging on the device.
- **Voice dialing (Samsung Knox only)** - Enables or disables the voice dialing feature on the device.
- **Voice roaming (Samsung Knox only)** - Allows voice roaming when the device is on a cellular network.
- **Bluetooth (Samsung Knox only)** - Allows the use of Bluetooth on the device.
- **NFC (Samsung Knox only)** - Allows operations that use near field communication on supported devices.
- **Wi-Fi (Samsung Knox only)** - Allows the use of the Wi-Fi capabilities of the device.
- **Wi-Fi tethering (Samsung Knox only)** - Allows the use of Wi-Fi tethering on the device.

## Kiosk

Kiosk settings apply only to Samsung Knox Standard devices, and only to apps you manage using Intune.

- **Select a managed app** - Choose one of the following options to add one or more managed apps that can run when the device is in kiosk mode. No other apps are allowed to run on the device.
	- **Add apps by package name**
	- **Add apps by URL**
	- **Add managed apps**.
- **Screen sleep button** - Enables or disables the screen sleep wake button on the device.
- **Volume buttons** - Enables or disables the use of the volume buttons on the device.


## Next steps

Continue using the instructions in [How to configure device restriction settings](device-restrictions-configure.md) to create, then assign the device restriction profile.
