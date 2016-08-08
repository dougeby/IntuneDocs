---
# required metadata

title: Windows 10 policy settings | Microsoft Intune
description: Use the policy settings listed in this topic to help you configure built-in and custom settings for enrolled Windows 10 desktop, and Windows 10 Mobile devices.
keywords:
author: robstackmsft
manager: angrobe
ms.date: 07/31/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Windows 10 policy settings in Microsoft Intune

Use the policy settings listed in this topic to help you configure built-in and custom settings for enrolled Windows 10 desktop, and Windows 10 Mobile devices.

> [!IMPORTANT]
> You can manage Windows 10 PCs in two ways; by enrolling them, or by installing the Intune PC client software. Each method offers different capabilities (See [Choose how to manage devices](/intune/get-started/choose-how-to-manage-devices) for more information.
> When you manage your Windows 10 PCs with the Intune PC client software, you cannot use the policies and settings detailed in this topic. To apply these settings, your Windows 10 devices must be enrolled with Intune.

## General configuration policy settings

Use the Microsoft Intune **general configuration policy** for Windows 10 to configure general settings for enrolled Windows 10 desktop, and Windows 10 Mobile devices. 


## - Password

|Setting name|Details|
|----------------|----------------------|
|**Require a password to unlock devices**|Require a password on supported devices.|
|**Required password type**|Specifies the type of password that will be required, such as numeric only, or alphanumeric|
|**Required password type** - **Minimum number of character sets**|There are four character sets, lowercase letters, uppercase letters, numbers, and symbols. This setting specifies how many different character sets must be included in the password.|
|**Minimum password length**|Specifies the minimum number of characters the device password must contain.<br>(Windows 10 Mobile only)|
|**Number of repeated sign-in failures to allow before the device is wiped**|Wipes the device if this number of login attempts fail.|
|**Minutes of inactivity before screen turns off**|Specifies the length of time a device must be idle before the screen is locked.|
|**Password expiration (days)**|Specifies the length of time after which the device password must be changed.|
|**Remember password history**|Specifies whether you want to restrict the end user from creating previously used passwords.|
|**Remember password history** - **Prevent reuse of previous passwords**|Specifies the number off previously used passwords remembered by the device.|
|**Require a password when the device returns from an idle state**|If enabled, the user must enter a password to unlock the device from an idle state.<br>(Windows 10 Mobile only)|

## - Encryption

|Setting name|Details|
|----------------|----------------------|
|**Require encryption on mobile device**|Enables encryption on targeted devices.<br>(Windows 10 Mobile only)|

## - System

|Setting name|Details|
|----------------|----------------------|
|**Allow screen capture**|Let's the user capture the device screen as an image.<br>(Windows 10 Mobile only)|
|**Allow manual unenrollment**|Lets the user manually delete the workplace account from the device.|
|**Allow manual root certificate installation**|Specifies whether the user can manually install root certificates.<br>(Windows 10 Mobile only)|
|**Allow diagnostic and usage data to be sent to Microsoft**|Determines the amount of diagnostic and usage data that is sent to Microsoft from devices.<br><br>**No** - No data is sent to Microsoft<br>**Basic** - The device sends only limited information to Microsoft<br>**Enhanced** - Sends enhanced diagnostic data to Microsoft<br>**Full (recommended)** - Sends the same data as **Enhanced**, plus additional data about the device state|


## - Account and synchronization

|Setting name|Details|
|----------------|----------------------|---------------------|
|**Allow Microsoft account**|Lets the user associate a Microsoft account with the device.|
|**Allow adding non-Microsoft accounts manually**|Lets the user add email accounts to the device that are not associated with a Microsoft account.|
|**Allow settings synchronization for Microsoft accounts**|Allow device and app settings associated with a Microsoft account to synchronize between devices.|

## - Microsoft Edge

|Setting name|Details|
|----------------|----------------------|
|**Allow web browser**|Allow the use of the Edge web browser on the device.<br>(Windows 10 Mobile only)|
|**Allow search suggestions in address bar**|Lets your search engine suggest sites as you type search phrases.|
|**Allow sending intranet traffic to Internet Explorer**|Lets users open intranet websites in Internet Explorer.<br>(Windows 10 desktop only)|
|**Allow do not track**|Configures the Edge browser to send do not track headers to websites that users visit.|
|**Enable SmartScreen**|Enables the SmartScreen browser setting on devices.|
|**Allow active scripting**|Allows scripts, like Javascript to be run in the Edge browser.|
|**Allow pop-ups**|Enables or disables the browser pop-up blocker.<br>(Windows 10 desktop only)|
|**Allow cookies**|Allow or disable cookies.|
|**Allow Autofill**|Allow users to change autocomplete settings in the browser.<br>(Windows 10 desktop only)|
|**Allow Password Manager**|Enable or disable the Edge Password Manager feature.|
|**Enterprise Mode site list location**|Specifies where to find the list of web sites that will open in Enterprise mode. Users cannot edit this list.<br>(Windows 10 desktop only)|

## - Apps

|Setting name|Details|
|----------------|----------------------|---------------------|
|**Allow application store**|Allow the user to access the app store on the device.<br>(Windows 10 Mobile only)|



## - Cellular

|Setting name|Details|
|----------------|----------------------|---------------------|
|**Allow data roaming**|Allow roaming between networks when accessing data.|
|**Allow VPN over cellular**|Controls whether the device can access VPN connections when connected to a cellular network.|
|**Allow VPN roaming over cellular**|Controls whether the device can access VPN connections when roaming on a cellular network.|

## - Hardware

|Setting name|Details|
|----------------|----------------------|
|**Allow camera**|Specifies whether the device camera can be used.|
|**Allow removable storage**|Specifies whether external storage devices such as an SD card can be used with the device.|
|**Allow Wi-Fi**|Allows the use of the devices Wi-Fi capability.<br>(Windows 10 Mobile only)|
|**Allow internet sharing**|Allow the use of Internet connection sharing on the device.|
|**Allow manual Wi-Fi configuration**|Controls whether the user can configure their own Wi-Fi connections, or whether they can only use connections configured by a Wi-Fi profile.<br>(Windows 10 Mobile only)|
|**Allow automatic connection to free Wi-Fi hotspots**|Lets the device automatically connect to free Wi-Fi hotspots and automatically accept any terms and conditions for the connection.|
|**Allow geolocation**|Specifies whether the device can use location services information.|
|**Allow NFC**|Allows the device to use it's Near Field Communications capabilities.|
|**Allow Bluetooth**|Enables the use of Bluetooth capabilities on the device.|
|**Allow Bluetooth discoverable mode**|Let's this device be discovered by other Bluetooth-enabled devices.|
|**Allow Bluetooth advertising**|Allows devices to receive advertisements over Bluetooth.|
|**Allow phone reset**|Controls whether the user can factory reset their device.|
|**Allow USB connection**|Controls whether devices can access external storage devices through a USB connection.|
|**Allow AntiTheft mode**|Configure whether Windows Antitheft mode is enabled.|

## - Features

|Setting name|Details|
|----------------|----------------------|---------------------|
|**Allow copy and paste**|Enable or disable the use of copy and paste on the device.<br>(Windows 10 Mobile only)|
|**Allow voice recording**|Enable or disable the voice recording features on the device.<br>(Windows 10 Mobile only)|
|**Allow Cortana**|Enable or disable the Cortana voice assistant.|
|**Allow action center notifications**|Enable or disable action center notifications on the device lock screen.<br>(Windows 10 Mobile only)|

## - Windows Defender

All settings are for Windows 10 desktop only.

|Setting name|Details|
|-|-|
|**Allow real-time monitoring**|Enables real-time scanning for malware, spyware, and other unwanted software.|
|**Allow behavior monitoring**|Lets Defender check for certain known patterns of suspicious activity on devices.|
|**Enable Network Inspection System**|The Network Inspection System (NIS) helps to protect devices against network-based exploits by using the signatures of known vulnerabilities from the Microsoft Endpoint Protection Center to help detect and block malicious traffic.|
|**Scan all downloads**|Controls whether Defender scans all files downloaded from the Internet.|
|**Allow script scanning**|Lets Defender scan scripts that are used in Internet Explorer.|
|**Monitor file and program activity**|Enable this setting to allow Defender to monitor file and program activity on devices.|
|**Days to track resolved malware**|Lets Defender continue to track resolved malware for the number of days you specify so that you can manually check previously affected devices. If you set the number of days to **0**, malware remains in the Quarantine folder and is not automatically removed. |
|**Allow client UI access**|Controls whether the Windows Defender user interface is hidden from end users.<br>When this setting is changed, it will take effect the next time the end user's PC is restarted.|
|**Schedule a daily quick scan**|Lets you schedule a quick scan that occurs daily at the time you select.|
|**Schedule a system scan**|Lets you schedule a full or quick system scan that occurs regularly on the day and time you select.|
|**Limit CPU usage during a scan**|Lets you limit the amount of CPU that scans are allowed to use (from **1** to **100**)|
|**Scan archive files**|Allows Defender to scan archived files such as Zip or Cab files.|
|**Scan email messages**|Allows Defender to scan email messages as they arrive on the device.|
|**Scan removable drives**|Lets Defender scan removable drives like USB sticks.|
|**Scan mapped network drives**|Lets Defender scan files on mapped network drive.<br>If the files on the drive are read-only, Defender will be unable to remove any malware found in them.|
|**Scan files opened from network shared folders**|Lets Defender scan files on shared network drives (for instance, those accessed from a UNC path.<br>If the files on the drive are read-only, Defender will be unable to remove any malware found in them.|
|**Signature update interval**|Specify the interval at which Defender will check for new signature files.|
|**Allow cloud protection**|Allow or block the Microsoft Active Protection Service from receiving information about malware activity from devices you manage. This information is used to improve the service in the future.|
|**Prompt users for samples submission**|Controls whether files that might require further analysis by Microsoft to determine if they are malicious are automatically sent to Microsoft.|
|**Potentially Unwanted Application Detection**|This setting can be used to protect enrolled Windows desktop devices against running software classified by Windows Defender as potentially unwanted. You can protect against these applications running, or use audit mode to report when a potentially unwanted application is installed.|
|**Files and folders to exclude when running a scan or using real-time protection**|Add one or more files and folders like **C:\Path** or **%ProgramFiles%\Path\filename.exe** to the exclusions list. These files and folders will not be included in any real-time, or scheduled scans.|
|**File extensions to exclude when running a scan or using real-time protection**|Add one or more file extensions like **jpg** or **txt** to the exclusions list. Any files with these extensions will not be included in any real-time, or scheduled scans.|
|**Processes to exclude when running a scan or using real-time protection**|Add one or more processes of the type **.exe**, **.com**, or **.scr** to the exclusions list. These processes will not be included in any real-time, or scheduled scans.| 


## - Updates

|Setting name|Details|
|----------------|---------------|
|**Allow automatic updates**|Enable this setting to allow automatic updates. Then, configure one of the following settings to control update behavior:<br /><br />**Notify download**<br /><br />**Auto install at maintenance time**<br /><br />**Auto install and reboot at maintenance time**<br /><br />**Auto install and reboot at scheduled time** **Note:** When this option is selected, you can also configure the following settings:  **Suppress notification to end user** and **Define install day for scheduled updates**.<br>(Windows 10 desktop only)|
|**Allow pre-release features**|Lets Microsoft deploy pre-release settings and features to Windows 10 devices. You can select to allow settings only, or all pre-release settings and features to be installed.|

## Custom policy settings
Use the Microsoft Intune **custom configuration policy** for Windows 10 and Windows 10 Mobile to deploy OMA-URI (Open Mobile Alliance Uniform Resource Identifier) settings that can be used to control features on Windows 10 and Windows 10 Mobile devices. These are standard settings that many mobile device manufacturers use to control device features.

This capability is intended to allow you to deploy Windows 10 settings that are not configurable with an Intune general configuration policy.



## - General

|Setting name|Details|
    |----------------|--------------------|
    |**Name**|Enter a unique name for the policy to help you identify it in the Intune console.|
    |**Description**|Provide a description that gives an overview of the policy and other relevant information that helps you to locate it.|

## - OMA-URI settings

|Setting name|Details|
    |--------|--------------------|
    |**Setting name**|Enter a unique name for the OMA-URI setting to help you identify it in the list of settings.|
    |**Setting description**|Provide a description that gives an overview of the setting and other relevant information to help you locate it.|
    |**Data type**|Select the date type in which you will specify this OMA-URI setting. Choose from:<br /><br />-   **String**<br />-   **String (XML)**<br />-   **Date and time**<br />-   **Integer**<br />-   **Floating point**<br />-   **Boolean**|
    |**OMA-URI (case sensitive)**|Specify the OMA-URI you want to supply a setting for.|
    |**Value**|Specify the value to associate with the OMA-URI you specified previously.|


## Windows 10 URI settings
This topic lists the settings that you can configure for Windows 10 and Windows 10 Mobile devices in a Microsoft Intune **Windows 10 Custom Policy**.

All devices must be enrolled with Intune if you want to use the Windows Custom URI Policy.

## - Policy

|Policy name|Details|
|---------------|------------|-----------|
|**​Allow Auto Update**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Update/AllowAutoUpdate<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** - **5** (default: **1**)|
|**Schedule Install Day**<br>(mobile only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Update/ScheduledInstallDay<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** - Every day (default)<br>**1** - Sunday<br>**2** - Monday<br>**3** - Tuesday<br>**4** - Wednesday<br>**5** - Thursday<br>**6** - Friday<br>**7** - Saturday|
|**Schedule Install Time**<br>(desktop and mobile)|**URI full path:** ./Vendor/MSFT/Policy/Config/Update/ScheduledInstallTime<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – **23** hours (**0** is midnight) (default: **3**)|
|**DeviceLock/AllowIdleReturnWithoutPassword**<br>(mobile only)|**URI full path:** ./Vendor/MSFT/Policy/Config/DeviceLock/AllowIdleReturnWithoutPassword<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** - user is not able to set the password grace period timer, and the value is set as “each time”<br>**1** - user is able to set the password grace period timer (default)|
|**WiFi/AllowWiFi**<br>(mobile only)|**URI full path:** ./Vendor/MSFT/Policy/Config/WiFi/AllowWiFi<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – Do not allow **use Wi-Fi connection**.<br>**1** –**Allow use Wi-Fi connection** (default)|
|**WiFi/AllowInternetSharing**<br>(desktop and mobile)|**URI full path:** ./Vendor/MSFT/Policy/Config/WiFi/AllowInternetSharing<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – Do not allow Internet Sharing.<br>**1** – Allow Internet Sharing (default)|
|**WiFi/AllowAutoConnectToWiFiSenseHotspots**<br>(desktop and mobile)|**URI full path:** ./Vendor/MSFT/Policy/Config/WiFi/AllowAutoConnectToWiFiSenseHotspots<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**WiFi/AllowManualWiFiConfiguration**<br>(mobile only)|**URI full path:** ./Vendor/MSFT/Policy/Config/WiFi/AllowManualWiFiConfiguration<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – No Wi-Fi connection outside of MDM provisioned is allowed.<br>**1** – Adding new network SSIDs beyond the already MDM provisioned ones is allowed (default)|
|**System/AllowLocation**<br>(desktop and mobile)|**URI full path:** ./Vendor/MSFT/Policy/Config/System/AllowLocation<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**System/AllowTelemetry**<br>(desktop and mobile)|**URI full path:** ./Vendor/MSFT/Policy/Config/System/AllowTelemetry<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – Not allowed (Enterprise only setting)<br>**1** – Limited<br>**2** – Full (default)<br>**3** -  Full and  diagnostics information|
|**System/AllowExperimentation**<br>(desktop and mobile)|**URI full path:** ./Vendor/MSFT/Policy/Config/System/AllowExperimentation<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – Not allowed<br>**1**- Settings only (default)<br>**2**- Settings and experimentation|
|**Security/AntiTheftMode**<br>(mobile only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Security/AntiTheftMode<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** - don't allow Anti Theft mode<br>**1** User preference (default)|
|**Connectivity/AllowUSBConnection**<br>(mobile only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowUSBConnection<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**System/AllowUserToResetPhone**<br>(mobile only)|**URI full path:** ./Vendor/MSFT/Policy/Config/System/AllowUserToResetPhone<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**Connectivity/AllowCellularDataRoaming**<br>(desktop and mobile)|**URI full path:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowCellularDataRoaming<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**Connectivity/AllowVPNOverCellular**<br>(desktop and mobile)|**URI full path:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNOverCellular<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** - VPN is not allowed over cellular<br>**1** – VPN could use any connection including cellular (default)|
|**Connectivity/AllowVPNRoamingOverCellular**<br>(mobile only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**Connectivity/AllowVPNRoamingOverCellular**<br>(mobile only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**Connectivity/AllowBluetooth**<br>(desktop and mobile)|**URI full path:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowBluetooth<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – Don’t allow the user to turn Bluetooth on.<br>**1** – Reserved. The user can turn on and configure Bluetooth (not supported in Windows Phone 8.1 for MDM, EAS, Windows 10 desktop or Windows 10 Mobile)<br>**2** - Allowed. The user can turn on and configure Bluetooth (default)|
|**Experience/AllowScreenCapture**<br>(mobile only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Experience/AllowScreenCapture<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**Experience/AllowTaskSwitcher**<br>(mobile only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Experience/AllowTaskSwitcher<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**Experience/AllowVoiceRecording**<br>(mobile only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Experience/AllowVoiceRecording<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**Experience/AllowSyncMySettings**<br>(mobile only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Experience/AllowSyncMySettings<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – Don’t allow roaming<br>**1** – Allow roaming (default)|
|**Experience/AllowManualMDMUnenrollment**<br>(desktop and mobile)|**URI full path:** ./Vendor/MSFT/Policy/Config/Experience/AllowManualMDMUnenrollment<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**Accounts/AllowMicrosoftAccountConnection**<br>(desktop and mobile)|**URI full path:** ./Vendor/MSFT/Policy/Config/Accounts/AllowMicrosoftAccountConnection<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**Accounts/AllowAddingNonMicrosoftAccountsManually**<br>(desktop and mobile)|**URI full path:** ./Vendor/MSFT/Policy/Config/Accounts/AllowAddingNonMicrosoftAccountsManually<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**Security/AllowManualRootCertificateInstallation**<br>(mobile only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Security/AllowManualRootCertificateInstallation<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**Security/AllowAddProvisioningPackages**<br>(desktop and mobile)|**URI full path:** ./Vendor/MSFT/Policy/Config/Security/AllowAddProvisioningPackages<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**Search/DisableBackoff**<br>(desktop and mobile)|**URI full path:** ./Vendor/MSFT/Policy/Config/Search/DisableBackoff<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** (default)<br>**1**|
|**Search/PreventRemoteQueries**<br>(desktop and mobile)|**URI full path:** ./Vendor/MSFT/Policy/Config/Search/PreventRemoteQueries<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0**<br>**1** (default)|
|**Search/AllowUsingDiacritics**<br>(desktop and mobile)|**URI full path:** ./Vendor/MSFT/Policy/Config/Search/AllowUsingDiacritics<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br> **0** (default)<br>**1**|
|**Search/AlwaysUseAutoLangDetection**<br>(desktop and mobile)|**URI full path:** ./Vendor/MSFT/Policy/Config/Search/AlwaysUseAutoLangDetection<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** (default)<br>**1**|
|**Search/DisableRemovableDriveIndexing**<br>(desktop and mobile)|**URI full path:** ./Vendor/MSFT/Policy/Config/Search/DisableRemovableDriveIndexing<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** (default)<br>**1**|
|**Search/PreventIndexingLowDiskSpaceMB**<br>(desktop and mobile)|**URI full path:** ./Vendor/MSFT/Policy/Config/Search/PreventIndexingLowDiskSpaceMB<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0**<br>**1** (default)|
|**Search/AllowIndexingEncryptedStoresOrItems**<br>(desktop and mobile)|**URI full path:** ./Vendor/MSFT/Policy/Config/Search/AllowIndexingEncryptedStoresOrItems<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** (default)<br>**1**|
|**Security/AllowRemoveProvisioningPackage**<br>(desktop and mobile)|**URI full path:** ./Vendor/MSFT/Policy/Config/Security/AllowRemoveProvisioningPackage<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**Security/RequireProvisioningPackageSignature**<br>(desktop and mobile)|**URI full path:** ./Vendor/MSFT/Policy/Config/Security/RequireProvisioningPackageSignature<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** (default)<br>**1**|
|**AboveLock/AllowActionCenterNotifications**<br>(desktop and mobile)|**URI full path:** ./Vendor/MSFT/Policy/Config/AboveLock/AllowActionCenterNotifications<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**TextInput/AllowIMENetworkAccess**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/TextInput/AllowIMENetworkAccess<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – Don’t allow<br>Open Extended Dictionary is turned off.<br>A user cannot:<br>Add a new Open Extended Dictionary<br /><br />Add a new search integration configuration file<br>Use the cloud candidate feature<br>Send user registered word<br>Additionally:<br>An Open Extended Dictionary that was added before enabling this policy setting is not used for conversion.<br>A search integration configuration file that was installed before enabling this policy setting is not used.<br>**1** - Allow<br>Open Extended Dictionary can be added and used by default. Also, the search integration function can be used by default.<br>A user can:<br>Use the cloud candidate feature<br>Send user registered word.|
|**TextInput/AllowIMELogging**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/TextInput/AllowIMELogging<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** - Misconversion logging is turned off. Auto-tuned data and input history data is not saved to a file.<br>**1** - Misconversion logging is turned on. Auto-tuned data and input history data is saved to a file (default)|
|**TextInput/AllowJapaneseNonPublishingStandardGlyph**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseNonPublishingStandardGlyph<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**TextInput/AllowJapaneseIVSCharacters**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIVSCharacters<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**TextInput/AllowJapaneseUserDictionary**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseUserDictionary<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**TextInput/AllowJapaneseIMESurrogatePairCharacters**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIMESurrogatePairCharacters<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**TextInput/ExcludeJapaneseIMEExceptShiftJIS**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptShiftJIS<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** - No characters are filtered (default)<br>**1** - All Except Shift JIS characters are filtered|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** - No characters are filtered (default)<br>**1** - All except JIS0208 characters are filtered|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** - No characters are filtered (default)<br>**1** - All except JIS0208 characters or EUDC characters are filtered|
|**TextInput/AllowInputPanel**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/TextInput/AllowInputPanel<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**Bluetooth/AllowDiscoverableMode**<br>(desktop and mobile)|**URI full path:** ./Vendor/MSFT/Policy/Config/Bluetooth/AllowDiscoverableMode<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**Bluetooth/AllowAdvertising**<br>(desktop and mobile)|**URI full path:** ./Vendor/MSFT/Policy/Config/Bluetooth/AllowAdvertising<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**Settings/AllowDataSense**<br>(desktop and mobile)|**URI full path:** ./Vendor/MSFT/Policy/Config/Settings/AllowDataSense<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**Settings/AllowVPN**<br>(desktop and mobile)|**URI full path:** ./Vendor/MSFT/Policy/Config/Settings/AllowVPN<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**Settings/AllowWorkplace**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Settings/AllowWorkplace<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**Settings/AllowDateTime**<br>(desktop and mobile)|**URI full path:** ./Vendor/MSFT/Policy/Config/Settings/AllowDateTime<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**Settings/AllowLanguage**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Settings/AllowLanguage<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**Settings/AllowRegion**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Settings/AllowRegion<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**Settings/AllowSignInOptions**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Settings/AllowSignInOptions<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**Settings/AllowYourAccount**<br>(desktop and mobile)|**URI full path:** ./Vendor/MSFT/Policy/Config/Settings/AllowYourAccount<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**Settings/AllowPowerSleep**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Settings/AllowPowerSleep<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**Settings/AllowAutoPlay**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Settings/AllowAutoPlay<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**Experience/AllowCortana**<br>(desktop and mobile)|**URI full path:** ./Vendor/MSFT/Policy/Config/Experience/AllowCortana<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**Search/SafeSearchPermissions**<br>(mobile only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Search/SafeSearchPermissions<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – Strict, highest filtering against adult content<br>**1** – Moderate, moderate filtering against adult content (valid search results will not be filtered - default)|
|**Experience/AllowCopyPaste**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Experience/AllowCopyPaste<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**Force Start Size**<br>(mobile only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Start/ForceStartSize<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** - allow user change size (default)<br>**1** - force non-full screen<br>**2** - force full screen|
|**Update/RequireDeferUpgrade**<br>(desktop and mobile)|**URI full path:** ./Vendor/MSFT/Policy/Config/Update/RequireDeferUpgrade<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0**: do not defer upgrade (stay in current branch, CB - default)<br>**1**: Enable updates and upgrades to be deferred (Device follows current branch for business, CBB, rules)<br /><br />For more information, see:<br>[Introduction to Windows 10 servicing](https://technet.microsoft.com/library/mt598226.aspx)<br>[Plan for Windows 10 deployment](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpdatePeriod**<br>(desktop and mobile)|**Description:** Policy to defer software updates for up to 4 weeks<br /><br />**URI full path:** ./Vendor/MSFT/Policy/Config/Update/DeferUpdatePeriod<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br> **0**: Apply updates immediately (default)<br>**1**-**4**: number of weeks to defer software updates.<br /><br />For more information, see:<br>[Introduction to Windows 10 servicing](https://technet.microsoft.com/library/mt598226.aspx)<br>[Plan for Windows 10 deployment](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpgradePeriod**<br>(desktop and mobile)|**Description:** Policy to defer feature upgrades for up to 8 months<br /><br />**URI full path:** ./Vendor/MSFT/Policy/Config/Update/DeferUpgradePeriod<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0**: Apply updates immediately (default)<br>**1**-**8**: number of months to defer feature upgrades.<br /><br />For more information, see:<br>[Introduction to Windows 10 servicing](https://technet.microsoft.com/library/mt598226.aspx)<br>[Plan for Windows 10 deployment](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/PauseDeferrals**<br>(desktop and mobile)|**Description:** Allows a CBB machine to stop receiving updates and upgrades for 5 weeks. This should be used in case there is an issue with an update.<br /><br />**URI full path:** ./Vendor/MSFT/Policy/Config/Update/PauseDeferrals<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0**: Apply updates immediately (default)<br>**1**: Pause updates and upgrades (expires after 5 weeks)|

## - Windows Defender

|Policy name|Details|
|---------------|-----------|
|**AllowRealtimeMonitoring**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/AllowRealtimeMonitoring<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**AllowBehaviorMonitoring**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/AllowBehaviorMonitoring<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**AllowIntrusionPreventionSystem**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/AllowIntrusionPreventionSystem<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**AllowIOAVProtection**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/AllowIOAVProtection<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**AllowScriptScanning**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/AllowScriptScanning<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**AllowOnAccessProtection**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/AllowOnAccessProtection<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**RealTimeScanDirection**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/RealTimeScanDirection<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – Monitor all files (bi-directional - default)<br>**1** – Monitor incoming files<br>**2** – Monitor outgoing files|
|**DaysToRetainCleanedMalware**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/DaysToRetainCleanedMalware<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** - **90** – Represents what how long malware will be retained<br>**Default value:** **0** – keeps in the quarantine folder forever, and doesn’t automatically remove|
|**AllowUserUIAccess**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/AllowUserUIAccess<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**ScanParameter**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/ScanParameter<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**1** – Quick scan (default)<br>**2** - Full scan|
|**ScheduleScanDay**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleScanDay<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** - Everyday (default)<br>**1** - Monday<br>**2** - Tuesday<br>**3** - Wednesday<br>**4** - Thursday<br>**5** - Friday<br>**6** - Saturday<br>**7** - Sunday<br>**8** – No scheduled scan|
|**ScheduleScanTime**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleScanTime<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** - 12:00 am<br>**60** – 1:00 am<br>**120** – 2:00 am (default)<br>**180** – 3:00 am<br>**240** – 4:00 am<br>**300** – 5:00 am<br>**360** – 6:00 am<br>**420** – 7:00 am<br>**480** – 8:00 am<br>**540** – 9:00 am<br>**600** – 10:00 am<br>**660** – 11:00 am<br>**720** – 12:00 pm<br>**780** – 1:00 pm<br>**840** – 2:00 pm<br>**900** – 3:00 pm<br>**960** – 4:00 pm<br>**1020** – 5:00 pm<br>**1080** – 6:00 pm<br>**1140** – 7:00 pm<br>**1200** – 8:00 pm<br>**1260** – 9:00 pm<br>**1320** – 10:00 pm<br>**1381** – Maintenance window|
|**ScheduleQuickScanTime**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleQuickScanTime<br>**Data type:** Integer<br /><br />**Allowed values:**<br>**0** - 12:00 am<br>**60** – 1:00 am<br>**120** – 2:00 am (default)<br>**180** – 3:00 am<br>**240** – 4:00 am<br>**300** – 5:00 am<br>**360** – 6:00 am<br>**420** – 7:00 am<br>**480** – 8:00 am<br>**540** – 9:00 am<br>**600** – 10:00 am<br>**660** – 11:00 am<br>**720** – 12:00 pm<br>**780** – 1:00 pm<br>**840** – 2:00 pm<br>**900** – 3:00 pm<br>**960** – 4:00 pm<br>**1020** – 5:00 pm<br>**1080** – 6:00 pm<br>**1140** – 7:00 pm<br>**1200** – 8:00 pm<br>**1260** – 9:00 pm<br>**1320** – 10:00 pm<br>**1380** – 11:00 pm|
|**AVGCPULoadFactor**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/AVGCPULoadFactor<br /><br />**Data type:** Integer<br /><br />**Allowed values:0** - **100** (default: **50**)|
|**AllowArchiveScanning**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/AllowArchiveScanning<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**AllowEmailScanning**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/AllowEmailScanning<br /><br />**Data type:** Integer<br>**Allowed values:**<br>**0** – not allowed (default)<br>**1** – allowed|
|**AllowFullScanRemovableDriveScanning**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/AllowFullScanRemovableDriveScanning<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed (default)<br>**1** – allowed|
|**AllowFullScanOnMappedNetworkDrives**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/AllowFullScanOnMappedNetworkDrives<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**AllowScanningNetworkFiles**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/AllowScanningNetworkFiles<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default) – Also runs when RTP is on when it is set to allowed|
|**SignatureUpdateInterval**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/SignatureUpdateInterval<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – Do not check for signatures on an interval<br>**1** - Check for signatures every hour<br>**2** – Check for signatures every 2 hours, etc.<br>**24** – Check for signatures every day<br>**Default value:** 8 – Check for signatures every 8 hours|
|**AllowCloudProtection**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/AllowCloudProtection<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – not allowed<br>**1** – allowed (default)|
|**SubmitSamplesConsent**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/SubmitSamplesConsent<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – Always prompt (default)<br>**1** – Send safe samples automatically<br>**2** – Never send<br>**3** – Send all samples automatically|
|**ExcludedExtensions**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedExtensions<br /><br />**Data type:** String<br /><br />**Allowed values:**<br>*&lt;list of extensions separated by semi-colon&gt;* E.g. **obj;lib**<br>**Default:** No extensions excluded|
|**ExcludedPaths**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedPaths<br /><br />**Data type:** String<br /><br />**Allowed values:**<br /><br />*&lt;list of paths separated by semi-colon&gt;*<br /><br />Example: **c:\test;c:\test1.exe**<br /><br />**Default value:** No paths are excluded|
|**ExcludedProcesses**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedProcesses<br /><br />**Data type:** String<br /><br />**Allowed values:**<br>*&lt;list of paths separated by semi-colon&gt;*<br>Example: **c:\test.exe;c:\test1.exe**<br>**Default value:** No processes are excluded|

## - Edge browser

|Policy name|Details|
|---------------|------------|-----------|
|**Allow Browser**<br>(mobile only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Browser/AllowBrowser<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0**: browsing turned off<br>**1**: browsing turned on (default)|
|**AllowSearchSuggestionsinAddressBar**<br>(desktop and mobile)|**URI full path:** ./Vendor/MSFT/Policy/Config/Browser/AllowSearchSuggestionsinAddressBar<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0**: Don't show search suggestions<br>**1**: Show search suggestions (default)|
|**SendIntranetTraffictoInternetExplorer**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Browser/SendIntranetTraffictoInternetExplorer<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0**: Disabled (open intranet sites in Edge browser - default))<br>**1** - Enabled (open intranet sites in Internet Explorer).|
|**Allow Do Not Track**<br>(desktop and mobile)|**URI full path:** ./Vendor/MSFT/Policy/Config/Browser/AllowDoNotTrack<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – Disabled (DNT not sent - default)<br>**1** – Enabled (send DNT)|
|**Configure SmartScreen**<br>(desktop and mobile)|**URI full path:** ./Vendor/MSFT/Policy/Config/Browser/AllowSmartScreen<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – Do not allow<br>**1** – Allow (default)|
|**Allow Pop-ups**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Browser/AllowPopups<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – Block pop-ups (default)<br>**1** – Allow pop-ups|
|**Allow Cookies**<br>(desktop and mobile)|**URI full path:** ./Vendor/MSFT/Policy/Config/Browser/AllowCookies<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – Don’t Block. Allow cookies from all web sites (default)<br>**1** – Block only third party cookies<br>**2** – Block all cookies|
|**Allow Save Password**<br>(desktop and mobile)|**URI full path:** ./Vendor/MSFT/Policy/Config/Browser/AllowPasswordManager<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – Password manager is disabled; <br>**1** – Password manager is enabled (default)|
|**Allow Autofill**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Browser/AllowAutofill<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br>**0** – Disabled (default)<br>**1** – Enabled|
|**Configure Enterprise Site List**<br>(desktop only)|**URI full path:** ./Vendor/MSFT/Policy/Config/Browser/EnterpriseModeSiteList<br /><br />**Data type:** String<br /><br />**Allowed values:<br>0** – Not configured<br>**1** – Use IE’s enterprise mode site list if configured (default)<br>**2** – Specify location of the  enterprise site list|

### See also
[Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)

