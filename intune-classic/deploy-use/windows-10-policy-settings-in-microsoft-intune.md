---
# required metadata

title: Windows 10 policy settings 
description: Use the policy settings listed in this topic to help you configure built-in and custom settings for enrolled Windows 10 desktop and Windows 10 Mobile devices.
keywords:
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 09/05/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855ROBOTS: NOINDEX,NOFOLLOW

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Intune policy settings for Windows 10 devices in Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

This topic contains information to help you to understand the Intune policy settings that you can use to manage Windows 10 devices. Read this topic alongside the procedures in [Manage settings and features on your-devices with Microsoft Intune policies](/intune-classic/get-started/windows-pc-management-capabilities-in-microsoft-intune).

You can choose from two policy types:

- **Custom policy**: Use the Microsoft Intune **custom policy** for Windows 10 and Windows 10 Mobile to deploy OMA-URI (Open Mobile Alliance Uniform Resource Identifier) settings that can be used to control features on devices. Windows 10 makes many CSP settings available, for example, the [Policy Configuration Service Provider (Policy CSP)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).
- **General configuration policy**: Use this policy type when you want to select settings from the built-in list that's supplied with Microsoft Intune.

## Custom policy settings

Supply the following settings in a custom policy.

### General settings

Enter a name and an optional description for this policy to help you identify it in the Intune console.

### OMA-URI settings

For each OMA-URI setting you want to add, enter the following information:

- **Setting name**: Enter a unique name for the OMA-URI setting to help you identify it in the list of settings. You can find more information about URI settings at [Policy Configuration Service Provider (Policy CSP)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).
- **Setting description**: Optionally, enter a description for the setting.
- **Data type**: Choose from the following data types:
	- **String**
	- **String (XML)**
	- **Date and time**
	- **Integer**
	- **Floating point**
	- **Boolean**
- **OMA-URI (case sensitive)**: Specify the OMA-URI you want to supply a setting for.
- **Value**: Specify the value to associate with the OMA-URI that you entered.

### Example
In the following screenshot, the setting **Connectivity/AllowVPNOverCellular** has been enabled. This lets a Windows 10 device open a VPN connection when it's on a cellular network.

> ![Example of a custom policy that contains VPN settings](./media/custom-policy-example.png)

### How to find the policies you can configure

You’ll find a complete list of all configuration service providers (CSPs) that Windows 10 supports in the [Configuration service provider reference](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) in the Windows documentation library.

Not all settings are compatible with all Windows 10 versions. The table in the Windows topic tells you which versions are supported for each CSP.

Additionally, Intune does not support all of the settings listed in the topic. To find out if Intune supports the setting you want, open the topic for that setting. Each setting page shows it’s supported operation. To work with Intune, the setting must support the **Add** or **Replace** operations.

## General configuration policy settings

Use the Microsoft Intune **general configuration policy** for Windows 10 to configure built-in settings for enrolled Windows 10 desktop and Windows 10 Mobile devices.

### Password

|Setting name|Additional information (where required)|
|----------------|----------------------|
|**Require a password to unlock devices**|-|
|**Required password type**|Specifies whether the password must be alphanumeric or numeric only|
|**Required password type** - **Minimum number of character sets**| Specifies how many of the character sets (lowercase letters, uppercase letters, numbers, and symbols)  must be included in the password|
|**Minimum password length**|Applies to Windows 10 Mobile only|
|**Number of repeated sign-in failures to allow before the device is wiped**.|For devices that are running Windows 10: If the device has BitLocker enabled, it's put into BitLocker recovery mode after sign-in fails the number of times that you specified. If the device is not BitLocker enabled, then this setting doesn't apply.<br>For devices that are running Windows 10 Mobile: After sign-in fails the number of times you specify, the device is wiped.|
|**Minutes of inactivity before screen turns off**|Specifies the length of time a device must be idle before the screen is locked|
|**Password expiration (days)**|Specifies the length of time after which the device password must be changed|
|**Remember password history**|Specifies whether to restrict the user from creating previously used passwords|
|**Remember password history** - **Prevent reuse of previous passwords**|Specifies the number of previously used passwords that are remembered by the device|
|**Require a password when the device returns from an idle state**|Specifies that the user must enter a password to unlock the device (Windows 10 Mobile only)|

### Encryption

|Setting name|Additional information (where required)|
|----------------|----------------------|
|**Require encryption on mobile device**|Enables encryption on targeted devices<br>(Windows 10 Mobile only)|

