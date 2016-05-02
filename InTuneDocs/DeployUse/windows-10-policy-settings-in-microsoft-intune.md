---
# required metadata

title: Windows 10 policy settings in Microsoft Intune | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Windows 10 policy settings in Microsoft Intune

Use the policy settings listed in this topic to help you configure settings for enrolled Windows 10 desktop, and Windows 10 Mobile devices.

## General configuration policy settings

Use the Microsoft **general configuration policy** for Windows 10 to configure general settings for enrolled Windows 10 desktop, and Windows 10 Mobile devices:


### Password

|Setting name|Details|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Require a password to unlock devices**|Require a password on supported devices.|Yes|Yes|
|**Required password type**|Specifies the type of password that will be required, such as numeric only, or alphanumeric|Yes|Yes|
|**Required password type** - **Minimum number of character sets**|There are four character sets, lowercase letters, uppercase letters, numbers, and symbols. This setting specifies how many different character sets must be included in the password.|Yes|Yes|
|**Minimum password length**|Specifies the minimum number of characters the device password must contain.|No|Yes|
|**Number of repeated sign-in failures to allow before the device is wiped**|Wipes the device if this number of login attempts fail.|Yes|Yes|
|**Minutes of inactivity before screen turns off**|Specifies the length of time a device must be idle before the screen is locked.|Yes|Yes|
|**Password expiration (days)**|Specifies the length of time after which the device password must be changed.|Yes|Yes|
|**Remember password history**|Specifies whether you want to restrict the end user from creating previously used passwords.|Yes|Yes|
|**Remember password history** - **Prevent reuse of previous passwords**|Specifies the number off previously used passwords remembered by the device.|Yes|Yes|
|**Allow picture password and PIN**|Lets you use simple gestures on a picture, or a simple PIN to login.|Yes|No|
|**Require a password when the device returns from an idle state**|If enabled, the user must enter a password to unlock the device from an idle state.|No|Yes|

### Encryption

|Setting name|Details|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Require encryption on mobile device**|Enables encryption on targeted devices.|No|Yes|

### System

|Setting name|Details|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Allow screen capture**|Let's the user capture the device screen as an image.|No|Yes|
|**Allow manual unenrollment**|Lets the user manually delete the workplace account from the device.|Yes|Yes|
|**Allow manual root certificate installation**|Specifies whether the user can manually install root certificates|No|Yes|
|**Allow diagnostic and usage data to be sent to Microsoft**|Determines the amount of diagnostic and usage data that is sent to Microsoft from devices.<br>**No** - No data is sent to Microsoft<br>**Basic** - The device sends only limited information to Microsoft<br>**Enhanced** - Sends enhanced diagnostic data to Microsoft<br>**Full (recommended)** - Sends the same data as **Enhanced**, plus additional data about the device state|Yes|Yes|


### Account and synchronization

|Setting name|Details|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Allow Microsoft account**|Lets the user associate a Microsoft account with the device.|Yes|Yes|
|**Allow adding non-Microsoft accounts manually**|Lets the user add email accounts to the device that are not associated with a Microsoft account.|Yes|Yes|
|**Allow settings synchronization for Microsoft accounts**|Allow device and app settings associated with a Microsoft account to synchronize between devices.|Yes|Yes|

### Email settings

|Setting name|Details|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Make Microsoft account optional in Windows Mail application**|Configure this to remove the requirement for a Microsoft account in Windows Mail.|Yes|No|



### Microsoft Edge

|Setting name|Details|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Allow web browser**|Allow the use of the Edge web browser on the device.|No|Yes|
|**Allow search suggestions in address bar**|Lets your search engine suggest sites as you type search phrases.|Yes|Yes|
|**Allow sending intranet traffic to Internet Explorer**|Lets users open intranet websites in Internet Explorer.|Yes|No|
|**Allow do not track**|Configures the Edge browser to send do not track headers to websites that users visit.|Yes|Yes|
|**Enable SmartScreen**|Enables the SmartScreen browser setting on devices.|Yes|Yes|
|**Allow active scripting**|Allows scripts, like Javascript to be run in the Edge browser.|Yes|Yes|
|**Allow pop-ups**|Enables or disables the browser pop-up blocker.|Yes|No|
|**Allow cookies**|Allow or disable cookies.|Yes|Yes|
|**Allow Autofill**|Allow users to change autocomplete settings in the browser.|Yes|No|
|**Allow Password Manager**|Enable or disable the Edge Password Manager feature.|Yes|Yes|
|**Enterprise Mode site list location**|Specifies where to find the list of web sites that will open in Enterprise mode. Users cannot edit this list.|Yes|No|

### Apps

|Setting name|Details|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Allow application store**|Allow the user to access the app store on the device.|No|Yes|



### Cellular

