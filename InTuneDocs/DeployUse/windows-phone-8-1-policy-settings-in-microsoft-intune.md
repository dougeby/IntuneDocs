---
title: Windows Phone 8.1 policy settings in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 83f7469c-272e-43f2-8139-b0d7bc34f43f
author: robstackmsft
---
# Windows Phone 8.1 policy settings in Microsoft Intune

## General configuration settings

Use the Microsoft Intune **Windows Phone general configuration policy** to configure the following settings for Windows Phone 8.1 devices:

-   **Mobile device security settings** – Choose from a list of predefined settings that let you control a range of features and functionality on the device.

-   **Compliant and noncompliant apps** - Specify a list of apps that are compliant, or not compliant in your company. Windows Phone devices can block, or allow installation of these apps.

### Password settings

|Setting name|Details|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Require a password to unlock mobile devices**|Specifies whether users must enter a password to access their devices.|Yes|Yes|
|**Required password type**|Specifies the type of password that will be required, such as numeric only, or alphanumeric.|Yes|Yes|
|**Required password type – Minimum number of character sets**|There are four character sets, lowercase letters, uppercase letters, numbers, and symbols. This setting specifies how many different character sets must be included in the password). However, for iOS devices, this specifies the number of symbol characters must be included in the password)|Yes|Yes|
|**Minimum password length**|Specifies the minimum number of characters required in the password.|Yes|Yes|
|**Allow simple passwords**|Simple passwords include ‘0000’ and ‘1234’|Yes|Yes|
|**Number of repeated sign-in failures to allow before the device is wiped**|Specifies the number of times an incorrect password can be remembered before the device is wiped.|Yes|Yes|
|**Minutes of inactivity before screen turns off**|Specifies the amount of time a device must remain idle before the screen is automatically locked.|Yes|Yes|
|**Password expiration (days)**|Specifies the number of days before the device password must be changed.|Yes|Yes|
|**Remember password history**|Specifies whether previously used passwords are remembered to prevent the user from using them again.|Yes|Yes|
|**Remember password history** – **Prevent reuse of previous passwords**|Specifies how many previously used passwords are remembered.|Yes|Yes|

### Encryption settings

|Setting name|Details|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Require encryption on mobile device**|Requires the data on supported mobile devices to be encrypted.<br>For Windows Phone 8 devices, you must set this to **Yes**.|Yes|Yes|

### System settings

|Setting name|Details|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Allow screen capture**|Lets the user capture the contents of the screen as an image file.|No|Yes|
|**Allow diagnostic data submission**|Allows the device to submit diagnostic information to Microsoft.|No|Yes|

### Cloud settings – accounts and synchronization

|Setting name|Details|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Allow Microsoft account**|Allows a Microsoft account to be linked to the device.|No|Yes|

### Email settings

|Setting name|Details|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Allow custom email accounts**|Allow the device to connect to non-Microsoft email accounts.|No|Yes|

### Application settings - browser

|Setting name|Details|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Allow web browser**|Allows or blocks the built-in web browser on devices.|No|Yes|

### Application settings - apps

|Setting name|Details|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Allow application store**|Lets users connect to the app store from the device.|No|Yes|

### Device capabilities settings - hardware

|Setting name|Details|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Allow camera**|Allow or block the device camera.|No|Yes|
|**Allow removable storage**|Lets the device use removable storage, for example, an SD card.|Yes|Yes|
|**Allow Wi-Fi**|Enables or disables the Wi-Fi functionality of the device.|No|Yes|
|**Allow Wi-Fi tethering**|Allow the use of Wi-Fi tethering on the device.|No|Yes
|**Allow automatic connection to free Wi-Fi hotspots**|Allow the device to automatically connect to free Wi-Fi hotspots and automatically accept any terms of use.|No|Yes|
|**Allow Wi-Fi hotspot reporting**|Send information about Wi-Fi connections to help discover nearby connections.|No|Yes|
|**Allow geolocation**|Allows the device to utilize location information.|No|Yes|
|**Allow NFC**|Allows operations that use near field communication.|No|Yes|
|**Allow Bluetooth**|Enables or disables the Bluetooth functionality of the device.|No|Yes|