### System

|Setting name|Additional information (where required)|
|----------------|----------------------|
|**Allow screen capture**|Lets the user capture the device screen as an image (Windows 10 Mobile only)|
|**Allow manual unenrollment**|Lets the user manually delete the workplace account from the device|
|**Allow manual root certificate installation**|Applies to Windows 10 Mobile|
|**Allow diagnostic and usage data to be sent to Microsoft**|Possible values are:<br><br>**No** - No data is sent to Microsoft<br>**Basic** - Limited information is sent to Microsoft<br>**Enhanced** - Enhanced diagnostic data   is sent to Microsoft<br>**Full (recommended)** - Sends the same data as **Enhanced**, plus additional data about the device state|


### Account and synchronization

|Setting name|Additional information (where required)|
|----------------|----------------------|---------------------|
|**Allow Microsoft account**|Lets the user associate a Microsoft account with the device|
|**Allow adding non-Microsoft accounts manually**|Lets the user add email accounts to the device that are not associated with a Microsoft account|
|**Allow settings synchronization for Microsoft accounts**|Allow device and app settings that are associated with a Microsoft account to synchronize between devices|

### Microsoft Edge

|Setting name|Additional information (where required)|
|----------------|----------------------|
|**Allow web browser**|Allows the use of the Edge web browser on the device<br>(Windows 10 Mobile only)|
|**Allow search suggestions in address bar**|Lets your search engine suggest sites as you type search phrases|
|**Allow sending intranet traffic to Internet Explorer**|Lets users open intranet websites in Internet Explorer<br>(Windows 10 desktop only)|
|**Allow do not track**|Configures the Edge browser to send do not track headers to websites that users visit|
|**Enable SmartScreen**||
|**Allow active scripting**|Allows scripts, such as Javascript, to run in the Edge browser|
|**Allow pop-ups**|Applies to Windows 10 desktop only|
|**Allow cookies**||
|**Allow Autofill**|Allows users to change autocomplete settings in the browser<br>(Windows 10 desktop only)|
|**Allow Password Manager**|Enables or disables the Edge Password Manager feature|
|**Enterprise Mode site list location**|Specifies where to find the list of web sites that open in Enterprise mode. Users cannot edit this list.<br>(Windows 10 desktop only)|

### Apps

|Setting name|Additional information (where required)|
|----------------|----------------------|---------------------|
|**Allow application store**|Applies to Windows 10 Mobile only|



### Cellular

|Setting name|Additional information (where required)|
|----------------|----------------------|---------------------|
|**Allows data roaming**|Allow roaming between networks when accessing data|
|**Allow VPN over cellular**|Controls whether the device can access VPN connections when connected to a cellular network|
|**Allow VPN roaming over cellular**|Controls whether the device can access VPN connections when roaming on a cellular network|

### Hardware

|Setting name|Additional information (where required)|
|----------------|----------------------|
|**Allow camera**|-|
|**Allow removable storage**|Specifies whether external storage devices such as an SD card can be used with the device|
|**Allow Wi-Fi**|Applies to Windows 10 Mobile only|
|**Allow Internet sharing**|Allows the use of Internet connection sharing on the device|
|**Allow manual Wi-Fi configuration**|Controls whether the user can configure their own Wi-Fi connections, or whether they can only use connections configured by a Wi-Fi profile<br>(Windows 10 Mobile only)|
|**Allow automatic connection to free Wi-Fi hotspots**|Lets the device automatically connect to free Wi-Fi hotspots and automatically accept any terms and conditions for the connection|
|**Allow geolocation**|Specifies whether the device can use location services information|
|**Allow NFC**|Allows the device to use it's Near Field Communications capabilities|
|**Allow Bluetooth**|-|
|**Allow Bluetooth discoverable mode**|Lets this device be discovered by other Bluetooth-enabled devices|
|**Allow Bluetooth advertising**|Allows devices to receive advertisements over Bluetooth|
|**Allow phone reset**|Controls whether the user can do a factory reset on their device|
|**Allow USB connection**|Controls whether devices can access external storage devices through a USB connection|
|**Allow AntiTheft mode**|Configure whether Windows AntiTheft mode is enabled|

### Features

