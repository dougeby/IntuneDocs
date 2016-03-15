---
title: MD Conversion - Windows 10 configuration policy settings in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 95371132-e7a0-4148-b11d-fdb95f110adc
---
# MD Conversion - Windows 10 configuration policy settings in Microsoft Intune
Use the [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)]**general configuration policy** for Windows 10 to configure settings for enrolled Windows 10 desktop, and Windows 10 Mobile devices:

## Create a Windows 10 general configuration policy

#### To provide basic settings for the configuration policy

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Policy** &gt; **Overview** &gt; **Add Policy**.

2.  Click **Windows** &gt; **General Configuration (Windows 10 Desktop and Mobile and later)** and then click **Create Policy**.

    > [!NOTE]
    > You cannot create a configuration policy using recommended settings. You must create a custom policy.

3.  In the **General** section of the **Create Policy** page, specify a name and a description for the new policy.

4.  Use the information in the following sections to help you supply settings for the policy.

5.  When you are finished, click **Save Policy**.

The new policy displays in the **Configuration Policies** node of the **Policy** workspace.

## Security settings

### Password

|Setting name|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Require a password to unlock devices**|Yes|Yes|
|**Required password type**<br /><br />(Specifies the type of password that will be required, such as numeric only, or alphanumeric)|Yes|Yes|
|**Required password type** - **Minimum number of character sets**<br /><br />(There are four character sets, lowercase letters, uppercase letters, numbers, and symbols. This setting specifies how many different character sets must be included in the password).|Yes|Yes|
|**Minimum password length (Windows 10 Desktop only)**<br /><br />This setting is no longer supported and will be removed in the future. You can use the setting for Windows 10 Mobile below for desktop computers.|Yes|No|
|**Minimum password length (Windows 10 Mobile only)**|No|Yes|
|**Number of repeated sign-in failures to allow before the device is wiped**|Yes|Yes|
|**Minutes of inactivity before screen turns off**|Yes|Yes|
|**Password expiration (days)**|Yes|Yes|
|**Remember password history**|Yes|Yes|
|**Remember password history** - **Prevent reuse of previous passwords**|Yes|Yes|
|**Allow picture password and PIN**<br /><br />Lets you use simple gestures on a picture, or a simple PIN to login.|Yes|No|
|**Require a password when the device returns from an idle state**|No|Yes|

### Encryption

|Setting name|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Require encryption on mobile device**|No|Yes|

### System

|Setting name|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Allow screen capture**|No|Yes|
|**Allow manual unenrollment**<br /><br />Lets the user manually delete the workplace account from the device.|Yes|Yes|
|**Allow manual root certificate installation**<br /><br />Specifies whether the user can manually install root certificates|No|Yes|
|**Allow diagnostic and usage data to be sent to Microsoft**|Yes|Yes|

## Cloud settings

### Account and synchronization

|Setting name|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Allow Microsoft account**|Yes|Yes|
|**Allow adding non-Microsoft accounts manually**|Yes|Yes|
|**Allow settings synchronization for Microsoft accounts**|Yes|Yes|

## Email settings

|Setting name|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Make Microsoft account optional in Windows Mail application**|Yes|No|

## Application settings

### Microsoft Edge

|Setting name|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Allow web browser**|No|Yes|
|**Allow search suggestions in address bar**|Yes|Yes|
|**Allow sending intranet traffic to Internet Explorer**|Yes|No|
|**Allow do not track**|Yes|Yes|
|**Enable SmartScreen**|Yes|Yes|
|**Allow active scripting**|Yes|Yes|
|**Allow pop-ups**|Yes|No|
|**Allow cookies**|Yes|Yes|
|**Allow Autofill**|Yes|No|
|**Allow Password Manager**|Yes|Yes|
|**Enterprise Mode site list location**<br /><br />Specifies where to find the list of web sites that will open in Enterprise mode. Users cannot edit this list.|Yes|No|

### Apps

|Setting name|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Allow application store**|No|Yes|

## Device capability settings

### Cellular

|Setting name|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Allow data roaming**|Yes|Yes|
|**Allow VPN over cellular**|Yes|Yes|
|**Allow VPN roaming over cellular**|Yes|Yes|

### Hardware

|Setting name|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Allow camera**|Yes|Yes|
|**Allow removable storage**|Yes|Yes|
|**Allow Wi-Fi**|No|Yes|
|**Allow internet sharing**|Yes|Yes|
|**Allow manual Wi-Fi configuration**|No|Yes|
|**Allow automatic connection to free Wi-Fi hotspots**|Yes|Yes|
|**Allow geolocation**<br /><br />Specifies whether the device can use location services information.|Yes|Yes|
|**Allow NFC**|Yes|Yes|
|**Allow Bluetooth**|Yes|Yes|
|**Allow Bluetooth discoverable mode**|Yes|Yes|
|**Allow Bluetooth advertising**<br /><br />Allows devices to receive advertisements over Bluetooth.|Yes|Yes|
|**Allow Bluetooth connectable mode** **Important:** This setting is no longer supported by Windows 10 and will be removed in the future.|Yes|Yes|
|**Allow phone reset**|Yes|Yes|
|**Allow USB connection**|Yes|Yes|
|**Allow AntiTheft mode**<br /><br />Configure whether Windows Antitheft mode is enabled.|Yes|Yes|

### Features

|Setting name|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Allow copy and paste**|No|Yes|
|**Allow voice recording**|No|Yes|
|**Allow Cortana**|Yes|Yes|
|**Allow action center notifications**|No|Yes|

## Updates settings

|Setting name|Description|Windows 10 Desktop|Windows 10 Mobile|
|----------------|---------------|----------------------|---------------------|
|**Allow automatic updates**|Enable this setting to allow automatic updates. Then, configure one of several settings to control update behavior.|Yes|No|

## Deploy the Configuration Policy

1.  Deploy the configuration policy to one or more groups of users or devices in your organization.

For more information about how to deploy policies, see [Use policies to manage computers and mobile devices with Microsoft Intune](../Topic/Use-policies-to-manage-computers-and-mobile-devices-with-Microsoft-Intune.md).

A status summary and alerts In the **Policy** workspace identify issues with the policy that require your attention. Additionally, a status summary appears in the **Dashboard** workspace.

## See Also
[Use policies to manage computers and mobile devices with Microsoft Intune](../Topic/Use-policies-to-manage-computers-and-mobile-devices-with-Microsoft-Intune.md)

