---
# required metadata

title: Android app protection policy settings
titlesuffix: Microsoft Intune
description: This topic describes the app protection policy settings for Android devices.
keywords:
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/09/2019
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 9e9ef9f5-1215-4df1-b690-6b21a5a631f8

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: andcerat
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure
---
# Android app protection policy settings in Microsoft Intune
This article describes the app protection policy settings for Android devices. The policy settings that are described can be [configured](app-protection-policies.md) for an app protection policy on the **Settings** blade in the Azure portal.
There are two categories of policy settings: data protection settings and access settings. In this article, the term *policy-managed apps* refers to apps that are configured with app protection policies.

##  Data protection 

### Data Transfer
| Setting | How to use | Default value |
|------|------|------|
| **Backup Org data to Android backup services** | Select **Block** to prevent this app from backing up work or school data to the [Android Backup Service](https://developer.android.com/google/backup/index.html).<br><br> Select **Allow** to allow this app to back up work or school data.| **Allow** |
| **Send Org data to other apps** | Specify what apps can receive data from this app: <ul><li> **Policy managed apps**: Allow transfer only to other policy-managed apps.</li> <li>**All apps**: Allow transfer to any app. </li> <li>**None**: Do not allow data transfer to any app, including other policy-managed apps.</li></ul> <p>There are some exempt apps and services to which Intune may allow data transfer by default. In addition, you can create your own exemptions if you need to allow data to transfer to an app that doesn't support Intune APP. For more information, see [Data transfer exemptions](#Data-transfer-exemptions).<p>This policy may also apply to Android App Links.  General web links are managed by the **Open app links in Intune Managed Browser** policy setting.<p>**Note:** *Intune doesn't currently support the Android Instant Apps feature. Intune will block any data connection to or from the app. For more information, see [Android Instant Apps](https://developer.android.com/topic/instant-apps/index.html) in the Android Developer documentation.*</p>| **All apps** | 
|<ul><ui> **Select apps to exempt** | This option is available when you select *Policy managed apps* for the previous option. | |
| **Receive data from other apps** | Specify what apps can transfer data to this app: <ul><li>**Policy managed apps**: Allow transfer only from other policy-managed apps.</li><li>**All apps**: Allow data transfer from any app.</li><li>**None**: Do not allow data transfer from any app, including other policy-managed apps. </li></ul> <p>There are some exempts apps and services from which Intune may allow data transfer. See  [Data transfer exemptions](#Data-transfer-exemptions) for a full list of apps and services. | **All apps** |
| **Save copies of Org data** | Choose **Block** to disable the use of the Save As option in this app. Choose **Allow** if you want to allow the use of Save As. **Note:** *This setting is supported for Microsoft Excel, OneNote, PowerPoint, and Word. It may also be supported by third-party and LOB apps.*| **Allow** |  
|<ul><ui> **Allow user to save copies to selected services** |Users can save to the selected services (OneDrive for Business, SharePoint, and Local Storage). All other services will be blocked.  | **0 selected** |
| **App cannot use cut, copy, and paste actions with selected apps** | Specify when cut, copy, and paste actions can be used with this app. Choose from: <ul><li>**Blocked**:  Do not allow cut, copy, and paste actions between this app and any other app.</li><li>**Policy managed apps**: Allow cut, copy, and paste actions between this app and other policy-managed apps.</li><li>**Policy managed with paste in**: Allow cut or copy between this app and other policy-managed apps. Allow data from any app to be pasted into this app.</li><li>**Any app**: No restrictions for cut, copy, and paste to and from this app. | **Any app** |
| **Screen capture and Google Assistant** | Select **Disable** to block screen capture and the **Android Assistant** capabilities of the device when using this app. Choosing **Disable** will also blur the App-switcher preview image when using this app with a work or school account.| **Enable** |
  
### Encryption
| Setting | How to use | Default value |
|------|------|------|
| **Encrypt Org data** | Choose **Require** to enable encryption of work or school data in this app. Intune uses an OpenSSL, 256-bit AES encryption scheme along with the Android Keystore system to securely encrypt app data. Data is encrypted synchronously during file I/O tasks. Content on the device storage is always encrypted. The SDK will continue to provide support of 128-bit keys for compatibility with content and apps that use older SDK versions. <br><br> The encryption method is **not** FIPS 140-2 certified.     |  **Require**|
|<ul><ui> **Disable app encryption when device encryption is enabled**  |Choose **Yes** to disable app encryption for internal app storage when device encryption is detected on an enrolled device. <br><br>**Note:** *Intune can only detect device enrollment with Intune MDM. External app storage will still be encrypted to ensure data cannot be accessed by unmanaged applications.* | **Not required** |  



### Functionality
| Setting | How to use | Default value |
|------|------|------|
| **Sync app with native contacts app** | Choose **Disable** to prevent the app from saving data to the native Contacts app on the device. If you choose **Enable**, the app can save data to the native Contacts app on the device. <br><br>When you perform a selective wipe to remove work, or school data from the app, contacts synced directly from the app to the native Contacts app are removed. Any contacts synced from the native address book to another external source can't be wiped. Currently this applies only to the Microsoft Outlook app. | **Enable** |
| **Printing** | Choose **Disable** to prevent the app from printing work or school data. | **Enable** |
|**Open app links in Intune Managed Browser** | Specify how web content (http/https links) are opened from policy-managed applications. Choose from:<ul><li>**Require**: Allow web content to open only in policy-managed browsers.</li><li>**Not configured**: Allow web links in any app </li></ul><br><br> If you're using Intune to manage your devices, see [Manage Internet access using managed browser policies with Microsoft Intune](app-configuration-managed-browser.md).<br><br>**Policy-managed browsers**<br>If you deploy multiple policy-managed browsers, only one will be launched.  The launch order will be Intune Managed Browser and then Microsoft Edge.  On Android, your end users can choose from other policy-managed apps that support http/https links if neither Intune Managed Browser nor Microsoft Edge are installed.<p>If a policy-managed browser is required but not installed, your end users will be prompted to install the Intune Managed Browser.<p>If a policy-managed browser is required, Android App Links are managed by the **Allow app to transfer data to other apps** policy setting.<p>**Intune device enrollment**<br>If you are using Intune to manage your devices, see Manage Internet access using managed browser policies with Microsoft Intune. <p>**Policy-managed Microsoft Edge**<br>The Microsoft Edge browser for mobile devices (iOS and Android) supports Intune app protection policies. Users who sign in with their corporate Azure AD accounts in the Microsoft Edge browser application will be protected by Intune. The Microsoft Edge browser integrates the MAM SDK and supports all of its data protection policies, with the exception of preventing:<br><ul><li>**Save-as**: The Microsoft Edge browser does not allow a user to add direct, in-app connections to cloud storage providers (such as OneDrive).</li><li>**Contact sync**: The Microsoft Edge browser does not save to native contact lists.</li></ul><br>**Note:** *The APP SDK cannot determine if a target app is a browser. On Android devices, other managed browser apps that support the http/https intent are allowed.* | **Not configured** |



  ## Data transfer exemptions
  There are some exempt apps and platform services that Intune app protection policy may allow data transfer to and from. For example, all Intune-managed apps on Android must be able to transfer data to and from the Google Text-to-speech, so that text from your mobile device screen can be read aloud. This list is subject to change and reflects the services and apps considered useful for secure productivity.

  ### Full exemptions
  These apps and services are fully allowed for data transfer to and from Intune-managed apps.

  |App/service name | Description |
  | ------ | ---- |
  | com.android.phone | Native phone app
  | com.android.vending | Google Play Store |
  | com.android.documentsui | Android Document Picker|
  | com.google.android.webview | [WebView](https://developer.android.com/reference/android/webkit/WebView.html), which is necessary for many apps including Outlook. |
  | com.android.webview |[Webview](https://developer.android.com/reference/android/webkit/WebView.html), which is necessary for many apps including Outlook.|
  | com.google.android.tts | Google Text-to-speech |
  | com.android.providers.settings | Android system settings |
  | com.android.settings | Android system settings |
  | com.azure.authenticator | Azure Authenticator app, which is required for successful authentication in many scenarios. |
  | com.microsoft.windowsintune.companyportal | Intune Company Portal|

  ### Conditional exemptions
  These apps and services are only allowed for data transfer to and from Intune-managed apps under certain conditions.

  |App/service name | Description | Exemption condition|
  | ------ | ---- | --- |
  | com.android.chrome | Google Chrome Browser | Chrome is used for some WebView components on Android 7.0+ and is never hidden from view. Data flow to and from the app, however, is always restricted.  |
  | com.skype.raider | Skype | The Skype app is allowed only for certain actions that result in a phone call. |
  | com.android.providers.media | Android media content provider | The media content provider allowed only for the ringtone selection action. |
  | com.google.android.gms; com.google.android.gsf | Google Play Services packages | These packages are allowed for Google Cloud Messaging actions, such as push notifications. |

For more information, see [Data transfer policy exceptions for apps](app-protection-policies-exception.md).

##  Access requirements
| Setting | How to use | Default value |
|------|------|------|
| **PIN for access** | Select **Require** to require a PIN to use this app. The user is prompted to set up this PIN the first time they run the app in a work or school context. <br><br> Configure the following settings for PIN strength:| **Require** |
|<ul><ui> **PIN Type** | Set a requirement for either numeric or passcode type PINs before accessing an app that has app protection policies applied. Numeric requirements involve only numbers, while a passcode can be defined with at least 1 alphabetical letter **or** at least 1 special character. <br><br>**Note:** *Special characters allowed include the special characters and symbols on the Android English language keyboard.*| **Numeric** |
|<ul><ui>  **Simple PIN** |Select **Allow** to allow users to use simple PIN sequences like *1234*, *1111*, *abcd* or *aaaa*. Select **Block** to prevent them from using simple sequences. <br><br>**Note:** *If PIN Type is set to Passcode, and Simple PIN is set to Allow, the user needs at least one letter **or** at least one special character in their PIN. If PIN Type is set to Passcode and Simple PIN is set to Block, the user needs at least one number **and** one letter **and** at least one special character in their PIN.* | **Allow** |
| <ul><ui> **Select minimum PIN length** | Specify the minimum number of digits in a PIN sequence.  | **4** |
|<ul><ui> **Fingerprint instead of PIN for access (Android 6.0+)** | Select **Allow** to allow the user to use [fingerprint authentication](https://developer.android.com/about/versions/marshmallow/android-6.0.html#fingerprint-authentication) instead of a PIN for app access. <br><br>**Note:** *This feature supports generic controls for biometric on Android devices. OEM-specific biometric settings, like *Samsung Pass*, are not supported.* <br><br>On Android, you can let the user prove their identity by using [Android fingerprint authentication](https://developer.android.com/about/versions/marshmallow/android-6.0.html#fingerprint-authentication) instead of a PIN. When the user tries to use this app with their work or school account, they are prompted to provide their fingerprint identity instead of entering a PIN. <br><br> Android work profiles require registering a separate fingerprint for the **Allow fingerprint instead of PIN** policy to be enforced. This policy takes effect only for policy-managed apps installed in the Android work profile. The separate fingerprint must be registered with the device after the Android work profile is created by enrolling in the Company Portal. For more information about work profile fingerprints using Android work profiles, see [Lock your work profile](https://support.google.com/work/android/answer/7029958). |**Allow** |
| <ul><ul><ui>**Override fingerprint with PIN after timeout** |  When set to **Require**, a PIN prompt will override Touch ID prompts after the app has been idle for the *Timeout* period you specify.   | **Require** |
| <ul><ul><ui>**Timeout (minutes of inactivity)** | Specify in minutes how long the app can be idle before the Touch ID prompts are replaced by PIN prompts.  <br><br>This timeout value should be greater than the value specified under *Recheck the access requirements after (minutes of inactivity)*.| **30** |
|<ul><ui> **PIN reset after number of days** | Select **Yes** to require users to change their app PIN after a set period of time, in days. <br><br> Default value = **No** <br><br> When set to *Yes*, you can then configure the number of days before the reset is required. | **No**|
| <ul><ul><ui>**Number of days** | When *PIN reset after number of days* is set to Yes, specify how long before the PIN reset is required. | **30** | 
|<ul><ui> **App PIN when device PIN is set** | If set to **Disable**, an app PIN isn't needed on an MDM enrolled device that has a device PIN set.   | **Enable** |
| **Work or school account credentials for access** | Choose **Require** to require the user to sign in with their work or school account instead of entering a PIN for app access. When set to **Require**, and PIN or biometric prompts are turned on, both corporate credentials and either the PIN or biometric prompts are shown. | **Not required** |
| **Recheck the access requirements after (minutes of inactivity)** | Configure the number of minutes of inactivity that must pass before the app requires the user to again specify the access requirements.  <br><br>**Note:** *On Android, the PIN is shared with all Intune-managed apps. The PIN timer is reset once the app leaves the foreground on the device. The user won't have to enter a PIN on any Intune-managed app that shares its PIN for the duration of the timeout defined in this setting.*| **30** |

> [!NOTE]  
> To learn more about how multiple Intune app protection settings configured in the Access section to the same set of apps and users work on Android, see [Intune MAM frequently asked questions](mam-faq.md) and [Selectively wipe data using app protection policy access actions in Intune](app-protection-policies-access-actions.md).


## Conditional launch
Configure conditional launch settings to set sign-in security requirements for your access protection policy. 

By default, several settings are provided with pre-configured values and actions. You can delete some of settings, like the *Min OS version*. You can also select additional settings from the **Select one** dropdown. 

| Setting | How to use |  
|---------|------------| 
| **Max PIN attempts** | Specify the number of tries the user has to successfully enter their PIN before the configured action is taken. This policy setting format supports a positive whole number. *Actions* include: <br><ul><li>**Reset PIN** - The user must reset their PIN.</li></ul> <ul><li>**Wipe data** - The user account that is associated with the application is wiped from the device.  </li></ul> </li></ul> Default value = **5** |
| **Offline grace period** | The number of minutes that MAM apps can run offline. Specify the time (in minutes) before the access requirements for the app are rechecked. *Actions* include: <br><ul><li>**Block access (minutes)** - The number of minutes that MAM apps can run offline. Specify the time (in minutes) before the access requirements for the app are rechecked. After this period expires, the app requires user authentication to Azure Active Directory (Azure AD) so that the app can continue to run. <br><br>This policy setting format supports a positive whole number. <br><br>Default value = **720** minutes (12 hours) </li></ul> <ul><li>**Wipe data (days)** - After this many days (defined by the admin) of running offline, the app will require the user to connect to the network and reauthenticate. If the user successfully authenticates, they can continue to access their data and the offline interval will reset.  If the user fails to authenticate, the app will perform a selective wipe of the users' account and data. For more information, see [How to wipe only corporate data from Intune-managed apps](https://docs.microsoft.com/intune/apps-selective-wipe). <br><br> This policy setting format supports a positive whole number. <br><br>  Default value = **90 days** </li></ul>  This entry can appear multiple times, with each instance supporting a different action. |   
| **Jailbroken/rooted devices** |There is no value to set for this setting. *Actions* include: <br><ul><li>**Block access** - Prevent this app from running on jailbroken or rooted devices. The user continues to be able to use this app for personal tasks, but will have to use a different device to access work or school data in this app.</li></ul> <ul><li>**Wipe data** - The user account that is associated with the application is wiped from the device.  </li></ul> |
| **Min OS version** | Specify a minimum Android operating system that is required to use this app.. *Actions* include: <br><ul><li>**Warn** - The user will see a notification if the Android version on the device doesn't meet the requirement. This notification can be dismissed.  </li></ul> <ul><li>**Block access** - The user will be blocked from access if the Android version on the device doesn't meet this requirement.</li></ul> <ul><li>**Wipe data** - The user account that is associated with the application is wiped from the device.  </li></ul> </li></ul>This policy setting format supports either major.minor, major.minor.build, major.minor.build.revision. |
| **Min app version** | Specify a value for the minimum operating system value. *Actions* include: <br><ul><li>**Warn** - The user sees a notification if the app version on the device doesn't meet the requirement. This notification can be dismissed.</li></ul> <ul><li>**Block access** - The user is blocked from access if the app version on the device does not meet the requirement. </li></ul> <ul><li>**Wipe data** - The user account that is associated with the application is wiped from the device. </li></ul> </li></ul> As apps often have distinct versioning schemes between them, create a policy with one minimum app version targeting one app (for example, *Outlook version policy*).<br><br> This entry can appear multiple times, with each instance supporting a different action.<br><br> This policy setting format supports either major.minor, major.minor.build, major.minor.build.revision.|
| **Min patch version** | Require devices have a minimum Android security patch released by Google.  <br><ul><li>**Warn** - The user will see a notification if the Android version on the device doesn't meet the requirement. This notification can be dismissed.  </li></ul> <ul><li>**Block access** - The user will be blocked from access if the Android version on the device doesn't meet this requirement.</li></ul> <ul><li>**Wipe data** - The user account that is associated with the application is wiped from the device.  </li></ul></li></ul> This policy setting supports the date format of *YYYY-MM-DD*. |
| **Device manufacturer(s)** | Specify a device manufacturer that is required to use this app. *Actions* include: <br><ul><li>**Allow specified (Block non-specified)** - Only devices that match the specified manufacturer can use the app. All other devices are blocked. </li></ul> <ul><li>**Allow specified (Wipe non-specified)** - The user account that is associated with the application is wiped from the device. </li></ul> |
