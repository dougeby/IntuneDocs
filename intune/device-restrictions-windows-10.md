---
# required metadata

title: Intune device restriction settings for Windows 10
titleSuffix: "Intune on Azure"
description: Learn the Intune settings you can use to control device settings and functionality on Windows 10 devices."
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/23/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 89f2d806-2e97-430c-a9a1-70688269627f

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Windows 10 and later device restriction settings in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## General
- 	**Screen capture (mobile only)** - Lets the user capture the device screen as an image.
- 	**Copy and paste (mobile only)** - Allow copy and paste actions between apps on the device.
- 	**Manual unenrollment** - Lets the user manually delete the workplace account from the device.
- 	**Manual root certificate installation (mobile only)** - Stops the user from manually installing root certificates, and intermediate CAP certificates.
- 	**Diagnostic data submission** - Possible values are:
	- 		**None** No data is sent to Microsoft
	- 		**Basic** Limited information is sent to Microsoft
	- 		**Enhanced** Enhanced diagnostic data is sent to Microsoft
	- 		**Full** Sends the same data as Enhanced, plus additional data about the device state
- 	**Camera** - Allow or block use of the camera on the device.
- 	**OneDrive file sync** - Blocks the device from synchronizing files to OneDrive.
- 	**Removable storage** - Specifies whether external storage devices, like SD cards can be used with the device.
- 	**Geolocation** - Specifies whether the device can use location services information.
- 	**Internet sharing** - Allow the use of Internet connection sharing on the device.
- 	**Phone reset** - Controls whether the user can do a factory reset on their device.
- 	**USB connection (mobile only)** - Controls whether devices can access external storage devices through a USB connection.
- 	**AntiTheft mode (mobile only)** - Configure whether Windows Antitheft mode is enabled.
- 	**Cortana** - Enable or disable the Cortana voice assistant.
- 	**Voice recording (mobile only)** - Allow or block use of the device voice recorder.
- 	**Device name modification** - Prevents the end user from changing the device name (Windows 10 Mobile only)
- 	**Add provisioning packages** - Blocks the run time configuration agent that installs provisioning packages.
- 	**Remove provisioning packages** - Blocks the run time configuration agent that removes provisioning packages.
- 	**Device discovery** - Block a device from being discovered by other devices.
- 	**Task Switcher (mobile only)** - Blocks the task switcher on the device.
- 	**SIM card error dialog (mobile only)** - Blocks an error message from displaying on the device if no SIM card is detected.


## Password
- 	**Password** - Require the end user to enter a password to access the device.
	- 	**Required password type** - Specifies whether the password must be numeric only, or alphanumeric.
	- 	**Minimum password length** - Applies to Windows 10 Mobile only.
	- 	**Number of sign-in failures before wiping device**	- For devices running Windows 10: If the device has BitLocker enabled, it's put into BitLocker recovery mode after sign-in fails the number of times that you specified. If the device is not BitLocker enabled, then this setting doesn't apply.
For devices running Windows 10 Mobile: After sign-in fails the number of times you specify, the device is wiped.
	- 	**Maximum minutes of inactivity until screen locks** - Specifies the length of time a device must be idle before the screen is locked.
	- 	**Password expiration (days)** - Specifies the length of time after which the device password must be changed.
	- 	**Prevent reuse of previous passwords** - Specifies the number of previously used passwords that are remembered by the device.
	- 	**Require password when device returns from idle state (Mobile only)** - Specifies that the user must enter a password to unlock the device (Windows 10 Mobile only).
	- 	**Simple passwords** – Lets you allow the use of simple passwords like 1111 and 1234. This setting also allows or blocks the use of Windows picture passwords.
- 	**Encryption** - Enable encryption on targeted devices (Windows 10 Mobile only).

## Personalization

- 	**Desktop background picture URL (Desktop only)** - Specify the URL to a picture in PNG, JPG, or JPEG format that you want to use as the Windows desktop wallpaper. Users will not be able to change this.

## Privacy

-	**Input personalization** – Don’t allow the use of cloud-based speech services for Cortana, dictation, or Windows Store apps. If you allow these services, Microsoft might collect voice data to improve the service.
-	**Automatic acceptance of the pairing and privacy user consent prompts** – Allow Windows to automatically accept pairing and privacy consent messages when running apps.


## Locked screen experience


- 	**Action center notifications (mobile only)** – Lets Action Center notifications appear on the device lock screen (Windows 10 Mobile only).
- 	**Locked screen picture URL (Desktop only)** - Specify the URL to a picture in PNG, JPG, or JPEG format that will be used as the Windows lock screen wallpaper. Users will not be able to change this.
-	**User configurable screen timeout (mobile only)** – Lets users configure the amount of time 
-	**Cortana on locked screen (desktop only)** – Don’t allow the user to interact with Cortana when the device is on the lock screen (Windows 10 desktop only).
-	**Toast notifications on locked screen** – Block alert messages from being displayed on the device lock screen.
-	**Screen timeout (mobile only)** - Specifies the time in seconds after the screen locks, when it will turn off.