|Setting name|Details|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Allow data roaming**|Allow roaming between networks when accessing data.|Yes|Yes|
|**Allow VPN over cellular**|Controls whether the device can access VPN connections when connected to a cellular network.|Yes|Yes|
|**Allow VPN roaming over cellular**|Controls whether the device can access VPN connections when roaming on a cellular network.|Yes|Yes|

### Hardware

|Setting name|Details|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Allow camera**|Specifies whether the device camera can be used.|Yes|Yes|
|**Allow removable storage**|Specifies whether external storage devices such as an SD card can be used with the device.|Yes|Yes|
|**Allow Wi-Fi**|Allows the use of the devices Wi-Fi capability.|No|Yes|
|**Allow internet sharing**|Allow the use of Internet connection sharing on the device.|Yes|Yes|
|**Allow manual Wi-Fi configuration**|Controls whether the user can configure their own Wi-Fi connections, or whether they can only use connections configured by a Wi-Fi profile.|No|Yes|
|**Allow automatic connection to free Wi-Fi hotspots**|Lets the device automatically connect to free Wi-Fi hotspots and automatically accept any terms and conditions for the connection.|Yes|Yes|
|**Allow geolocation**|Specifies whether the device can use location services information.|Yes|Yes|
|**Allow NFC**|Allows the device to use it's Near Field Communications capabilities.|Yes|Yes|
|**Allow Bluetooth**|Enables the use of Bluetooth capabilities on the device.|Yes|Yes|
|**Allow Bluetooth discoverable mode**|Let's this device be discovered by other Bluetooth-enabled devices.|Yes|Yes|
|**Allow Bluetooth advertising**|Allows devices to receive advertisements over Bluetooth.|Yes|Yes|
|**Allow Bluetooth connectable mode** **Important:** |This setting is no longer supported by Windows 10 and will be removed in the future.|Yes|Yes|
|**Allow phone reset**|Controls whether the user can factory reset their device.|Yes|Yes|
|**Allow USB connection**|Controls whether devices can access external storage devices through a USB connection.|Yes|Yes|
|**Allow AntiTheft mode**|Configure whether Windows Antitheft mode is enabled.|Yes|Yes|

### Features

|Setting name|Details|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Allow copy and paste**|Enable or disable the use of copy and paste on the device.|No|Yes|
|**Allow voice recording**|Enable or disable the voice recording features on the device.|No|Yes|
|**Allow Cortana**|Enable or disable the Cortana voice assistant.|Yes|Yes|
|**Allow action center notifications**|Enable or disable action center notifications on the device lock screen.|No|Yes|

### Defender

