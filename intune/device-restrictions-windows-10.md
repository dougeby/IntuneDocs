---
# required metadata

title: Device restriction settings for Windows 10 in Microsoft Intune - Azure | Microsoft Docs
description: See a list of all the settings and their descriptions for creating device restrictions on Windows 10 and later devices. Use these settings in a configuration profile to control screenshots, password requirements, kiosk settings, apps in the store, Microsoft Edge browser, Windows defender, access to the cloud, start menu, and more in Microsoft Intune.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/03/2019
ms.topic: reference
ms.prod:
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
---

# Windows 10 (and newer) device settings to allow or restrict features using Intune

This article lists and describes all the different settings you can control on Windows 10 and newer devices. As part of your mobile device management (MDM) solution, use these settings to allow or disable features, set password rules, customize the lock screen, use Windows Defender, and more.

These settings are added to a device configuration profile in Intune, and then assigned or deployed to your Windows 10 devices.

> [!Note]
> Not all options are available on all editions of Windows. To see the supported editions, refer to the [policy CSPs](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider) (opens another Microsoft web site).

## Before you begin

[Create a device configuration profile](device-restrictions-configure.md#create-the-profile).

## App Store

- **App store (mobile only)**: Enable or block use of the app store on Windows 10 Mobile devices.
- **Auto-update apps from store**: Allows apps installed from the Microsoft Store to be automatically updated.
- **Trusted app installation**: Allows apps signed with a trusted certificate to be sideloaded.
- **Developer unlock**: Allow Windows developer settings, such as allowing sideloaded apps to be modified by the end user.
- **Shared user app data**: Allows apps to share data between different users on the same device.
- **Use private store only**: Enable to only allow end users to download apps from your private store.
- **Store originated app launch**: Used to disable all apps that were pre-installed on the device, or downloaded from the Microsoft Store.
- **Install app data on system volume**: Stops apps from storing data on the system volume of the device.
- **Install apps on system drive**: Stops apps from storing data on the system drive of the device.
- **Game DVR (desktop only)**: Configures whether recording and broadcasting of games is allowed.
- **Apps from the store only**: Configures whether users can install apps from places other than the app store.

## Cellular and Connectivity

- **Cellular data channel**: Stop users from using data, like browsing the web, when they're connected to a cellular network. 
- **Data roaming**: Allow roaming between networks when accessing data.
- **VPN over the cellular network**: Controls whether the device can access VPN connections when connected to a cellular network.
- **VPN roaming over the cellular network**: Controls whether the device can access VPN connections when roaming on a cellular network.
- **Bluetooth**: Controls whether the user can enable and configure Bluetooth on the device.
- **Bluetooth discoverability**: Lets the device be discovered by other Bluetooth-enabled devices.
- **Bluetooth pre-pairing**: Lets you configure specific Bluetooth devices to automatically pair with a host device.
- **Bluetooth advertising**: Lets the device receive advertisements over Bluetooth.
- **Connected devices service**: Lets you choose to allow the connected devices service, which enables discovery and connection to other Bluetooth devices.
- **NFC**: Lets the user enable and configure near field communications (NFC) features on the device.
- **Wi-Fi**: Lets the user enable and configure Wi-Fi on the device (Windows 10 Mobile only).
- **Automatically connect to Wi-Fi hotspots**: Lets the device automatically connect to free Wi-Fi hotspots and automatically accept any terms and conditions for the connection.
- **Manual Wi-Fi configuration**: Controls whether the user can configure their own Wi-Fi connections, or whether they can only use connections configured by a Wi-Fi profile (Windows 10 Mobile only).
- **Wi-Fi scan interval**: Enter how often devices scan for Wi-Fi networks. Enter a value from 1 (most frequent) to 500 (least frequent).
- **Bluetooth allowed services**: Enter as hex strings, a list of allowed Bluetooth services and profiles.

## Cloud and Storage

- **Microsoft account**: Lets the user associate a Microsoft account with the device.
- **Non-Microsoft account**: Lets users add email accounts to the device that aren't associated with a Microsoft account.
- **Settings synchronization for Microsoft account**: Allow device and app settings that are associated with a Microsoft account to synchronize between devices.
- **Microsoft Account sign-in assistant**: Choose **Disable** to prevent end users from controlling the Microsoft Sign-in Assistant service (wlidsvc), such as manually stopping or starting the service. When set to **Not configured**, the wlidsvc NT service uses the operating system (OS) default, which may allow end users to start and stop the service. This service is used by the OS to allow users to sign in to their Microsoft account.

## Cloud Printer

- **Printer discovery URL**: Enter the URL for finding cloud printers.
- **Printer access authority URL**: Enter the Authentication endpoint URL to get OAuth tokens. For example, enter something like `https://login.microsoftonline.com/your Azure AD Tenant ID`.
- **Azure native client app GUID**: Enter the GUID of a client application allowed to get OAuth tokens from the OAuthAuthority.
- **Print service resource URI**: Enter the OAuth resource URI for print service configured in the Azure portal. For example, enter something like `http://MicrosoftEnterpriseCloudPrint/CloudPrint`.
- **Maximum printers to query (Mobile only)**: Enter the maximum number of printers that you want to be queried. For example, enter `10`.
- **Printer discovery service resource URI**: Enter the OAuth resource URI for printer discovery service configured in the Azure portal. For example, enter something like `http://MopriaDiscoveryService/CloudPrint`.

> [!TIP]
> After you setup a [Windows Server Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-overview), you can configure these settings, and then deploy to Windows devices.

## Control Panel and Settings

- **Settings app**: Block access to the Windows settings app.
  - **System**: Blocks access to the system area of the settings app.
    - **Power and sleep settings modification (desktop only)**: Prevents the end user from changing power and sleep settings on the device.
  - **Devices**: Blocks access to the devices area of the settings app.
  - **Network Internet**: Blocks access to the network and internet area of the settings app.
  - **Personalization**: Blocks access to the personalization area of the settings app.
  - **Accounts**: Blocks access to the accounts area of the settings app.
  - **Time and Language**: Blocks access to the time and language area of the settings app.
    - **System Time modification**: Prevents the end user from changing the device date and time.
    - **Region settings modification (desktop only)**: Prevents the end user from changing the region settings on the device.
    - **Language settings modification (desktop only)**: Prevents the user from changing the language settings on the device.
  - **Gaming**: Blocks access to the Gaming app in Settings.
  - **Ease of Access**: Blocks access to the ease of access area of the settings app.
  - **Privacy**: Blocks access to the privacy area of the settings app.
  - **Update and Security**: Blocks access to the updates and security area of the settings app.

## Display

- **Turn on GDI scaling for apps**
- **Turn off GDI scaling for apps**

  GDI DPI Scaling lets apps that aren't DPI aware to become per-monitor DPI aware. Enter the legacy apps that have GDI DPI Scaling turned on. With GDI DPI Scaling configured to turn on and turn off on an app, scaling is turned off for the app.

## General

- **Screen capture (mobile only)**: Lets the user capture the device screen as an image.
- **Copy and paste (mobile only)**: Allow copy and paste actions between apps on the device.
- **Manual unenrollment**: Lets the user manually delete the workplace account from the device.
  - This policy setting doesn't apply if the computer is Azure AD joined and auto-enrollment is enabled. 
  - This policy setting doesn't apply to computers running Windows 10 Home.
- **Manual root certificate installation (mobile only)**: Stops the user from manually installing root certificates, and intermediate CAP certificates.

- **Camera**: Allow or block use of the camera on the device.
- **OneDrive file sync**: Blocks the device from synchronizing files to OneDrive.
- **Removable storage**: Specifies whether external storage devices, like SD cards can be used with the device.
- **Geolocation**: Specifies whether the device can use location services information.
- **Internet sharing**: Allow the use of Internet connection sharing on the device.
- **Phone reset**: Controls whether the user can do a wipe on their device.
- **USB connection (mobile only)**: Controls whether devices can access external storage devices through a USB connection.
- **AntiTheft mode (mobile only)**: Configure whether Windows Antitheft mode is enabled.
- **Cortana**: Enable or disable the Cortana voice assistant.
- **Voice recording (mobile only)**: Allow or block use of the device voice recorder.
- **Device name modification**: Prevents the end user from changing the device name (Windows 10 Mobile only)
- **Add provisioning packages**: Blocks the run time configuration agent that installs the provisioning packages.
- **Remove provisioning packages**: Blocks the run time configuration agent that removes the provisioning packages.
- **Device discovery**: Block a device from being discovered by other devices.
- **Task Switcher (mobile only)**: Blocks the task switcher on the device.
- **SIM card error dialog (mobile only)**: Blocks an error message from displaying on the device if no SIM card is detected.
- **Ink Workspace**: Block users from accessing the ink workspace. **Not configured** turns on the ink workspace, and the user is allowed to use it above the lock screen.
- **Automatic redeployment**: Allows users with administrative rights to delete all user data and settings using **CTRL + Win + R** at the device lock screen. The device is automatically reconfigured and reenrolled into management.
- **Require users to connect to network during device setup (Windows Insider only)**: Choose **Require** so the device connects to a network before going past the Network page during Windows 10 setup. While this feature is in preview, a Windows insider build 1809 or later is required to use this setting.

  If a device doesn't have network connectivity during Windows 10 setup, then this setting isn't applied. The setting becomes effective the next time the device is wiped or reset. So, it may not apply to brand new devices. Like any other Intune configuration, the device must be enrolled and managed by Intune to receive configuration settings. But once it's enrolled, and receiving policies, then resetting the device enforces the setting during the next Windows setup.

- **Direct Memory Access**: **Block** prevents direct memory access (DMA) for all hot pluggable PCI downstream ports until a user signs into Windows. **Enabled** (default) allows access to DMA, even when a user isn't signed in.

  CSP: [DataProtection/AllowDirectMemoryAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dataprotection#dataprotection-allowdirectmemoryaccess)

- **End processes from Task Manager**: This setting determines whether non-administrators can use Task Manager to end tasks. **Block** prevents standard users (non-administrators) from using Task Manager to end a process or task on the device. **Not configured** (default) allows standard users to end a process or task using Task Manager.

## Locked screen experience

- **Action center notifications (mobile only)**: Lets Action Center notifications appear on the device lock screen (Windows 10 Mobile only).
- **Locked screen picture URL (Desktop only)**: Enter the URL to a picture in JPEG format that's used as the Windows lock screen wallpaper. This setting locks the image. The image can't be changed afterwards.
- **User configurable screen timeout (mobile only)**: Lets users configure the amount of time 
- **Cortana on locked screen (desktop only)**: Don’t allow the user to interact with Cortana when the device is on the lock screen (Windows 10 desktop only).
- **Toast notifications on locked screen**: Block alert messages from showing on the device lock screen.
- **Screen timeout (mobile only)**: Specifies the time in seconds after the screen locks, when it will turn off.

## Messaging

- **Message sync (mobile only)**: Disable Messaging Everywhere and text message back up and restore.
- **MMS (mobile only)**: Disable the MMS send/receive functionality on the device.
- **RCS (mobile only)**: Disable the Rich Communication Services send/receive functionality on the device.

## Microsoft Edge Browser

### Use Microsoft Edge kiosk mode

The available settings change depending on what you choose. Your options:

- **No** (default): Microsoft Edge isn't running in kiosk mode. All Microsoft Edge settings are available for you to change and configure.
- **Digital/Interactive signage (single app kiosk)**: Filters Microsoft Edge settings that are applicable for Digital/Interactive signage Microsoft Edge Kiosk mode for use only on Windows 10 single-app kiosks. Choose this setting to open a URL full screen, and only show the content on that website. [Set up digital signs](https://docs.microsoft.com/windows/configuration/setup-digital-signage) provides more information on this feature.
- **InPrivate Public browsing (single app kiosk)**: Filters Microsoft Edge settings that are applicable for InPrivate Public Browsing Microsoft Edge Kiosk mode for use on Windows 10 single-app kiosks. Runs a multi-tab version of Microsoft Edge.
- **Normal mode (multi-app kiosk)**: Filters Microsoft Edge settings that are applicable for Normal Microsoft Edge Kiosk mode. Runs a full-version of Microsoft Edge with all browsing features.
- **Public browsing (multi-app kiosk)**: Filters Microsoft Edge settings that are applicable for Public browsing on a Windows 10 multi-app kiosk.  Runs a multi-tab version of Microsoft Edge InPrivate.

> [!TIP]
> For more information on what these options do, see [Microsoft Edge kiosk mode configuration types](https://docs.microsoft.com/microsoft-edge/deploy/microsoft-edge-kiosk-mode-deploy#supported-configuration-types).

This device restrictions profile is directly related to the kiosk profile you create using the [Windows kiosk settings](kiosk-settings-windows.md). To summarize:

1. Create the [Windows kiosk settings](kiosk-settings-windows.md) profile to run the device in kiosk mode. Select Microsoft Edge as the application and set the Microsoft Edge Kiosk Mode in the Kiosk profile.
2. Create the device restrictions profile described in this article, and configure specific features and settings allowed in Microsoft Edge. Be sure to choose the same Microsoft Edge kiosk mode type as selected in your kiosk profile ([Windows kiosk settings](kiosk-settings-windows.md)). 

    [Supported kiosk mode settings](https://docs.microsoft.com/microsoft-edge/deploy/microsoft-edge-kiosk-mode-deploy#supported-policies-for-kiosk-mode) is a great resource.

> [!IMPORTANT] 
> Be sure to assign this Microsoft Edge profile to the same devices as your kiosk profile ([Windows kiosk settings](kiosk-settings-windows.md)).

[ConfigureKioskMode CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-configurekioskmode)

### Start experience

- **Start Microsoft Edge with**: Choose which pages open when Microsoft Edge starts. Your options:
  - **Start pages**: Microsoft Edge start with the default start page defined by the OS
  - **New Tab page**: Microsoft Edge load whatever is defined in the **New Tab page URL** setting
  - **Last session’s page**: Microsoft Edge loads the last session page 
  - **Custom start page**: Microsoft Edge loads the start page defined by the IT administrator
- **User can change Start pages**: **Allow** lets users change the Start pages. Administrators can use the `EdgeHomepageUrls` to enter the Start pages that users see by default when open Microsoft Edge. **Not configured** blocks users from changing the start pages.
- **New Tab page URL**: Enter the URL to open on the New Tab page. For example, enter `https://www.bing.com`.
- **Open web content on New Tab page**: Choose **Block** to stop Microsoft Edge from opening a website on a new tab. When blocked, new tab open blank. **Not configured** uses the OS default behavior on the device, which may allow users to choose what's shown.
- **Home button**: Choose what happens when the Home button is selected. Your options:
  - **Start pages**: The option you chose for the **Start Microsoft Edge with** setting opens
  - **New Tab page**: The option you chose for the **New Tab page URL** setting opens
  - **Custom Home button URL**: The option you chose for the **Home button URL** setting opens
  - **Hide Home button**: Hides the home button
- **User can change Home button**: **Allow** lets users change the home button. The user's changes override any administrator settings to the home button.​ **Not configured** uses the OS default behavior on the device, which may block users from changing how administrator configured the home button.
- **Show First Run Experience page**: **Block** stops the introduction page from showing the first time you run Microsoft Edge. This feature allows enterprises, like those organizations enrolled in zero emissions configurations, to block this page. **Not configured** shows the introduction page.
  - **First Run Experience URL**: Enter the page URL to show the first time a user runs Microsoft Edge (Windows 10 Mobile only).
- **Refresh browser after idle time**: Enter the number of idle minutes until the browser is refreshed, from 0-1440 minutes. Default is `5` minutes. When set to `0` (zero), the browser doesn't refresh after being idle.

  This setting is only available when running in [InPrivate Public browsing (single-app kiosk)](#use-microsoft-edge-kiosk-mode).

  CSP: [ConfigureKioskResetAfterIdleTimeout](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-configurekioskresetafteridletimeout)

- **Pop-ups**: Choose **Block** to stop pop-up windows in the browser. Applies to Windows 10 desktop only. **Not configured** allows pop-ups in the web browser.
- **Send intranet traffic to Internet Explorer**: **Allow** lets users open intranet websites in Internet Explorer instead of Microsoft Edge (Windows 10 desktop only). **Not configured** allows users to use Microsoft Edge.
- **Enterprise mode site list location**: Enter the URL that includes a list of web sites that open in Enterprise mode. Users can't change this list. Applies to Windows 10 desktop only.
- **Message when opening sites in Internet Explorer**: Use this setting to configure Microsoft Edge to show a notification before a site opens in Internet Explorer 11. Your options:
  - **Not configured**: The OS default behavior is used, which may not show a message.
  - **Show message without option to open sites in Microsoft Edge**: Show the message when opening sites in IE. Sites open in IE. There isn't an option to open sites in Microsoft Edge.
  - **Show message when opening sites in Microsoft Edge**: Show the message when opening sites in IE. The message includes a **Keep going in Microsoft Edge** link so users can choose Microsoft Edge instead of IE.

  > [!IMPORTANT]
  > This setting requires you to enable the **Configure the Enterprise Mode Site List** setting, the **Send all intranet sites to Internet Explorer 11** setting, or both settings.

- **Microsoft compatibility list**: **Block** prevents the Microsoft compatibility list in Microsoft Edge. This list from Microsoft helps Microsoft Edge properly display sites with known compatibility issues. **Not configured** allows using a Microsoft compatibility list.
- **Preload Start pages and New Tab page**: Choose **Block** to prevent Microsoft Edge from preloading start pages and the new tab page. Preloading minimizes the time to start Microsoft Edge, and load a new tab. **Not configured** uses the OS default behavior, which may be to preload these pages.
- **Prelaunch Start pages and New Tab page**: Choose **Block** to prevent Microsoft Edge from pre-launching the start pages and new tab page. Pre-launching helps the performance of Microsoft Edge, and minimizes the time required to start Microsoft Edge. **Not configured** uses the OS default behavior, which may be to prelaunch these pages.

### Favorites and search

- **Favorites bar**: Choose what happens to the favorites bar on any Microsoft Edge page. Your options:
  - **Not configured**: Uses the OS default behavior, which may be to hide the favorites bar on all pages. User can change this setting.
  - **Hide**: Hides the favorites bar on all pages. User can't change this setting.
  - **Show**: Shows the favorites bar on all pages. User can't change this setting.
- **Favorites List**: Add a list of URLs to the favorites file. For example, add `http://contoso.com/favorites.html`.
- **Restrict changes to Favorites**: **Block** to prevent users from adding, importing, sorting, or editing the Favorites list. **Not configured** uses the OS default, which may allow users to change the list.
- **Sync favorites between Microsoft browsers (desktop only)**: **Require** forces Windows to synchronize favorites between Internet Explorer and Microsoft Edge. Additions, deletions, modifications, and order changes to favorites are shared between browsers.  **Not configured** uses the OS default, which may give users the choice to sync favorites between the browsers.
- **Default search engine**: Choose the default search engine on the device. End users can change this value at any time. Your options:
  - Default
  - Bing
  - Google
  - Yahoo
  - Custom value
- **Search suggestions**: **Not configured** lets your search engine suggest sites as you type search phrases in the address bar. **Block** prevents this feature.
- **Allow changes to search engine**: **Yes** (default) allows users to add new search engines, or change the default search engine in Microsoft Edge. Choose **No** to prevent users from customizing the search engine.

  This setting is only available when running in [Normal mode (multi-app kiosk)](#use-microsoft-edge-kiosk-mode).

  CSP: [AllowSearchEngineCustomization](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-allowsearchenginecustomization)

### Privacy and security

- **InPrivate browsing**: **Block** prevents end users from opening InPrivate browsing sessions. **Not configured** allows this feature.
- **Save browsing history**: **Block** prevents Microsoft Edge from saving the browsing history. **Not configured** allow saving the browsing history.
- **Clear browsing data on exit (Desktop only)**: **Require** clears history, and browsing data when the user exits Microsoft Edge. **Not configured** uses the OS default, which may cache the browsing data.
- **Sync browser settings between user's devices**: Choose how you want to sync browser settings between devices. Your options:
  - **Allow**: Allow syncing of Microsoft Edge browser settings between user’s devices
  - **Block and enable user override**: Block syncing of Microsoft Edge browser settings between user’s devices. Users can override this setting.
  - **Block**: Block syncing of Microsoft Edge browser setting between user’s devices. Users can't override this setting.
- **Password Manager**: **Block** disables the Microsoft Edge Password Manager feature. **Not configured** allows this feature.
- **Cookies**: Choose how cookies are handled in the web browser. Your options:
  - **Allow**: Cookies are stored on the device.
  - **Block all cookies**: Cookies aren't stored on the device.
  - **Block only third party cookies**: Third party or partner cookies aren't stored on the device.
- **Autofill**: **Block** disables the Autofill feature on the device. **Not configured** allows users to change autocomplete settings in the browser (Windows 10 desktop only).
- **Send do-not-track headers**: **Not configured** requires devices to send do-not-track headers to websites requesting tracking info (recommended). Choose **Block** to prevent the device from sending these headers, which allows websites to track the user.
- **WebRtc localhost IP address**: **Block** prevents users localhost IP address being shown when making phone calls using the web RTC protocol. **Not configured** allows users localhost IP address to be shown when making phone calls using this protocol.
- **Live Tile data collection**: Choose **Block** to stop Windows from collecting information from the Live Tile a site is pinned to the start menu from Microsoft Edge. **Not configured** allows this information to be collected.
- **User can override certificate errors**: **Block** prevents users from accessing websites that have SSL or TLS errors. **Not configured** allows users to access these sites.

### Additional

- **Microsoft Edge browser (mobile only)**: Choose **Block** to prevent using Microsoft Edge on the device. If you block Microsoft Edge, the individual settings only apply to desktop. **Not configured** allows using the Microsoft Edge web browser on the device.
- **Address bar dropdown (desktop only)**: **Block** stops Microsoft Edge from showing a list of suggestions in a drop-down list when you type. This option helps minimize network bandwidth between Microsoft Edge and Microsoft services. **Not configured** allows Microsoft Edge to show a list of suggestions.
- **Full screen**: Choose **Block** to prevent Microsoft Edge from only showing the web content, and hiding the Microsoft Edge (fullscreen mode). **Not configured** uses the OS default, which allows Microsoft Edge to use fullscreen mode.
- **About flags**: **Block** prevents end users from accessing the `about:flags` page in Microsoft Edge that includes the developer and experimental settings. **Not configured** uses the OS default, which may allow accessing the `about:flags` page.
- **Developer tools**: **Block** prevents end users from opening the Microsoft Edge developer tools. **Not configured** allows users to open the developer tools.
- **Extensions**: **Not configured** allows end users to install Microsoft Edge extensions on the device. **Block** prevents the installation.
- **Sideloading developer extensions**: **Block** prevents Microsoft Edge from sideloading, which installs and runs unverified extensions using the **Load extensions** feature. **Not configured** uses the OS default, which may allow sideloading.
- **Required extensions**: Choose which extensions can't be turned off by end users in Microsoft Edge. Enter the package family names, and select **Add**. [Find a package family name (PFN)](https://docs.microsoft.com/sccm/protect/deploy-use/find-a-pfn-for-per-app-vpn) lists provides some guidance.

  You can also **Import** a CSV file that includes the package family names.

- **JavaScript**: Choose **Block** to prevent Java scripts in the browser from running on the device. **Not configured** allows scripts, such as Javascript, to run in the Microsoft Edge browser.

## Network proxy

- **Automatically detect proxy settings**: When enabled, the device tries to find the path to a PAC script.
- **Use proxy script**: Select this option to enter a path to a PAC script to configure the proxy server.
  - **Setup script address URL**: Enter the URL of a PAC script you want to use to configure the proxy server.
- **Use manual proxy server**: Select this option to manually enter proxy server information.
  - **Address**: Enter the name, or IP address of the proxy server.
  - **Port number**: Enter the port number of your proxy server.
  - **Proxy exceptions**: Enter any URLs that must not use the proxy server. Use a semicolon to separate each item.
  - **Bypass proxy server for local address**: If you don't want to use the proxy server for local addresses on your intranet, enable this option.

## Password

- **Password**: Require the end user to enter a password to access the device.
  - **Required password type**: Specifies whether the password must be numeric only, or alphanumeric.
  - **Minimum password length**: Applies to Windows 10 Mobile only.
  - **Number of sign-in failures before wiping device**: For devices running Windows 10: If the device has BitLocker enabled, it's put into BitLocker recovery mode after sign in fails the number of times that you specified. If the device isn't BitLocker enabled, then this setting doesn't apply. For devices running Windows 10 Mobile: After sign in fails the number of times you enter, the device is wiped.
  - **Maximum minutes of inactivity until screen locks**: Specifies the length of time a device must be idle before the screen is locked.
  - **Password expiration (days)**: Specifies the length of time after which the device password must be changed.
  - **Prevent reuse of previous passwords**: Specifies the number of previously used passwords that are remembered by the device.
  - **Require password when device returns from idle state (Mobile only)**: Specifies that the user must enter a password to unlock the device (Windows 10 Mobile only).
  - **Simple passwords**: Lets you allow the use of simple passwords like 1111 and 1234. This setting also allows or blocks the use of Windows picture passwords.

## Per-app privacy exceptions

You can add apps that should have a different privacy behavior from what you defined in “Default privacy”.

- **Package Name**: App package family name.
- **App Name**: The name of the app.

### Exceptions

- **Account information**: Define whether this app can access the user name, picture, and other contact info.
- **Background apps**: Define whether this app can run in the background.
- **Calendar**: Define whether this app can access the calendar.
- **Call history**: Define whether this app can access my call history.
- **Camera**: Define whether this app can access the camera.
- **Contacts**: Define whether this app can access contacts.
- **Email**: Define whether this app can access and send email.
- **Location**: Define whether this app can access location information.
- **Messaging**: Define whether this app can read or send text or MMS messages.
- **Microphone**: Define whether this app can use the microphone.
- **Motion**: Define whether this app can access device motion information.
- **Notifications**: Define whether this app can access notifications.
- **Phone**: Define whether this app can access the phone.
- **Radios**: Some apps use radios (for example, Bluetooth) in your device to send and receive data and need to turn these radios on or off. Define whether this app can control these radios.
- **Tasks**: Define whether this app can access your tasks.
- **Trusted devices**: Choose if this app can use trusted devices. Trusted devices are hardware you've already connected, or hardware that comes with device. For example, use TVs, projectors, and so on, as trusted devices.
- **Feedback and diagnostics**: Define whether this app can access diagnostic information.
- **Sync with devices**: Choose if this app can automatically share and sync info with wireless devices that don't explicitly pair with the device.

## Personalization

- **Desktop background picture URL (Desktop only)**: Enter the URL to a picture in JPEG format that you want to use as the Windows desktop wallpaper. Users can't change the picture.

## Printer

- **Printers**: List of local printers that have been added.
- **Default printer**: Set the default printer.
- **User access to add new printers**: Allow or block use of local printers.

## Privacy

- **Input personalization**: Don’t allow the use of cloud-based speech services for Cortana, dictation, or Microsoft Store apps. If you allow these services, Microsoft might collect voice data to improve the service.
- **Automatic acceptance of the pairing and privacy user consent prompts**: Allow Windows to automatically accept pairing and privacy consent messages when running apps.
- **Publish user activities**: **Block** prevents shared experiences and discovery of recently used resources in the task switcher.
- **Local activities only**: **Block** prevents shared experiences and the discovery of recently used resources in task switcher, based only on local activity.

You can configure information that all apps on the device can access. Also, define exceptions on a per-app basis using **Per-app privacy exceptions**.

### Exceptions

- **Account information**: Define whether this app can access the user name, picture, and other contact info.
- **Background apps**: Define whether this app can run in the background.
- **Calendar**: Define whether this app can access the calendar.
- **Call history**: Define whether this app can access my call history.
- **Camera**: Define whether this app can access the camera.
- **Contacts**: Define whether this app can access contacts.
- **Email**: Define whether this app can access and send email.
- **Location**: Define whether this app can access location information.
- **Messaging**: Define whether this app can read or send text or MMS messages.
- **Microphone**: Define whether this app can use the microphone.
- **Motion**: Define whether this app can access device motion information.
- **Notifications**: Define whether this app can access notifications.
- **Phone**: Define whether this app can access the phone.
- **Radios**: Some apps use radios (for example, Bluetooth) in your device to send and receive data and need to turn these radios on or off. Define whether this app can control these radios.
- **Tasks**: Define whether this app can access your tasks.
- **Trusted devices**: Choose if this app can use trusted devices. Trusted devices are hardware you've already connected, or hardware that comes with the device. For example, use TVs, projectors, and so on, as trusted devices.
- **Feedback and diagnostics**: Choose if this app can access diagnostic information.
- **Sync with devices** -Define whether this app can automatically share and sync info with wireless devices that don't explicitly pair with this PC, tablet, or phone.

## Projection

- **User input from wireless display receivers**: Blocks user input from wireless display receivers.
- **Projection to this PC**: Stops other devices from finding the PC for projection.
- **Require PIN for pairing**: Require a PIN when connecting to a projection device.

## Reporting and telemetry

- **Share usage data**: Choose the level of diagnostic data that's submitted. Your options:
  - Security
  - Basic
  - Enhanced
  - Full
- **Send Microsoft Edge browsing data to Microsoft 365 Analytics**: To use this feature, set the **Share usage data** settings to **Enhanced** or **Full**. This feature controls what data Microsoft Edge sends to Microsoft 365 Analytics for enterprise devices with a configured commercial ID. Your options:
  - **Not configured**: Uses the OS default, which may not send any browsing history data
  - **Only send intranet data**: Allows the administrator to send intranet data history
  - **Only send internet data**: Allows the administrator to send internet data history
  - **Send intranet and internet data**: Allows the administrator to send intranet and internet data history
- **Telemetry proxy server**: Enter the fully qualified domain name (FQDN) or IP address of a proxy server to forward Connected User Experiences and Telemetry requests, using a Secure Sockets Layer (SSL) connection. The format for this setting is *server*:*port*. If the named proxy fails, or if a proxy isn't entered when enabling this policy, the Connected User Experiences and Telemetry data isn't sent, and stays on the local device.

  Example formats:

  ```
  IPv4: 192.246.246.106:100
  IPv6: [2001:4898:4010:4013:95c1:a8b2:953c:c633]:100
  FQDN: www.contoso.com:345
  ```

## Search

- **Safe Search (mobile only)**: Control how Cortana filters adult content in search results. You can select **Strict**, **Moderate**, or allow the end user to choose their own settings.
- **Display web results in search**: Block or allow web results to appear in searches made on the device.

## Start

- **Start menu layout**: To customize the start menu on desktop devices, you can upload an XML file that includes your customizations, including the order the apps are listed, and more. Users can't change the Start menu layout you enter.
- **Pin websites to tiles in Start menu**: Import images from Microsoft Edge that are shown as links in the Windows Start menu for desktop devices.
- **Unpin apps from task bar**: Choose **Block** to stop the user from unpinning apps from the task bar.
- **Fast user switching**: Choose **Block** to prevent switching between users that are logged on simultaneously without logging off.
- **Most used apps**: Choose **Block** to hide the most used apps from showing on the start menu. It also disables the corresponding toggle in the Settings app.
- **Recently added apps**: Choose **Block** to hide recently added apps from showing on the start menu. It also disables the corresponding toggle in the Settings app.
- **Start screen mode**: Choose how the start screen is shown. Choose to show it as **Full screen** or **Non-full screen**.
- **Recently opened items in Jump Lists**: Choose **Block** to hide recent jump lists from being shown on the start menu and taskbar. It also disables the corresponding toggle in the Settings app.
- **App list**: Choose how the Settings app is shown. Your options: 
  - Collapse
  - Collapse and disable the Settings app 
  - Removes and disables the Settings app
- **Power button**: Choose **Block** to hide the power button from showing in the start menu.
- **User Tile**: Choose **Block** to hide the user tile from showing in the start menu.
  - **Lock**: Choose **Block** to hide the `Lock` option from showing in the user tile in the start menu.
  - **Sign out**: Choose **Block** to hide the `Sign out` option from showing in the user tile in the start menu.
- **Shut Down**: Choose **Block** to hide the `Update and shut down` and `Shut down` options from showing in the power button in the start menu.
- **Sleep**: Choose **Block** to hide the `Sleep` option from showing in the power button in the start menu.
- **Hibernate**: Choose **Block** to hide the `Hibernate` option from showing in the power button in the start menu.
- **Switch Account**: Choose **Block** to hide the `Switch account` from showing in the user tile in the start menu.
- **Restart Options**:  Choose **Block** to hide the `Update and restart` and `Restart` options from showing in the power button in the start menu.
- **Documents on Start**: Hide or show the Documents folder in the Windows Start menu.
- **Downloads on Start**: Hide or show the Downloads folder in the Windows Start menu.
- **File Explorer on Start**: Hide or show the File Explorer app in the Windows Start menu.
- **HomeGroup on Start**: Hide or show the HomeGroup folder in the Windows Start menu.
- **Music on Start**: Hide or show the Music folder in the Windows Start menu.
- **Network on Start**: Hide or show the Network folder in the Windows Start menu.
- **Personal folder on Start**: Hide or show the Personal folder in the Windows Start menu.
- **Pictures on Start**: Hide or show the folder for pictures in the Windows Start menu.
- **Settings on Start**: Hide or show the Settings app in the Windows Start menu.
- **Videos on Start**: Hide or show the folder for videos in the Windows Start menu.

## Windows Defender Smart Screen

- **SmartScreen for Microsoft Edge**: Enable Microsoft Edge SmartScreen for accessing site and file downloads.
- **Malicious site access**: Block users from ignoring the Windows Defender SmartScreen Filter warnings and block them from going to the site.
- **Unverified file download**: Block users from ignoring the Windows Defender SmartScreen Filter warnings and block them from downloading unverified files.

## Windows Spotlight

- **Windows Spotlight**: Use this setting to block all Windows Spotlight functionality on Windows 10 devices. If you block this setting, the following settings aren't available:
  - **Windows Spotlight on lock screen**: Stop Windows Spotlight from displaying information on the device lock screen.
  - **Third-party suggestions in Windows Spotlight**: Stop Windows Spotlight from suggesting content that is not published by Microsoft.
  - **Consumer Features**: Lets you block consumer features like Start menu suggestions, and membership notifications.
  - **Windows Tips**: Lets you block pop-up tips from displaying in Windows.
  - **Windows Spotlight in action center**: Block Windows Spotlight suggestions like new app or security content from appearing in the Windows Action Center.
  - **Windows Spotlight personalization**: Stops Windows Spotlight from personalizing results based on the usage of a device.
  - **Windows welcome experience**: Block the Windows welcome experience that shows the user information about new, or updated features.

## Windows Defender Antivirus

- **Real-time monitoring**: Enables real-time scanning for malware, spyware, and other unwanted software.
- **Behavior monitoring**: Lets Defender check for certain known patterns of suspicious activity on devices.
- **Network Inspection System (NIS)**: NIS helps to protect devices against network-based exploits. It uses the signatures of known vulnerabilities from the Microsoft Endpoint Protection Center to help detect and block malicious traffic.
- **Scan all downloads**: Controls whether Defender scans all files downloaded from the Internet.
- **Scan scripts loaded in Microsoft web browsers**: Lets Defender scan scripts that are used in Internet Explorer.
- **End user access to Defender**: Controls whether the Windows Defender user interface is hidden from end users. When this setting is changed, it takes effect the next time the end user's PC is restarted.
- **Signature update interval (in hours)**: Enter the interval at which Defender checks for new signature files.
- **Monitor file and program activity**: Allows Defender to monitor file and program activity on devices.
- **Days before deleting quarantined malware**: Continue tracking resolved malware for the number of days you enter so you can manually check previously-affected devices. If you set the number of days to **0**, malware stays in the Quarantine folder, and isn't automatically removed.
- **CPU usage limit during a scan**: Limit the amount of CPU that scans are allowed to use, from **1** to **100**.
- **Scan archive files**: Allows Defender to scan archived files such as Zip or Cab files.
- **Scan incoming mail messages**: Allows Defender to scan email messages as they arrive on the device.
- **Scan removable drives during a full scan**: Lets Defender scan removable drives like USB sticks.
- **Scan mapped network drives during a full scan**: Lets Defender scan files on mapped network drives.
  If the files on the drive are read-only, Defender can't remove any malware found in them.
- **Scan files opened from network folders**: Lets Defender scan files on shared network drives (for example, files accessed from a UNC path). If the files on the drive are read-only, Defender can't remove any malware found in them.
- **Cloud protection**: Allows or blocks the Microsoft Active Protection Service from receiving information about malware activity from devices that you manage. This information improves the service in the future.
- **Prompt users before sample submission**: Controls whether potentially malicious files that might require further analysis are automatically sent to Microsoft.
- **Time to perform a daily quick scan**: Choose the hour to run a daily quick scan. **Not configured** doesn't run a daily scan. If you want more customization, configure the **Type of system scan to perform** setting.

  [Defender/ScheduleQuickScanTime CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulequickscantime)
- **Type of system scan to perform**: Schedule a system scan, including the level of scanning, and the day and time to run the scan. Your options:
  - **Not configured**: Doesn't schedule a system scan on the device. End users can manually run scans as needed or wanted on their devices.
  - **Disable**: Disables any system scanning on the device. Choose this option if you're using a partner anti-virus solution that scans devices.
  - **Quick scan**: Looks at common locations where there could be malware registered, such as registry keys and known Windows startup folders.
    - **Day scheduled**: Choose the day to run the scan.
    - **Time scheduled**: Choose the hour to run the scan.
  - **Full scan**: Looks at common locations where there could be malware registered, and also scans every file and folder on the device.
    - **Day scheduled**: Choose the day to run the scan.
    - **Time scheduled**: Choose the hour to run the scan.

  This setting may conflict with the **Time to perform a daily quick scan** setting. Some recommendations:

  - To run a daily quick scan, configure the **Time to perform a daily quick scan** setting.
  - To run a daily quick scan and a full scan every week, then configure the **Time to perform a daily quick scan**, and set **Type of system scan to perform** to a full scan with the day and time.
  - Don't configure the **Time to perform a daily quick scan** setting simultaneously with the **Type of system scan to perform** set to **Quick scan**. These settings may conflict, and a scan may not run.
  - To run a quick scan every Tuesday at 6 AM, configure the **Type of system scan to perform** setting.

  [Defender/ScanParameter CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-scanparameter)  
  [Defender/ScheduleScanDay CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulescanday)  
  [Defender/ScheduleScanTime CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulescantime)

- **Detect potentially unwanted applications**: Choose the level of protection when Windows detects potentially unwanted applications from:
  - **Block**
  - **Audit**
  For more information about potentially unwanted apps, see [Detect and block potentially unwanted applications](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus).
- **Actions on detected malware threats**: Choose the actions you want Defender to take for each threat level it detects: low, moderate, high, and severe. Your options:
  - **Clean**
  - **Quarantine**
  - **Remove**
  - **Allow**
  - **User defined**
  - **Block**

### Windows Defender Antivirus Exclusions

- **Files and folders to exclude from scans and real-time protection**: Adds one or more files and folders like **C:\Path** or **%ProgramFiles%\Path\filename.exe** to the exclusions list. These files and folders aren't included in any real-time or scheduled scans.
- **File extensions to exclude from scans and real-time protection**: Add one or more file extensions like **jpg** or **txt** to the exclusions list. Any files with these extensions aren't included in any real-time or scheduled scans.
- **Processes to exclude from scans and real-time protection**: Add one or more processes of the type **.exe**, **.com**, or **.scr** to the exclusions list. These processes aren't included in any real-time, or scheduled scans.

## Next steps

For additional technical details on each setting and what editions of Windows are supported, see [Windows 10 Policy CSP Reference](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider)
