---
# required metadata

title: iOS policy settings in Microsoft Intune | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: ab46be6c-ab73-4c99-8492-66d1dd418293

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# iOS policy settings in Microsoft Intune

## General configuration policy settings

Use the Microsoft Intune **iOS general configuration policy** to configure settings for:

-   **Mobile device security settings** – Choose from a list of predefined settings that let you control a range of features and functionality on the device.

-   **Kiosk mode** - Lock a device to only allow certain features to work. For example, you can allow a device to only run one managed app that you specify, or you can disable the volume buttons on a device. These settings might be used for a demonstration model of a device, or a device that is dedicated to performing only one function, such as a point of sale device.

-   **Compliant and noncompliant apps** - Specify a list of apps that are compliant, or not compliant in your company. On Android and iOS devices, the **Noncompliant Apps Report** can be used to view the compliance of apps you specified in the list against the apps that users have installed (but cannot actually block the installation of the app).

> [!TIP]
> You can configure terms and conditions for users to ensure that they acknowledge that apps on their device, including personal apps will be evaluated, and noncompliant apps will either be blocked, or reported as noncompliant. Users must accept these terms and conditions before they can enroll their device and use the company portal to get apps. For more information about using terms and conditions, see [Working with terms and conditions policies in Microsoft Intune](http://msdn.microsoft.com/en-us/library/ce59fb93-01fd-4822-a57d-45ca7d89843d).

If the setting you are looking for does not appear in this topic, you might be able to create it using an iOS custom policy that lets you import settings you created using the [Apple Configurator Tool](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12). For more information, see **Custom policy settings** later in this topic.

### Security settings

|Setting name|Details|iOS|
|----------------|-------|
|**Require a password to unlock mobile devices**|Specify whether users are required to enter a password to access their device.|Yes|
|**Required password type**|Specifies the type of password that will be required, such as numeric only, or alphanumeric)|Yes|
|**Required password type – Minimum number of character sets**|There are four character sets, lowercase letters, uppercase letters, numbers, and symbols. This setting specifies how many different character sets must be included in the password). However, for iOS devices, this specifies the number of symbol characters must be included in the password)|Yes|
|**Minimum password length**|Specifies the minimum number of characters in the password.|Yes|
|**Allow simple passwords**|Allow simple passwords like ‘0000’ and ‘1234’.|Yes|
|**Number of repeated sign-in failures to allow before the device is wiped**|Wipes the device if this number of login attempts fail.|Yes|
|**Minutes of inactivity before screen turns off**<sup>1</sup>|Specify the number of minutes before the device display is turned off.|Yes|
|**Password expiration (days)**|Specifies the number of days before the device password must be changed.|Yes|
|**Remember password history**|Specifies whether the user can use passwords they have previously used.|Yes|
|**Remember password history** – **Prevent reuse of previous passwords**|Specifies the number of previously used passwords that are remembered by the device.|Yes|
|**Minutes of inactivity before password is required**<sup>1</sup>|Specifies how long the device can remain idle before the user must re-enter their password.|Yes|
|**Allow fingerprint unlock**|Allow using a fingerprint to unlock the device.|iOS 7.1 and later|
<sup>1</sup> For iOS devices, when you configure the settings **Minutes of inactivity before screen turns off** and **Minutes of inactivity before password is required**, they are applied in sequence. For example, if you set the value for both settings to **5** minutes, the screen will turn off automatically after 5 minutes, and the device will be locked after an additional 5 minutes. However, if the user turns off the screen manually, the second setting is immediately applied. In the same example, after the user turns off the screen, the device will lock 5 minutes later.

### System settings

|Setting name|Details|iOS|
|----------------|-------|
|**Allow screenshot**|Allows the user to capture the contents of the screen as an image.|Yes|
|**Allow control center in lock screen**|Controls whether the control center app can be accessed when the device is locked.|iOS 7.1 and later|
|**Allow notification view in lock screen**|Allow the user to access the notifications view without unlocking the device.|iOS 7.1 and later|
|**Allow today view in lock screen**|Controls whether notifications can be viewed when the device is locked.|iOS 7.1 and later|
|**Allow diagnostic data submission**|Allow or block the device from submitting diagnostic data to Apple.|Yes|
|**Allow untrusted TLS certificates**|Allow untrusted Transport Layer Security certificates on the device.|Yes|
|**Allow passbook while locked**|Allow the user to access the Passbook app while the device is locked.|Yes|

### Cloud settings – documents and data