|Setting name|Details|Windows 10 Desktop|Windows 10 Mobile|
|-|-|
|**Allow real-time monitoring**|Enables real-time scanning for malware, spyware, and other unwanted software.|Yes|No|
|**Allow behavior monitoring**|Lets Defender check for certain known patterns of suspicious activity on devices.|Yes|No
|**Enable Network Inspection System**|The Network Inspection System (NIS) helps to protect devices against network-based exploits by using the signatures of known vulnerabilities from the Microsoft Endpoint Protection Center to help detect and block malicious traffic.|Yes|No
|**Scan all downloads**|Controls whether Defender scans all files downloaded from the Internet.|Yes|No
|**Allow script scanning**|Lets Defender scan scripts that are used in Internet Explorer.|Yes|No
|**Monitor file and program activity**|Enable this setting to allow Defender to monitor file and program activity on devices.|Yes|No
|**Days to track resolved malware**|Lets Defender continue to track resolved malware for the number of days you specify so that you can manually check previously affected devices. If you set the number of days to **0**, malware remains in the Quarantine folder and is not automatically removed. |Yes|No
|**Allow client UI access**|Controls whether the Windows Defender user interface is hidden from end users.<br>When this setting is changed, it will take effect the next time the end user's PC is restarted.|Yes|No
|**Schedule a daily quick scan**|Lets you schedule a quick scan that occurs daily at the time you select.|Yes|No
|**Schedule a system scan**|Lets you schedule a full or quick system scan that occurs regularly on the day and time you select.|Yes|No
|**Limit CPU usage during a scan**|Lets you limit the amount of CPU that scans are allowed to use (from **1** to **100**)|Yes|No
|**Scan archive files**|Allows Defender to scan archived files such as Zip or Cab files.|Yes|No
|**Scan email messages**|Allows Defender to scan email messages as they arrive on the device.|Yes|No
|**Scan removable drives**|Lets Defender scan removable drives like USB sticks.|Yes|No
|**Scan mapped network drives**|Lets Defender scan files on mapped network drive.<br>If the files on the drive are read-only, Defender will be unable to remove any malware found in them.|Yes|No
|**Scan files opened from network shared folders**|Lets Defender scan files on shared network drives (for instance, those accessed from a UNC path.<br>If the files on the drive are read-only, Defender will be unable to remove any malware found in them.|Yes|No
|**Signature update interval**|Specify the interval at which Defender will check for new signature files.|Yes|No
|**Allow cloud protection**|Allow or block the Microsoft Active Protection Service from receiving information about malware activity from devices you manage. This information is used to improve the service in the future.|Yes|No
|**Prompt users for samples submission**|Controls whether files that might require further analysis by Microsoft to determine if they are malicious are automatically sent to Microsoft.|Yes|No
|**Files and folders to exclude when running a scan or using real-time protection**|Add one or more files and folders like **C:\Path** or **%ProgramFiles%\Path\filename.exe** to the exclusions list. These files and folders will not be included in any real-time, or scheduled scans.|Yes|No
|**File extensions to exclude when running a scan or using real-time protection**|Add one or more file extensions like **jpg** or **txt** to the exclusions list. Any files with these extensions will not be included in any real-time, or scheduled scans.|Yes|No
|**Processes to exclude when running a scan or using real-time protection**|Add one or more processes of the type **.exe**, **.com**, or **.scr** to the exclusions list. These processes will not be included in any real-time, or scheduled scans.|Yes|No| 


### Updates settings

|Setting name|Details|Windows 10 Desktop|Windows 10 Mobile|
|----------------|---------------|----------------------|---------------------|
|**Allow automatic updates**|Enable this setting to allow automatic updates. Then, configure one of the following settings to control update behavior:<br /><br />**Notify download**<br /><br />**Auto install at maintenance time**<br /><br />**Auto install and reboot at maintenance time**<br /><br />**Auto install and reboot at scheduled time** **Note:** When this option is selected, you can also configure the following settings:  **Suppress notification to end user** and **Define install day for scheduled updates**.|Yes|No|

## Custom policy settings
Use the Microsoft Intune **custom configuration policy** for Windows 10 and Windows 10 Mobile to deploy OMA-URI (Open Mobile Alliance Uniform Resource Identifier) settings that can be used to control features on Windows 10 and Windows 10 Mobile devices. These are standard settings that many mobile device manufacturers use to control device features.

This capability is intended to allow you to deploy Windows 10 settings that are not configurable with an Intune general configuration policy. For information about the settings you can configure with these policies, see [Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

For a list of OMA-URI settings that you can configure on enrolled Windows 10 devices, see Custom URI settings for Windows 10 devices later in this topic.

### General settings

|Setting name|Details|
    |----------------|--------------------|
    |**Name**|Enter a unique name for the policy to help you identify it in the Intune console.|
    |**Description**|Provide a description that gives an overview of the policy and other relevant information that helps you to locate it.|

### OMA-URI settings

|Setting name|Details|
    |--------|--------------------|
    |**Setting name**|Enter a unique name for the OMA-URI setting to help you identify it in the list of settings.|
    |**Setting description**|Provide a description that gives an overview of the setting and other relevant information to help you locate it.|
    |**Data type**|Select the date type in which you will specify this OMA-URI setting. Choose from:<br /><br />-   **String**<br />-   **String (XML)**<br />-   **Date and time**<br />-   **Integer**<br />-   **Floating point**<br />-   **Boolean**|
    |**OMA-URI (case sensitive)**|Specify the OMA-URI you want to supply a setting for.|
    |**Value**|Specify the value to associate with the OMA-URI you specified previously.|


## Custom URI settings for Windows 10 devices
This topic lists the settings that you can configure for Windows 10 and Windows 10 Mobile devices in a Microsoft Intune **Windows 10 Custom Policy**.


> [!NOTE]
> In the **Supports** column of the following table, the following values are used:
> 
> -   **Desktop** – The setting supports Windows 10 Professional and Enterprise computers that are enrolled with Intune only.
> -   **Mobile** – The setting supports Windows 10 Mobile devices only.
> -   **Both** – The setting supports both desktop and mobile devices.
> 
> All devices must be enrolled with Intune if you want to use the Windows Custom URI Policy.

### Policy

|Policy name|Supports|Details|
|---------------|------------|-----------|
|**​Allow Auto Update**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/Update/AllowAutoUpdate<br /><br />**Data type:** Integer<br /><br />**Allowed values:0** - **5**<br /><br />**Default value:** 1|
|**Schedule Install Day**|Both|**URI full path:** ./Vendor/MSFT/Policy/Config/Update/ScheduledInstallDay<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** - Every day.<br /><br />**1** - Sunday<br /><br />**2** - Monday<br /><br />**3** - Tuesday<br /><br />**4** - Wednesday<br /><br />**5** - Thursday<br /><br />**6** - Friday<br /><br />**7** - Saturday.<br /><br />**Default value:** 0|
|**Schedule Install Time**|Both|**URI full path:** ./Vendor/MSFT/Policy/Config/Update/ScheduledInstallTime<br /><br />**Data type:** Integer<br /><br />**Allowed values:0** – **23** hours (0 is midnight)<br /><br />**Default value:** 3|
|**DeviceLock/AllowIdleReturnWithoutPassword**|Mobile|**URI full path:** ./Vendor/MSFT/Policy/Config/DeviceLock/AllowIdleReturnWithoutPassword<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** - user is not able to set the password grace period timer, and the value is set as “each time”<br /><br />**1** - user is able to set the password grace period timer<br /><br />**Default value:** 1|
|**WiFi/AllowWiFi**|Mobile|**URI full path:** ./Vendor/MSFT/Policy/Config/WiFi/AllowWiFi<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – Do not allow **use Wi-Fi connection**.<br /><br />**1** –**Allow use Wi-Fi connection**.<br /><br />**Default value:** 1|
|**WiFi/AllowInternetSharing**|Both|**URI full path:** ./Vendor/MSFT/Policy/Config/WiFi/AllowInternetSharing<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – Do not allow Internet Sharing.<br /><br />**1** – Allow Internet Sharing<br /><br />**Default value:** 1|
|**WiFi/AllowAutoConnectToWiFiSenseHotspots**|Both|**URI full path:** ./Vendor/MSFT/Policy/Config/WiFi/AllowAutoConnectToWiFiSenseHotspots<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**WiFi/AllowManualWiFiConfiguration**|Mobile|**URI full path:** ./Vendor/MSFT/Policy/Config/WiFi/AllowManualWiFiConfiguration<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – No Wi-Fi connection outside of MDM provisioned is allowed.<br /><br />**1** – Adding new network SSIDs beyond the already MDM provisioned ones is allowed.<br /><br />**Default value:** 1|
|**System/AllowLocation**|Both|**URI full path:** ./Vendor/MSFT/Policy/Config/System/AllowLocation<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**System/AllowTelemetry**|Both|**URI full path:** ./Vendor/MSFT/Policy/Config/System/AllowTelemetry<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – Not allowed (Enterprise only setting)<br /><br />**1** – Limited<br /><br />**2** – Full<br /><br />**3** -  Full and  diagnostics information<br /><br />**Default value:** 2|
|**System/AllowExperimentation**|Both|**URI full path:** ./Vendor/MSFT/Policy/Config/System/AllowExperimentation<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – Not allowed<br /><br />**1**- Settings only<br /><br />**2**- Settings and experimentation<br /><br />**Default value:** 1|
|**Security/AntiTheftMode**|Mobile|**URI full path:** ./Vendor/MSFT/Policy/Config/Security/AntiTheftMode<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** - don't allow Anti Theft mode<br /><br />**1** User preference<br /><br />**Default value:** 1|
|**Connectivity/AllowUSBConnection**|Mobile|**URI full path:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowUSBConnection<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**System/AllowUserToResetPhone**|Mobile|**URI full path:** ./Vendor/MSFT/Policy/Config/System/AllowUserToResetPhone<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**Connectivity/AllowCellularDataRoaming**|Both|**URI full path:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowCellularDataRoaming<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**Connectivity/AllowVPNOverCellular**|Both|**URI full path:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNOverCellular<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** - VPN is not allowed over cellular<br /><br />**1** – VPN could use any connection including cellular.<br /><br />**Default value:** 1|
|**Connectivity/AllowVPNRoamingOverCellular**|Mobile|**URI full path:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**Connectivity/AllowVPNRoamingOverCellular**|Mobile|**URI full path:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**Connectivity/AllowBluetooth**|Both|**URI full path:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowBluetooth<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – Don’t allow the user to turn Bluetooth on.<br /><br />**1** – Reserved. The user can turn on and configure Bluetooth (not supported in Windows Phone 8.1 for MDM, EAS, Windows 10 desktop or Windows 10 Mobile)<br /><br />**2** - Allowed. The user can turn on and configure Bluetooth.<br /><br />**Default value:** 2|
|**Experience/AllowScreenCapture**|Mobile|**URI full path:** ./Vendor/MSFT/Policy/Config/Experience/AllowScreenCapture<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**Experience/AllowTaskSwitcher**|Mobile|**URI full path:** ./Vendor/MSFT/Policy/Config/Experience/AllowTaskSwitcher<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**Experience/AllowVoiceRecording**|Mobile|**URI full path:** ./Vendor/MSFT/Policy/Config/Experience/AllowVoiceRecording<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**Experience/AllowSyncMySettings**|Mobile|**URI full path:** ./Vendor/MSFT/Policy/Config/Experience/AllowSyncMySettings<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – Don’t allow roaming<br /><br />**1** – Allow roaming<br /><br />**Default value:** 1|
|**Experience/AllowManualMDMUnenrollment**|Both|**URI full path:** ./Vendor/MSFT/Policy/Config/Experience/AllowManualMDMUnenrollment<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**Accounts/AllowMicrosoftAccountConnection**|Both|**URI full path:** ./Vendor/MSFT/Policy/Config/Accounts/AllowMicrosoftAccountConnection<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**Accounts/AllowAddingNonMicrosoftAccountsManually**|Both|**URI full path:** ./Vendor/MSFT/Policy/Config/Accounts/AllowAddingNonMicrosoftAccountsManually<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**Security/AllowManualRootCertificateInstallation**|Mobile|**URI full path:** ./Vendor/MSFT/Policy/Config/Security/AllowManualRootCertificateInstallation<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**Security/AllowAddProvisioningPackages**|Both|**URI full path:** ./Vendor/MSFT/Policy/Config/Security/AllowAddProvisioningPackages<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**Search/DisableBackoff**|Both|**URI full path:** ./Vendor/MSFT/Policy/Config/Search/DisableBackoff<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0**<br /><br />**1**<br /><br />**Default value:** 0|
|**Search/PreventRemoteQueries**|Both|**URI full path:** ./Vendor/MSFT/Policy/Config/Search/PreventRemoteQueries<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0**<br /><br />**1**<br /><br />**Default value:** 1|
|**Search/AllowUsingDiacritics**|Both|**URI full path:** ./Vendor/MSFT/Policy/Config/Search/AllowUsingDiacritics<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0**<br /><br />**1**<br /><br />**Default value:** 0|
|**Search/AlwaysUseAutoLangDetection**|Both|**URI full path:** ./Vendor/MSFT/Policy/Config/Search/AlwaysUseAutoLangDetection<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0**<br /><br />**1**<br /><br />**Default value:** 0|
|**Search/DisableRemovableDriveIndexing**|Both|**URI full path:** ./Vendor/MSFT/Policy/Config/Search/DisableRemovableDriveIndexing<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0**<br /><br />**1**<br /><br />**Default value:** 0|
|**Search/PreventIndexingLowDiskSpaceMB**|Both|**URI full path:** ./Vendor/MSFT/Policy/Config/Search/PreventIndexingLowDiskSpaceMB<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0**<br /><br />**1**<br /><br />**Default value:** 1|
|**Search/AllowIndexingEncryptedStoresOrItems**|Both|**URI full path:** ./Vendor/MSFT/Policy/Config/Search/AllowIndexingEncryptedStoresOrItems<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0**<br /><br />**1**<br /><br />**Default value:** 0|
|**Security/AllowRemoveProvisioningPackage**|Both|**URI full path:** ./Vendor/MSFT/Policy/Config/Security/AllowRemoveProvisioningPackage<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**Security/RequireProvisioningPackageSignature**|Both|**URI full path:** ./Vendor/MSFT/Policy/Config/Security/RequireProvisioningPackageSignature<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0**<br /><br />**1**<br /><br />**Default value:** 0|
|**AboveLock/AllowActionCenterNotifications**|Both|**URI full path:** ./Vendor/MSFT/Policy/Config/AboveLock/AllowActionCenterNotifications<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**TextInput/AllowIMENetworkAccess**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/TextInput/AllowIMENetworkAccess<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – Don’t allow<br /><br />Open Extended Dictionary is turned off.<br /><br />A user cannot:<br /><br />Add a new Open Extended Dictionary<br /><br />Add a new search integration configuration file<br /><br />Use the cloud candidate feature<br /><br />Send user registered word<br /><br />Additionally:<br /><br />An Open Extended Dictionary that was added before enabling this policy setting is not used for conversion.<br /><br />A search integration configuration file that was installed before enabling this policy setting is not used.<br /><br />**1** - Allow<br /><br />Open Extended Dictionary can be added and used by default. Also, the search integration function can be used by default.<br /><br />A user can:<br /><br />Use the cloud candidate feature<br /><br />Send user registered word<br /><br />**Default value:**|
|**TextInput/AllowKoreanExtendedHanja**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/TextInput/AllowKoreanExtendedHanja<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**TextInput/AllowIMELogging**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/TextInput/AllowIMELogging<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** - Misconversion logging is turned off. Auto-tuned data and input history data is not saved to a file.<br /><br />**1** - Misconversion logging is turned on. Auto-tuned data and input history data is saved to a file.<br /><br />**Default value:** 1|
|**TextInput/AllowJapaneseNonPublishingStandardGlyph**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseNonPublishingStandardGlyph<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**TextInput/AllowJapaneseIVSCharacters**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIVSCharacters<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**TextInput/AllowJapaneseUserDictionary**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseUserDictionary<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**TextInput/AllowJapaneseIMESurrogatePairCharacters**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIMESurrogatePairCharacters<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**TextInput/ExcludeJapaneseIMEExceptShiftJIS**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptShiftJIS<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** - All Except JIS characters are filtered<br /><br />**1** - Any characters are not filtered<br /><br />**Default value:** 1|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** - All except JIS0208 characters are filtered<br /><br />**1** - No characters are filtered<br /><br />**Default value:** 1|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** - All except JIS0208 characters or EUDC characters are filtered<br /><br />**1** - No characters are filtered.<br /><br />**Default value:** 1|
|**TextInput/AllowInputPanel**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/TextInput/AllowInputPanel<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**Bluetooth/AllowDiscoverableMode**|Both|**URI full path:** ./Vendor/MSFT/Policy/Config/Bluetooth/AllowDiscoverableMode<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**Bluetooth/AllowAdvertising**|Both|**URI full path:** ./Vendor/MSFT/Policy/Config/Bluetooth/AllowAdvertising<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**Settings/AllowDataSense**|Both|**URI full path:** ./Vendor/MSFT/Policy/Config/Settings/AllowDataSense<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**Settings/AllowVPN**|Both|**URI full path:** ./Vendor/MSFT/Policy/Config/Settings/AllowVPN<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**Settings/AllowWorkplace**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/Settings/AllowWorkplace<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**Settings/AllowDateTime**|Both|**URI full path:** ./Vendor/MSFT/Policy/Config/Settings/AllowDateTime<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**Settings/AllowLanguage**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/Settings/AllowLanguage<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**Settings/AllowRegion**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/Settings/AllowRegion<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**Settings/AllowSignInOptions**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/Settings/AllowSignInOptions<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**Settings/AllowYourAccount**|Both|**URI full path:** ./Vendor/MSFT/Policy/Config/Settings/AllowYourAccount<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**Settings/AllowPowerSleep**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/Settings/AllowPowerSleep<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**Settings/AllowAutoPlay**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/Settings/AllowAutoPlay<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**Experience/AllowCortana**|Both|**URI full path:** ./Vendor/MSFT/Policy/Config/Experience/AllowCortana<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**Search/SafeSearchPermissions**|Mobile|**URI full path:** ./Vendor/MSFT/Policy/Config/Search/SafeSearchPermissions<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – Strict, highest filtering against adult content<br /><br />**1** – Moderate, moderate filtering against adult content (valid search results will not be filtered)<br /><br />**Default value:** 1|
|**Experience/AllowCopyPaste**|Mobile|**URI full path:** ./Vendor/MSFT/Policy/Config/Experience/AllowCopyPaste<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**Force Start Size**|Mobile|**URI full path:** ./Vendor/MSFT/Policy/Config/Start/ForceStartSize<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** - allow user change size<br /><br />**1** - force non-full screen<br /><br />**2** - force full screen<br /><br />**Default value:** 0|
|**Update/RequireDeferUpgrade**|Both|**URI full path:** ./Vendor/MSFT/Policy/Config/Update/RequireDeferUpgrade<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0**: do not defer upgrade (stay in current branch, CB)<br /><br />**1**: Enable updates and upgrades to be deferred (Device follows current branch for business, CBB, rules)<br /><br />**Default value:0**<br /><br />For more information, see:<br /><br />[Introduction to Windows 10 servicing](https://technet.microsoft.com/library/mt598226(v=vs.85).aspx)<br /><br />[Plan for Windows 10 deployment](https://technet.microsoft.com/library/mt574241(v=vs.85).aspx)|
|**Update/DeferUpdatePeriod**|Both|**Description:** Policy to defer software updates for up to 4 weeks<br /><br />**URI full path:** ./Vendor/MSFT/Policy/Config/Update/DeferUpdatePeriod<br /><br />**Data type:** Integer<br /><br />**Allowed values:** 0: Apply updates immediately; 1-4: number of weeks to defer software updates.<br /><br />**Default value:0**<br /><br /><br />For more information, see:<br /><br />[Introduction to Windows 10 servicing](https://technet.microsoft.com/library/mt598226(v=vs.85).aspx)<br /><br />[Plan for Windows 10 deployment](https://technet.microsoft.com/library/mt574241(v=vs.85).aspx)|
|**Update/DeferUpgradePeriod**|Both|**Description:** Policy to defer feature upgrades for up to 8 months<br /><br />**URI full path:** ./Vendor/MSFT/Policy/Config/Update/DeferUpgradePeriod<br /><br />**Data type:** Integer<br /><br />**Allowed values:** 0: Apply updates immediately; 1-8: number of months to defer feature upgrades.<br /><br />**Default value:0**<br /><br />For more information, see:<br /><br />[Introduction to Windows 10 servicing](https://technet.microsoft.com/library/mt598226(v=vs.85).aspx)<br /><br />[Plan for Windows 10 deployment](https://technet.microsoft.com/library/mt574241(v=vs.85).aspx)|
|**Update/PauseDeferrals**|Both|**Description:** Allows a CBB machine to stop receiving updates and upgrades for 5 weeks. This should be used in case there is an issue with an update.<br /><br />**URI full path:** ./Vendor/MSFT/Policy/Config/Update/PauseDeferrals<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0**: Apply updates immediately (default)<br /><br />**1**: Pause updates and upgrades (expires after 5 weeks)<br /><br />**Default value:0**|

### Windows Defender

|Policy name|Supports|Details|
|---------------|------------|-----------|
|**AllowRealtimeMonitoring**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/AllowRealtimeMonitoring<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**AllowBehaviorMonitoring**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/AllowBehaviorMonitoring<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**AllowIntrusionPreventionSystem**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/AllowIntrusionPreventionSystem<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**AllowIOAVProtection**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/AllowIOAVProtection<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**AllowScriptScanning**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/AllowScriptScanning<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**AllowOnAccessProtection**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/AllowOnAccessProtection<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**RealTimeScanDirection**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/RealTimeScanDirection<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – Monitor all files (bi-directional)<br /><br />**1** – Monitor incoming files<br /><br />**2** – Monitor outgoing files<br /><br />**Default value:** 0|
|**DaysToRetainCleanedMalware**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/DaysToRetainCleanedMalware<br /><br />**Data type:** Integer<br /><br />**Allowed values:0** - **90** – Represents what how long malware will be retained<br /><br />**Default value:** 0 – keeps in the quarantine folder forever, and doesn’t automatically remove|
|**AllowUserUIAccess**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/AllowUserUIAccess<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**ScanParameter**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/ScanParameter<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**1** – Quick scan<br /><br />**2** - Full scan<br /><br />**Default value:** 1|
|**ScheduleScanDay**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleScanDay<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** - Everyday<br /><br />**1** - Monday<br /><br />**2** - Tuesday<br /><br />**3** - Wednesday<br /><br />**4** - Thursday<br /><br />**5** - Friday<br /><br />**6** - Saturday<br /><br />**7** - Sunday<br /><br />**8** – No scheduled scan<br /><br />**Default value:** 0|
|**ScheduleScanTime**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleScanTime<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** - 12:00 am<br /><br />**60** – 1:00 am<br /><br />**120** – 2:00 am<br /><br />**180** – 3:00 am<br /><br />**240** – 4:00 am<br /><br />**300** – 5:00 am<br /><br />**360** – 6:00 am<br /><br />**420** – 7:00 am<br /><br />**480** – 8:00 am<br /><br />**540** – 9:00 am<br /><br />**600** – 10:00 am<br /><br />**660** – 11:00 am<br /><br />**720** – 12:00 pm<br /><br />**780** – 1:00 pm<br /><br />**840** – 2:00 pm<br /><br />**900** – 3:00 pm<br /><br />**960** – 4:00 pm<br /><br />**1020** – 5:00 pm<br /><br />**1080** – 6:00 pm<br /><br />**1140** – 7:00 pm<br /><br />**1200** – 8:00 pm<br /><br />**1260** – 9:00 pm<br /><br />**1320** – 10:00 pm<br /><br />**1381** – Maintenance window<br /><br />**Default value:** 120|
|**ScheduleQuickScanTime**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleQuickScanTime<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** - 12:00 am<br /><br />**60** – 1:00 am<br /><br />**120** – 2:00 am<br /><br />**180** – 3:00 am<br /><br />**240** – 4:00 am<br /><br />**300** – 5:00 am<br /><br />**360** – 6:00 am<br /><br />**420** – 7:00 am<br /><br />**480** – 8:00 am<br /><br />**540** – 9:00 am<br /><br />**600** – 10:00 am<br /><br />**660** – 11:00 am<br /><br />**720** – 12:00 pm<br /><br />**780** – 1:00 pm<br /><br />**840** – 2:00 pm<br /><br />**900** – 3:00 pm<br /><br />**960** – 4:00 pm<br /><br />**1020** – 5:00 pm<br /><br />**1080** – 6:00 pm<br /><br />**1140** – 7:00 pm<br /><br />**1200** – 8:00 pm<br /><br />**1260** – 9:00 pm<br /><br />**1320** – 10:00 pm<br /><br />**1380** – 11:00 pm<br /><br />**Default value:** 120|
|**AVGCPULoadFactor**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/AVGCPULoadFactor<br /><br />**Data type:** Integer<br /><br />**Allowed values:0** - **100**<br /><br />**Default value:** 50|
|**AllowArchiveScanning**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/AllowArchiveScanning<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**AllowEmailScanning**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/AllowEmailScanning<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 0|
|**AllowFullScanRemovableDriveScanning**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/AllowFullScanRemovableDriveScanning<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 0|
|**AllowFullScanOnMappedNetworkDrives**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/AllowFullScanOnMappedNetworkDrives<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**AllowScanningNetworkFiles**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/AllowScanningNetworkFiles<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1 – Also runs when RTP is on when it is set to allowed|
|**SignatureUpdateInterval**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/SignatureUpdateInterval<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – Do not check for signatures on an interval<br /><br />**1** - Check for signatures every hour<br /><br />**2** – Check for signatures every 2 hours, etc.<br /><br />**24** – Check for signatures every day<br /><br />**Default value:** 8 – Check for signatures every 8 hours|
|**AllowCloudProtection**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/AllowCloudProtection<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – not allowed<br /><br />**1** – allowed<br /><br />**Default value:** 1|
|**SubmitSamplesConsent**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/SubmitSamplesConsent<br /><br />**Data type:** Integer<br /><br />**Allowed values:**<br /><br />**0** – Always prompt<br /><br />**1** – Send safe samples automatically<br /><br />**2** – Never send<br /><br />**3** – Send all samples automatically<br /><br />**Default value:** 0|
|**ExcludedExtensions**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedExtensions<br /><br />**Data type:** String<br /><br />**Allowed values:**<br /><br />*&lt;list of extensions separated by semi-colon&gt;* E.g. **obj;lib**<br /><br />**Default value:** No extensions excluded|
|**ExcludedPaths**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedPaths<br /><br />**Data type:** String<br /><br />**Allowed values:**<br /><br />*&lt;list of paths separated by semi-colon&gt;*<br /><br />Example: **c:\test;c:\test1.exe**<br /><br />**Default value:** No paths are excluded|
|**ExcludedProcesses**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedProcesses<br /><br />**Data type:** String<br /><br />**Allowed values:**<br /><br />*&lt;list of paths separated by semi-colon&gt;*<br /><br />Example: **c:\test.exe;c:\test1.exe**<br /><br />**Default value:** No processes are excluded|

### Edge browser

|Policy name|Supports|Details|
|---------------|------------|-----------|
|**Allow Browser**|Mobile|**URI full path:** ./Vendor/MSFT/Policy/Config/Browser/AllowBrowser<br /><br />**Data type:** Integer<br /><br />**Allowed values:0**: browsing turned off; **1**: browsing turned on.<br /><br />**Default value:** 1|
|**AllowSearchSuggestionsinAddressBar**|Both|**URI full path:** ./Vendor/MSFT/Policy/Config/Browser/AllowSearchSuggestionsinAddressBar<br /><br />**Data type:** Integer<br /><br />**Allowed values:0**: Don't show search suggestions; **1**: Show search suggestions.<br /><br />**Default value:** 1|
|**SendIntranetTraffictoInternetExplorer**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/Browser/SendIntranetTraffictoInternetExplorer<br /><br />**Data type:** Integer<br /><br />**Allowed values:0**: Disabled (open intranet sites in Edge browser); **1** - Enabled (open intranet sites in Internet Explorer).<br /><br />**Default value:** 0|
|**Allow Do Not Track**|Both|**URI full path:** ./Vendor/MSFT/Policy/Config/Browser/AllowDoNotTrack<br /><br />**Data type:** Integer<br /><br />**Allowed values:0** – Disabled (DNT not sent);  **1** – Enabled (send DNT)<br /><br />**Default value:** 0|
|**Configure SmartScreen**|Both|**URI full path:** ./Vendor/MSFT/Policy/Config/Browser/AllowSmartScreen<br /><br />**Data type:** Integer<br /><br />**Allowed values:0** – Do not allow;  **1** – Allow<br /><br />**Default value:** 1|
|**Allow Pop-ups**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/Browser/AllowPopups<br /><br />**Data type:** Integer<br /><br />**Allowed values:0** – Block pop-ups; **1** – Allow pop-ups<br /><br />**Default value:** 0|
|**Allow Cookies**|Both|**URI full path:** ./Vendor/MSFT/Policy/Config/Browser/AllowCookies<br /><br />**Data type:** Integer<br /><br />**Allowed values:0** – Don’t Block. Allow cookies from all web sites; **1** – Block only third party cookies; **2** – Block all cookies<br /><br />**Default value:** 0|
|**Allow Save Password**|Both|**URI full path:** ./Vendor/MSFT/Policy/Config/Browser/AllowPasswordManager<br /><br />**Data type:** Integer<br /><br />**Allowed values:0** – Password manager is disabled; <br />                        **1** – Password manager is enabled<br /><br />**Default value:** 1|
|**Allow Autofill**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/Browser/AllowAutofill<br /><br />**Data type:** Integer<br /><br />**Allowed values:0** – Disabled; **1** – Enabled<br /><br />**Default value:** 0|
|**Configure Enterprise Site List**|Desktop|**URI full path:** ./Vendor/MSFT/Policy/Config/Browser/EnterpriseModeSiteList<br /><br />**Data type:** String<br /><br />**Allowed values:0** – Not configured; **1** – Use IE’s enterprise mode site list if configured; **2** – Specify location to enterprise site list<br /><br />**Default value:** 1|

### See also
[Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)

