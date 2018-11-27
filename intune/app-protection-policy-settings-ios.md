---
# required metadata

title: iOS app protection policy settings
titlesuffix: Microsoft Intune
description: This topic describes the app protection policy settings for iOS devices.
keywords:
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/28/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 0f8b08f2-504c-4b38-bea2-b8a4ef0526b8

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

#  iOS app protection policy settings
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

The policy settings described in this article can be [configured](app-protection-policies.md) for an app protection policy on the **Add a Policy** > **Settings** blade in the Azure portal.

There are three categories of policy settings: *Data relocation*, *Access requirements*, and *Conditional launch*. In this article, the term ***policy-managed apps*** refers to apps that are configured with app protection policies.

##  Data protection settings

| Setting | How to use |  
|------|------| 
| **Prevent iTunes and iCloud backups** | Select **Yes** to prevent this app from backing up work or school data to iTunes and iCloud. Select **No** to allow this app to back up of work or school data to iTunes and iCloud. <br><br> Default value = **Yes** |
| **Allow app to transfer data to other apps** | Specify what apps can receive data from this app: <ul><li>**None**: Do not allow data transfer to any app, including other policy-managed apps.</li><li> **Policy managed apps**: Allow transfer only to other policy-managed apps.</li><li>**Policy managed apps with OS sharing**: Only allow data transfer to other policy managed apps, as well as file transfers to other MDM managed apps on enrolled devices.<p><p>**Note:** *The **Policy managed apps with OS sharing** value is applicable to MDM enrolled devices only. If this setting is targeted to a user on an unenrolled device, the behavior of the **Policy managed apps** value applies.*<p><p></li><li>**Policy managed apps with Open-In/Share filtering**: Allow transfer only to other policy managed apps and filter OS Open-in/Share dialogs to only display policy managed apps.<p><p>**Note:** *To configure the filtering of the **Open-In/Share** dialog, it requires both the app(s) acting as the file/document source and the app(s) that can open this file/document to have Intune SDK for iOS version 8.1.1 or above.*<p><p></li><li>**All apps**: Allow transfer to any app.</li></ul><br>In addition, when set to **Policy managed apps** or **None**, the iOS 9 feature that allows Spotlight Search to search data within apps will be blocked. <p><p>This policy may also apply to iOS Universal Links.  General web links are managed by the **Restrict web content transfer with other apps** policy setting. <p> There are some exempt apps and services to which Intune may allow data transfer by default. In addition, you can create your own exemptions if you need to allow data to transfer to an app that doesn't support Intune APP. See [data transfer exemptions](#data-transfer-exemptions) for more information. <br><br> Default value = **All apps** |
| **Allow app to receive data from other apps** | Specify what apps can transfer data to this app: <ul><li>**None**: Do not allow data transfer from any app, including other policy-managed apps.</li><li>**Policy managed apps**: Allow transfer only from other policy-managed apps.</li><li>**All apps**: Allow data transfer from any app.</li><li>**All apps with incoming Org data**: Allow data transfer from any app. Treat all incoming data without a user identity as data from your organization. The data will be marked with the MDM enrolled user's identity as defined by the `IntuneMAMUPN` setting.<p><p>**Note:** *The **All apps with incoming Org data** value is applicable to MDM enrolled devices only. If this setting is targeted to a user on an unenrolled device, the behavior of the **Any apps** value applies.*</li></ul> There are some exempt apps and services from which Intune may allow data transfer. See [data transfer exemptions](#data-transfer-exemptions) for a full list of apps and services. Multi-identity MAM enabled applications on non-enrolled iOS devices ignore this policy and allow all incoming data.<br><br> Default value = **All apps**|
| **Prevent "Save As"** | Select **Yes** to disable the use of the *Save As* option in this app. Select **No** if you want to allow the use of *Save As*. <br><br> Default value = **No** <br><br>***Note:** This setting is supported for Microsoft Excel, OneNote, Outlook, PowerPoint, and Word. It can also be supported by third-party and LOB apps.* <br><br> When set to *Yes*, you can configure the following setting: <ul><li>**Select which storage services corporate data can be saved to**: Users can save to the selected services (OneDrive for Business, SharePoint, and Local Storage). All other services are blocked. <br><br> Default value = **0 selected** |
| **Restrict cut, copy, and paste with other apps** | Specify when cut, copy, and paste actions can be used with this app. Select from: <ul><li>**Blocked**:  Don't allow cut, copy, and paste actions between this app and any other app.</li><li>**Policy managed apps**: Allow cut, copy, and paste actions between this app and other policy-managed apps.</li><li>**Policy managed with paste in**: Allow cut or copy between this app and other policy-managed apps. Allow data from any app to be pasted into this app.</li><li>**Any app**: No restrictions for cut, copy, and paste to and from this app.</ul><br> Default value = **Any app** |
|**Restrict web content transfer with other apps** | Specify how web content (http/https links) are opened from policy-managed applications. Choose from: <ul><li>**Policy managed browsers**: Allow web content to open only in policy-managed browsers.</li><li>**Any app**: Allow web links in any app </li></ul><br><br> If you're using Intune to manage your devices, see [Manage Internet access using managed browser policies with Microsoft Intune](app-configuration-managed-browser.md).<br><br>**Policy-managed browsers**<br>If you deploy multiple policy-managed browsers, only one will be launched.  The launch order will be Intune Managed Browser and then Microsoft Edge.<p>If a policy-managed browser is required but not installed, your end users will be prompted to install the Intune Managed Browser.<p>If a policy-managed browser is required, iOS Universal Links are managed by the **Allow app to transfer data to other apps** policy setting. <p>**Intune device enrollment**<br>If you are using Intune to manage your devices, see Manage Internet access using managed browser policies with Microsoft Intune. <p>**Policy-managed Microsoft Edge**<br>The Microsoft Edge browser for mobile devices (iOS and Android) supports Intune app protection policies. Users who sign in with their corporate Azure AD accounts in the Microsoft Edge browser application will be protected by Intune. The Microsoft Edge browser integrates the MAM SDK and supports all of its data protection policies, with the exception of preventing:<br><ul><li>**Save-as**: The Microsoft Edge browser does not allow a user to add direct, in-app connections to cloud storage providers (such as OneDrive).</li><li>**Contact sync**: The Microsoft Edge browser does not save to native contact lists.</li></ul><br>**Note**:<br>The APP SDK cannot determine if a target app is a browser. On iOS devices, no other managed browser apps are allowed. <br><br>Default value = **Any app** |
| **Encrypt app data** | For policy-managed apps, data is encrypted at rest using the device-level encryption scheme provided by iOS. When a PIN is required, the data is encrypted according to the settings in the app protection policy. <br><br> Go to the [official Apple documentation](https://support.apple.com/HT202739) to see which iOS encryption modules are FIPS 140-2 certified or pending FIPS 140-2 certification. <br><br> Specify when work or school data in this app is encrypted. Select from: <ul><li>**Yes**: All app data that is associated with this policy is encrypted while the device is locked and protected by app layer encryption from Intune. When you enable this setting, the user may be required to set up and use a PIN to access their device.  If there's no device PIN and encryption is required, the apps won't open and the user is prompted to set a PIN with the message *Your organization has required you to first enable a device PIN to access this app.</li><li>**No**: Intune won't enforce encryption.</li></ul> Default value = **Yes**|
| **Disable contacts sync** | Select **Yes** to prevent the app from saving data to the native Contacts app on the device. If you Select **No**, the app can save data to the native Contacts app on the device. <br><br>When you perform a selective wipe to remove work, or school data from the app, contacts synced directly from the app to the native Contacts app are removed. Any contacts synced from the native address book to another external source can't be wiped. Currently this applies only to the Microsoft Outlook app.  <br><br>Default value = **No** |
| **Disable printing** | Select **Yes** to prevent the app from printing work or school data. <br><br>Default value = **No** |
| **Block third party keyboards** | Select **Yes** to prevent the use of third-party keyboards in managed applications. <br><br>When this setting is enabled, the user receives a one-time message stating that the use of third-party keyboards is blocked. This message appears the first time a user interacts with organizational data that requires the use of a keyboard. Only the standard iOS keyboard is available while using managed applications, and all other keyboard options are disabled. This setting doesn't affect the use of third-party keyboards in unmanaged applications.  <br><br>Default value = **No** |


> [!NOTE]
> None of the data protection settings control the Apple managed open-in feature on iOS devices. To use manage Apple open-in, see [Manage data transfer between iOS apps with Microsoft Intune](data-transfer-between-apps-manage-ios.md).

## Data transfer exemptions

There are some exempt apps and platform services that Intune app protection policy may allow data transfer to and from in certain scenarios. This list is subject to change and reflects the services and apps considered useful for secure productivity.

| App/service name(s) | Description |
| ---- | --- |
|<code>tel; telprompt</code> | Native phone app |
| <code>skype</code> | Skype |
| <code>app-settings</code> | Device settings |
| <code>itms; itmss; itms-apps; itms-appss; itms-services</code> | App Store |
| <code>calshow</code> | Native Calendar |


## Access settings

| Setting | How to use |  
|------|------| 
| **Require PIN for access** | Select **Yes** to require a PIN to use this app. The user is prompted to set up this PIN the first time they run the app in a work or school context. The PIN is applied when working either online or offline.  <br><br> Default value = **Yes**. <br><br> Configure the following settings for PIN strength: <br><br> <ul><li>**Select Type**: Set a requirement for either numeric or passcode type PINs before accessing an app that has app protection policies applied. Numeric requirements involve only numbers, while a passcode can be defined with at least 1 alphabetical letter **or** at least 1 special character.  <br><br> ***Note:** To configure passcode type, it requires app to have Intune SDK version 7.1.12 or above. Numeric type has no Intune SDK version restriction. Special characters allowed include the special characters and symbols on the iOS English language keyboard.*  <br><br> Default value = **Numeric**.  </li></ul> <br> <ul><li>**Allow Simple PIN**: Select **Yes** to allow users to use simple PIN sequences like 1234, 1111, abcd or aaaa. Select **No** to prevent them from using simple sequences. <br><br>**Note**: *If Passcode type PIN is configured, and Allow simple PIN is set to Yes, the user needs at least 1 letter **or** at least 1 special character in their PIN. If Passcode type PIN is configured, and Allow simple PIN is set to No, the user needs at least 1 number **and** 1 letter **and** at least 1 special character in their PIN.*  <br><br> Default value = **Yes**.  </li></ul> <br> <ul><li>**PIN Length**: Specify the minimum number of digits in a PIN sequence. <br><br>Default value = **4**.</li></ul> </li></ul> <br> <ul><li>**Allow fingerprint instead of PIN (iOS 8.0+)**: Select **Yes** to allow the user to use [Touch ID](https://support.apple.com/HT201371) instead of a PIN for app access.  <br><br> Default value = **Yes**. <br><br><ul><li>**Override with PIN instead of biometric after (minutes)**: To use this setting, select **Yes** and then configure an inactivity timeout. <br><br>Default value = **No** </li></ul> <br> <ul><li>**Inactivity timeout**: Specify a time in minutes after which the PIN will override the use of a fingerprint. </li></ul></li></ul> <br> <ul><li> **Allow facial recognition instead of PIN (iOS 11+)**: Select **Yes** to allow the user to use [Facell ID](https://support.apple.com/HT208109) instead of a PIN for app access.     <br><br>***Note:** To configure facial recognition, it requires app to have Intune SDK version 7.1.19 or above.* <br><br>Default value = **Yes**. Users are prompted to provide face identification when they access the app with their work accounts.</li></ul>  </li></ul> <br> <ul><li>**Disable app PIN when device PIN is managed**: Select **Yes** to disable the app PIN when a device lock is detected on an enrolled device with Company Portal configured.<br><br> ***Note:** Requires app to have Intune SDK version 7.0.1 or above.*  <br><br> Default value = **No**. </li></ul> <br> On iOS devices, you can let the user prove their identity by using [Touch ID](https://support.apple.com/HT201371) or [Face ID](https://support.apple.com/HT208109) instead of a PIN. Intune uses the [LocalAuthentication](https://developer.apple.com/documentation/localauthentication/) API to authenticate users using Touch ID and Face ID. To learn more about Touch ID and Face ID, see the [iOS Security Guide](https://www.apple.com/business/docs/iOS_Security_Guide.pdf).  <br><br> When the user tries use this app with their work or school account, they're prompted to provide their fingerprint identity or face identity instead of entering a PIN. When this setting is enabled, the App-switcher preview image will be blurred while using a work or school account.  |  
| **Require corporate credentials for access** | Select **Yes** to require the user to sign in with their work or school account instead of entering a PIN for app access. If you set this to **Yes**, and PIN or biometric prompts are turned on, both corporate credentials and either the PIN or biometric prompts are shown. <br><br> Default value = **No** |
| **Recheck the access requirements after (minutes)** | Configure the following settings: <br><br><ul><li>**Timeout**: The number of minutes before the access requirements (defined earlier in the policy) are rechecked. For example, an admin turns on PIN and Blocks rooted devices in the policy, a user opens an Intune-managed app, must enter a PIN, and must be using the app on a non-rooted device. When using this setting, the user would not have to enter a PIN or undergo another root-detection check on any Intune-managed app for a period of time equal to the configured value.  <br><br> Default value = **30 minutes**  <br><br>***Note:** On iOS, the PIN is shared amongst all Intune-managed apps of the **same publisher**. The PIN timer for a specific PIN is reset once the app leaves the foreground on the device. The user wouldn't have to enter a PIN on any Intune-managed app that shares its PIN for the duration of the timeout defined in this setting. This policy setting format supports a positive whole number.*    <br><br></li>
> [!NOTE]
> To learn more about how multiple Intune app protection settings configured in the Access section to the same set of apps and users work on iOS, see [Intune MAM frequently asked questions](https://docs.microsoft.com/intune/mam-faq#app-experience-on-ios) and [Selectively wipe data using app protection policy access actions in Intune](app-protection-policies-access-actions.md).

## Conditional launch
Configure conditional launch settings to set sign-in security requirements for your access protection policy. 

By default, several settings are provided with pre-configured values and actions. You can delete some of these, like the *Min OS version*. You can also select additional settings from the **Select one** dropdown. 

| Setting | How to use |  
|---------|------------| 
| **Min OS version** | Specify a minimum iOS operating system to use this app.. *Actions* include: <br><ul><li>**Warn** - The user will see a notification if the iOS version on the device doesn't meet the requirement. This notification can be dismissed. <br><br> </li></ul> <ul><li>**Block access** - The user will be blocked from access if the iOS version on the device doesn't meet this requirement.</li></ul> <ul><li>**Wipe data** - The user account that is associated with the application is wiped from the device.  </li></ul> </li></ul> ***Note:** Requires app to have Intune SDK version 7.0.1 or above.* |
| **Max PIN attempts** | Specify the number of tries the user has to successfully enter their PIN before the configured action is taken. This policy setting format supports a positive whole number. *Actions* include: <br><ul><li>**Reset PIN** - The user must reset their PIN.</li></ul> <ul><li>**Wipe data** - The user account that is associated with the application is wiped from the device.  </li></ul></li></ul> Default value = **5** |
| **Offline grace period** | The number of minutes that MAM apps can run offline. Specify the time (in minutes) before the access requirements for the app are rechecked. *Actions* include: <br><ul><li>**Block access (minutes)** - The number of minutes that MAM apps can run offline. Specify the time (in minutes) before the access requirements for the app are rechecked. After the configured period expires, the app blocks access to work or school data until network access is available. This policy-setting format supports a positive whole number.<br><br>Default value = **720** minutes (12 hours) </li></ul> <ul><li>**Wipe data (days)** - After this many days (defined by the admin) of running offline, the app will require the user to connect to the network and reauthenticate. If the user successfully authenticates, they can continue to access their data and the offline interval will reset.  If the user fails to authenticate, the app will perform a selective wipe of the users account and data.  See [How to wipe only corporate data from Intune-managed apps](https://docs.microsoft.com/intune/apps-selective-wipe) for more information on what data is removed with a selective wipe. This policy setting format supports a positive whole number.</li></ul>  Default value = **90 days** <br><br>  This entry can appear multiple times, with each instance supporting a different action. |
| **Jailbroken/rooted devices** | There is no value to set for this setting. *Actions* include: <br><ul><li>**Block access** - Prevent this app from running on jailbroken or rooted devices. The user continues to be able to use this app for personal tasks, but must use a different device to access work or school data in this app.</li></ul> <ul><li>**Wipe data**  - The user account that is associated with the application is wiped from the device. </li></ul> |
| **Min app version** | Specify a value for the minimum operating system value. *Actions* include: <br><ul><li>**Warn** - The user sees a notification if the app version on the device doesn't meet the requirement. This notification can be dismissed.</li></ul> <ul><li>**Block access** - The user is blocked from access if the app version on the device doesn't meet the requirement. </li></ul> <ul><li>**Wipe data** - The user account that is associated with the application is wiped from the device. </li></ul> </li></ul>   As apps often have distinct versioning schemes between them, create a policy with one minimum app version targeting one app (for example, *Outlook version policy*).<br><br> This entry can appear multiple times, with each instance supporting a different action.<br><br> This policy setting format supports either major.minor, major.minor.build, major.minor.build.revision.||
| **Min SDK version** | Specify a minimum value for the SDK version. *Actions* include: <br><ul><li>**Block access** - The user is blocked from access if the app’s Intune app protection policy SDK version doesn't meet the requirement. <br> <br> To learn more about the Intune app protection policy SDK, see [Intune App SDK overview](app-sdk.md).</li></ul> <ul><li>**Wipe data** - The user account that is associated with the application is wiped from the device. </li></ul>  </li></ul> As apps often have distinct versioning schemes between them, create a policy with one minimum app version targeting one app (for example, *Outlook version policy*). <br><br> This entry can appear multiple times, with each instance supporting a different action.|
| **Device model(s)** | Specify a device model that is required to use this app. *Actions* include: <br><ul><li>**Allow specified (Block non-specified)** - Only devices that match the specified device model can use the app. All other device models are blocked. </li></ul> <ul><li>**Allow specified (Wipe non-specified)** - The user account that is associated with the application is wiped from the device.</li></ul> |






##  Add-ins for Outlook app

Outlook recently brought add-ins to Outlook for iOS, which let you integrate popular apps with the email client. Add-ins for Outlook are available on the web, Windows, Mac, and Outlook for iOS. The Intune SDK and Intune app protection policies do not include support for managing add-ins for Outlook, but there are other ways to limit their use. Since add-ins are managed via Microsoft Exchange, users will be able to share data and messages across Outlook and unmanaged add-in applications unless add-ins are turned off for the user by their Exchange.

If you want to stop your end users from accessing and installing Outlook add-ins (this affects all Outlook clients), make sure you have the following changes to roles in the Exchange admin center:

- To prevent users from installing Office Store add-ins, remove the My Marketplace role from them.
- To prevent users from side loading add-ins, remove the My Custom Apps role from them.
- To prevent users from installing all add-ins, remove both, My Custom Apps and My Marketplace roles from them.

These instructions apply to Office 365, Exchange 2016, Exchange 2013 across Outlook on the web, Windows, Mac and mobile.

- Learn more about [add-ins for Outlook](https://technet.microsoft.com/library/jj943753(v=exchg.150).aspx).
- Learn more about [how to specify the administrators and users who can install and manage add-ins for Outlook app](https://technet.microsoft.com/library/jj943754(v=exchg.150).aspx).

##  LinkedIn account connections for Microsoft apps

LinkedIn account connections allow users to see public LinkedIn profile information within certain Microsoft apps. By default, your users can choose to connect their LinkedIn and Microsoft work or school accounts to see additional LinkedIn profile information. 

> [!NOTE]
> LinkedIn integration is currently unavailable for United States Government customers and for organizations with Exchange Online mailboxes hosted in Australia, Canada, China, France, Germany, India, South Korea, United Kingdom, Japan, and South Africa.

The Intune SDK and Intune app protection policies don't include support for managing LinkedIn account connections, but there are other ways to manage them. You can disable LinkedIn account connections for your entire organization, or you can enable LinkedIn account connections for selected user groups in your organization. These settings affect LinkedIn connections across Office 365 apps on all platforms (web, mobile, and desktop). You can:

- Enable or disable LinkedIn account connections for your tenant in the Azure portal. 
- Enable or disable LinkedIn account connections for your organization's Office 2016 apps using Group Policy.

If LinkedIn integration is enabled for your tenant, when users in your organization connect their LinkedIn and Microsoft work or school accounts, they have two options: 

- They can give permission to share data between both accounts. This means that they give permission for their LinkedIn account to share data with their Microsoft work or school account, as well as their Microsoft work or school account to share data with their LinkedIn account. Data that is shared with LinkedIn leaves the online services. 
- They can give permission to share data only from their LinkedIn account to their Microsoft work and school account

If a user consents to sharing data between accounts, as with Office add-ins, LinkedIn integration uses existing Microsoft Graph APIs. LinkedIn integration uses only a subset of the APIs available to Office add-ins and supports various exclusions.


|Microsoft Graph permissions  |Description  |
|---------|---------|
|Read permissions for [People](https://developer.microsoft.com/graph/docs/concepts/permissions_reference#people-permissions)     |Allows the app to read a scored list of people relevant to the signed-in user. The list can include local contacts, contacts from social networking or your organization's directory, and people from recent communications (such as email and Skype).         |
|Read permissions for [Calendars](https://developer.microsoft.com/graph/docs/concepts/permissions_reference#calendars-permissions)     |Allows the app to read events in user calendars. Includes the meetings in signed-in user calendars, their times, locations, and attendees.         |
|Read permissions for [User Profile](https://developer.microsoft.com/graph/docs/concepts/permissions_reference#user-permissions)     |Allows users to sign in to the app, and allows the app to read the profile of signed-in users. It also allows the app to read basic company information for signed-in users.         |
|Subscriptions     |This scope isn't available and not yet in use. It includes subscriptions provided by the user's organization to Microsoft apps and services, such as Office 365.         |
|Insights     |This scope isn't available and not yet in use. It includes the interests associated with the signed-in user's account based on their use of Microsoft services.         |

### Learn more

- Learn about [LinkedIn information and features in your Microsoft apps](https://go.microsoft.com/fwlink/?linkid=850740).
- Learn about LinkedIn account connections release on the [Office 365 Roadmap page](https://products.office.com/en-US/business/office-365-roadmap?filters=%26freeformsearch=linkedin#abc). 
- Learn about [Configuring LinkedIn account connections](https://docs.microsoft.com/azure/active-directory/linkedin-integration).
- For more information about data that is shared between users’ LinkedIn and Microsoft work or school accounts, see [LinkedIn in Microsoft applications at your work or school](https://www.linkedin.com/help/linkedin/answer/84077).

