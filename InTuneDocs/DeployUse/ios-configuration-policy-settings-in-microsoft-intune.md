---
title: iOS configuration policy settings in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: ab46be6c-ab73-4c99-8492-66d1dd418293
author: robstackmsft
---
# iOS configuration policy settings in Microsoft Intune
Use the [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] **iOS general configuration policy** to configure settings for:

-   **Mobile device security settings** – Choose from a list of predefined settings that let you control a range of features and functionality on the device.

-   **Kiosk mode** - Lock a device to only allow certain features to work. For example, you can allow a device to only run one managed app that you specify, or you can disable the volume buttons on a device. These settings might be used for a demonstration model of a device, or a device that is dedicated to performing only one function, such as a point of sale device.

-   **Compliant and noncompliant apps** - Specify a list of apps that are compliant, or not compliant in your company. On Android and iOS devices, the **Noncompliant Apps Report** can be used to view the compliance of apps you specified in the list against the apps that users have installed (but cannot actually block the installation of the app).

> [!TIP]
> You can configure terms and conditions for users to ensure that they acknowledge that apps on their device, including personal apps will be evaluated, and noncompliant apps will either be blocked, or reported as noncompliant. Users must accept these terms and conditions before they can enroll their device and use the company portal to get apps. For more information about using terms and conditions, see [Working with terms and conditions policies in Microsoft Intune](http://msdn.microsoft.com/en-us/library/ce59fb93-01fd-4822-a57d-45ca7d89843d).

## Create an iOS general configuration policy

#### To provide basic settings for the configuration policy

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Policy** &gt; **Overview** &gt; **Add Policy**.

2.  Click **iOS** &gt; **General Configuration** and then click **Create Policy**.

    > [!NOTE]
    > You cannot create a configuration policy using recommended settings. You must create a custom policy.

3.  In the **General** section of the **Create Policy** page, specify a name and a description for the new policy.

4.  Use the information in the following sections to help you supply settings for the policy.

5.  When you are finished, click **Save Policy**.

The new policy displays in the **Configuration Policies** node of the **Policy** workspace.

## <a name="BKMK_Settings"></a>Settings for iOS devices
If the setting you are looking for does not appear in this list, you might be able to create it using an iOS custom policy that lets you import settings you created using the [Apple Configurator Tool](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12). For more information, see [iOS custom policy settings in Microsoft Intune](../Topic/iOS-custom-policy-settings-in-Microsoft-Intune.md).

### <a name="BKMK_sec"></a>Security settings

|Setting name|iOS|
|----------------|-------|
|**Require a password to unlock mobile devices**|Yes|
|**Required password type**<br /><br />(specifies the type of password that will be required, such as numeric only, or alphanumeric)|Yes|
|**Required password type – Minimum number of character sets**<br /><br />There are four character sets, lowercase letters, uppercase letters, numbers, and symbols. This setting specifies how many different character sets must be included in the password). However, for iOS devices, this specifies the number of symbol characters must be included in the password)|Yes|
|**Minimum password length**|Yes|
|**Allow simple passwords**<br /><br />Simple passwords include ‘0000’ and ‘1234’|Yes|
|**Number of repeated sign-in failures to allow before the device is wiped**|Yes|
|**Minutes of inactivity before screen turns off**<sup>1</sup>|Yes|
|**Password expiration (days)**|Yes|
|**Remember password history**|Yes|
|**Remember password history** – **Prevent reuse of previous passwords**|Yes|
|**Minutes of inactivity before password is required**<sup>1</sup>|Yes|
|**Allow fingerprint unlock**|iOS 7.1 and later|
<sup>1</sup> For iOS devices, when you configure the settings **Minutes of inactivity before screen turns off** and **Minutes of inactivity before password is required**, they are applied in sequence. For example, if you set the value for both settings to **5** minutes, the screen will turn off automatically after 5 minutes, and the device will be locked after an additional 5 minutes. However, if the user turns off the screen manually, the second setting is immediately applied. In the same example, after the user turns off the screen, the device will lock 5 minutes later.

### System settings

|Setting name|iOS|
|----------------|-------|
|**Allow screenshot**|Yes|
|**Allow control center in lock screen**|iOS 7.1 and later|
|**Allow notification view in lock screen**|iOS 7.1 and later|
|**Allow today view in lock screen**|iOS 7.1 and later|
|**Allow diagnostic data submission**|Yes|
|**Allow untrusted TLS certificates**|Yes|
|**Allow passbook while locked**|Yes|

### <a name="BKMK_cloud"></a>Cloud settings – documents and data

|Setting name|iOS|
|----------------|-------|
|**Allow backup to iCloud**|Yes|
|**Allow document sync to iCloud**|Yes|
|**Allow Photo Stream sync to iCloud**|Yes|
|**Require encrypted backup**|Yes|

### <a name="BKMK_browser"></a>Application settings - browser

