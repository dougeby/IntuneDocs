---
# required metadata

title: Android app protection policy settings
titlesuffix: "Azure portal"
description: This topic describes the app protection policy settings for Android devices."
keywords:
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 06/06/2017
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
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Android app protection policy settings
The policy settings that are described in this topic can be [configured](app-protection-policies.md) for an app protection policy on the **Settings** blade in the Azure portal.
There are two categories of policy settings: data relocation settings and access settings. In this topic, the term *policy-managed apps* refers to apps that are configured with app protection policies.

##  Data relocation settings

| Setting | How to use | Default value(s) |
|------|------|------|
| **Prevent Android backups** | Choose **Yes** to prevent this app from backing up work or school data to the [Android Backup Service](https://developer.android.com/google/backup/index.html) Choose **No** to allow this app to back up work or school data.| Yes |
| **Allow app to transfer data to other apps** | Specify what apps can receive data from this app: <ul><li> **Policy managed apps**: Allow transfer only to other policy-managed apps.</li> <li>**All apps**: Allow transfer to any app. </li> <li>**None**: Do not allow data transfer to any app, including other policy-managed apps.</li></ul> <p>There are some exempts apps and services to which Intune may allow data transfer. See  [Data transfer exemptions](#Data-transfer-exemptions) for a full list of apps and services.| All apps |
| **Allow app to receive data from other apps** | Specify what apps can transfer data to this app: <ul><li>**Policy managed apps**: Allow transfer only from other policy-managed apps.</li><li>**All apps**: Allow data transfer from any app.</li><li>**None**: Do not allow data transfer from any app, including other policy-managed apps. </li></ul> <p>There are some exempts apps and services from which Intune may allow data transfer. See  [Data transfer exemptions](#Data-transfer-exemptions) for a full list of apps and services. | All apps |
| **Prevent "Save As"** | Choose **Yes** to disable the use of the Save As option in this app. Choose **No** if you want to allow the use of Save As. <p><br>**Select which storage services corporate data can be saved to** <br>Users are able to save to the selected services (OneDrive for Busines, SharePoint and Local Storage). All other services will be blocked.</p> | No <br><br> 0 selected |
| **Restrict cut, copy and paste with other apps** | Specify when cut, copy, and paste actions can be used with this app. Choose from: <ul><li>**Blocked**:  Do not allow cut, copy, and paste actions between this app and any other app.</li><li>**Policy managed apps**: Allow cut, copy, and paste actions between this app and other policy-managed apps.</li><li>**Policy managed with paste in**: Allow cut or copy between this app and other policy-managed apps. Allow data from any app to be pasted into this app.</li><li>**Any app**: No restrictions for cut, copy, and paste to and from this app. | Any app |
|**Restrict web content to display in the Managed Browser** | Choose **Yes** to enforce web links in the app to be opened in the Managed Browser app. <br><br> For devices not enrolled in Intune, the web links in policy-managed apps can open only in the Managed Browser app. <br><br> If you are using Intune to manage your devices, see [Manage Internet access using managed browser policies with Microsoft Intune](app-configuration-managed-browser.md). | No |
| **Encrypt app data** | Choose **Yes** to enable encryption of work or school data in this app. Intune uses an OpenSSL, 128-bit AES encryption scheme along with the Android Keystore system to securely encrypt app data. Data is encrypted synchronously during file I/O tasks. Content on the device storage is always encrypted. <br><br> The encryption method is **not** FIPS 140-2 certified.  | Yes |
| **Disable app encryption when device encryption is enabled** | Choose **Yes** to disable app encryption for internal app storage when device encryption is detected on an enrolled device. <br><br>**Note:** Intune can only detect device enrollment with Intune MDM. External app storage will still be encrypted to ensure data cannot be accessed by unmanaged applications. | Yes |
| **Disable contact sync** | Choose **Yes** to prevent the app from saving data to the native Contacts app on the device. If you choose **No**, the app can save data to the native Contacts app on the device. <br><br>When you perform a selective wipe to remove work or school data from the app, contacts synced directly from the app to the native Contacts app are removed. Any contacts synced from the native address book to another external source cannot be wiped. Currently this applies only to the Microsoft Outlook app. | No |
| **Disable printing** | Choose **Yes** to prevent the app from printing work or school data. | No |

  >[!NOTE]
  >The encryption method for the **Encrypt app data** setting is **not** FIPS 140-2 certified.


  ## Data transfer exemptions

  There are some exempt apps and platform services that Intune app protection policy may allow data transfer to and from. For example, all Intune-enlightened apps on Android must be able to transfer data to and from the Google Text-to-speech, so that text from your mobile device screen can be read aloud. This list is subject to change and reflects the services and apps considered useful for secure productivity.

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
  | com.azure.authenticator | Azure Authenticator app, which is required for successful authentication in many scenarios. |
  | com.microsoft.windowsintune.companyportal | Intune Company Portal|

  ### Conditional exemptions
  These apps and services are only allowed for data transfer to and from Intune-managed apps under certain conditions.

  |App/service name | Description | Exemption condition|
  | ------ | ---- | --- |
  | com.android.chrome | Google Chrome Browser | Chrome is used for some WebView components on Android 7.0+ and is never hidden from view. Data flow to and from the app, however, is always restricted.
  | com.skype.raider | Skype | The Skype app is allowed only for certain actions that result in a phone call. |
  | com.android.providers.media | Android media content provider | The media content provider allowed only for the ringtone selection action. |
  | com.google.android.gms; com.google.android.gsf | Google Play Services packages | These packages are allowed for Google Cloud Messaging actions, such as push notifications. |



##  Access settings

| Setting | How to use | Default value(s) |
|------|------|------|
| **Require PIN for access** | Choose **Yes** to require a PIN to use this app. The user is prompted to set up this PIN the first time they run the app in a work or school context. Default value = **Yes**.<br><br> Configure the following settings for PIN strength: <ul><li>**Number of attempts before PIN reset**: Specify the number of tries the user has to successfully enter their PIN before they must reset it. Default value = **5**.</li><li> **Allow simple PIN**: Choose **Yes** to allow users to use simple PIN sequences like 1234 or 1111. Choose **No** to prevent them from using simple sequences. Default value = **Yes**. </li><li> **PIN length**: Specify the minimum number of digits in a PIN sequence. Default value = **4**. </li><li> **Allow fingerprint instead of PIN (Android 6.0+)**: Choose **Yes** to allow the user to use [fingerprint authentication](https://developer.android.com/about/versions/marshmallow/android-6.0.html#fingerprint-authentication) instead of a PIN for app access. Default value = **Yes**.</li></ul> On Android devices, you can let the user prove their identity by using [Android fingerprint authentication](https://developer.android.com/about/versions/marshmallow/android-6.0.html#fingerprint-authentication) instead of a PIN. When the user tries use this app with their work or school account, they are prompted to provide their fingerprint identity instead of entering a PIN. </li></ul>| Require PIN: Yes <br><br> PIN reset attempts: 5 <br><br> Allow simple PIN: Yes <br><br> PIN length: 4 <br><br> Allow fingerprint: Yes |
| **Require corporate credentials for access** | Choose **Yes** to require the user to sign in with their work or school account instead of entering a PIN for app access. If you set this to **Yes**, this overrides the requirements for PIN or Touch ID.  | No |
| **Block managed apps from running on jailbroken or rooted devices** |Choose **Yes** to prevent this app from running on jailbroken or rooted devices. The user will continue to be able to use this app for personal tasks, but will have to use a different device to access work or school data in this app. | Yes |
| **Recheck the access requirements after (minutes)** | Configure the following settings: <ul><li>**Timeout**: This is the number of minutes before the access requirements (defined earlier in the policy) are rechecked. For example, an admin turns on PIN in the policy, a user opens a MAM app, and must enter a pin. When using this setting, the user would not have to enter a PIN on any MAM app for another **30 minutes** (default value).</li><li>**Offline grace period**: This is the number of minutes that MAM apps can run offline, specify the time (in minutes) before the access requirements for the app are rechecked. Default value = **720** minutes (12 hours). After this period is expired, the app will require user authentication to AAD, so the app can continue to run.</li></ul>| Timeout: 30 <br><br> Offline: 720 |
| **Offline interval before app data is wiped (days)** | After this many days (defined by the admin) of running offline, the app will require the user to connect to the network and reauthenticate. If the user successfully authenticates, they can continue to access their data and the offline interval will reset.  If the user fails to authenticate, the app will perform a selective wipe of the users account and data.  See [How to wipe only corporate data from Intune-managed apps](https://docs.microsoft.com/en-us/intune/apps-selective-wipe) for more information on what data is removed with a selective wipe.<br><br> | 90 days |
| **Block screen capture and Android Assistant (Android 6.0+)** | Choose **Yes** to block screen capture and the **Android Assistant** capabilities of the device when using this app. Choosing **Yes** will also blur the App-switcher preview image when using this app with a work or school account. | No |
| **Disable app PIN when device PIN is managed** | Choose **Yes** to disable the app PIN when a device lock is detected on an enrolled device. | No |