|Setting name|Additional information (where required)|
|----------------|----------------------|---------------------|
|**Allow copy and paste**|Applies to Windows 10 Mobile only|
|**Allow voice recording**|Applies to Windows 10 Mobile only|
|**Allow Cortana**|Enable or disable the Cortana voice assistant|
|**Allow action center notifications**|Enable or disable action center notifications on the device lock screen<br>(Windows 10 Mobile only)|

### Windows Defender

All settings are for Windows 10 desktop only.

|Setting name|Additional information (where required)|
|----------------|----------------------|---------------------|
|**Allow real-time monitoring**|Enables real-time scanning for malware, spyware, and other unwanted software|
|**Allow behavior monitoring**|Lets Defender check for certain known patterns of suspicious activity on devices|
|**Enable Network Inspection System**|The Network Inspection System (NIS) helps to protect devices against network-based exploits by using the signatures of known vulnerabilities from the Microsoft Endpoint Protection Center to help detect and block malicious traffic|
|**Scan all downloads**|Controls whether Defender scans all files that are downloaded from the Internet|
|**Allow script scanning**|Lets Defender scan scripts that are used in Internet Explorer|
|**Monitor file and program activity**|Allows Defender to monitor file and program activity on devices|
|**Days to track resolved malware**|Lets Defender continue to track resolved malware for the number of days you specify so that you can manually check previously affected devices. If you set the number of days to **0**, malware remains in the Quarantine folder and is not automatically removed. |
|**Allow client UI access**|Controls whether the Windows Defender user interface is hidden from users.<br>When this setting is changed, it takes effect the next time the user's PC is restarted.|
|**Schedule a daily quick scan**|Lets you schedule a quick scan that occurs daily at the time you select|
|**Schedule a system scan**|Lets you schedule a full or quick system scan that occurs regularly on the day and time you select|
|**Limit CPU usage during a scan**|Lets you limit the amount of CPU that scans are allowed to use (from **1** to **100**)|
|**Scan archive files**|Allows Defender to scan archived files such as .zip or .cab files.|
|**Scan email messages**|Allows Defender to scan email messages as they arrive on the device|
|**Scan removable drives**|Lets Defender scan removable drives like USB sticks|
|**Scan mapped network drives**|Lets Defender scan files on mapped network drives.<br>If the files on the drive are read-only, Defender will be unable to remove any malware found in them.|
|**Scan files opened from network shared folders**|Lets Defender scan files on shared network drives (for example, those accessed from a UNC path).<br>If the files on the drive are read-only, Defender will be unable to remove any malware found in them.|
|**Signature update interval**|Specifies the interval at which Defender checks for new signature files.|
|**Allow cloud protection**|Allows or blocks the Microsoft Active Protection Service from receiving information about malware activity from devices that you manage. This information is used to improve the service in the future.|
|**Prompt users for samples submission**|Controls whether files that might require further analysis by Microsoft to determine if they are malicious are automatically sent to Microsoft|
|**Potentially Unwanted Application Detection**|Protects enrolled Windows desktop devices against running software that's classified by Windows Defender as potentially unwanted. You can protect against these applications running, or use audit mode to report when a potentially unwanted application is installed.|
|**Files and folders to exclude when running a scan or using real-time protection**|Adds one or more files and folders like **C:\Path** or **%ProgramFiles%\Path\filename.exe** to the exclusions list. These files and folders aren't included in any real-time or scheduled scans.|
|**File extensions to exclude when running a scan or using real-time protection**|Add one or more file extensions like **jpg** or **txt** to the exclusions list. Any files with these extensions are not  included in any real-time or scheduled scans.|
|**Processes to exclude when running a scan or using real-time protection**|Adds one or more processes of the type **.exe**, **.com**, or **.scr** to the exclusions list. These processes are not included in any real-time or scheduled scans.|


### Updates

|Setting name|Additional information (where required)|
|----------------|---------------|
|**Allow automatic updates**|Allows automatic updates. Configure one of the following settings to control update behavior:<br />**Notify download**<br />**Auto install at maintenance time**<br />**Auto install and reboot at maintenance time**<br />**Auto install and reboot at scheduled time**:  Note that when this option is selected, you can also configure the following settings:  **Suppress notification to end user** and **Define install day for scheduled updates**.<br>(Windows 10 desktop only)|
|**Allow pre-release features**|Lets Microsoft deploy pre-release settings and features to Windows 10 devices. You can select to allow settings only, or all pre-release settings and features to be installed.|

### See also
[Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