|Setting name|iOS|
|----------------|-------|
|**Allow Safari**|Yes|
|**Allow autofill**|Yes|
|**Allow pop-up blocker**|Yes|
|**Allow cookies**|Yes|
|**Allow Java scripting**|Yes|
|**Allow fraud warning**|Yes|

### <a name="BKMK_apps"></a>Application settings - apps

|Setting name|iOS|
|----------------|-------|
|**Allow application store**|Yes|
|**Require a password to access application store**|Yes|
|**Allow in-app purchases**|Yes|
|**Allow managed documents in other unmanaged apps**|iOS 7.1 and later|
|**Allow unmanaged documents in other managed apps**|iOS 7.1 and later|
|**Allow video conferencing**|Yes|
|**Allow adult content in media store**|Yes|

### Application settings - Games

|Setting name|iOS|
|----------------|-------|
|**Allow adding Game Center friends**|Yes|
|**Allow multiplayer gaming**|Yes|

### <a name="BKMK_hard"></a>Device capabilities settings - hardware

|Setting name|iOS|
|----------------|-------|
|**Allow camera**|Yes|

### Device capabilities settings - cellular

|Setting name|iOS|
|----------------|-------|
|**Allow voice roaming**|Yes|
|**Allow data roaming**|Yes|
|**Allow global background fetch while roaming**|Yes|

### Device capabilities settings - features

|Setting name|iOS|
|----------------|-------|
|**Allow Siri**|Yes|
|**Allow Siri while device is locked**|Yes|
|**Allow voice dialing**|Yes|
|**Allow clipboard share between applications**|No|
|**Allow YouTube**|No|

## Settings for compliant and noncompliant apps
In the **Compliant &amp; Noncompliant Apps** list, specify a list of compliant or noncompliant apps using the following information:

> [!NOTE]
> A single policy can only contain a list of compliant, or a list of noncompliant apps. You cannot specify both in the same policy.

|Setting name|More information|
|----------------|--------------------|
|**Report noncompliance when users install the listed apps**|Lists the apps that are not managed by Intune which users are not allowed to install and run.|
|**Do not report noncompliance when users install the listed apps**|Lists the apps that users are allowed to install. To remain compliant, users must not install apps that are not listed. Apps that are managed by Intune are automatically allowed.|
|**Add**|Adds an app to the selected list. Specify a name of your choice, optionally the app publisher, and the URL to the app in the app store.<br /><br />[How to specify URLs to app stores](../Topic/iOS-configuration-policy-settings-in-Microsoft-Intune.md#BKMK_URL)|
|**Import Apps**|Imports a list of apps you have specified in a comma-separated values file. Use the format, application name, publisher, app URL in the file.|
|**Edit**|Let’s you edit the name, publisher and URL of the selected app.|
|**Delete**|Deletes the selected app from the list.|

## Kiosk mode settings
Specify the following settings for **iOS devices**:

|Setting name|More information|
|----------------|--------------------|
|**Select a managed app that will be allowed to run when the device is in kiosk mode**|Click **Browse**, then specify the managed app, or app from a store that will be allowed to run when the device is in kiosk mode. No other apps will be allowed to run on the device.<br /><br />[How to specify URLs to app stores](../Topic/iOS-configuration-policy-settings-in-Microsoft-Intune.md#BKMK_URL).|
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

## Deploy the Configuration Policy

1.  Deploy the configuration policy to one or more groups of users or devices in your organization.

For more information about how to deploy policies, see [Use policies to manage computers and mobile devices with Microsoft Intune](../Topic/Use-policies-to-manage-computers-and-mobile-devices-with-Microsoft-Intune.md).

A status summary and alerts In the **Policy** workspace identify issues with the policy that require your attention. Additionally, a status summary appears in the **Dashboard** workspace.

## Reference information for compliant and noncompliant apps

### Monitor compliant and noncompliant apps
Use the **Noncompliant Apps Report** to view the compliance of allowed and blocked apps.

##### To run the Noncompliant Apps Report

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Reports** &gt; **Noncompliant Apps Report**.

2.  Select the device groups that you would like to check, whether you want to check for compliant apps, noncompliant apps, or both, then click **View Report**.

### <a name="BKMK_URL"></a>How to specify URLs to app stores
To specify an app URL in the compliant and noncompliant apps list, or in the **Select a managed app that will be allowed to run when the device is in kiosk mode** option (iOS only), use the following format:

Using a search engine, find the app you want to use in the iTunes App Store and open the page for the app.

Copy the URL of the page and use this as the URL to configure the compliant or noncompliant apps list or the app you want to run in kiosk mode.

**Example:** Search for **Microsoft Word for iPad**. The URL you use will be **https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8**.

> [!NOTE]
> You can also use the iTunes software to find the app and then use the **Copy Link** command to get the app URL.

## See Also
[Use policies to manage computers and mobile devices with Microsoft Intune](../Topic/Use-policies-to-manage-computers-and-mobile-devices-with-Microsoft-Intune.md)