### Device capabilities settings - features

|Setting name|Details|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Allow copy and paste**|Allow copy and paste functionality on devices.|No|Yes|

### Settings for compliant and noncompliant apps
In the **Compliant &amp; Noncompliant Apps** list, specify a list of compliant or noncompliant apps using the following information:

> [!NOTE]
> A single policy can only contain a list of compliant, or a list of noncompliant apps. You cannot specify both in the same policy.

|Setting name|Details|
|----------------|--------------------|
|**Block devices from opening the listed apps**|Lists the apps that are not managed by Intune which users are not allowed to install and run.|
|**Allow devices to install only the listed apps**|Lists the apps that users are allowed to install. Users cannot install any other apps. Apps that are managed by Intune are automatically allowed.|
|**Add**|Adds an app to the selected list. Specify a name of your choice, optionally the app publisher, and the URL to the app in the app store.<br /><br />[How to specify URLs to app stores](windows-phone-configuration-policy-settings-in-microsoft-intune.md#BKMK_URL)|
|**Import Apps**|Imports a list of apps you have specified in a comma-separated values file. Use the format, application name, publisher, app URL in the file.|
|**Edit**|Let’s you edit the name, publisher and URL of the selected app.|
|**Delete**|Deletes the selected app from the list.|
> [!IMPORTANT]
> If you specify a list of allowed apps for Windows Phone 8.1 devices, you must add the Company Portal app to this list, or else it will be blocked.


### Reference information for compliant and noncompliant apps

#### How to specify URLs to app stores
To specify an app URL in the compliant and noncompliant apps list, use the following format:

From the [Windows Phone Apps+Games](http://www.windowsphone.com/en-us/store/overview) page, search for the app you want to use.

Open the app’s page, and copy the URL to the clipboard. You can now use this as the URL in either the compliant or noncompliant apps list.

**Example:** Search the store for the Skype app. The URL you use will be **http://www.windowsphone.com/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51**.

## Custom policy settings 
Use the Microsoft Intune **Windows Phone custom configuration policy** to deploy OMA-URI (Open Mobile Alliance Uniform Resource Identifier) settings that can be used to control features on **Windows Phone 8.1 devices**. These are standard settings that many mobile device manufacturers use to control device features.

This capability is intended to allow you to deploy Windows Phone settings that are not configurable with an Intune general configuration policy. For information about the settings you can configure with these policies, see [Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

For help creating OMA-URI settings for Windows Phone devices, see [Windows Phone 8.1 MDM protocol documentation](http://technet.microsoft.com/library/dn499787.aspx).

### General settings

|Setting name|Details|
|----------------|--------------------|
|**Name**|Enter a unique name for the policy to help you identify it in the Intune console.|
|**Description**|Provide a description that gives an overview of the policy and other relevant information that helps you to locate it.|

### OMA-URI settings

In the **OMA-URI Settings** section, click **Add** to add a setting. You can also edit or delete an existing setting.

In the **Add or Edit OMA-URI Setting** dialog box, specify the following information:

|Setting name|Details|
    |--------|--------------------|
    |**Setting name**|Enter a unique name for the OMA-URI setting to help you identify it in the list of settings.|
    |**Setting description**|Provide a description that gives an overview of the setting and other relevant information to help you locate it.|
    |**Data type**|Select the date type in which you will specify this OMA-URI setting. Choose from:<br /><br />-   **String**<br />-   **String (XML)**<br />-   **Date and time**<br />-   **Integer**<br />-   **Floating point**<br />-   **Boolean**|
    |**OMA-URI (Case Sensitive)**|Specify the OMA-URI you want to supply a setting for.|
    |**Value**|Specify the value to associate with the OMA-URI you specified previously.|

### See Also
[Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)