|Setting name|Details|iOS|
|----------------|-------|
|**Allow backup to iCloud**|Allows the user to back up the device to iCloud.|Yes|
|**Allow document sync to iCloud**|Allow document and key-value synchronization to your iCloud storage space.Yes|
|**Allow Photo Stream sync to iCloud**|Allow photos on the device to sync to iCloud.|Yes|
|**Require encrypted backup**|Require any device backups to be encrypted.|Yes|

### Application settings - browser

|Setting name|Details|iOS|
|----------------|-------|
|**Allow Safari**|Specify whether the Safari browser can be used on the device.|Yes|
|**Allow autofill**|User can change autocomplete settings in the browser.|Yes|
|**Allow pop-up blocker**|Enable or disable the browser pop-up blocker.|Yes|
|**Allow cookies**|Allow the device web browser to use cookies.|Yes|
|**Allow Java scripting**|Allow Java scripts to run in the browser.|Yes|
|**Allow fraud warning**|Allow fraud warnings in the device browser.|Yes|

### Application settings - apps

|Setting name|Details|iOS|
|----------------|-------|
|**Allow application store**|Allows the device to access the app store.|Yes|
|**Require a password to access application store**|Yes|
|**Allow in-app purchases**|Allow store purchases to be made from within a running app.|Yes|
|**Allow managed documents in other unmanaged apps**|Allows corporate documents to be viewed in any app.|OS 7.1 and later|
|**Allow unmanaged documents in other managed apps**|Allow any document to be viewed in corporate managed apps.|iOS 7.1 and later|
|**Allow video conferencing**|Allow video conferencing apps such as Facetime on the device.|Yes|
|**Allow adult content in media store**|Allow the device to access content rated as adult from the store.|Yes|

### Application settings - Games

|Setting name|Details|iOS|
|----------------|-------|
|**Allow adding Game Center friends**|Allow the user to add friends in Game Center.|Yes|
|**Allow multiplayer gaming**|Allow the user to play multiplayer games on the device.|Yes|

### Device capabilities settings - hardware

|Setting name|Details|iOS|
|----------------|-------|
|**Allow camera**|Specifies whether the camera on the device can be used.|Yes|

### Device capabilities settings - cellular

|Setting name|Details|iOS|
|----------------|-------|
|**Allow voice roaming**|Allow voice roaming when the device is on a cellular network.|Yes|
|**Allow data roaming**|Allow data roaming when the device is on a cellular network.|Yes|
|**Allow global background fetch while roaming**|Allow the device to fetch data such as email while it is roaming on a cellular network.|Yes|

### Device capabilities settings - features

|Setting name|Details|iOS|
|----------------|-------|
|**Allow Siri**|Allow use of the Siri voice assistant on the device.|Yes|
|**Allow Siri while device is locked**|Allow use of the Siri voice assistant on the device while it is locked.|Yes|
|**Allow voice dialing**|Allow use of the voice dialing feature on the device.|Yes|


### Settings for compliant and noncompliant apps
In the **Compliant &amp; Noncompliant Apps** list, specify a list of compliant or noncompliant apps using the following information:

> [!NOTE]
> A single policy can only contain a list of compliant, or a list of noncompliant apps. You cannot specify both in the same policy.

|Setting name|Details|
|----------------|--------------------|
|**Report noncompliance when users install the listed apps**|Lists the apps that are not managed by Intune which users are not allowed to install and run.|
|**Do not report noncompliance when users install the listed apps**|Lists the apps that users are allowed to install. To remain compliant, users must not install apps that are not listed. Apps that are managed by Intune are automatically allowed.|
|**Add**|Adds an app to the selected list. Specify a name of your choice, optionally the app publisher, and the URL to the app in the app store. Read **How to specify URLs to app stores** later in this topic for more help.|
|**Import Apps**|Imports a list of apps you have specified in a comma-separated values file. Use the format, application name, publisher, app URL in the file.|
|**Edit**|Let’s you edit the name, publisher and URL of the selected app.|
|**Delete**|Deletes the selected app from the list.|

### Kiosk mode settings