## App Store

- 	**App store (mobile only)** - Enable or block use of the app store on Windows 10 Mobile devices.
- 	**Auto-update apps from store** - Allows apps installed from the Windows Store to be automatically updated.
- 	**Trusted app installation** - Allows apps signed with a trusted certificate to be sideloaded.
- 	**Developer unlock** - Allow Windows developer settings, such as allowing sideloaded apps to be modified by the end user.
- 	**Shared user app data** - Allows apps to share data between different users on the same device.
- 	**Use private store only** - Enable this to only allow end users to download apps from your private store.
- 	**Store originated app launch** - Used to disable all apps that were pre-installed on the device, or downloaded from the Windows Store.
- 	**Install app data on system volume** - Stops apps from storing data on the system volume of the device.
- 	**Install apps on system drive** - Stops apps from storing data on the system drive of the device.
- 	**Game DVR (desktop only)** - Configures whether recording and broadcasting of games is allowed.
- 	**Apps from the store only** - Configures whether users can install apps from places other than the app store.



## Edge Browser
- 	**Microsoft Edge browser (mobile only)** - Allow the use of the Edge web browser on the device.
- 	**Address bar dropdown (desktop only)** – Use this to stop Edge from displaying a list of suggestions in a drop-down list when you type. This helps to minimize network bandwidth use between Edge and Microsoft services.
-	**Sync favorites between Microsoft browsers (desktop only)** – Lets Windows synchronize favorites between Internet Explorer and Edge.
- 	**Send do-not-track headers** - Configures the Edge browser to send do not track headers to websites that users visit.
- 	**Cookies** - Lets the browser save internet cookies to the device.
- 	**JavaScript** - Allows scripts, such as Javascript, to run in the Edge browser.
- 	**Pop-ups** - Blocks pop-up windows in the browser (Applies to Windows 10 desktop only).
- 	**Search suggestions** - Lets your search engine suggest sites as you type search phrases.
- 	**Send intranet traffic to Internet Explorer** - Lets users open intranet websites in Internet Explorer (Windows 10 desktop only).
- 	**Autofill** - Allow users to change autocomplete settings in the browser (Windows 10 desktop only).
- 	**Password Manager** - Enable or disable the Edge Password Manager feature.
- 	**Enterprise mode site list location** - Specifies where to find the list of web sites that open in Enterprise mode. Users cannot edit this list.<br>(Windows 10 desktop only).
- 	**Developer tools** - Prevent the end user from opening the Edge developer tools.
- 	**Extensions** - Allow the end user to install Edge extensions on the device.
- 	**InPrivate browsing** - Prevent the end user from opening InPrivate browsing sessions.
-	**Show first run page** – Stops the introduction page from appearing the first time you run Edge.
	-	**First run URL** – Specifies the URL of a page that is displayed the first time a user runs Edge (Windows 10 Mobile only).
- 	**Homepages** - Add a list of sites that you want to use as home pages in the Edge browser (desktop only).
- 	**Changes to start page** – Lets users change the start pages displayed when Edge is opened. Use the Homepages setting to create the page, or list of pages that is opened when Edge starts.
- 	**Block access to about flags** - Prevent the end user from accessing the about:flags page in Edge that contains developer and experimental settings.
- 	**WebRtc localhost ip address** - Block the users localhost IP address from being displayed when making phone calls using the web RTC protocol.
- 	**Default search engine** - Specify the default search engine to be used. End users can change this value at any time.
- 	**Clear browsing data on exit** – Clears history, and browsing data when the user exits Edge.
-	**Live Tile data collection** – Stops Windows collecting information from the Live Tile when users pin a site to the start menu from Edge.

## Edge Browser SmartScreen

- 	**SmartScreen** - Enables or disables SmartScreen, which blocks fraudulent web sites.
- 	**Smart screen prompt override** - Allow the end user to bypass SmartScreen filter warnings about potentially malicious websites.
- 	**Smart screen prompt override for files** - Allow the end user to bypass SmartScreen filter warnings about downloading potentially malicious files.

## Search
- **Safe Search (mobile only)** - Control how Cortana filters adult content in search results. You can select **Strict**, **Moderate**, or allow the end user to choose their own settings.

## Cloud and Storage
- 	**Microsoft account** - Lets the user associate a Microsoft account with the device.
- 	**Non-Microsoft account** - Lets the user add email accounts to the device that are not associated with a Microsoft account.
- 	**Settings synchronization for Microsoft account** - Allow device and app settings that are associated with a Microsoft account to synchronize between devices.

