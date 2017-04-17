---
# required metadata

title: Intune device restrictions settings for iOStitleSuffix: "Intune Azure preview"
description: "Intune Azure preview: Learn the Intune settings you can use to control device settings and functionality on iOS devices."
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 73590192-54ca-4833-9f1d-83e1b654399f

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# iOS device restriction settings in Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## General
- 	**Camera** - Select whether the camera on the device can be used. 	
- 	**Diagnostic data submission** - Allow or block the device from submitting diagnostic data to Apple.
- 	**FaceTime** - Allow the FaceTime app to be used on the device.
- 	**Screen capture** - Allow the user to capture the contents of the screen as an image.
- 	**Siri** - Allow use of the Siri voice assistant on the device.
	- 	**Siri while device is locked** - Allow use of the Siri voice assistant on the device while it is locked.
	- 	**Siri profanity filter (supervised only)** - Prevents Siri from dictating, or speaking profane language.
	- 	**Siri to query user-generated content from the internet (supervised only)** - Allow Siri to access websites to answer questions.
- 	**Untrusted TLS certificates** - Allow untrusted Transport Layer Security certificates on the device.
- 	**Control Center access while device locked** - Allow the user to access the control center app when the device is locked.
- 	**Notifications while device locked** - Allow the user to access the notifications view without unlocking the device.
- 	**Passbook while device locked** - Allow the user to access the Passbook app while the device is locked.
- 	**Today view while device locked** - Allow the user to see the Today view when the device is locked.
- 	**Enterprise app trust** - Lets the user select to trust apps that were not downloaded from the app store.
- 	**AirDrop (supervised only)** - Allow use of the AirDrop feature to exchange content with nearby devices.
- 	**Spotlight search to return results from internet (supervised only)** - Let Spotlight search connect to the Internet to provide further results.
- 	**Word definition lookup (supervised only)** - Allow the iOS feature that lets you highlight a word and look up it's definition.
- 	**Predictive keyboards (supervised only)** - Allow the use of predictive keyboards that suggest words the user might want.
- 	**Auto-correction (supervised only)** - Lets the device automatically correct misspelled words.
- 	**Keyboard spell-check (supervised only)** - Allows the device spell checker.
- 	**Keyboard shortcuts (supervised only)** - Allows use of keyboard shortcuts.
- 	**Wrist detection for paired Apple watch** - When enabled, the Apple Watch won't display notifications when it is not being worn.
- **Require AirPlay outgoing requests pairing password** - Require a pairing password when the user uses AirPlay to stream content to other Apple devices.
- **Account modification (supervised only)** - When blocked, this prevents the user from modifying device-specific settings from the iOS settings app, like creating new device accounts, and changing the user name or password.
This also applies to settings accessible from the iOS settings app like Mail, Contacts, Calendar, Facebook, and Twitter. This does not apply to apps with account settings that are not configurable from the iOS settings app, for example, the Microsoft Outlook app.
- **Apple Watch pairing (supervised only)** - Allow the device to pair with an Apple Watch.
- **Bluetooth modification (supervised only)** - Block the end user from changing Bluetooth settings on the device.
- **Remote screen observation by Classroom app (supervised only)** - Allow or block the Classroom app from observing the screen on remote devices.
- **Enabling restrictions in the device settings (supervised only)** - Allow the user to configure device restrictions (parental controls) on the device.
- **Use of the erase all content and settings option on the device (supervised only)** - Allow the user to use the option of erasing all content and settings on the device.
- **Device name modification (supervised only)** - Allow the user to change the name of the device.
- **Diagnostics submission settings modification (supervised only)** - Allow or block the device from submitting diagnostic data to Apple.
- **Host pairing to control the devices an iOS device can pair with (supervised only)** - Allow host pairing to let the administrator control which devices an iOS device can pair with.
- **Notification settings modification (supervised only)** - Allow the user to change the device notification settings.
- **Passcode modification (supervised only)** - Allow the device password to be added, changed, or removed.
- **Wallpaper modification (supervised only)** - Allow the user to change the device wallpaper.
- **Enterprise app trust settings modification (supervised only)** - Lets the user select to trust apps that were not downloaded from the app store.
- **Installing apps from App Store (supervised only)** - Allow the device to access the app store and install apps.
- **Changes to the Find My Friends app settings (supervised only)** - Allow the user to change settings for the Find My Friends app.
- **iBooks store (supervised only)** - Allow the user to browse and purchase books from the iBooks store.
- **Messages app on the device (supervised only)** - Allow use of the Messages app to send and read text messages.
- **Podcasts (supervised only)** - Allow use of the Podcasts app.
- **Music service (supervised only)** - Allow use of the Apple Music app.
- **iTunes Radio service (supervised only)** - Allow use of the iTunes Radio app.
- **Apple News (supervised only)** - Allow use of the Apple News app.
- **Configuration profile changes** - Allow the user to install configuration profiles.