|Setting name|Details|
|----------------|--------------------|
|**Select a managed app that will be allowed to run when the device is in kiosk mode**|Click **Browse**, then specify the managed app, or app from a store that will be allowed to run when the device is in kiosk mode. No other apps will be allowed to run on the device.For more help, see **How to specify URLs to app stores** later in this topic.|
|**Allow touch**|Enables or disables the touch screen on the device.|
|**Allow screen rotation**|Enables or disables changing the screen orientation when you rotate the device.|
|**Allow volume buttons**|Enables or disables the use of the volume buttons on the device.|
|**Allow ringer switch**|Enables or disables the ringer (mute) switch on the device.|
|**Allow screen sleep wake button**|Enables or disables the screen sleep wake button on the device.|
|**Allow auto lock**|Enables or disables automatic locking of the device.|
|**Enable mono audio**|Enables or disables the accessibility setting **Mono audio**.|
|**Enable voice over**|Enables or disables the accessibility setting **VoiceOver** which reads aloud text on the device display.|
|**Enable voice over adjustments**|Enables or disables voiceover adjustments which let you adjust the VoiceOver function (for example, how fast on-screen text is read aloud).|
|**Enable zoom**|Enables or disables the **Zoom** accessibility setting which lets you use touch to zoom into the device display.|
|**Enable zoom adjustments**|Enables or disables zoom adjustments which let you adjust the zoom function.|
|**Enable invert colors**|Enables or disables the **Invert Colors** accessibility setting which adjusts the display to help users with visual impairments.|
|**Enable invert colors adjustments**|Enables or disables invert colors adjustments which let you adjust the invert colors function.|
|**Enable assistive touch**|Enables or disables the **Assistive Touch** accessibility setting which helps users perform on screen gestures which might be difficult for them to perform.|
|**Enable assistive touch adjustments**|Enables or disables assistive touch adjustments which let you adjust the assistive touch function.|
|**Enable speech selection**|Enables or disables the **Speak Selection** accessibility settings which can read aloud the text you select.|
> [!NOTE]
> The following notes apply to kiosk mode settings for iOS devices:
> 
> -   Before you can configure an iOS device for kiosk mode, you must use the [Apple Configurator Tool](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12) or device enrollment manager to put the device into supervised mode. For more information about the Apple Configurator Tool, see your Apple documentation.
> -   If the iOS app you specify is installed after you deploy the configuration policy, the device will not enter kiosk mode until after it is restarted.

### Reference information for compliant and noncompliant apps

#### Monitor compliant and noncompliant apps
Use the **Noncompliant Apps Report** to view the compliance of allowed and blocked apps.

##### To run the Noncompliant Apps Report

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Reports** &gt; **Noncompliant Apps Report**.

2.  Select the device groups that you would like to check, whether you want to check for compliant apps, noncompliant apps, or both, then click **View Report**.

#### How to specify URLs to app stores
To specify an app URL in the compliant and noncompliant apps list, or in the **Select a managed app that will be allowed to run when the device is in kiosk mode** option (iOS only), use the following format:

Using a search engine, find the app you want to use in the iTunes App Store and open the page for the app.

Copy the URL of the page and use this as the URL to configure the compliant or noncompliant apps list or the app you want to run in kiosk mode.

**Example:** Search for **Microsoft Word for iPad**. The URL you use will be **https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8**.

> [!NOTE]
> You can also use the iTunes software to find the app and then use the **Copy Link** command to get the app URL.


## Custom policy settings

Use the Microsoft Intune **iOS custom policy** to deploy settings that you created using the [Apple Configurator tool](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12) to iOS devices. This tool lets you create many settings that control the operation of these devices and export them to a configuration profile. You can then import this configuration profile into an Intune iOS custom policy and deploy the settings to users and devices in your organization.

This capability is intended to allow you to deploy iOS settings that are not configurable with Intune general configuration policies policies. For information about the settings you can configure with these policies, see [iOS configuration policy settings in Microsoft Intune](iOS-configuration-policy-settings-in-Microsoft-Intune.md).

### Prerequisites
Before you start, you must have installed the Apple Configurator and created a configuration file containing the settings you want to deploy to users or devices. You can download and learn about the Apple Configurator from [the Mac App Store](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12)

> [!NOTE]
> Intune does not report the compliance of individual settings in an iOS custom policy. However, the overall compliance of the policy is reported.

### General settings

|Setting name|Details|
    |----------------|--------------------|
    |**Name**|Enter a unique name for the iOS custom policy to help you identify it in the Intune console.|
    |**Description**|Provide a description that gives an overview of the iOS custom policy and other relevant information that helps you to locate it.|

### Custom settings

|Setting name|Details|
    |----------------|--------------------|
|**Custom configuration profile name (displayed to users)**|Provide a name for the policy as it will be displayed on the device, and in Intune policy reports.|
|**Configuration profile file**|Click **Import**, then browse to the configuration profile that you created using the Apple Configurator. **Note:** Ensure that the settings you export from the Apple Configurator tool are compatible with the version of iOS on the devices to which you deploy the iOS custom policy. For information about how incompatible settings are resolved, search for **Configuration Profile Reference** and **Mobile Device Management Protocol Reference** on the [Apple Developer](https://developer.apple.com/) web site.|
    |**Configuration profile details**|Displays the xml code for the configuration profile that you imported.|

### See also
[Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)