## Cellular and Connectivity

-	**Cellular data channel** – Stop users from using data, like browsing the web, when they are connected to a cellular network. 
- 	**Data roaming** - Allow roaming between networks when accessing data.
- 	**VPN over the cellular network** - Controls whether the device can access VPN connections when connected to a cellular network.
- 	**VPN roaming over the cellular network** - Controls whether the device can access VPN connections when roaming on a cellular network.
- 	**Bluetooth** - Controls whether the user can enable and configure Bluetooth on the device.
- 	**Bluetooth discoverability** - Lets the device be discovered by other Bluetooth-enabled devices.
- 	**Bluetooth pre-pairing** – Lets you configure specific Bluetooth devices to automatically pair with a host device.
- 	**Bluetooth advertising** - Lets the device receive advertisements over Bluetooth.
- 	**Connected devices service** – Lets you choose whether to allow the connected devices service, which enables discovery and connection to other Bluetooth devices.
- 	**NFC**	- Lets the user enable and configure Near Field Communications capabilities on the device.
- 	**Wi-Fi** - Lets the user enable and configure Wi-Fi on the device (Windows 10 Mobile only).
- 	**Automatically connect to Wi-Fi hotspots** - Lets the device automatically connect to free Wi-Fi hotspots and automatically accept any terms and conditions for the connection.
- 	**Manual Wi-Fi configuration** - Controls whether the user can configure their own Wi-Fi connections, or whether they can only use connections configured by a Wi-Fi profile (Windows 10 Mobile only).
- 	**Wi-Fi scan interval** – Specify how often devices scan for Wi-Fi networks. Specify a value from 1 (most frequent) to 500 (least frequent).
-   **Bluetooth allowed services** – Specify as hex strings, a list of allowed Bluetooth services and profiles.


## Control Panel and Settings

- 	**Settings app** - Block access to the Windows settings app.
	- 	**System** - Blocks access to the system area of the settings app.
		- 	**Power and sleep settings modification (desktop only)** - Prevents the end user from changing power and sleep settings on the device.
	- 	**Devices** - Blocks access to the devices area of the settings app.
	- 	**Network ​Internet** - Blocks access to the network and internet area of the settings app.
	- 	**Personalization** - Blocks access to the personalization area of the settings app.
	- 	**Accounts** - Blocks access to the accounts area of the settings app.
	- 	**Time and Language** - Blocks access to the time and language area of the settings app.
		- 	**System Time modification** - Prevents the end user from changing the device date and time.
		- 	**Region settings modification (desktop only)** - Prevents the end user from changing the region settings on the device.
		- 	**Language settings modification (desktop only)** - Prevents the user from changing the language settings on the device.
	- 	**Gaming** - Blocks access to the Gaming app in Settings.
	- 	**Ease of Access** - Blocks access to the ease of access area of the settings app.
	- 	**Privacy** - Blocks access to the privacy area of the settings app.
	- 	**Update and Security** - Blocks access to the updates and security area of the settings app.

## Defender

- 	**Real-time monitoring** - Enables real-time scanning for malware, spyware, and other unwanted software.
- 	**Behavior monitoring**	- Lets Defender check for certain known patterns of suspicious activity on devices.
- 	**Network Inspection System (NIS)**	- NIS helps to protect devices against network-based exploits. It uses the signatures of known vulnerabilities from the Microsoft Endpoint Protection Center to help detect and block malicious traffic.
- 	**Scan all downloads** - Controls whether Defender scans all files downloaded from the Internet.
- 	**Scan scripts loaded in Microsoft web browsers** - Lets Defender scan scripts that are used in Internet Explorer.
- 	**End user access to Defender**	- Controls whether the Windows Defender user interface is hidden from end users.
When this setting is changed, it takes effect the next time the end user's PC is restarted.
- 	**Signature update interval (in hours)** - Specify the interval at which Defender checks for new signature files.
- 	**Monitor file and program activity** - Allows Defender to monitor file and program activity on devices.
- 	**Days before deleting quarantined malware** - Lets Defender continue to track resolved malware for the number of days you specify so that you can manually check previously affected devices. If you set the number of days to **0**, malware remains in the Quarantine folder and is not automatically removed.
- 	**CPU usage limit during a scan** - Lets you limit the amount of CPU that scans are allowed to use (from **1** to **100**).
- 	**Scan archive files** - Allows Defender to scan archived files such as Zip or Cab files.
- 	**Scan incoming mail messages**	- Allows Defender to scan email messages as they arrive on the device.
- 	**Scan removable drives during a full scan** - Lets Defender scan removable drives like USB sticks.
- 	**Scan mapped network drives during a full scan** - Lets Defender scan files on mapped network drives.<br>If the files on the drive are read-only, Defender cannot remove any malware found in them.
- 	**Scan files opened from network folders** - Lets Defender scan files on shared network drives (for example, files accessed from a UNC path).
If the files on the drive are read-only, Defender cannot remove any malware found in them.
- 	**Cloud protection** - Allows or blocks the Microsoft Active Protection Service from receiving information about malware activity from devices that you manage. This information is used to improve the service in the future.
- 	**Prompt users before sample submission** - Controls whether potentially malicious files that might require further analysis are automatically sent to Microsoft.
- 	**Time to perform a daily quick scan** - Lets you schedule a quick scan that occurs daily at the time you select.
- 	**Type of system scan to perform** - Lets you specify the level of scanning that is performed when you schedule a system scan.
- 	**Detect potentially unwanted applications**  – Choose the level of protection when Windows detects potentially unwanted applications from:
		- **Block**
		- **Audit**
	For more information about potentially unwanted apps, see [this topic](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus).