## Password
- 	**Password required** - Require the end user to enter a password to access the device.
- 	**Simple passwords** - Allow simple passwords like 0000 and 1234.
- 	**Required password type** - Specify the type of password that will be required, such as numeric only or alphanumeric.
- 	**Number of non-alphanumeric characters in password** - Specify the number of symbol characters (like **#** or **@**) that must be included in the password.
- 	**Minimum password length** - Specify the minimum number of characters in the password.
- 	**Number of sign-in failures before wiping device** - Specify the number of failed login attempts before this setting wipes the device.
- 	**Maximum minutes after screen lock before password is required**<sup>1</sup> - Specify how long the device can remain idle before the user must re-enter their password.
- 	**Maximum minutes of inactivity until screen locks**<sup>1</sup> - Specify the number of minutes before the device display is turned off.
- 	**Password expiration (days)** - Specify the number of days before the device password must be changed.
- 	**Prevent reuse of previous passwords** - Specify the number of previously used passwords that the device remembers.
- 	**Fingerprint unlock** - Allow using a fingerprint to unlock compatible devices.

<sup>1</sup>When you configure the settings **Maximum minutes of inactivity until screen locks** and **Maximum minutes after screen lock before password is required**, they are applied in sequence. For example, if you set the value for both settings to **5** minutes, the screen will turn off automatically after 5 minutes, and the device will be locked after an additional 5 minutes. However, if the user turns off the screen manually, the second setting is immediately applied. In the same example, after the user turns off the screen, the device will lock 5 minutes later.

## App Store, Doc Viewing, Gaming


-   **App store (supervised only)** - Block access to the app store on supervised devices.
- 	**Password to access app store** - Require the user to enter a password before they can visit the app store.
- 	**In-app purchases** - Allow store purchases to be made from within a running app.
- 	**Automatic app downloads (supervised only)** -
- 	**Explicit iTunes music, podcast, or news content (supervised only)** - Allow the device to access content rated as adult from the store.
- 	**Download content from iBook store flagged as 'Erotica'** - Allow the user to download books with the "Erotica" category.
- 	**Viewing corporate documents in unmanaged apps** - Allow corporate documents to be viewed in any app.<br>**Example:** You want to prevent users from saving files from the OneDrive app to Dropbox. Configure this setting as no. After the device receives the policy (for example, after a restart), it will no longer allow saving.
- 	**Viewing non-corporate documents in corporate apps** - Allow any document to be viewed in corporate managed apps.
- 	**Treat AirDrop as an unmanaged destination** - Stops managed apps from being able to send data via. Airdrop.
- 	**Adding Game Center friends (supervised only)** - Allow the user to add friends in Game Center.
- 	**Game Center (supervised only)** - Block or enable the use of the Game Center app.
- 	**Multiplayer gaming (supervised only)** - Allow the user to play multiplayer games on the device.
- 	**Ratings region** - Choose the ratings region for which you want to configure allowed downloads, then choose the allowed ratings for **Movies** and **TV Shows**.
- 	**Apps** - Choose the allowed age rating of apps that users will be able to download, or you can choose **Allow All Apps**.

## Restricted apps

In the restricted apps list, you can configure one of the following lists:

A **Prohibited apps** list - List the apps (not managed by Intune) that users are not allowed to install and run.
An **Approved apps** list - List the apps that users are allowed to install. To remain compliant, users must not install apps that are not listed. Apps that are managed by Intune are automatically allowed.

To configure the list, click **Add**, then specify a name of your choice, optionally the app publisher, and the URL to the app in the app store.

### How to specify the URL to an app in the store

To specify an app URL in the apps list, use the following format:

Using a search engine, find the app that you want to use in the iTunes App Store and open the page for the app.
Copy the URL of the page and use this as the URL to configure the allowed or prohibited apps list or an app that you want to run in kiosk mode.
Device profiles that contain restricted app settings must be deployed to groups of users.

Example: Search for Microsoft Word for iPad. The URL that you use will be https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8.

> [!Note]
> You can also use the iTunes software to find the app and then use the **Copy Link** command to get the app URL.



### Additional options

You can also click **Import** to populate the list from a csv file in the format <*app url*>, <*app name*>, <*app publisher*> or click **Export** to create a csv file containing the contents of the restricted apps list in the same format.

## Show or hide apps

In the show or hide apps list, you can configure one of the following lists (requires supervised devices running iOS 9.3 or later).

A **Hidden apps** list - Specify a list of apps that will be hidden from users. Users cannot view, or launch these apps.
An **Visible apps** list - Specify a list of apps that users can view and launch. No other apps can be viewed or launched.

To configure the list, click **Add**, then specify a name of your choice, optionally the app publisher, and the URL to the app in the app store.

### How to specify the URL to an app in the store

To specify an app URL in the apps list, use the following format:

Using a search engine, find the app that you want to use in the iTunes App Store and open the page for the app.
Copy the URL of the page and use this as the URL to configure the allowed or prohibited apps list or an app that you want to run in kiosk mode.

Example: Search for Microsoft Word for iPad. The URL that you use will be https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8.

> [!Note]
> You can also use the iTunes software to find the app and then use the **Copy Link** command to get the app URL.

### Additional options

You can also click **Import** to populate the list from a csv file in the format <*app url*>, <*app name*>, <*app publisher*> or click **Export** to create a csv file containing the contents of the hidden or visible apps list in the same format.

### App information for built-in iOS apps
Use the information in this list to identify the name, publisher, and bundle ID of the built-in iOS apps that you might want to show or hide. If you want to show or hide all of the apps in the list, you can copy the data below into a text file with the extension **.csv**, then use the **Import** option to import all of the apps simultaneously.


    App Store,Apple,com.apple.AppStore
    Calculator,Apple,com.apple.calculator
    Calendar,Apple,com.apple.mobilecal
    Camera,Apple,com.apple.camera
    Clock,Apple,com.apple.mobiletimer
    Compass,Apple,com.apple.compass
    Contacts,Apple,com.apple.MobileAddressBook
    FaceTime,Apple,com.apple.facetime
    Find Friends,Apple,com.apple.mobileme.fmf1
    Find iPhone,Apple,com.apple.mobileme.fmip1
    Game Center,Apple,com.apple.gamecenter
    GarageBand,Apple,com.apple.mobilegarageband
    Health,Apple,com.apple.Health
    iBooks,Apple,com.apple.iBooks
    iTunes Store,Apple,com.apple.MobileStore
    iTunes U,Apple,com.apple.itunesu
    Keynote,Apple,com.apple.Keynote
    Mail,Apple,com.apple.mobilemail
    Maps,Apple,com.apple.Maps
    Messages,Apple,com.apple.MobileSMS
    Music,Apple,com.apple.Music
    News,Apple,com.apple.news
    Notes,Apple,com.apple.mobilenotes
    Numbers,Apple,com.apple.Numbers
    Pages,Apple,com.apple.Pages
    Photo Booth,Apple,com.apple.Photo-Booth
    Photos,Apple,com.apple.mobileslideshow
    Podcasts,Apple,com.apple.podcasts
    Reminders,Apple,com.apple.reminders
    Safari,Apple,com.apple.mobilesafari
    Settings,Apple,com.apple.Preferences
    Stocks,Apple,com.apple.stocks
    Tips,Apple,com.apple.tips
    Videos,Apple,com.apple.videos
    VoiceMemos,Apple,com.apple.VoiceMemos
    Wallet,Apple,com.apple.Passbook
    Watch,Apple,com.apple.Bridge
    Weather,Apple,com.apple.weather





## Cellular
- 	**Data roaming** - Allow data roaming when the device is on a cellular network.
- 	**Global background fetch while roaming** - Allow the device to fetch data such as email while it is roaming on a cellular network.
- 	**Voice dialing** - Allow use of the voice dialing feature on the device.
- 	**Voice roaming** - Allow voice roaming when the device is on a cellular network.
- 	**Changes to app cellular data usage settings (supervised only)** - Allow the user to control which apps are allowed to use cellular data.

## Cloud and Storage
- 	**Backup to iCloud** - Allow the user to back up the device to iCloud.
- 	**Document sync to iCloud (supervised only)** - Allow document and key-value synchronization to your iCloud storage space.
- 	**Photo stream syncing to iCloud** - Lets users enable **My Photo Stream** on their device which allow photos to sync to iCloud and be available on all the users devices.
- 	**Encrypted backup** - Require any device backups to be encrypted.
- 	**iCloud Photo Library** - If set to **No**, disables the use of iCloud photo library which lets users store photos and videos in the cloud.	Any photos not fully downloaded from iCloud Photo Library to the device will be removed from the device if this is set to **No**.
- 	**Managed apps sync to cloud** - Allow apps that you manage with Intune to sync data to the user's iCloud account.
- 	**Shared photo stream** - Set to **No** to disable **iCloud Photo Sharing** on the device..
- 	**Activity continuation** - Allow the user to continue work that they started on an iOS device on another iOS or macOS device (Handoff).

## Autonomous single app mode (supervised only)

Use these settings to configure iOS devices to run specified apps in autonomous single app mode. When this mode is configured, and the app is run, the device is locked so that it can only run that app. An example of this is when you configure an app that lets users take a test on the device. When the apps actions are complete, or you remove this policy, the device returns to its normal state.

### Settings

- **App name** - Enter the name of the app as it will appear in the apps list on this blade.
- **App Bundle ID** - Enter the bundle ID of the app. For help, see **Bundle ID reference for built-in iOS apps** in this topic.

After you specify each app name and bundle ID, choose **Add** to append it to the list.

- **Import** - Import a comma-separated values (.csv) file containing a list of app names, and their associated bundle IDs.
- **Export** - Export the app names, and associated bundle IDs you have configured to a comma-separated values (.csv) file.

### Bundle ID reference for built-in iOS apps

This list shows the bundle ID of some common built-in iOS apps. To find the bundle ID of other apps, contact your software vendor. 

|||
|-|-|
|App name|BundleID|
|App Store|com.apple.AppStore|
|Calculator|com.apple.calculator|
|Calendar|com.apple.mobilecal|
|Camera|com.apple.camera|
|Clock|com.apple.mobiletimer|
|Compass|com.apple.compass|
|Contacts|com.apple.MobileAddressBook|
|FaceTime|com.apple.facetime|
|Find Friends|com.apple.mobileme.fmf1|
|Find iPhone|com.apple.mobileme.fmip1|
|Game Center|com.apple.gamecenter|
|GarageBand|com.apple.mobilegarageband|
|Health|com.apple.Health|
|iBooks|com.apple.iBooks|
|iTunes Store|com.apple.MobileStore|
|iTunes U|com.apple.itunesu|
|Keynote|com.apple.Keynote|
|Mail|com.apple.mobilemail|
|Maps|com.apple.Maps|
|Messages|com.apple.MobileSMS|
|Music|com.apple.Music|
|News|com.apple.news|
|Notes|com.apple.mobilenotes|
|Numbers|com.apple.Numbers|
|Pages|com.apple.Pages|
|Photo Booth|com.apple.Photo-Booth|
|Photos|com.apple.mobileslideshow|
|Podcasts|com.apple.podcasts|
|Reminders|com.apple.reminders|
|Safari|com.apple.mobilesafari|
|Settings|com.apple.Preferences|
|Stocks|com.apple.stocks|
|Tips|com.apple.tips|
|Videos|com.apple.videos|
|VoiceMemos|com.apple.VoiceMemos|
|Wallet|com.apple.Passbook|
|Watch|com.apple.Bridge|
|Weather|com.apple.weather|


## Kiosk
- 	**Activation Lock** - Enable Activation Lock on supervised iOS devices.
- 	**App that runs in kiosk mode** - Choose **Managed App** to select an app you've added to Intune, or **Store App** to specify the URL to an app in the store. No other apps will be allowed to run on the device. For more help, see "How to specify URLs to app stores" later in this topic.
- 	**Assistive touch** - Enable or disable the **Assistive Touch** accessibility setting, which helps the user perform on-screen gestures that might be difficult for them to perform.
- 	**Invert colors** - Enable or disable the Invert Colors accessibility setting, which adjusts the display to help users with visual impairments.
- 	**Mono audio** - Enable or disable the accessibility setting Mono audio.
- 	**VoiceOver** - Enable or disable the accessibility setting **VoiceOver**, which reads aloud text on the device display.
- 	**Zoom** - Enable or disable the **Zoom** accessibility setting, which lets the user use touch to zoom in to the device display.
- 	**Auto lock** - Enable or disable automatic locking of the device.
- 	**Ringer switch** - Enable or disable the ringer (mute) switch on the device.
- 	**Screen rotation** - Enable or disable changing the screen orientation when the user rotates the device.
- 	**Screen sleep button** - Enable or disable the screen sleep wake button on the device.
- 	**Touch** - Enable or disable the touchscreen on the device.
- 	**Volume buttons** - Enable or disable the use of the volume buttons on the device.
- 	**Assistive touch control** - Enable or disable assistive touch adjustments, which let the user adjust the assistive touch function.
- 	**Invert colors control** - Enable or disable invert colors adjustments, which let the user adjust the invert colors function.
- 	**Speak on selected text** - Enable or disable the Speak Selection accessibility settings, which can read aloud the text that the user selects.
- 	**VoiceOver control** - Enable or disable voiceover adjustments, which let the user adjust the VoiceOver function (for example, how fast on-screen text is read aloud).
- 	**Zoom control** - Enable or disable zoom adjustments, which let the user adjust the zoom function.

>[!NOTE]
> Before you can configure an iOS device for kiosk mode, you must use the Apple Configurator tool or the Apple Device Enrollment Program to put the device into supervised mode. For more information about the Apple Configurator tool, see your Apple documentation.
>If the iOS app that you specify is installed after you deploy the configuration policy, the device will not enter kiosk mode until after it is restarted.

## Safari
- 	**Safari (supervised only)** - Specify whether the Safari browser can be used on the device.
- 	**Autofill** - Allow the user to change autocomplete settings in the browser.
- 	**Cookies** - Allow the browser to use cookies.
- 	**JavaScript** - Allow Java scripts to run in the browser.
- 	**Fraud warnings** - Allow fraud warnings in the browser.
- 	**Pop-ups** - Enable or disable the browser pop-up blocker.


## Domains

### Unmarked email domains

In the **Email Domain URL** field, add one or more URLs to the list. When end users receive an email from a domain other than those you configured, the email will be marked as untrusted in the iOS Mail app.


### Managed web domains

In the **Web Domain URL** field, add one or more URLs to the list. When documents are downloaded from the domains you specify, they will be considered managed. This setting applies only to documents downloaded using the Safari browser.


### Safari password auto fill domains

In the **Domain URL** field, add one or more URLs to the list. Users can only save web passwords from URLs in this list. This setting applies only to the Safari browser, and to iOS 9.3 and later devices in supervised mode. If you don't specify any URLs, then passwords can be saved from all web sites.