-	**Actions on detected malware threats** – Enable this option to specify the actions you want Defender to take for each threat level it detects (Low, Moderate, High, and Severe). The actions you can take are:
	-	**Clean**
	-	**Quarantine**
	-	**Remove**
	-	**Allow**
	-	**User defined**
	-	**Block**



## Defender Exclusions

- 	**Files and folders to exclude from scans and real-time protection** - Adds one or more files and folders like **C:\Path** or **%ProgramFiles%\Path\filename.exe** to the exclusions list. These files and folders aren't included in any real-time or scheduled scans.
- 	**File extensions to exclude from scans and real-time protection** - Add one or more file extensions like **jpg** or **txt** to the exclusions list. Any files with these extensions are not included in any real-time or scheduled scans.
- 	**Processes to exclude from scans and real-time protection** - Add one or more processes of the type **.exe**, **.com**, or **.scr** to the exclusions list. These processes are not included in any real-time, or scheduled scans.


## Network proxy

- 	**Automatically detect proxy settings** - When enabled, the device attempts to find the path to a PAC script.
- 	**Use proxy script** - Select this if you want to specify a path to a PAC script to configure the proxy server.
	- 	**Setup script address URL** - Enter the URL of a PAC script you want to use to configure the proxy server.
- 	**Use manual proxy server** - Select this if you want to manually provide proxy server information.
	- 	**Address** - Enter the name, or IP address of the proxy server.
	- 	**Port number** - Enter the port number of your proxy server.
	- 	**Proxy exceptions** - Enter any URLs that must not use the proxy server. Use a semicolon to separate each item.
	- 	**Bypass proxy server for local address** - If you don't want to use the proxy server for local addresses on your intranet, enable this option .


## Windows Spotlight


- **Windows Spotlight** – Use this setting to block all Windows Spotlight functionality on Windows 10 devices. If you block this setting, the following settings are not available.
	- **Windows Spotlight on lock screen** – Stop Windows Spotlight from displaying information on the device lock screen.
	- **Third-party suggestions in Windows Spotlight** – Stop Windows Spotlight from suggesting content that is not published by Microsoft.
	- **Consumer Features** - Lets you block consumer features like Start menu suggestions, and membership notifications.
	- **Windows Tips** - Lets you block pop-up tips from displaying in Windows.
	- **Windows Spotlight in action center** – Block Windows Spotlight suggestions like new app or security content from appearing in the Windows Action Center.
	- **Windows Spotlight personalization** – Stops Windows Spotlight from personalizing results based on the usage of a device.
	- **Windows welcome experience** – Block the Windows welcome experience that shows the user information about new, or updated features.


## Projection

- **User input from wireless display receivers** - Blocks user input from wireless display receivers.
- **Projection to this PC** - Stops other devices from discovering the PC for projection.
- **Require PIN for pairing** - Require a PIN when connecting to a projection device.

## Start

- **Unpin apps from task bar** - Stop the user from unpinning apps from the Start menu.
- **Documents on Start** - Hide or show the Documents folder in the Windows Start menu.
- **Downloads on Start** - Hide or show the Downloads folder in the Windows Start menu.
- **File Explorer on Start** - Hide or show the File Explorer app in the Windows Start menu.
- **HomeGroup on Start** - Hide or show the HomeGroup folder in the Windows Start menu.
- **Music on Start** - Hide or show the Music folder in the Windows Start menu.
- **Network on Start** - Hide or show the Network folder in the Windows Start menu.
- **Personal folder on Start** - Hide or show the Personal folder in the Windows Start menu.
- **Pictures on Start** - Hide or show the folder for pictures in the Windows Start menu.
- **Settings on Start** - Hide or show the Settings app in the Windows Start menu.
- **Videos on Start** - Hide or show the folder for videos in the Windows Start menu.