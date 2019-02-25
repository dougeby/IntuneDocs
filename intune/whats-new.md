---
# required metadata
title: What's new in Microsoft Intune - Azure | Microsoft Docs
titlesuffix:
description: Find out what's new in the Intune Azure portal
keywords:
author: ErikjeMS  
ms.author: erikje
manager: dougeby
ms.date: 02/22/2019
ms.topic: conceptual
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
---

# What's new in Microsoft Intune
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Learn what’s new each week in Microsoft Intune. You can also find upcoming changes, [important notices](#notices), and information about [past releases](whats-new-archive.md). 

> [!Note]
> Some features may roll out over several weeks and might not be available to all customers in the first week.

**RSS feed**: Get notified when this page is updated by copying and pasting the following URL into your feed reader: `https://docs.microsoft.com/api/search/rss?search=%22What%27s+new+in+microsoft+intune%3F+-+Azure%22&locale=en-us`

<!-- Common categories:  
### App management
### Device configuration
### Device enrollment
### Device management
### Intune apps
### Monitor and troubleshoot
### Role-based access control

-->     

## Week of February 18, 2019

### App management

#### Intune will leverage Google Play Protect APIs on Android devices <!-- 2577355   -->
Some IT admins are faced with a BYOD landscape where end users may end up rooting or jailbreaking their mobile phone. This behavior, while sometimes not ill-intentioned, results in a bypass of many Intune policies that are set in order to protect the organization's data on end user devices. Thus, Intune provides root and jailbreak detection for both enrolled and unenrolled devices. With this release, Intune will now leverage Google Play Protect APIs to add to our existing root detection checks for unenrolled devices. While Google does not share the entirety of the root detection checks that occur, we expect these APIs to detect users who have rooted their devices for any reason from device customization to being able to get newer OS updates on older devices. These users can then be blocked from accessing corporate data, or their corporate accounts can be wiped from their policy enabled apps. For additional value, the IT admin will now have several reporting updates within the Intune App Protection blade - the "Flagged Users" report will show which users are detected via Google Play Protect's SafetyNet API scan, the "Potentially Harmful Apps" report will show which apps are detected via Google's Verify Apps API scanning. This feature is available on Android.

#### Win32 app information available in Troubleshooting blade <!-- 2617342   -->
You can now collect failure log files for a Win32 app installation from the Intune app **Troubleshooting** blade. For more information about app installation troubleshooting, see [Troubleshoot app installation issues](troubleshoot-app-install.md) and [Troubleshoot Win32 app issues](apps-win32-app-management.md#troubleshoot-win32-app-issues).

#### App status details for iOS apps <!-- 3761235   -->
There are new app installation error messages related to the following:
- Failure for VPP apps when installing on shared iPad
- Failure when app store is disabled
- Failure to find VPP license for app
- Failure to install system apps with MDM provider
- Failure to install apps when device is in lost mode or kiosk mode
- Failure to install app when user is not signed in to the App Store

In Intune, select **Client apps** > **Apps** > "App name" > **Device install status**. New error messages will be available in the **Status details** column.

#### New App categories screen in the Company Portal app for Windows 10<!-- 3834780  -->
A new screen called **App categories** has been added to improve the app browsing and selection experience in Company Portal for Windows 10. Users will now see their apps sorted under categories such as **Featured**, **Education**, and **Productivity**. This change appears in Company Portal versions 10.3.3451.0 and later. To view the new screen, see [What's new in the app UI](https://docs.microsoft.com/intune/whats-new). For more information about apps in the Company Portal, see [Install and share apps on your device](/intune-user-help/install-apps-cpapp-windows).  

#### Power BI Compliance app <!-- 1455231 doc-work-item -->
Access your Intune Data Warehouse in Power BI Online using the [Intune Compliance (Data Warehouse)](https://app.powerbi.com/groups/me/getapps/services/Intune_dw_compliance) app. With this Power BI app, you can now access and share pre-created reports without any setup and without leaving your web browser. For additional information, see [Change log - Power BI Compliance app](reports-changelog.md#power-bi-compliance-app). For additional Intune Data Warehouse updates, see [Upcoming changes to the Intune Data Warehouse API](whats-new.md#upcoming-change-to-the-intune-data-warehouse-api).


### Device configuration

#### PowerShell scripts can run in a 64-bit host on 64-bit devices <!-- 1862675   -->
When you add a PowerShell script to a device configuration profile, the script always executes in 32-bit, even on 64-bit operating systems. With this update, an administrator can run the script in a 64-bit PowerShell host on 64-bit devices (**Device configuration** > **PowerShell scripts** > **Add** > **Configure** > **Run script in 64 bit PowerShell Host**).

For more details on using PowerShell, see [PowerShell scripts in Intune](intune-management-extension.md).

Applies to:
Windows 10 and later

#### macOS users are prompted to update their password <!-- 1873216 -->
Intune is enforcing the **ChangeAtNextAuth** setting on macOS devices. This setting impacts end-users and devices that have compliance password policies or device restriction password profiles. End users are prompted once to update their password. This prompt happens whenever a user first runs a task that requires authentication, such as signing in to the device. Users can also be prompted to update their password when doing anything that requires administrative privileges, such as requesting keychain access. 

Any new or existing password policy changes by the administrator prompts end users again to update their password.

Applies to:  
macOS

#### Assign SCEP certificates to a userless macOS device    <!-- 2340521    -->
You can assign Simple Certificate Enrollment Protocol (SCEP) certificates using device attributes to macOS devices, including devices without user affinity, and associate the certificate profile with Wi-Fi or VPN profiles. This expands the support we already have to [assign SCEP certificates to devices with and without user affinity](certificates-scep-configure.md#create-a-scep-certificate-profile) that run Windows, iOS, and Android.  This update adds the option to select a Certificate type of *Device* when you configure a SCEP certificate profile for the macOS.

Applies to: 
- macOS

#### Intune conditional access UI update   <!-- 2432313   -->
We've made improvements to the UI for conditional access in the Intune console. These include:
-  Replaced the Intune *Conditional access* blade with the blade from Azure Active Directory. This ensures you'll have access to the full range of settings and configurations for [conditional access](conditional-access.md) (which remains an Azure AD technology), from within the Intune console. 
- We've renamed the *On-premises access* blade to *Exchange access*, and relocated the *Exchange service connector* setup to this renamed blade.  This change consolidates where you [configure and monitor details related to Exchange online and on-premises](exchange-connector-install.md).  

#### Kiosk Browser and Microsoft Edge Browser apps can run on Windows 10 devices in kiosk mode <!-- 2935135   -->
You can use Windows 10 devices in kiosk mode to run one app, or many apps. This update includes several changes to using browser apps in kiosk mode, including:

- Add the Microsoft Edge Browser or Kiosk Browser to run as apps on the kiosk device (**Device configuration** > **Profiles** > **New profile** > **Windows 10 and later** for platform > **Kiosk** for profile type).
- New features and settings are available to allow or restrict (**Device configuration** > **Profiles** > **New profile** > **Windows 10 and later** for platform > **Device restrictions** for profile type), including:

  - Microsoft Edge Browser:​
    - Use Microsoft Edge kiosk mode​
    - Refresh browser after idle time​
​
 - Favorites and search:​
    - Allow changes to search engine

For a list of these settings, see:

- [Windows 10 and later device settings to run as a kiosk](kiosk-settings-windows.md)
- [Microsoft Edge Browser device restrictions](device-restrictions-windows-10.md#microsoft-edge-browser)
- [Favorites and search device restrictions](device-restrictions-windows-10.md##favorites-and-search)

Applies to:
Windows 10 and later

#### New device restriction settings for iOS and macOS devices <!-- 3448774   -->
You can restrict some settings and features on devices running iOS and macOS (**Device configuration** > **Profiles** > **New profile** > **iOS** or **macOS** for platform > **Device restrictions** for profile type). This update adds more features and settings you can control, including setting screen time, changing eSIM settings and cellular plans, and more on iOS devices. Also, delaying the user's visibility of software updates and blocking content caching on macOS devices. 

To see the features and settings you can restrict, see:

- [iOS device restriction settings](device-restrictions-ios.md)
- [macOS device restriction settings](device-restrictions-macos.md)

Applies to:

- iOS
- macOS

#### "Kiosk" devices are now called "Dedicated devices" on Android Enterprise devices <!-- 3598402   -->
To align with Android terminology, **kiosk** is changed to **dedicated devices** for Android enterprise devices (**Device configuration** > **Profiles** > **Create profile** > **Android enterprise for platform > **Device Owner Only** > **Device Restrictions** > **Dedicated devices**).

To see the available settings, go to [Device settings to allow or restrict features](device-restrictions-android-for-work.md#dedicated-device-settings).

Applies to:  
Android Enterprise

#### Safari and Delaying user software update visibility iOS settings are moving in the Intune UI <!-- 3640850, 3803313   -->
For iOS devices, you can set Safari settings and configure Software Updates. In this update, these settings are moving to different parts of the Intune UI:

- The Safari settings moved from **Safari** (**Device configuration** > **Profiles** > **New profile** > **iOS** for platform > **Device restrictions** for profile type) to **[Built-in Apps](device-restrictions-ios.md#built-in-apps)**.
- The **Delaying user software update visibility for supervised iOS devices** setting (**Software updates** > **Update policies for iOS**) is moving to **Device restrictions** > **[General](device-restrictions-ios.md#general)**.  For details on the impact to existing policies, see [iOS software updates](software-updates-ios.md#configure-the-policy). 

For a list of the settings, see:

- [iOS device restrictions](device-restrictions-ios.md) 
- [iOS software updates](software-updates-ios.md)

This feature applies to: 

- iOS

#### Enabling restrictions in the device settings is renamed to Screen Time on iOS devices <!-- 3699164   -->
You can configure the **Enabling restrictions in the device settings** on supervised iOS devices (**Device configuration** > **Profiles** > **New profile** > **iOS** for platform > **Device restrictions** for profile type > **General**). In this update, this setting is renamed to **Screen Time (supervised only)**. 

The behavior is the same. Specifically: 

- iOS 11.4.1 and earlier: **Block** prevents end users from setting their own restrictions in the device settings. 
- iOS 12.0 and later: **Block** prevents end users from setting their own **Screen Time** in the device settings, including content & privacy restrictions. Devices upgraded to iOS 12.0 won't see the restrictions tab in the device settings anymore. These settings are in **Screen Time**. 

For a list of the settings, see [iOS device restrictions](device-restrictions-ios.md#general).

Applies to: 
- iOS


### Device management

#### Rename an enrolled Windows device <!-- 1911112  -->
You can now rename an enrolled Windows 10 device (RS4 or later). To do, choose **Intune** > **Devices** > **All devices** > choose a device > **Rename device**.

#### Auto-assign scope tags to resources created by an admin with that scope <!-- 3173823  -->
When an admin creates a resource, any scope tags assigned to the admin will automatically be assigned to those new resources.

### Monitor and troubleshoot

#### Failed enrollment report moves to the Device Enrollment blade <!-- 3560202  -->
The **Failed enrollments** report has been moved to the **Monitor** section of the **Device enrollment** blade. Two new columns (Enrollment Method and OS Version) have been added.

#### Company Portal abandonment report renamed to Incomplete user enrollments <!--3815076 eemiss -->
The **Company Portal abandonment** report has been renamed to **Incomplete user enrollments**.



## Week of February 4, 2019

### App management

#### Intune macOS Company Portal Dark Mode <!-- 3300524  -->
The Intune macOS Company Portal now supports Dark Mode for macOS. When you enable Dark Mode on a macOS 10.14+ device, the Company Portal will adjust its appearance to colors that reflect that mode.

## Week of January 21, 2019

### App management

#### Toast notifications for Win32 apps <!-- 3136566   -->
You can suppress showing end user toast notifications per app assignment. From Intune, select **Client apps** > **Apps** > select the app > **Assignments** > **Include Groups**. 

#### Intune app protection policies UI update <!-- 3251427  -->
We’ve changed the labels for settings and buttons for Intune app protection to make each easier to understand. Some of the changes include:  
- Controls are changed from **yes** / **no** controls to primarily **block** / **allow** and **disable** / **enable** controls. The labels are also updated.  
- Settings are reformatted, so the setting and its label are side-by-side in the control, to provide better navigation.   

The default settings and number of settings remain the same, but this change allows the user to understand, navigate, and utilize the settings more easily to apply selected app protection policies. For information, see [iOS settings](app-protection-policy-settings-ios.md) and [Android settings](app-protection-policy-settings-android.md).

#### Additional settings for Outlook <!-- 3301182  -->
You can now configure the followiong additional settings for Outlook for iOS and Android using Intune:
- Only allow work or school accounts to be used in Outlook in iOS and Android
- Deploy modern authentication for Office 365 and hybrid modern authentication on-premises accounts
- Use `SAMAccountName` for the username field in the email profile when basic authentication is selected

The following settings are still being rolled out gradually and will be available in your console soon:
- Allow contacts to be saved
- Configure external recipients MailTips
- Configure **Focused Inbox**
- Require biometrics to access Outlook for iOS

The setting below appears in the Intune console, but when configured, will not work as expected. This issue will be fixed soon:
- Block external images

> [!NOTE]
> If you are using Intune App Protection policies to manage access for corporate identities, you should consider not enabling **require biometrics**. For more information, see **Require corporate credentials for access** for [iOS Access Settings](app-protection-policy-settings-ios.md#access-requirements) and [Android Access Settings](app-protection-policy-settings-android.md#access-requirements).

#### Delete Android Enterprise apps <!-- 1352553 -->
You can delete managed Google Play apps from Microsoft Intune. To delete a managed Google Play app, open Microsoft Intune in the Azure portal and select **Client apps** > **Apps**. From the app list, select the ellipses (...) to the right of the managed Google Play app, then select **Delete** from the displayed list. When you delete a managed Google Play app from the app list, the managed Google Play app is automatically unapproved.

#### Managed Google Play app type <!-- 1352580 -->
The **managed Google Play** app type will allow you to specifically add [managed Google Play apps](https://play.google.com/work/search?q=microsoft&c=apps) to Intune. As the Intune admin, you can now browse, search, approve, sync and assign approved managed Google Play apps within Intune.  You no longer need to browse to the managed Google Play console separately, and you no longer have to reauthenticate.  In Intune, select **Client apps** > **Apps** > **Add**. In the **App type** list, select **Managed Google Play** as the app type.

### Default Android PIN keyboard <!-- 3802457 -->
For end users who have set an Intune App Protection Policy (APP) PIN on their Android devices with PIN type of 'Numeric', they will now see the default Android keyboard instead of the fixed Android keyboard UI that was previously designed. This change was made to be consistent when using default keyboards on both Android and iOS, for both PIN types of 'Numeric' and/or 'Passcode'. For more information about end user Access settings on Android, such as APP PIN, see [Android access requirements](app-protection-policy-settings-android.md#access-requirements).

### Device configuration

#### Use Microsoft-recommended settings with Security Baselines (Public Preview) <!-- 2055484   -->

Intune integrates with other services that focus on security, including Windows Defender ATP and Office 365 ATP. Customers are asking for a common strategy and a cohesive set of end-to-end security workflows across the Microsoft 365 services. Our goal is to align strategies to build solutions that bridge security operations and common administrator tasks. 
In Intune, we aim to accomplish this goal by publishing a set of Microsoft recommended “Security baselines” (**Intune** > **Security baselines**).  An administrator can create security policies directly from these baselines, and then deploy them to their users. You can also customize the best practice recommendations to meet the needs of your organization. Intune makes sure that devices stay in compliance with these baselines, and notifies administrators of users or devices that aren't in compliance.

This feature is in public preview so any profiles created now will not move over to Security Baselines templates that are generally available (GA). You shouldn’t plan to use these preview templates in your production environment.

To learn more about security baselines, see [Create a Windows 10 security baseline in Intune](security-baselines-monitor.md).

This feature applies to:
Windows 10 and later

#### Non-Administrators can enable BitLocker on Windows 10 devices joined to Azure AD<!-- 2147379   -->​
When you enable BitLocker settings on Windows 10 devices (**Device configuration** > **Profiles** > **Create profile** > **Windows 10 and later** for platform > **Endpoint protection** for profile type > **Windows Encryption**), you add BitLocker settings. ​
​
This update includes a new BitLocker setting to allow standard users (non-administrators) to enable encryption. ​
​
To see the settings, go to [Endpoint protection settings for Windows 10](endpoint-protection-windows-10.md#windows-encryption).​

#### Check for Configuration Manager compliance <!-- 2192052  eepublished  -->
This update includes a new System Center Configuration Manager compliance setting (**Device compliance** > **Policies** > **Create policy** > **Windows 10 and later** > **Configuration Manager Compliance**). Configuration Manager sends signals to Intune compliance. Using this setting, you can require all Configuration Manager signals to return "compliant".

For example, you require all software updates to be installed on devices. In Configuration Manager, this requirement has the “Installed” state. If any programs on the device are in unknown state, then the device is non-compliant in Intune.

[Configuration Manager Compliance](compliance-policy-create-windows.md#configuration-manager-compliance) describes this setting.

Applies to: 
Windows 10 and later

#### Customize wallpaper on supervised iOS devices using a device configuration profile <!-- 2809324   -->
When you create a device configuration profile for iOS devices, you can customize some features (**Device configuration** > **Profiles** > **Create profile** > **iOS** for platform > **Device features** for profile type). This update includes new **Wallpaper** settings that allow an Administrator to use a .png, .jpg, or .jpeg image on the home screen or lock screen. These wallpaper settings apply only to supervised devices. 

For a list of these settings, see [iOS device feature settings](ios-device-features-settings.md).

#### Windows 10 kiosk is generally available <!-- 3594661  -->
In this update, the Kiosk feature on Windows 10 and later devices is generally available (GA). To see all the settings you can add and configure, see [Kiosk settings for Windows 10 (and later)](kiosk-settings.md).

#### Contact Sharing via Bluetooth is removed in Device Restrictions > Device Owner for Android Enterprise <!-- 3598396   -->
When you create a device restrictions profile for Android Enterprise devices, there is a **Contact Sharing via Bluetooth** setting. In this update, the **Contact Sharing via Bluetooth** setting is removed (**Device configuration** > **Profiles** > **Create profile** > **Android Enterprise** for platform > **Device Restrictions > Device owner** for profile type > **General**). 

The **Contact Sharing via Bluetooth** setting isn't supported for Android Enterprise Device Owner management. So when this setting is removed, it won't impact any devices or tenants, even if this setting is enabled and configured in your environment.

To see the current list of settings, go to [Android Enterprise device settings to allow or restrict features](device-restrictions-android-for-work.md).

Applies to: Android Enterprise Device Owner

### Device management

#### Selective wipe support for WIP Without Enrollment devices <!-- 1434452 -->
Windows Information Protection Without Enrollment (WIP-WE) allows customers to protect their corporate data on Windows 10 devices without the need for full MDM enrollment. Once documents are protected with a WIP-WE policy, the protected data can be selectively wiped by an Intune administrator. By selecting the user and device, and sending a wipe request, all data that was protected via the WIP-WE policy will become unusable. From the Intune in the Azure portal, select **Mobile app** > **App selective wipe**.

### Monitor and troubleshoot

#### New operational logs, and ability to send logs to Azure Monitor services <!-- 3762211  -->
Intune has built-in audit logging that tracks events as changes are made. This update includes new logging features, including: 
- Operational logs (preview) that show details on users and devices that enrolled, including success and failed attempts.
- The audit logs and operational logs can be sent to Azure Monitor, including storage accounts, event hubs, and log analytics. These services allow you to store, use analytics such as Splunk and QRadar, and get visualizations of your logging data.

[Send log data to storage, event hubs, or log analytics in Intune](review-logs-using-azure-monitor.md) provides more information on this feature.

### Skip more Setup Assistant screens on an iOS DEP device <!-- 2687509  -->
In addition to the screens you can currently skip, you can set iOS DEP devices to skip the following screens in the Setup Assistant when a user enrolls the device: Display Tone, Privacy, Android Migration, Home Button, iMessage & FaceTime, Onboarding, Watch Migration, Appearance, Screen Time, Software Update, SIM Setup.
To choose which screens to skip, go to **Device enrollment** > **Apple enrollment** > **Enrollment program tokens** > choose a token > **Profiles** > choose a profile > **Properties** > **Setup Assistant customization** > choose **Hide** for any screens that you want to skip > **OK**.
If you create a new profile or edit a profile, the selected skip screens need to sync with the Apple MDM server. Users can issue a manual sync of the devices so that there is no delay in picking up the profile changes.

#### Android Enterprise APP-WE app deployment <!-- 1171203 -->
For Android devices in a non-enrolled App Protection Policy Without Enrollment (APP-WE) deployment scenario, you can now use managed Google Play to deploy store apps and LOB apps to users. Specifically, you can provide end users with an app catalog and installation experience that no longer requires end users to loosen the security posture of their devices by allowing installations from unknown sources. In addition, this deployment scenario will provide an improved end user experience.

## Week of January 14, 2019

### Preview of support for Android corporate-owned, fully managed devices <!-- 1574342  -->
Intune now supports fully managed Android devices, a corporate-owned "device owner" scenario where devices are tightly managed by IT and are affiliated with individual users. This allows admins to manage the entire device, enforce an extended range of policy controls unavailable to work profiles, and restricts users to installing apps from managed Google Play only. For more information, see [Set up Intune enrollment of Android fully managed devices](android-fully-managed-enroll.md) and [Enroll your dedicated devices or fully managed devices](android-dedicated-devices-fully-managed-enroll.md).  Please note that this feature is in preview. Some Intune capabilities, such as certificates, compliance, and Conditional Access, are not currently available with Android fully managed user devices.

## Week of January 7, 2019

### App management

#### Intune app PIN <!-- 2298397 -->
As the IT admin, you can now configure the number of days an end user can wait until their Intune app PIN must be changed. The new setting is *PIN reset after number of days* and is available in the Azure portal by selecting **Intune** > **Client apps** > **App protection policies** > **Create Policy** > **Settings** > **Access requirements**. Available for [iOS](app-protection-policy-settings-ios.md) and [Android](app-protection-policy-settings-android.md) devices, this feature supports a positive integer value.


#### Intune device reporting fields <!-- 2748738 -->
Intune provides additional device reporting fields, including App Registration Id, Android manufacturer, model, and security patch version, as well as iOS model. In Intune, these fields are available by selecting **Client apps** > **App protection status** and choosing **App Protection Report: iOS, Android**. In addition, these parameters will help you configure the **Allow** list for device manufacturer (Android), the **Allow** list for device model (Android and iOS), and the minimum Android security patch version setting. 


### Device configuration

#### Administrative templates are in public preview, and moved to their own configuration profile <!-- 3322847 -->

Administrative templates in Intune (**Device configuration** > **Administrative templates**) are currently in private preview. With this update:

- Administrative templates include about 300 settings that can be managed in Intune. Previously, these settings only existed in the group policy editor.
- Administrative templates are available in public preview.
- Administrative templates are moving from **Device configuration** > **Administrative templates** to **Device configuration** > **Profiles** > **Create profile** > in **Platform**, choose **Windows 10 and later** > in **Profile type**, choose **Administrative templates**.
- Reporting is enabled

To read more about this feature, go to [Windows 10 templates to configure group policy settings](administrative-templates-windows.md).

Applies to: Windows 10 and later

#### Use S/MIME to encrypt and sign multiple devices for a user  <!-- 1333642 -->
This update includes S/MIME email encryption using a new imported certificate profile (**Device configuration** > **Profiles** > **Create profile** > select the platform > **PKCS imported certificate** profile type). In Intune, you can import certificates in PFX format. Intune can then deliver those same certificates to multiple devices enrolled by a single user. This also includes:
- The native iOS email profile supports enabling S/MIME encryption using imported certificates in PFX format.
- The native mail app on Windows Phone 10 devices automatically use the S/MIME certificate.
- The private certificates can be delivered across multiple platforms. But, not all email apps support S/MIME.
- On other platforms, you may need to manually configure the mail app to enable S/MIME.  
- Email apps that support S/MIME encryption may handle retrieving certificates for S/MIME email encryption in a way that an MDM cannot support, such as reading from their publisher's certificate store.
For more information on this feature, see [S/MIME overview to sign and encrypt email](certificates-s-mime-encryption-sign.md).
Supported on: Windows, Windows Phone 10, macOS, iOS, Android

#### New options to automatically connect and persist rules when using DNS settings on Windows 10 and later devices <!-- 1333665, 2999078 -->
On Windows 10 and later devices, you can create a VPN configuration profile that includes a list of DNS servers to resolve domains, such as contoso.com. This update includes new settings for name resolution (**Device configuration** > **Profiles** > **Create profile** > Choose **Windows 10 and later** for platform > Choose **VPN** for profile type > **DNS settings** >**Add**): 
- **Automatically connect**: When **Enabled**, the device automatically connects to the VPN when a device contacts a domain you enter, such as contoso.com.
- **Persistent**: By default, all Name Resolution Policy table (NRPT) rules are active as long as the device is connected using this VPN profile. When this setting is **Enabled** on an NRPT rule, the rule remains active on the device, even when the VPN disconnects. The rule stays until the VPN profile is removed or until the rule is manually removed, which can be done using PowerShell.
[Windows 10 VPN settings](vpn-settings-windows-10.md) describes the settings. 

#### Use trusted network detection for VPN profiles on Windows 10 devices <!-- 1500165 -->​
​When using trusted network detection, you can prevent VPN profiles from automatically creating a VPN connection when the user is already on a trusted network. With this update, you can add DNS suffixes to enable trusted network detection on devices running Windows 10 and later (**Device configuration** > **Profiles** > **Create profile** > **Windows 10 and later** for platform > **VPN** for profile type).
​[Windows 10 VPN settings](vpn-settings-windows-10.md) lists the current VPN settings.​

#### Manage Windows Holographic for Business devices used by multiple users <!-- 1907917, 1063203 -->
Currently, you can configure shared PC settings on Windows 10 and Windows Holographic for Business devices using a custom OMA-URI setting. With this update, a new profile is added to configure shared device settings (**Device configuration** > **Profiles** > **Create Profile** > **Windows 10 and later** > **Shared multi-user device**).
To learn more about this feature, go to [Intune settings to manage shared devices](shared-user-device-settings.md).
Applies to: Windows 10 and later, Windows Holographic for Business

#### New Windows 10 Update settings <!--2626030  2512994  -->
For your [Windows 10 Update Rings](windows-update-for-business-configure.md), you can configure:
- **Automatic update behavior** - Use a new option, *Reset to default* to restore the original auto update settings on a Windows 10 machine on machines running the *October 2018 Update*
- **Block user from pausing Windows updates** - Configure a new Software updates setting that lets you block or allow your users to pause update installation from the *Settings* of their machines. 

#### iOS email profiles can use S/MIME signing and encryption <!-- 2662949 -->
You can create an email profile that includes different settings. This update includes S/MIME settings that can be used for signing and encrypting email communications on iOS devices (**Device configuration** > **Profiles** > **Create profile** > Choose **iOS** for platform > **Email** for profile type).
[iOS email configuration settings](email-settings-ios.md) lists the settings.

#### Some BitLocker settings support Windows 10 Pro edition<!-- 2727036 -->​
You can create a configuration profile that sets endpoint protection settings on Windows 10 devices, including BitLocker. This update adds support for Windows 10 Professional edition for some BitLocker settings. ​
To see these protection settings, go to [Endpoint protection settings for Windows 10](endpoint-protection-windows-10.md#windows-encryption).

#### Shared device configuration is renamed to Lock Screen Message for iOS devices in the Azure portal<!-- 2809362 -->
When you create a configuration profile for iOS devices, you can add **Shared Device Configuration** settings to show specific text on the lock screen. This update includes the following changes: 
- The **Shared Device Configuration** settings in the Azure portal are renamed to "Lock Screen Message (supervised only)" (**Device configuration** > **Profiles** > **Create profile** > Choose **iOS** for platform > Choose **Device features** for profile type > **Lock Screen Message**).
- When adding lock screen messages, you can insert a serial number, a device name, or another device-specific value as a variable in **Asset tag information** and **Lock screen footnote**. For example, you can enter `Device name: {{devicename}}` or `Serial number is {{serialnumber}}` using curly brackets. [iOS tokens](app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) lists the available tokens that can be used.
[Settings to display messages on the lock screen](shared-device-settings-ios.md) lists the settings.

#### New App Store, Doc Viewing, Gaming device restriction settings added to iOS devices <!-- 2827760-->
In **Device Configuration** > **Profiles** > **Create profile** > **iOS** for platform > **Device restrictions** for profile type > **App Store, Doc Viewing, Gaming**, the following settings are added: 
Allow managed apps to write contacts to unmanaged contacts accounts 
Allow unmanaged apps to read from managed contacts accounts 
To see these settings, go to [iOS device restrictions](device-restrictions-ios.md#app-store-doc-viewing-gaming).

#### New notification, hints, and keyguard settings to Android Enterprise device owner devices <!-- 3201839 3201843 -->
​This update includes several new features on Android Enterprise devices when running as device owner. To use these features, go to **Device Configuration** > **Profiles** > **Create profile** > In **Platform**, choose **Android Enterprise** > In **Profile type**, choose **Device owner only** > **Device Restrictions**.​

​New features include: ​

- Disable system notifications from showing, including incoming calls, system alerts, system errors, and more.
- Suggests skip starting tutorials and hints for apps that are opened the first time​.
- Disable advanced keyguard settings, such as the camera, notifications, fingerprint unlock, and more​.
​

To see the settings, go to [Android Enterprise device restriction settings](device-restrictions-android-for-work.md).​

#### Android enterprise device owner devices can use Always On VPN connections <!-- 3202194 -->
In this update, you can use Always-on VPN connections on Android enterprise device owner devices. Always-on VPN connections stay connected, or immediately reconnect when the user unlocks their device, when the device restarts, or when the wireless network changes. You can also put the connection in "lockdown" mode, which blocks all network traffic until the VPN connection is active.
You can enable Always-on VPN in **Device configuration** > **Profiles** > **Create profile** > **Android enterprise** for platform > **Device restrictions** for Device Owner Only > **Connectivity** settings. 
To see the settings, go to [Android Enterprise device restriction settings](device-restrictions-android-for-work.md).

#### New setting to end processes in Task manager on Windows 10 devices <!-- 3285177 --> 
This update includes a new setting to end processes using Task Manager on Windows 10 devices. Using a device configuration profile (**Device configuration** > **Profiles** > **Create profile** > In **Platform**, choose **Windows 10** > In **Profile type**, choose **Device restrictions** > **General** settings), you choose to allow or prevent this setting.
To see these settings, go to [Windows 10 device restriction settings](device-restrictions-windows-10.md).
Applies to: Windows 10 and later


### Device enrollment

#### More detailed enrollment restriction failure messaging <!-- 3111564 -->
More detailed error messages are available when enrollment restrictions are not met. To see these messages, go to **Intune** > **Troubleshoot** > and check the Enrollment Failures table. For more information, see the [enrollment failures list](help-desk-operators.md#configuration-policies-reference).



### Monitor and troubleshoot

#### Tenant Status dashboard  <!-- 1124854 -->
The new [Tenant Status page](tenant-status.md) provides a single location where you can view status and related details for your tenant.  The dashboard is divided into four areas:
- **Tenant Details** - Displays information that includes your Tenant name and location, your MDM Authority, the total enrolled devices in your tenant, and your license counts. This section also lists the current service release for your tenant.
- **Connector Status** - Displays information about available connectors you have configured and can also list those which you have not yet enabled.  
   Based on the current state of each connector,  they are flagged as Healthy, Warning, or Unhealthy. Select a connector to drill through and view details or configure additional information for it.
-  **Intune Service Health** - Displays details about active incidents or outages for your tenant. The information in this section is retrieved directly from the Office Message Center.
-  **Intune News** - Displays active messages for your tenant. Messages include things like notifications when your tenant receives the latest Intune features.  The information in this section is retrieved directly from the Office Message Center.

#### New help and support experience in Company Portal for Windows 10 <!-- 1488939-->
The new Company Portal Help & support page helps users troubleshoot and request help for app and access problems. From the new page, they can email error and diagnostic log details and find their organization's Helpdesk details. They'll also find a FAQ section with links to the relevant Intune documentation. 

#### New Help and Support experience for Intune   <!-- #3307080 -->
We are rolling out the new Help and Support experience to all tenants over the next few days. This new experience is available for Intune and can be accessed when using the Intune blades in the [Azure portal](https://portal.azure.com/).
The new experience lets you describe your problem in your own words and receive troubleshooting insight and web-based remediation content. These solutions are offered via a rule-based machine learning algorithm, driven by user inquires. 
In addition to issue-specific guidance, you use the new case creation workflow to open a support case by email or phone. 
This new experience replaces the previous Help and Support experience of a static set of pre-selected options that are based on the area of the console you are in when you open Help and Support. 
For more information, see [How to get support for Microsoft Intune](get-support.md).

### Role-based access control

#### Scope tags for apps <!-- 1081941 -->
You can create scope tags to limit access for roles and apps. You can add a scope tag to an app so that only people with roles also assigned that scope tag have access to the app. Currently, apps added to Intune from managed Google Play or apps purchased using Apple Volume Purchase Program (VPP) can't be assigned scope tags (but support will come in the future). For more information, see [Use scope tags to filter policies](scope-tags.md).



## Week of December 10, 2018

### App management

#### Updates for Application Transport Security <!-- 748318 -->

Microsoft Intune supports Transport Layer Security (TLS) 1.2+ to provide best-in-class encryption, to ensure Intune is more secure by default, and to align with other Microsoft services such as Microsoft Office 365. In order to meet this requirement, the iOS and macOS company portals will enforce Apple's updated Application Transport Security (ATS) requirements, which also require TLS 1.2+. ATS is used to enforce stricter security on all app communications over HTTPS. This change impacts Intune customers using the iOS and macOS Company Portal apps. For more information, see the [Intune support blog](https://aka.ms/compportalats).

#### The Intune App SDK will support 256-bit encryption keys <!-- 1832174 -->
The Intune App SDK for Android now uses 256-bit encryption keys when encryption is enabled by App Protection Policies. The SDK will continue to provide support of 128-bit keys for compatibility with content and apps that use older SDK versions.

### Microsoft Auto Update version 4.5.0 required for macOS devices <!-- 3503442 -->
To continue receiving updates for the Company Portal and other Office applications, macOS devices managed by Intune must upgrade to Microsoft Auto Update 4.5.0. Users might already have this version for their Office apps.

### Intune requires macOS 10.12 or later <!-- 2827778 -->
Intune now requires macOS version 10.12 or later. Devices using prior macOS versions can't use the Company Portal to enroll into Intune. To receive support assistance and new features, users must upgrade their device to macOS 10.12 or later and upgrade the Company Portal to the latest version.

## Week of November 26, 2018

### App management

#### Uninstalling apps on corporate-owned supervised iOS devices <!-- 1281677 -->

You can remove any app on corporate-owned supervised iOS devices. You can remove any app by targeting either user or device groups with an **Uninstall** assignment type. For personal or unsupervised iOS devices, you will continue to be able to remove only apps that were installed using Intune.

#### Downloading Intune Win32 app content <!-- 2617320 -->
Windows 10 RS3 and above clients will download Intune Win32 app content using a Delivery Optimization component on the Windows 10 client. Delivery optimization provides Peer-to-Peer functionality that it is turned on by default. Delivery optimization can be configured by group policy and in the future via Intune MDM. For more information, see [Delivery Optimization for Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization). 

#### End user device and app content menu <!-- 2771453 -->
End users can now use context menu on device and apps to trigger common actions like renaming a device or checking compliance.

#### Set custom background in Managed Home Screen app  <!-- 3041945 -->
We're adding a setting that lets you customize the background appearance of the Managed Home Screen app on Android Enterprise, multi-app, kiosk mode devices.  To configure the **Custom URL background**, go to Intune in the Azure portal > Device configuration. Select a current device configuration profile or create a new one to edit its kiosk settings.
To see the kiosk settings, see [Android Enterprise device restrictions](device-restrictions-android-for-work.md).

#### App protection policy assignment save and apply <!-- 3104570 -->
You now have better control over your [app protection policy assignments](app-protection-policies.md#deploy-a-policy-to-users). When you select *Assignments* to set or edit the assignments of a policy, you must **Save** your configuration before the change applies. Use **Discard** to clear all changes you make without saving any changes to the Include or Exclude lists.  By requiring Save or Discard, only the users you intend are assigned an app protection policy.

#### New Microsoft Edge browser settings for Windows 10 and later <!-- 3174639 -->
This update includes new settings to help control and manage the Microsoft Edge browser on your devices. For a list of these settings, see [Device restriction for Windows 10 (and newer)](device-restrictions-windows-10.md#microsoft-edge-browser).

#### New apps support with app protection policies <!-- 3330037 -->
You can now manage the following apps with [Intune app protection policies](app-protection-policies.md):
- Stream (iOS)
- To DO (Android, iOS)
- PowerApps (Android, iOS)
- Flow (Android, iOS)

Use app protection policies to protect corporate data and control data transfer for these apps, like other Intune policy managed apps. 
Note: If Flow is not yet visible in the console, you add Flow when you create or edit and app protection policies. To do so, use the **+ More apps** option, and then specify the *App ID* for Flow in the input field. For Android use *com.microsoft.flow*,  and for iOS use *com.microsoft.procsimo*.


### Device configuration

#### iOS and macOS version numbers and build numbers are shown <!-- 1892471 -->
In **Device compliance** > **Device compliance**, the iOS and macOS operating system versions are shown, and available to use in compliance policies. This update includes, the build number, which is configurable for both platforms.
When security updates are released, Apple typically leaves the version number as-is, but updates the build number. By using the build number in a compliance policy, you can easily check if a vulnerability update is installed.
To use this feature, see [iOS](compliance-policy-create-ios.md#device-health) and [macOS](compliance-policy-create-mac-os.md#device-properties) compliance policies.

#### Update rings are being replaced with Delivery Optimization settings for Windows 10 and later <!-- 2753807 -->
Delivery optimization is a new configuration profile for Windows 10 and later. This feature provides a more streamlined experience to deliver software updates to devices in your organization. This update also helps you deliver the settings in new and existing update rings using a configuration profile.
To configure a delivery optimization configuration profile, see [Windows 10 (and newer) delivery optimization settings](delivery-optimization-windows.md).

#### New device restriction settings added to iOS and macOS devices <!-- 2827760 -->
This update includes new settings for your iOS and macOS devices that are released with iOS 12:

**iOS settings**: 
- General: Block app removal (supervised only)​
- General: Block USB Restricted mode (supervised only)​
- General: Force automatic date and time (supervised only)​​
- Password: Block password AutoFill (supervised only)​
- Password: Block password proximity requests (supervised only)​
- Password: Block password sharing (supervised only)

**macOS settings**: 
- Password: Block password AutoFill
- Password: Block password proximity requests
- Password: Block password sharing

To learn more about these settings, see [iOS](device-restrictions-ios.md) and [macOS](device-restrictions-macos.md) device restriction settings.

### Device enrollment

#### Select apps tracked on the Enrollment Status Page<!-- 2531007 -->
You can choose which apps are tracked on the enrollment status page. Until these apps are installed, the user can't use the device. For more information, see [Set up an enrollment status page](windows-enrollment-status.md).

#### Search for Autopilot device by serial number <!--2595788 -->
You can now search for Autopilot devices by serial number. To do so, choose **Device enrollment** > **Windows enrollment** > **Devices** > type a serial number in the **Search by serial number** box > press Enter.

#### Track installation of Office ProPlus <!--2620217 -->
Users can track the installation progress of [Office ProPlus](apps-add-office365.md) using the [Enrollment Status Page](windows-enrollment-status.md). For more information, see [Set up an enrollment status page](windows-enrollment-status.md).

#### Alerts for expiring VPP token or Company Portal license running low <!-- 2237572 -->
If you are using Volume Purchase Program (VPP) to pre-provision the Company Portal during DEP enrollment, Intune will alert you when the VPP token is about to expire and when the licenses for the Company Portal are running low.

### macOS Device Enrollment Program support for Apple School Manager accounts <!--3006133 -->
Intune now supports using the Device Enrollment Program on macOS devices for Apple School Manager accounts.  For more information, see [Automatically enroll macOS devices with Apple School Manager or Device Enrollment Program](device-enrollment-program-enroll-macos.md).

### New Intune device subscription SKU <!--3312071-->
To help lower the cost of managing devices in enterprises, a new device-based subscription SKU is now available. This Intune device SKU is licensed per device on a monthly basis. Price varies by the licensing program. It's available directly through the Office admin portal, and through the [Enterprise Agreement](https://www.microsoft.com/licensing/licensing-programs/enterprise?activetab=enterprise-tab:primaryr2) (EA), [Microsoft Products and Services Agreement](https://www.microsoft.com/licensing/mpsa/default) (MPSA), [Microsoft Open Agreements](https://partner.microsoft.com/licensing/licensing-agreements), and [Cloud Solution Provider](https://www.microsoftpartnercommunity.com/t5/Partnership-101/What-is-the-Cloud-Solution-Provider-CSP-program/td-p/2453) (CSP).

### Device management

#### Temporarily pause kiosk mode on Android devices to make changes <!-- 3041935 -->
When using Android devices in multi-app kiosk mode, an IT administrator may need to make changes to the device. This update includes new multi-app kiosk settings that allows an IT Administrator to temporarily pause kiosk-mode using a PIN, and get access to the entire device.
To see the kiosk settings, see [Android Enterprise device restrictions](device-restrictions-android-for-work.md).

#### Enable virtual home button on Android Enterprise kiosk devices  <!-- 3042021 -->
A new setting will allow users to tap a soft-key button on their device to switch between the Managed Home Screen app and other assigned apps on their multi-app kiosk device. This setting is particularly helpful in scenarios where a user's kiosk app does not respond appropriately to the "back" button. You'll be able to configure this setting for corporate-owned, single use Android devices. To enable or disable the **Virtual home button**, go to Intune in the Azure portal > Device configuration. Select a current device configuration profile or create a new one to edit its kiosk settings.
To see the kiosk settings, see [Android Enterprise device restrictions](device-restrictions-android-for-work.md).

## Week of November 12, 2018

### Network Access Control (NAC) support for Citrix SSO for iOS <!-- 3259404 -->

Citrix released an update to Citrix Gateway to allow Network Access Control (NAC) for Citrix SSO for iOS in Intune. You can opt in to include a device ID within a VPN profile in Intune, and then push this profile to your iOS devices. You will need to install the latest update to Citrix Gateway to use this functionality.

[Configure VPN settings on iOS devices](vpn-settings-ios.md#base-vpn-settings) provides more information on using NAC, including some additional requirements. 

## Week of November 5, 2018

### Support for iOS 12 OAuth in iOS email profiles <!--2155106 -->

Intune's iOS email profiles support iOS 12 Open Authorization (OAuth). To see this feature, create a new profile (**Device Configuration** > **Profiles** > **Create profile** > **iOS** for platform > **Email** for profile type), or update an existing iOS email profile. If you enable OAuth in a profile that's already deployed to users, then users are prompted to reauthenticate, and download their email again.

[iOS email profiles](email-settings-ios.md) has more information on using OAuth in an email profile.

### Autopilot support for hybrid Azure Active Directory joined devices (Preview) <!-- 1048100-->
You can now set up hybrid Azure Active Directory joined devices by using Autopilot. Devices must be joined to your organization's network to use the hybrid Autopilot feature. For more information, see [Deploy hybrid Azure AD joined devices using Intune and Windows Autopilot](windows-autopilot-hybrid.md).
This feature is rolling out across the user base over the next few days. Therefore, you might not be able to follow these steps until it rolls out to your account.

## Week of October 29, 2018

### App management

#### Require non-biometric PIN after a specified timeout <!-- 1506985 -->
By requiring a non-biometric PIN after an admin-specified timeout, Intune provides improved security for Mobile Application Management (MAM) enabled apps by restricting the use of biometric identification for access to corporate data. The settings affect users who rely on Touch ID (iOS), Face ID (iOS), Android Biometric, or other future biometric authentication methods to access their APP/MAM-enabled applications. These settings enable Intune admins to have more granular control over user access, eliminating cases where a device with multiple fingerprints or other biometric access methods can reveal corporate data to an incorrect user. In the Azure portal, open **Microsoft Intune**. Select **Client apps** > **App protection policies** > **Add a policy** > **Settings**. Locate the **Access** section for specific settings. For information about access settings, see [iOS settings](app-protection-policy-settings-ios.md#access-requirements) and [Android settings](app-protection-policy-settings-android.md#access-requirements).

#### Intune APP data transfer settings on iOS MDM enrolled devices <!-- 2244713 -->
You can separate the control of Intune APP data transfer settings on iOS MDM enrolled devices from specifying the enrolled user's identity, also known as the User Principal Name (UPN). Admins not using the IntuneMAMUPN will not observe a behavior change. When this functionality is available, admins using the IntuneMAMUPN to control data transfer behavior on enrolled devices should review the new settings and update their APP settings as needed.

#### Windows 10 Win32 apps <!-- 2617325 -->
You can configure your Win32 apps to be installed in user context for individual users, versus installing the app for all users of the device.

#### Windows Win32 apps and PowerShell scripts <!-- 2617330 -->
End users are no longer required to be logged in on the device to install Win32 apps or execute PowerShell scripts. 

#### Troubleshooting client app installation <!-- 1363711 -->
You can troubleshoot the installation success of client apps by reviewing the column labeled **App install** in the **Troubleshoot** blade. To view the **Troubleshoot** blade, in the Intune portal, select **Troubleshoot** under **Help and support**.

### Device configuration

#### Network access control support on iOS VPN clients <!-- 1333693 -->
With this update, there's a new setting to enable Network Access Control (NAC) when your create a VPN configuration profile for Cisco AnyConnect, F5 Access, and Citrix SSO for iOS. This setting allows the NAC ID of the device to be included in the VPN profile. Currently, there aren't any VPN clients or NAC partner solutions that support this new NAC ID, but we will keep you informed through our [support blog post](ttps://aka.ms/iOS12_and_vpn) when they do.

To use NAC, you'll need to:
1. Opt in to allow Intune to include device IDs in VPN profiles
2. Update your NAC provider software/firmware, using guidance directly from your NAC provider

For information on this setting within an iOS VPN profile, see [Add VPN settings on iOS devices in Microsoft Intune](vpn-settings-ios.md). For more information on network access control, see [Network access control (NAC) integration with Intune](network-access-control-integrate.md). 

Applies to: iOS

#### Remove an email profile from a device, even when there's only one email profile <!-- 1818139 -->
Previously, you couldn't remove an email profile from a device *if* it's the only email profile. With this update, this behavior changes. Now, you can remove an email profile, even if it's the only email profile on the device. 
See [Add email settings to devices using Intune](email-settings-configure.md) for details.

#### PowerShell scripts and AAD <!-- 2309469 -->
PowerShell scripts in Intune can be targeted to AAD device security groups.

#### New "Required password type" default setting for Android, Android enterprise<!-- 2649963 -->
When you create a new compliance policy (**Intune** > **Device compliance** > **Policies** > **Create policy** > **Android** or **Android enterprise** for Platform > System Security), the default value for **Required password type** changes:

From: Device default
To: At least numeric

Applies to: Android, Android Enterprise

To see these settings, go to [Android](compliance-policy-create-android.md) and [Android Enterprise](compliance-policy-create-android-for-work.md).

#### Use a pre-shared key in a Windows 10 Wi-Fi profile <!-- 2662938 -->
With this update, you can use a pre-shared key (PSK) with the WPA/WPA2-Personal security protocol to authenticate a Wi-Fi configuration profile for Windows 10. You can also specify the cost configuration for a metered network for devices on Windows 10 October 2018 update.

Currently, you must import a Wi-Fi profile, or create a custom profile to use a pre-shared key. [Wi-Fi settings for Windows 10](wi-fi-settings-windows.md) lists the current settings. 

#### Remove PKCS and SCEP certificates from your devices <!-- 3218390 -->
In some scenarios, PKCS and SCEP certificates remained on devices, even when removing a policy from a group, deleting a configuration or compliance deployment, or an admin updating an existing SCEP or PKCS profile. 
This update changes the behavior. There are some scenarios where PKCS and SCEP certificates are removed from devices, and some scenarios where these certificates remain on the device. 
See [Remove SCEP and PKCS certificates in Microsoft Intune](remove-certificates.md) for these scenarios.

#### Use Gatekeeper on macOS devices for compliance <!-- 2504381 -->
This update includes the macOS Gatekeeper to evaluate devices for compliance. To set the Gatekeeper property, [Add a device compliance policy for macOS devices](compliance-policy-create-mac-os.md).


### Device enrollment

#### Enrollment abandonment report <!-- 1382924 -->
A new report that provides details on abandoned enrollments is available under **Device enrollment** > **Monitor**. For more information, see [Company portal abandonment report](enrollment-report-company-portal-abandon.md).

#### New Azure Active Directory terms of use feature <!-- 2870393 -->
Azure Active Directory has a terms of use feature that you can use instead of existing Intune terms and conditions. The Azure AD terms of use feature provides more flexibility on which terms to show and when to show them, better localization support, more control in how terms are rendered and improved reporting. The Azure AD terms of use feature does require Azure Active Directory Premium P1 which is also part of the Enterprise Mobility + Security E3 suite. To learn more, see the [Manage your company's terms and conditions for user access article](terms-and-conditions-create.md).

#### Android Device Owner mode support <!--3188762-->
For Samsung Knox Mobile Enrollment, Intune now supports enrolling devices to the Android Device Owner mode of management. Users on WiFi or cellular networks can enroll with just a few taps when they turn on their devices for the first time. For more information, see [Automatically enroll Android devices by using Samsung's Knox Mobile Enrollment](android-samsung-knox-mobile-enroll.md).

### Device management
#### New settings for Software Updates   <!-- 1907869 -->  
- You can now configure some notifications to alert end-users about restarts that are required to finish installation of the latest software updates.   
- You can now configure a restart warning prompt for restarts that happen outside of work hours, which supports BYOD scenarios.

#### Group Windows Autopilot-enrolled devices by correlator ID <!-- 2075110 -->
Intune now supports grouping Windows devices by a correlator ID when enrolled using [Autopilot for existing devices](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/New-Windows-Autopilot-capabilities-and-expanded-partner-support/ba-p/260430) through Configuration Manager. The correlator ID is a parameter of the Autopilot configuration file. Intune will automatically set the [Azure AD device attribute enrollmentProfileName](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#using-attributes-to-create-rules-for-device-objects) to equal "OfflineAutopilotprofile-<correlator ID>". This allows arbitrary Azure AD dynamic groups to be created based off correlator ID via the enrollmentprofileName attribute for offline Autopilot enrollments. For more information, see [Windows Autopilot for existing devices](enrollment-autopilot.md#windows-autopilot-for-existing-devices).

#### Intune app protection policies <!-- 2984657 -->
Intune app protection policies allow you to configure various data protection settings for Intune protected apps, such as Microsoft Outlook and Microsoft Word. We’ve change the look and feel of these settings for both [iOS](app-protection-policy-settings-ios.md) and [Android](app-protection-policy-settings-android.md) to make it easier to find individual settings. There are three categories of policy settings:
- **Data relocation** - This group includes the data loss prevention (DLP) controls, like cut, copy, paste, and save-as restrictions. These settings determine how users interact with data in the apps.
- **Access requirements** - This group contains the per-app PIN options that determine how the end user accesses the apps in a work context.  
- **Conditional launch** - This group holds settings like the minimum OS settings, jailbreak and rooted device detection, and offline grace periods.  
  
The functionality of the settings doesn’t change, but it will be easier to find them when you work in the policy authoring flow.

### Intune apps

#### Intune will support a maximum package size of 8 GB for LOB apps <!-- 1727158 -->
Intune increased the maximum package size to 8 GB for Line-of-business (LOB) apps. For more information, see [Add apps to Microsoft Intune](apps-add.md).

#### Add custom brand image for Company Portal app <!-- 1916266 -->
As the Microsoft Intune admin, you can upload a custom brand image which will be displayed as a background image on the user's profile page in the iOS Company Portal app. For more information about configuring the Company Portal app, see [How to configure the Microsoft Intune Company Portal app](company-portal-app.md).

#### Intune will maintain the Office localized language when updating Office on end users machines <!-- 2971030 -->
When Intune installs Office on your end user's machines, end users automatically get the same language packs that they had with previous .MSI Office installations. For more information, see [Assign Office 365 apps to Windows 10 devices with Microsoft Intune](apps-add-office365.md).

### Monitor and troubleshoot

#### New Intune Support Experience in the Microsoft 365 Device Management portal <!-- 3076965 -->
We are rolling out a new Help and Support experience for Intune in the [Microsoft 365 Device Management portal]( http://devicemanagement.microsoft.com). The new experience lets you describe your problem in your own words and receive troubleshooting insight and web-based remediation content. These solutions are offered via a rule-based machine learning algorithm, driven by user inquiries.  

In addition to issue-specific guidance, you can also use the new case creation workflow to open a support case by email or phone.  

For customers who are part of the rollout, this new experience replaces the current Help and Support experience of a static set of pre-selected options that are based on the area of the console you are in when you open Help and Support.  

*This new Help and Support experience is being rolled out to some but not all tenants and is available in the Device Management portal. Participants for this new experience are randomly selected from the available Intune tenants. New tenants will be added as we expand the rollout.*  

For more information, see [Help and Support experience](get-support.md#help-and-support-experience) in How to get support for Microsoft Intune.  

### PowerShell module for Intune – Preview available <!-- 951068 -->
A new PowerShell module, which provides support for the Intune API through Microsoft Graph, is now available for preview on [GitHub]( https://aka.ms/intunepowershell). For details about how to use this module, see the README in that location. 


## Week of October 15, 2018

### PIN prompt when you change fingerprints or face ID on an iOS device  <!-- 2637704  -->
Users are now prompted for a PIN after making biometric changes on their iOS device. This includes changes to registered fingerprints or face ID. The timing of the prompt depends on how the configuration of the *Recheck access requirements after (minutes)* timeout.  When no PIN is set, the user is prompted to set one. 
 
This feature is only available for iOS, and requires the participation of applications that integrate the Intune APP SDK for iOS, version 9.0.1 or later. Integration of the SDK is necessary so that the behavior can be enforced on the targeted applications. This integration happens on a rolling basis and is dependent on the specific application teams. Some apps that participate include WXP, Outlook, Managed Browser, and Yammer.


## Week of October 1, 2018

### App management

#### Access to key profile properties using the company portal app <!-- 772203 -->
End users can now access key account properties and actions, such as password reset, from the Company portal app. 

#### 3rd-party keyboards can be blocked by APP settings on iOS <!-- 1248481 -->
On iOS devices, Intune admins can block the use of 3rd-party keyboards when accessing organization data in policy protected apps. When the Application Protection Policy (APP) is set to block 3rd-party keyboards, the device user receives a message the first time they interact with corporate data when using a 3rd-party keyboard. All options, other than the native keyboard, are blocked and device users will not see them. Device users will only see the dialog message once. 

#### User account access of Intune apps on managed Android and iOS devices <!-- 1248496 -->
As the Microsoft Intune admin, you can control which user accounts are added to Microsoft Office applications on managed devices. You can limit access to only allowed organization user accounts and block personal accounts on enrolled devices. 

#### Outlook iOS and Android app configuration policy <!--1828527 -->
You can now create an Outlook iOS and Android app configuration policy for iOS and Android for on-premises users that leverage Basic authentication with the ActiveSync protocol. Additional configuration settings will be added as they are enabled for the Outlook for iOS and Android.

#### Office 365 Pro Plus language packs <!-- 1833450 -->
As the Intune admin, you will be able to deploy additional languages for Office 365 Pro Plus apps managed through Intune. The list of available languages includes the **Type** of language pack (core, partial, and proofing). In the Azure portal, select **Microsoft Intune** > **Client apps** > **Apps** > **Add**. In the **App type** list of the **Add app** blade, select **Windows 10** under **Office 365 Suite**. Select **Languages** in the **App Suite Settings** blade.

####  Windows line-of-business (LOB) apps file extensions <!-- 1884873 -->
The file extensions for Windows LOB apps will now include *.msi*, *.appx*, *.appxbundle*, *.msix* and *.msixbundle*. You can add an app in Microsoft Intune by selecting **Client apps** > **Apps** > **Add**. The **Add app** pane is displayed which allows you to select the **App type**. For Windows LOB apps, select **Line-of-business** app as the app type, select the **App package file**, and then enter an installation file with the appropriate extension.

#### Windows 10 app deployment using Intune <!-- 2309001 -->
Building upon the existing support for line-of-business (LOB) apps and Microsoft Store for Business apps, administrators can use Intune to deploy most of their organization’s existing applications to end users on Windows 10 devices. Administrators can add, install, and uninstall applications for Windows 10 users in a variety of formats, such as MSIs, Setup.exe, or MSP. Intune will evaluate requirement rules before downloading and installing, notifying end users of the status or reboot requirements using the Windows 10 Action Center. This functionality will effectively unblock organizations interested in shifting this workload to Intune and the cloud. This feature is currently in public preview and we expect to add significant new capabilities to the feature over the next few months. 

#### End user device and app content menu <!-- 2771453 -->
End users can now use the context menu on device and apps to trigger common actions like renaming a device or checking compliance. 

#### Windows Company Portal keyboard shortcuts <!-- 2771518 -->
End users will now be able to trigger app and device actions in the Windows Company Portal using keyboard shortcuts (accelerators).

### Device configuration

#### Create DNS suffixes in VPN configuration profiles on devices running Windows 10<!-- 1333668 -->
When you create a VPN device configuration profile (**Device configuration** > **Profiles** > **Create profile** > **Windows 10 and later** platform > **VPN** profile type), you enter some DNS settings. With this update, you can also enter multiple **DNS suffixes** in Intune. When using DNS suffixes, you can search for a network resource using its short name, instead of the fully qualified domain name (FQDN). This update also lets you change the order of the DNS suffixes in Intune.
[Windows 10 VPN settings](vpn-settings-windows-10.md#dns-settings) lists the current DNS settings.
Applies to: Windows 10 devices

#### Support for always-on VPN for Android enterprise work profiles <!-- 1333705 -->
In this update, you can use Always-on VPN connections on Android enterprise devices with managed work profiles. Always-on VPN connections stay connected, or immediately reconnect when the user unlocks their device, when the device restarts, or when the wireless network changes. You can also put the connection in "lockdown" mode, which blocks all network traffic until the VPN connection is active.
You can enable Always-on VPN in **Device configuration** > **Profiles** > **Create profile** > **Android enterprise** for platform > **Device restrictions** > **Connectivity** settings.

#### Issue SCEP certificates to user-less devices <!-- 1744554 -->
Currently, certificates are issued to users. With this update, SCEP certificates can be issued to devices, including user-less devices such as kiosks (**Device configuration** > **Profiles** > **Create profile** > **Windows 10 and later** for platform > **SCEP certificate** for profile). 
Other updates include:
- The **Subject** property in an SCEP profile is now a custom textbox and can include new variables. 
- The **Subject alternative name (SAN)** property in an SCEP profile is now a table format and can include new variables. In the table, an admin can add an attribute and fill out the value in a custom textbox. The SAN will support the following attributes: 
  - DNS
  - Email address
  - UPN

  These new variables can be added with static text in a custom value textbox. For example, the DNS attribute can be added as `DNS = {{AzureADDeviceId}}.domain.com`.

  > [!NOTE]
  > Curly brackets, semicolons, and pipe symbols “ { } ; | ” will not work in the static text of the SAN. Curly brackets must only enclose one of the new device certificate variables to be accepted for either `Subject` or `Subject alternative name`. 

New device certificate variables:  

```
"{{AAD_Device_ID}}",
"{{Device_Serial}}",
"{{Device_IMEI}}",
"{{SerialNumber}}",
"{{IMEINumber}}",
"{{AzureADDeviceId}}",
"{{WiFiMacAddress}}",
"{{IMEI}}",
"{{DeviceName}}",
"{{FullyQualifiedDomainName}}",
"{{MEID}}",
```

> [!NOTE]
>  - `{{FullyQualifiedDomainName}}` only works for Windows and domain-joined devices. 
>  -  When specifying device properties such as IMEI, Serial Number, and Fully Qualified Domain Name in the subject or SAN for a device certificate, be aware that these properties could be spoofed by a person with access to the device. 

[Create a SCEP certificate profile](certificates-scep-configure.md#create-a-scep-certificate-profile) lists the current variables when creating an SCEP configuration profile. 

Applies to: Windows 10 and later and iOS, supported for Wi-Fi

#### Remotely lock uncompliant devices <!-- 2064495 -->
When a device is not compliant, you can create an action on the compliance policy that locks the device remotely. In Intune > **Device compliance**, create a new policy, or select an existing policy > **Properties**. Select **Actions for noncompliance** > **Add**, and choose to remotely lock the device.
Supported on: 
- Android
- iOS
- macOS
- Windows 10 Mobile 
- Windows Phone 8.1 and later 

#### Windows 10 and later Kiosk profile improvements in the Azure portal <!-- 2748224 -->
This update includes the following improvements to the Windows 10 Kiosk device configuration profile (**Device configuration** > **Profiles** > **Create profile** > **Windows 10 and later** for platform > **Kiosk preview** for profile type): 
- Currently, you can create multiple kiosk profiles on the same device. With this update, Intune will support only one kiosk profile per device. If you still need multiple kiosk profiles on a single device, you can use a Custom URI.
- In a **Multi-app kiosk** profile, you can select the application tile size and order for the **Start menu layout** in the application grid. If you prefer more customization, you can continue to upload an XML file.
- The Kiosk Browser settings are moving into the **Kiosk** settings. Currently, the **Kiosk web browser** settings have their own category in the Azure portal.
Applies to: Windows 10 and later




### Device enrollment

#### Apply Autopilot profile to enrolled Win 10 devices not already registered for Autopilot <!-- 1558983 -->
You can apply Autopilot profiles to enrolled Win 10 devices that have not already been registered for Autopilot. In the Autopilot profile, choose the **Convert all targeted devices to Autopilot** option to automatically register non-Autopilot devices with the Autopilot deployment service. Allow 48 hours for the registration to be processed. When the device is unenrolled and reset, Autopilot will provision it.

#### Create and assign multiple Enrollment Status  Page profiles to Azure AD groups <!-- 2526564 -->
You can now [create and assign](windows-enrollment-status.md) multiple Enrollment Status Page profiles to Azure ADD groups.

#### Migration from Device Enrollment Program to Apple Business Manager in Intune <!--2748613-->
Apple Business Manager (ABM) works in Intune and you can upgrade your account from Device Enrollment Program (DEP) to ABM. The process in Intune is the same. To upgrade your Apple account from DEP to ABM, go to [ https://support.apple.com/en-us/HT208817]( https://support.apple.com/en-us/HT208817).

### Alert and enrollment status tabs on the Device enrollment overview page <!--2748656-->
Alerts and enrollment failures now appear on separate tabs on the Device enrollment overview page.

### Device management

#### Restricts apps, and block access to company resources on Android devices <!-- 2451462  -->  
In **Device compliance** > **Policies** > **Create policy** > **Android** > **System Security**, there is a new setting under the *Device Security* section, named **Restricted apps**. The **Restricted apps** setting uses a compliance policy to block access to company resources if certain apps are installed on the device. The device is considered non-compliant until the restricted apps are removed from the device.
Applies to: 
- Android




## Week of September 24, 2018

### Microsoft 365 Device Management administration center <!-- 3078424 -->
One of the promises of Microsoft 365 is simplified administration, and over the years we’ve integrated the back-end Microsoft 365 services to deliver end-to-end scenarios such as Intune and Azure AD conditional access. The new [Microsoft 365 administration center](http://devicemanagement.microsoft.com) is the place to consolidate, simplify, and integrate the admin experience. The specialist workspace for Device Management provides easy access to all of the device and app management information and tasks that your organization needs. We expect this to become the primary cloud workspace for enterprise end user computing teams.

### Support for more third-party certification authorities (CA) <!-- 3093107 -->
By using the Simple Certificate Enrollment Protocol (SCEP), you can now issue new certificates and renew certificates on mobile devices using Windows, iOS, Android, and macOS.

### Intune moves to support iOS 10 and later <!-- 2454656 -->  
Intune enrollment, the Company Portal, and the managed browser now only support iOS devices running iOS 10 and later. To check for devices or users that are affected in your organization, go to Intune in the Azure portal > **Devices** > **All devices**. Filter by OS and then click **Columns** to surface OS version details. Ask these users to upgrade their devices to a supported OS version.  

If you have any of the devices listed below, or want to enroll any of the devices listed below, be aware that they only support iOS 9 and earlier.  To continue to access the Intune Company Portal, you must upgrade these devices to devices that support iOS 10 or later:  

* iPhone 4S 
* iPod Touch  
* iPad 2 
* iPad (3rd Generation) 
* iPad Mini (1st Generation)  

## Week of September 17, 2018

### App management

### Remove duplication of app protection status tiles <!-- 3083391 -->
The **User status for iOS** and the **User status for Android** tiles were present in both the **Client Apps - Overview** page, as well as the **Client Apps - App protection status** page. The status tiles have been removed from the **Client Apps - Overview** page to avoid duplication. 

## Week of August 27, 2018

### App management

#### Packet tunnel support for iOS per-app VPN profiles for custom and Pulse Secure connection types <!-- 1520957 -->
When using iOS per-app VPN profiles, you can choose to use app-layer tunneling (app-proxy) or packet-level tunneling (packet-tunnel). These options are available with the following connection types:
- Custom VPN
- Pulse Secure
If you are not sure which value to use, consult your VPN provider's documentation.

#### Delay when iOS software updates are shown on the device <!-- 1949583 -->
In Intune > **Software Updates** > **Update policies for iOS**, you can configure the days and times when you don't want devices to install any updates. In a future update, you'll be able to delay when a software update is visibly shown on the device, from 1-90 days. 
[Configure iOS update policies in Microsoft Intune](software-updates-ios.md) lists the current settings.

#### Office 365 ProPlus version <!-- 2213968 -->
When assigning the Office 365 ProPlus apps to Windows 10 devices using Intune, you will be able to select the version of Office. In the Azure portal, select **Microsoft Intune** > **Apps** > **Add App**. Then, select **Office 365 ProPlus Suite (Windows 10)** from the **Type** dropdown list. Select **App Suite Settings** to display the associated blade. Set the **Update Channel** to a value, such as **Monthly**. Optionally, remove other version of Office (msi) from end user devices by selecting **Yes**. Select **Specific** to install a specific version of Office for the selected channel on end user devices. At this point, you can select the **Specific version** of Office to use. The available versions will change over time. Therefore, when creating a new deployment, the versions available may be newer and not have certain older versions available. Current deployments will continue to deploy the older version, but the version list will be continually updated per channel. For more information, see [Overview of update channels for Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus).

#### Support for Register DNS setting for Windows 10 VPN <!-- 2282852 -->
With this update, you can configure Windows 10 VPN profiles to dynamically register the IP addresses assigned to the VPN interface with the internal DNS, without needing to use custom profiles.
For information about the current VPN profile settings available, see [Windows 10 VPN settings](vpn-settings-windows-10.md). 

#### The macOS Company Portal installer now includes the version number in the installer file name <!--2652728-->

#### iOS automatic app updates <!-- 2729759 -->
Automatic app updates work for both device and user licensed apps for iOS Version 11.0 and above.




### Device configuration

#### Windows Hello will target users and devices <!-- 1106609 -->
When you create a [Windows Hello for Business](windows-hello.md) policy, it applies to all users within the organization (tenant-wide). With this update, the policy can also be applied to specific users or specific devices using a device configuration policy (**Device Configuration** > **Profiles** > **Create profile** > **Identity Protection** > **Windows Hello for Business**).
In Intune in the Azure portal, the Windows Hello configuration and settings now exists in both **Device enrollment** and **Device configuration**. **Device enrollment** targets the entire organization (tenant-wide), and supports Windows AutoPilot (OOBE). **Device configuration** targets devices and users using a policy that's applied during check-in.
This feature applies to:  
- Windows 10 and later
- Windows Holographic for Business

#### Zscaler is an available connection for VPN profiles on iOS <!-- 1769858 -->
When you create an iOS VPN device configuration profile (**Device configuration** > **Profiles** > **Create profile** > **iOS** platform > **VPN** profile type), there are several connection types, including Cisco, Citrix, and more. This update adds Zscaler as a connection type. 
[VPN settings for devices running iOS](vpn-settings-ios.md) lists the available connection types.

#### FIPS mode for Enterprise Wi-Fi profiles for Windows 10 <!-- 1879077 -->
You can now enable Federal Information Processing Standards (FIPS) mode for Enterprise Wi-Fi profiles for Windows 10 in the Intune Azure portal. Be sure FIPS mode is enabled on your Wi-Fi infrastructure if you enable it in your Wi-Fi profiles.
[Wi-Fi settings for Windows 10 and later devices in Intune](wi-fi-settings-windows.md) shows you how to create a Wi-Fi profile.

#### Control S-mode on Windows 10 and later devices - public preview <!-- 1958649 -->
With this feature update, you can create a device configuration profile that switches a Windows 10 device out of S-mode, or prevent users from switching the device out of S-mode. This feature is in Intune > **Device configuration** > **Profiles** >  **Windows 10 and later** > **Edition upgrade and mode switch**.
[Introducing Windows 10 in S mode](https://www.microsoft.com/windows/s-mode) provides more information on S mode.
Applies to: the most recent [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) build (while in preview).


#### Windows Defender ATP configuration package automatically added to configuration profile <!-- 2144658 -->
When using [Advanced Threat Protection and onboarding](advanced-threat-protection.md#onboard-devices-using-a-configuration-profile) devices in Intune, you previously had to download a configuration package, and add it to your configuration profile. With this update, Intune automatically gets the package from Windows Defender Security Center, and adds it to your profile.
Applies to Windows 10 and later.

#### Require users to connect during device setup <!--2311457-->
You can now set device profiles to require that the device connects to a network before proceeding past the Network page during Windows 10 setup. While this feature is in preview, a Windows Insider build 1809 or later is required to use this setting.
Applies to: the most recent [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) build (while in preview).


#### Restricts apps, and block access to company resources on iOS and Android Enterprise devices <!-- 2451462 -->
In **Device compliance** > **Policies** > **Create policy** > **iOS** > **System Security**, there is a new **Restricted applications** setting. This new setting uses a compliance policy to block access to company resources if certain apps are installed on the device. The device is considered non-compliant until the restricted apps are removed from the device.
Applies to: iOS

#### Modern VPN support updates for iOS <!-- 2459928, 1819876, and 2650856 -->
This update adds support the following iOS VPN clients: 
- F5 Access (version 3.0.1 and higher)
- Citrix SSO
- Palo Alto Networks GlobalProtect version 5.0 and higher
Also in this update:
- Existing **F5 Access** connection type is renamed to **F5 Access Legacy** for iOS.
- Existing **Palo Alto Networks GlobalProtect** connection type is renamed to **Palo Alto Networks GlobalProtect (legacy)** for iOS.
Existing profiles with these connection types continue to work with their respective legacy VPN client. If you're using Cisco Legacy AnyConnect, F5 Access Legacy, Citrix VPN, or Palo Alto Networks GlobalProtect version 4.1 and earlier with iOS, you should move to the new apps. Do this as soon as possible to ensure that VPN access is available for iOS devices as they update to iOS 12.
For more information about iOS 12 and VPN profiles, see the [Microsoft Intune Support Team Blog](https://go.microsoft.com/fwlink/?linkid=2013806).

#### Export Azure classic portal compliance policies to recreate these policies in the Intune Azure portal <!-- 2469637 -->
Compliance policies created in the Azure classic portal will be deprecated. You can review and delete any existing compliance policies, however you can't update them. If you need to migrate any compliance policies to the current Intune Azure portal, you can export the policies as a comma-separated file (*.csv* file). Then, use the details in the file to recreate these policies in the Intune Azure portal.

> [!IMPORTANT]
> When the Azure classic portal retires, you will no longer be able to access or view your compliance policies. Therefore, be sure to export your policies and recreate them in the Azure portal before the Azure classic portal retires.

#### Better Mobile - New Mobile Threat Defense partner <!-- 22662717 -->
You can control mobile device access to corporate resources using conditional access based on risk assessment conducted by Better Mobile, a Mobile Threat Defense solution that integrates with Microsoft Intune.

### Device enrollment

#### Lock the Company Portal in single app mode until user sign-in <!--1067692 --> 
You now have the option to run the Company Portal in Single App mode if you authenticate a user through the Company Portal instead of Setup Assistant during DEP enrollment. This option locks the device immediately after Setup Assistant completes so that a user must sign in to access the device. This process makes sure that the device completes onboarding and is not orphaned in a state without any user tied.

#### Assign a user and friendly name to an Autopilot device <!--1346521 -->
You can now [assign a user to a single Autopilot device](enrollment-autopilot.md). Admins will also be able to give friendly names to greet the user when setting up their device with Autopilot.
Applies to: the most recent [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) build (while in preview).

#### Use VPP device licenses to pre-provision the Company Portal during DEP enrollment <!-- 1608345 -->
You can now use Volume Purchase Program (VPP) device licenses to pre-provision the Company Portal during Device Enrollment Program (DEP) enrollments. To do so, when you [create or edit an enrollment profile](device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile), specify the VPP token that you want to use to install the Company Portal. Make sure that your token doesn't expire and that you have enough licenses for the Company Portal app. In cases where the token expires or runs out of licenses, Intune will push the App Store Company Portal instead (this will prompt for an Apple ID).

#### Confirmation required to delete VPP token that is being used for Company Portal pre-provisioning <!-- 2237634 -->
A confirmation is now required to delete a Volume Purchase Program (VPP) token if it is being used to pre-provision the Company Portal during DEP enrollment.

#### Block Windows personal device enrollments <!-- 1849498 -->
You can [block Windows personal devices](enrollment-restrictions-set.md#set-device-type-restrictions) from enrolling with [mobile device management](windows-enroll.md) in Intune. Devices enrolled with [Intune PC agent](manage-windows-pcs-with-microsoft-intune.md) can't be blocked with this feature. This feature is rolling out over the next couple weeks so you might not see it immediately in the user interface.

#### Specify machine name patterns in an Autopilot profile <!--1849855-->
You can [specify a computer name template](enrollment-autopilot.md#create-an-autopilot-deployment-profile) to generate and set the [computer name](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) during Autopilot enrollment. Applies to: the most recent [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) build (while in preview).


#### For Windows Autopilot profiles, hide the change account options on the company sign-in page and domain error page <!--1901669 -->
There are [new Windows Autopilot profile options](enrollment-autopilot.md#create-an-autopilot-deployment-profile) for admins to hide the change account options on the company sign-in and domain error pages. Hiding these options requires Company Branding to be configured in Azure Active Directory. 
Applies to: the most recent [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) build (while in preview).



### Device management

#### Delete Jamf devices <!-- 2653306-->
You can delete JAMF-managed devices by going to **Devices** > choose the Jamf device > **Delete**.

#### Change terminology to "retire" and "wipe" <!-- 2175759 -->
To be consistent with the Graph API, the Intune user interface and documentation has changed the following terms:
- **Remove company data** will be changed to "retire"
- **Factory reset** will be changed to **wipe**

#### Confirmation dialog if admin tries to delete MDM Push Certificate <!-- 297909500-->
If anyone tries to delete an Apple MDM Push certificate, a confirmation dialog box displays the number of related iOS and macOS devices. If the certificate is deleted, these devices will need to be re-enrolled.

### Additional security settings for Windows installer <!-- 2282430 -->
You can allow users to control app installs. If enabled, installations that may otherwise be stopped due to a security violation would be permitted to continue. You can direct the Windows installer to use elevated permissions when it installs any program on a system. Additionally, you can enabled Windows Information Protection (WIP) items to be indexed and the metadata about them stored in an unencrypted location. When the policy is disabled, the WIP protected items are not indexed and do not show up in the results in Cortana or file explorer. The functionality for these options are disabled by default. 

### New user experience update for the Company Portal website <!--2000968 -->
We’ve added new features, based on feedback from customers, to the Company Portal website. You'll experience a significant improvement in existing functionality and usability from your devices. Areas of the site&ndash;such as device details, feedback and support, and device overview&ndash;have received a new, modern, responsive design. You'll also see:

- Streamlined workflows across all device platforms
- Improved device identification and enrollment flows
- More helpful error messages
- Friendlier language, less tech jargon
- Ability to share direct links to apps
- Improved performance for large app catalogs
- Increased accessibility for all users  

The [Intune Company Portal website documentation](https://docs.microsoft.com/intune-user-help/using-the-intune-company-portal-website) has been updated to reflect these changes. To view an example of the app enhancements, see [UI updates for Intune end-user apps](whats-new-app-ui.md).  

### Monitor and troubleshoot

#### Enhanced jailbreak detection in compliance reporting<!-- 2198738 -->
The enhanced jailbreak detection setting states now appears in all compliance reporting in the admin console.

### Role-based access control

#### Scope tags for policies <!--1081974 -->
You can [create scope tags](scope-tags.md) to limit access to Intune resources. Add a scope tag to a role assignment and then add the scope tag to a configuration profile. The role will only have access to resources with configuration profiles that have matching scope tags (or no scope tag).

## Week of August 14, 2018

### macOS support for Apple Device Enrollment Program <!-- 747651 -->
Intune now supports enrolling macOS devices into the Apple Device Enrollment Program (DEP). For more information, see [Automatically enroll macOS devices with Apple's Device Enrollment Program](device-enrollment-program-enroll-macos.md).

## Week of July 23, 2018

### App management

#### Line-of-business (LOB) app support for macOS <!-- 1895847 -->
Microsoft Intune allows macOS LOB apps to be deployed as **Required** or **Available with enrollment**. End users can get apps deployed as **Available** using the Company Portal for macOS or the [Company Portal website](https://portal.manage.microsoft.com).

#### iOS built-in app support for kiosk mode <!-- 2051098 -->
In addition to Store Apps and Managed Apps, you can now select a Built-In App (such as Safari) that runs in kiosk mode on an iOS device.

#### Edit your Office 365 Pro Plus app deployments <!-- 2150145 -->
As the Microsoft Intune admin, you have greater ability to edit your Office 365 Pro Plus app deployments. Additionally, you no longer have to delete your deployments to change any of the suite’s properties. In the Azure portal, select **Microsoft Intune** > **Client apps** > **Apps**. From the list of apps, select your Office 365 Pro Plus Suite.  


#### Updated Intune App SDK for Android is now available <!-- 2744271-->

An updated version of the Intune App SDK for Android is available to support the Android P release. If you are an app developer and use the Intune SDK for Android, you must install the updated version of the Intune app SDK to ensure that Intune functionality within your Android apps continue to work as expected on Android P devices. This version of the Intune App SDK provides a built-in plugin that performs the SDK updates. You do not need to rewrite any existing code that’s integrated. For details, see [Intune SDK for Android](https://github.com/msintuneappsdk/ms-intune-app-sdk-android). If you are using the old badging style for Intune, we recommend that you use the briefcase icon. For branding details, see [this GitHub repository](https://github.com/msintuneappsdk/intune-app-partner-badge).


### Device configuration

#### Create device compliance policy using Firewall settings on macOS devices <!-- 1497640 -->
When you create a new macOS compliance policy (**Device compliance** > **Policies** > **Create policy** > **Platform: macOS** > **System security**), there are some new **Firewall** settings available: 

- **Firewall**: Configure how incoming connections are handled in your environment.
- **Incoming connections**: **Block** all incoming connections except those required for basic internet services, such as DHCP, Bonjour, and IPSec. This setting also blocks all sharing services.
- **Stealth Mode**: **Enable** stealth mode to prevent the device from responding to probing requests. The device continues to answer incoming requests for authorized apps.

Applies to: macOS 10.12 and later

#### New Wi-Fi device configuration profile for Windows 10 and later <!-- 1879077 -->
Currently, you can import and export Wi-Fi profiles using XML files. With this update, you can create a Wi-Fi device configuration profile directly in Intune, just like some other platforms.

To create the profile, open **Device configuration** > **Profiles** > **Create Profile** > **Windows 10 and later** > **Wi-Fi**. 

Applies to Windows 10 and later.

#### Kiosk - obsolete is grayed out, and can't be changed <!-- 2149998 -->
The Kiosk (preview) feature (**Device configuration** > **Profiles** > **Create profile** > **Windows 10 and later** > **Device restrictions**) is obsolete, and replaced with [Kiosk settings for Windows 10 and later](kiosk-settings.md). With this update, the **Kiosk - Obsolete** feature is grayed out, and the user interface can't be changed or updated. 

To enable kiosk mode, see [Kiosk settings for Windows 10 and later](kiosk-settings.md).

Applies to Windows 10 and later, Windows Holographic for Business

#### APIs to use 3rd party certification authorities <!-- 2184013 -->
In this update, there is a Java API that enables third-party certificate authorities to integrate with Intune and SCEP. Then, users can add the SCEP certificate to a profile, and apply it to devices using MDM.

Currently, Intune supports [SCEP requests using Active Directory Certificate Services](certificates-scep-configure.md).

#### Toggle to show or not show the End Session button on a Kiosk browser <!-- 2455253 -->
You can now configure whether or not Kiosk browsers show the End Session button. You can see the control at **Device configuration** > **Kiosk (preview)** > **Kiosk Web Browser**. If turned on, when a user clicks the button, the app prompts for confirmation to end the session. When confirmed, the browser clears all browsing data and navigates back to the default URL.

#### Create an eSIM cellular configuration profile <!-- 2564077 -->
In **Device configuration**, you can create an eSIM cellular profile. You can import a file that contains cellular activation codes provided by your mobile operator. You can then deploy these profiles to your eSIM LTE enabled Windows 10 devices, such as the Surface Pro LTE and other eSIM capable devices.

Check to see if your [devices support eSIM profiles](https://support.microsoft.com/help/4020763/windows-10-use-esim-for-cellular-data).

Applies to Windows 10 and later. 




### Device enrollment

#### Automatically mark Android devices enrolled by using Samsung Knox Mobile Enrollment as "corporate". <!-- 2404851 -->
By default, Android devices enrolled using Samsung Knox Mobile Enrollment are now marked as **corporate** under **Device Ownership**. You don't need to manually identify corporate devices using IMEI or serial numbers prior to enrolling using Knox Mobile Enrollment.

### Device management

#### Bulk delete devices on devices blade <!-- 1793693 -->

You can now delete multiple devices at a time on the Devices blade. Choose **Devices** > **All devices** > select the devices you want to delete > **Delete**. For devices that can't be deleted, an alert will be displayed.

## Week of July 16, 2018  

### More opportunities to sync in the Company portal app for Windows  
The Company Portal app for Windows now lets you initiate a sync directly from the Windows taskbar and Start menu. This feature is especially useful if your only task is to sync devices and get access to corporate resources. To access the new feature, right-click the Company portal icon that's pinned to your taskbar or Start menu. In the menu options (also referred to as a jump list), select **Sync this device**. The Company Portal will open to the **Settings** page and initiate your sync. For a look at the new functionality see [What's new in the UI](whats-new-app-ui.md).   

### New browsing experiences in the Company portal app for Windows  

Now when browsing or searching for apps in the Company Portal app for Windows, you can toggle between the existing **Tiles** view and the newly added **Details** view. The new view lists application details such as name, publisher, publication date and installation status.  

The **Apps** page's **Installed** view lets you see details about completed and in-progress app installations. To see what the new view looks like, see [What's new in the UI](whats-new-app-ui.md).  
### Improved Company Portal app experience for device enrollment managers  
When a device enrollment manager (DEM) signs in to the Company Portal app for Windows, the app will now only list the DEM's current, running device. This improvement will reduce timeouts that previously occurred when the app tried to show all DEM-enrolled devices.  


## Week of July 9, 2018

### App management

### Block app access based on unapproved device vendors and models  <!-- 1425689 ! -->
The Intune IT admin can enforce a specified list of Android manufacturers, and/or iOS models through Intune App Protection Policies. The IT admin can provide a semicolon separated list of manufacturers for Android policies and device models for iOS policies. Intune App Protection Policies are for Android and iOS only. There are two separate actions that can be performed on this specified list:
- A block from app access on devices that are not specified.
- Or, a selective wipe of corporate data on devices that are not specified. 

The user will be unable to access the targeted application if the requirements through the policy are not met. Based on settings, the user may either be blocked, or selectively wiped of their corporate data within the app. On iOS devices, this feature requires the participation of applications (such as WXP, Outlook, Managed Browser, Yammer) to integrate the Intune APP SDK for this feature to be enforced with the targeted applications. This integration happens on a rolling basis and is dependent on the specific application teams. On Android, this feature requires the latest Company Portal. 

On end-user devices, the Intune client will take action based on a simple matching of the strings specified in the Intune blade for Application Protection Policies. This depends entirely on the value that the device reports. As such, the IT administrator is encouraged to ensure that the intended behavior is accurate. This can be accomplished by testing this setting based on a variety of device manufacturers and models targeted to a small user group. In Microsoft Intune, select **Client apps** > **App protection policies** to view and add app protection policies. For more information about app protection policies, see [What are app protection policies](app-protection-policy.md) and [Selectively wipe data using app protection policy access actions in Intune](app-protection-policies-access-actions.md).

### Access to macOS Company Portal pre-release build <!-- 1734766 -->
Using Microsoft AutoUpdate, you can sign up to receive builds early by joining the Insider program. Signing up will enable you to use the updated Company Portal before it’s available to your end users. For more information, see the [Microsoft Intune blog](https://blogs.technet.microsoft.com/intunesupport/2018/07/13/use-microsoft-autoupdate-for-early-access-to-the-macos-company-portal-app/).

## Week of July 2, 2018

### App management

#### Monitor iOS  app configuration status per device <!-- 880037 -->
As the Microsoft Intune admin, you can monitor iOS app configuration status for each managed device. From **Microsoft Intune** in the Azure portal, select **Devices** > **All devices**. From the list of managed devices, select a specific device to display a blade for the device. On the device blade, select **App configuration**.

#### Access actions for app protection policies <!-- 1483510 -->
You can configure app protection policies to explicitly wipe, block, or warn non-compliant devices. The *wipe* action removes your company’s corporate data from a device. If a wipe occurs, the device's user is notified of both the reason for the wipe and remediation steps. For some settings, like minimum OS version, you will be able to apply multiple actions, such as block and wipe. Note that these actions are triggered when the app is launched.

#### Selective wipe of organization's app data <!-- 1507030 -->
Administrators can now configure a selective wipe of the organization's data as a new action when the conditions of Application Protection Policies (APP) Access settings are not met.  This feature helps administrators automatically protect and remove sensitive organization data from applications based on pre-configured criteria.

#### Revoking an iOS app purchased through VPP <!-- 1777384 -->
As the Microsoft Intune admin, you can revoke all the licenses for a selected iOS app purchased through the volume-purchase program (VPP). You can notify users when a user licensed app is no longer assigned to them. Revoking an app license will not uninstall the related VPP app from the device. To uninstall a VPP app, you must change the assignment action to **Uninstall**. The reclaimed license count will be reflected in **Licensed Apps** node in the **App** workload of Intune. For more information related to iOS VPP apps, see [How to manage iOS apps purchased through a volume-purchase program with Microsoft Intune](vpp-apps-ios.md).

#### Updates to out-of-compliance messages in Company Portal app <!-- 1832222 -->
We revised the messages that device users see when a device is out-of-compliance. Messages  retain their original meanings but have been updated with friendlier language and less technical jargon. We also refreshed links to documentation and remediation steps to keep them up-to-date.
The following before and after text is one example of the improvements in messaging you'll see:
- **Before**: *This device hasn’t contacted the Intune service in the specified time period required by your IT admin. To resolve this issue, please open the company portal app on your device and click on the Check Compliance button.*
- **After**: *Your device has not checked in with your organization in a while. To reestablish a connection, open the Company Portal app on your device and tap Check Settings for your device.*

#### Revoke iOS VPP app license <!-- 1863797 -->
As the admin, you can reclaim an iOS VPP app license assigned to a user or device. Uninstalling an iOS VPP app will also allow you to reclaim the app license. Before uninstalling the app, the user or the device needs to be removed from the group to which the app is targeted. Removing the user or the device from the group avoids a reinstall of the app. Once these steps are complete, you can choose to assign the app license to another user or device. For more information about iOS VPP app licenses, see [Manage iOS volume-purchased apps in Microsoft Intune](vpp-apps-ios.md).

### Device configuration

#### Select device categories by using the Access Work or School settings <!-- 1058963 eenotready --> 
If you've enabled [device group mapping](https://docs.microsoft.com/intune/device-group-mapping), users on Windows 10 will now be prompted to select a device category after enrolling through the **Connect** button in **Settings** > **Accounts** > **Access work or school**. 

#### Use sAMAccountName as the account username for email profiles <!-- 1500307 -->
You can use the on-premises **sAMAccountName** as the account username for email profiles for Android, iOS, and Windows 10. You can also get the domain from the `domain` or `ntdomain` attribute in Azure Active Directory (Azure AD). Or, enter a custom static domain.

To use this feature, you must sync the `sAMAccountName` attribute from your on-premises Active Directory environment to Azure AD.

Applies to [Android](email-settings-android.md), [iOS](email-settings-ios.md), [Windows 10 and later](email-settings-windows-10.md)

#### See device configuration profiles in conflict <!-- 1556983 -->
In **Device Configuration**, a list of the existing profiles is shown. With this update, a new column is added that provides details on profiles that have a conflict. You can select a conflicting row to see the setting and profile that has the conflict. 

More on [manage configuration profiles](device-profile-monitor.md#view-conflicts).

#### New status for devices in device compliance <!-- 2308882 -->
In **Device compliance** > **Policies** > select a policy > **Overview**, the following new states are added:
- succeeded
- error
- conflict
- pending
- not-applicable
An image that shows the device count of a different platform is also shown. For example, if you're looking at an iOS profile, the new tile shows the count of non-iOS devices that are also assigned to this profile. See [Device compliance policies](compliance-policy-monitor.md#view-status-of-device-policies).

#### Device compliance supports 3rd party anti-virus solutions <!-- 2325484 -->
When you create a device compliance policy (**Device compliance** > **Policies** > **Create policy** > **Platform: Windows 10 and later** > **Settings** > **System Security**), there are new **[Device Security](compliance-policy-create-windows.md#windows-10-and-later-policy-settings)** options: 
- **Antivirus**: When set to **Require**, you can check compliance using antivirus solutions that are registered with Windows Security Center, such as Symantec and Windows Defender. 
- **AntiSpyware**: When set to **Require**, you can check compliance using antispyware solutions that are registered with Windows Security Center, such as Symantec and Windows Defender. 

Applies to: Windows 10 and later 

### Device enrollment

####  Devices without profiles column in the list of enrollment program tokens <!-- 1853904 -->
In the enrollment program tokens list, there is a new column showing the number of devices without a profile assigned. This helps admins assign profiles to these devices before handing them out to users. To see the new column, go to **Device enrollment** > **Apple enrollment** > **Enrollment program tokens**.

### Device management

#### Google name changes for Android for Work and Play for Work <!--842873 -->
Intune has updated "Android for Work" terminology to reflect Google branding changes. The terms "Android for Work" and "Play for Work" are no longer be used. Different terminology is used depending on the context:
- "Android enterprise" refers to the overall modern Android management stack.
- "Work profile" or "Profile Owner" refers to BYOD devices managed with work profiles.
- "Managed Google Play" refers to the Google app store.

#### Rules for removing devices <!-- 1609459 -->
New rules are available that let you automatically remove devices that haven't checked in for a number of days that you set. To see the new rule, go to the **Intune** pane, select **Devices**, and select **Device cleanup rules**.

#### Corporate-owned, single use support for Android devices <!-- 1630973 -->

Intune now supports highly-managed, locked-down, kiosk-style Android devices. This allows admins to further lock down the usage of a device to a single app or small set of apps, and prevents users from enabling other apps or performing other actions on the device. To set up Android kiosk, go to Intune > **Device enrollment** > **Android enrollment** > **Kiosk and task device enrollments**. For more information, see [Set up enrollment of Android enterprise kiosk devices](android-kiosk-enroll.md).

#### Per-row review of duplicate corporate device identifiers uploaded <!-- 2203794-->
When uploading corporate IDs, Intune now provides a list of any duplicates and gives you the option to replace or keep the existing information. The report will appear if there are duplicates after you choose **Device enrollment** > **Corporate Device Identifiers** > **Add Identifiers**. 

#### Manually add corporate device identifiers <!-- 2203803 -->
You can now manually add corporate device IDs. Choose **Device enrollment** > **Corporate Device Identifiers** > **Add**. 

## Week of June 25, 2018

### Pradeo - New Mobile Threat Defense partner <!-- 1169249 -->

You can control mobile device access to corporate resources using conditional access based on risk assessment conducted by Pradeo, a Mobile Threat Defense solution that integrates with Microsoft Intune.

## Week of June 18, 2018

### Microsoft Edge mobile support for Intune app protection policies <!-- 1817882 -->

The Microsoft Edge browser for mobile devices now supports app protection policies defined in Intune.

## Week of June 11, 2018

### Use FIPS mode with the NDES Certificate connector <!-- 1333688 -->
When you install the NDES Certificate connector on a computer with Federal Information Processing Standard (FIPS) mode enabled, issuing and revoking certificates didn't work as expected. With this update, support for FIPS is included with the NDES Certificate connector. 

This update also includes:

- The NDES Certificate connector requires .NET 4.5 Framework, which is automatically included with Windows Server 2016 and Windows Server 2012 R2. Previously, .NET 3.5 Framework was the minimum required version.
- TLS 1.2 support is included with the NDES Certificate connector. So if the server with NDES Certificate connector installed supports TLS 1.2, then TLS 1.2 is used. If the server doesn't support TLS 1.2, then TLS 1.1 is used. Currently, TLS 1.1 is used for authentication between the devices and server.

For more information, see [Configure and use SCEP certificates](certificates-scep-configure.md) and [Configure and use PKCS certificates](certficates-pfx-configure.md).

## Week of June 4, 2018

### App management

#### Retrieve the associated app user model ID (AUMID) for Microsoft Store for Business apps in kiosk mode <!-- 1560077 ! -->
Intune can now retrieve the app user model ids (AUMIDs) for Microsoft Store for Business (WSfB) apps to provide improved configuration of the kiosk profile.

For more information about Microsoft Store for Business apps, see [Manage apps from Microsoft Store for Business](windows-store-for-business.md).

#### New Company Portal branding page <!-- 1916370 -->
The Company Portal branding page has a new layout, messages, and tooltips.


### Device configuration

#### Support for Palo Alto Networks GlobalProtect VPN profiles <!-- 1333680 ! -->
With this update, you can choose Palo Alto Networks GlobalProtect as a VPN connection type for VPN profiles in Intune (**Device configuration** > **Profiles** > **Create profile** > **Profile type** > **VPN**). In this release, the following platforms are supported: 

- iOS
- Windows 10

#### Additions to Local Device Security Options settings <!-- 1403702 -->
You can now configure additional Local Device Security Options settings for Windows 10 devices. Additional settings are available in the areas of Microsoft Network Client, Microsoft Network Server, Network access and security, and Interactive logon. Find these settings in the Endpoint Protection category when you create a Windows 10 device configuration policy.

#### Enable kiosk mode on Windows 10 devices <!-- 1560072 ! -->
On Windows 10 devices, you can create a configuration profile and enable kiosk mode (**Device Configuration** > **Profiles** > **Create profile** > **Windows 10** > **Device Restrictions** > **Kiosk**). In this update, the **Kiosk (preview)** setting is renamed to **Kiosk (obsolete)**. **Kiosk (obsolete)** is no longer recommended for use, but will continue to function until the July update. **Kiosk (obsolete)** is replaced by the new **Kiosk** profile type (**Create profile** > **Windows 10** > **Kiosk (preview)**), which will contain the settings to configure Kiosks on Windows 10 RS4 and later.

Applies to Windows 10 and later.

#### Device profile graphical user chart is back <!-- 2160133 -->
While improving the numeric counts shown on the device profile graphical chart (**Device configuration** > **Profiles** > select an existing profile > **Overview**), the graphical user chart was temporarily removed.

With this update, the graphical user chart is back, and shown in the Azure portal.

### Device enrollment

#### Support for Windows Autopilot enrollment without user authentication <!-- 1165118 -->
Intune now supports Windows Autopilot enrollment without user authentication. This is a new option in the Windows Autopilot deployment profile "Autopilot Deployment mode" set to "Self-Deploying".  The device must be running Windows 10 Insider Preview Build 17672 or later and possess a TPM 2.0 chip to successfully complete this type of enrollment. Since no user authentication is required, you should only assign this option to devices that you have physical control over.

#### New language/region setting when configuring OOBE for Autopilot <!-- 1821766 -->
A new configuration setting is available to set the language and region for Autopilot profiles during the Out of Box Experience. To see the new setting, choose **Device enrollment** > **Windows enrollment** > **Deployment profiles** > **Create profile** > **Deployment mode** = **Self-deploying** > **Defaults configured**.

#### New setting for configuring device keyboard <!-- 1821768 -->
A new setting will be available to configure the keyboard for Autopilot profiles during the Out of Box Experience. To see the new setting, choose **Device enrollment** > **Windows enrollment** > **Deployment profiles** > **Create profile** > **Deployment mode** = **Self-deploying** > **Defaults configured**.

#### Autopilot profiles moving to group targeting <!-- 1877935 -->
AutoPilot deployment profiles can be assigned to Azure AD groups containing AutoPilot devices.

### Device management

#### Set compliance by device location <!-- 851881 ! -->
In some situations, you may want to restrict access to corporate resources to a specific location, defined by a network connection. You can now create a compliance policy (**Device compliance** > **Locations**) based on the IP address of the device. If the device moves outside the IP range, then the device cannot access corporate resources.

Applies to: Android devices 6.0 and higher, with the updated Company Portal app

#### Prevent consumer apps and experiences on Windows 10 Enterprise RS4 Autopilot devices<!-- 1621980 -->
You will be able to prevent the installation of consumer apps and experiences on your Windows 10 Enterprise RS4 AutoPilot devices. To see this feature, go to **Intune** > **Device configuration** > **Profiles** > **Create profile** > **Platform** = **Windows 10 or later** > **Profile type** = **Device restrictions** > **Configure** > **Windows Spotlight** > **Consumer features**. 

#### Uninstall the latest from Windows 10 software updates <!-- 1732948 -->
Should you discover a breaking issue on your Windows 10 machines, you can choose to uninstall (rollback) the latest feature update or the latest quality update. Uninstalling a feature or quality update is only available for the servicing channel the device is on. Uninstalling will trigger a policy to restore the previous update on your Windows 10 machines. For feature updates specifically, you can limit the time from 2-60 days that an uninstall of the latest version can be applied. To set software update uninstall options, select **Software updates** from the **Microsoft Intune** blade within the Azure portal. Then, select **Windows 10 Update Rings** from the **Software updates** blade. You can then choose the **Uninstall** option from the **Overview** section.

#### Search all devices for IMEI and serial number <!-- 1793685 -->
You can now search for IMEI and serial numbers on the All devices blade (email, UPN, device name, and management name are still available). In Intune, choose **Devices** > **All devices** > enter your search in the search box.

#### Management name field will be editable <!-- 1875989 -->
You can now edit the management name field on a device’s **Properties** blade. To edit this field, choose **Devices** > **All devices** > choose the device > **Properties**. You can use the management name field to uniquely identify a device.

#### New All devices filter: Device category <!-- 1878520 -->
You can now filter the **All devices** list by device category. To do so, choose **Devices** > **All devices** > **Filter** > **Device category**.

#### Use TeamViewer to screen share iOS and MacOS devices <!-- 1985547 -->
Administrators can now connect to [TeamViewer](device-profile-android-teamviewer.md), and start a screen sharing session with iOS and macOS devices. iPhone, iPad, and macOS users can share their screens live with any other desktop or mobile device. 

#### Multiple Exchange Connector support <!-- 2070451 -->
You're no longer limited to one Microsoft Intune Exchange Connector per tenant. Intune now supports multiple Exchange Connectors so that you can set up Intune conditional access with multiple on-premises Exchange organizations.

With an Intune on-premises Exchange connector, you can manage device access to your on-premises Exchange mailboxes based on whether a device is enrolled in Intune and complies with Intune device compliance policies. To set up a connector, you download the Intune on-premises Exchange connector from the Azure portal and install it on a server in your Exchange organization. On the Microsoft Intune dashboard, choose **On-premises access**, and then under **Setup**, choose **Exchange ActiveSync connector**. Download the Exchange on-premises connector and install it on a server in your Exchange organization. Now that you're no longer limited to one Exchange connector per tenant, if you have additional Exchange organizations, you can follow this same process to download and install a connector for each additional Exchange organization.

#### New device hardware detail: CCID <!-- 2156657 -->
The Chip Card Interface Device (CCID) information is now included for each device. To see it, choose **Devices** > **All devices** > choose a device > **Hardware**> check under **Network details**>

#### Assign all users and all devices as scope groups <!-- 2196803 -->
You can now assign all users, all devices, and all users and all devices in scope groups. To do this, choose **Intune roles** > **All roles** > **Policy and profile manager** > **Assignments** > choose an assignment > **Scope (groups)**.

#### UDID information now included for iOS and macOS devices <!-- 2219806 -->
To see the Unique Device Identifier (UDID) for iOS and macOS devices, go to **Devices** > **All devices** > choose a device > **Hardware**. UDID is only available for corporate devices (as set under **Devices** > **All devices** > choose a device > **Properties** > **Device ownership**).

### Intune apps

#### Improved troubleshooting for app installation <!-- 928990 -->
On Microsoft Intune MDM-managed devices, sometimes app installations can fail. When these app installs fail, it can be challenging to understand the failure reason or troubleshoot the issue. We're shipping a Public Preview of our App Troubleshooting features. You will notice a new node under each individual device called **Managed Apps**. This lists the apps that have been delivered via Intune MDM. Inside the node, you'll see a list of app install states. If you select an individual app, you'll see the troubleshooting view for that specific app. In the troubleshooting view, you'll see the end-to-end lifecycle of the app, such as when the app was created, modified, targeted, and delivered to a device. Additionally, if the app install was not successful, you'll be presented with the error code and a helpful message about the cause of the error. 

#### Intune app protection policies and Microsoft Edge <!-- 1818968 -->
The Microsoft Edge browser for mobile devices (iOS and Android) now supports Microsoft Intune app protection policies. Users of iOS and Android devices who sign in with their corporate Azure AD accounts in the Edge application will be protected by Intune. On iOS devices, the **Require managed browser for web content** policy will allow users to open links in Microsoft Edge when it is managed.

## Week of May 14, 2018

### App management

#### Require installation of policies, apps, certificate and network profiles <!-- 1553555 -->

Admins can block end users from accessing the Windows 10 RS4 desktop until Intune installs  policies, apps, and certificate and network profiles during the provisioning of AutoPilot devices. For more info, see [Set up an enrollment status page](windows-enrollment-status.md).

#### Configuring your app protection policies <!-- 2144597 Part 2 -->

In the Azure portal, instead of going to the Intune App Protection service blade, you now just go to Intune. There is now only one location for app protection policies within Intune. Note that all of your app protection policies are on the **Mobile app** blade in Intune under **App protection policies**. This integration helps to simplify your cloud management administration. Remember, all app protection policies are already in Intune and you can modify any of your previously configured policies. Intune App Policy Protection (APP) and Conditional Access (CA) policies are now under **Conditional access**, which can be found under the **Manage** section in the **Microsoft Intune** blade or under the **Security** section in the **Azure Active Directory** blade. For more information about modifying conditional access policies, see [Conditional access in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal). For additional information, see [What are app protection policies?](app-protection-policy.md)

## Week of May 7, 2018

### App management

#### Samsung Knox mobile enrollment support <!--1112863-->

When using Intune with Samsung Knox Mobile Enrollment (KME), you can enroll large numbers of company-owned Android devices. Users on WiFi or cellular networks can enroll with just a few taps when they turn on their devices for the first time. When using the Knox Deployment App, devices can be enrolled using Bluetooth or NFC. For more information, see [Automatically enroll Android devices by using Samsung's Knox Mobile Enrollment](android-samsung-knox-mobile-enroll.md).

#### Requesting help in the Company Portal for Windows 10 <!-- 1874137 -->

The Company Portal for Windows 10 will now send app logs directly to Microsoft when the user initiates the workflow to get help with an issue. This will make it easier to troubleshoot and resolve issues that are raised to Microsoft.

## Notices

### Check your “Delay Visibility of Software updates” setting in Intune
We shared in MC171466 that we were moving a few settings around in the console. With the March update to Intune, we'll completely remove the “Delay Visibility of Software updates” setting from the iOS update policy blade. This will not change the way your scheduled software updates apply but it may affect how long the visibility of an update is delayed for end users. You may need to take action before the end of March if you use this setting.

#### How does this affect me?
After the February Intune service update, you’ll notice that the setting appears both in Device restriction profiles in the console and in iOS update policies in the Software update blade. When you see this change reflected in the console, here’s what you may need to do.
• For existing Update policies for iOS: If you have custom configured this setting to anything other than the default 30 days, and want your existing configurations for the Delay visibility setting to continue to apply after the end of March, you’ll have to create a new iOS device restriction profile. Here, the Delay visibility setting will need to have the same values as in the existing iOS update policy and be targeted to the same groups. After the March service update, you will no longer be able to edit values for this setting in existing iOS update policies since it will no longer be visible in this blade. You will configure this setting in the new profiles instead.
If the value for number of days you can delay visibility does not match in both locations for custom configured setting values, the Delay Visibility setting will not work, and end users will see the update on their devices as soon as it is available. This may have minimal impact for most customers since the other settings in the Software Update Policy blade have always taken precedence over this setting in the console.
• For new update policies for iOS: If you try to create new policies in the Software updates blade after the Intune February service update, you will see this setting grayed out. You’ll see a note in the console redirecting you to the Device configuration blade if you wish to delay visibility of updates.

#### What can I do to prepare for this change?
You do not need to take action if you do not use this setting or do not want to delay visibility of software updates for your end users.

If you wish to delay visibility of updates, start configuring the setting in new profiles in the Device Configuration blade under Device Restrictions > General. If you have this setting custom configured in existing iOS update policies, create a new equivalent device restriction profile with the same value for “days” to delay visibility of updates to your users, after the February update and before the March update rolls out.
You may want to update your IT Pro guidance and inform your helpdesk.
See our support blog post at Additional Information for details on how to configure this setting.
 
#### Additional Information
https://aka.ms/Delay_visibility_setting_iOS

###  Upcoming change to the Intune Data Warehouse API
We will be making two changes during the 1903 timeframe:
- Beta Filter Deprecation<br>
    Deprecation of unsupported beta filters instantiated.   
- 1.0 changes reflecting back to beta<br>
    Changes made to our v1.0 collections will now be reflected in beta.  


###Plan for Change: Workflow changes for iOS 12 enrollment in Intune
Apple has announced some changes related to iOS devices enrolling into Mobile Device Management (MDM) services. The change will likely be seen in the spring 2019 release of iOS as well as all future iOS releases.

####How does this affect me?
If your end users upgrade their devices to this new version of iOS 12 in the spring, know that there is a modified workflow and they will need to take additional steps to complete enrollment into Intune. When Apple introduces these changes, end users will have to:
•            Begin the enrollment process in the Company Portal app to download a management profile
•            Go to Settings > General > Profiles
•            Select the correct profile and click through to Install
•            Return to the Company Portal to complete enrollment 

Devices that are already enrolled and upgrade to the new iOS release should not be affected unless they are unenrolled and need a fresh enrollment.
Enrollment experience on devices running iOS 12.1 or prior will not change with this new release by Apple.

####What can I do to prepare for this change?
You should plan to upgrade your documentation and your end user guidance. You may also want to let your helpdesk know of these changes. We’ll keep you informed through the Message Center and our What’s New page when this change goes live.

Click Additional Information for a support blog post with screenshots and a video of the expected enrollment flow.

####Additional Information
https://aka.ms/iOS_enrollment_changes

### Plan for Change: User experience update to Intune Company Portal app for iOS
We’re excited to share that Intune will soon be releasing a major user experience update to the iOS Company Portal app. The update will feature a visual redesign of the home page with advanced filters and faster access to apps and books.

#### How does this affect me?
This user experience update, while maintaining current iOS Company Portal functionality, will feature:
- A home page with native iOS look and feel 
- Filtering capabilities on content listings and search including the ability to filter by content type (apps or ebooks) and availability (device management required or available without enrollment)
- Ability to search ebooks
- Search history for apps and ebooks
If you’re part of the Apple TestFlight program, you will be notified about the pre-release version of Intune’s updated iOS Company Portal app when it becomes available. If you’re not part of the Apple TestFlight program, it’s not too late to register. Registering will enable you to use the updated Company Portal app before it’s available to your end users. You will also have the opportunity to provide feedback directly to the Intune team.  

#### What can I do to prepare for this change?
You do not need to take any action; these changes will be released in an upcoming iOS CP app release. 

#### Additional Information
[https://aka.ms/cp_update_iOS](https://aka.ms/cp_update_iOS)


### Reminder: Removal of existing Exchange Online to Intune connectors
We shared in MC165575 that we would be removing the Exchange Online to Intune ‘Service to Service’ connector functionality in an upcoming update. With the February update to the Intune service, we’ll disable the button to set up new connectors. We are planning to remove all existing Exchange Online to Intune connectors in March 2019.
 
#### How does this affect me?
You are receiving this message since our records indicate that you may be using the ‘Service to Service’ connector functionality in your environment. 

The ‘Service to Service’ connector supports Intune management of Exchange Active Sync Only devices for Exchange Online and does not support on-premises infrastructure. This connector, due to the way it displayed in the console, appears to be necessary for Conditional Access (CA), when in reality, it is not needed for CA. You may have been using this connector to understand the usage of Exchange Online prior to applying Conditional Access. This information is already provided by the Microsoft 365 Admin Center. Here, you’ll find provides usage reports for Exchange Online including the app type being used for between 7 and 180 days. For more information see Office 365 Reports in the Admin Center - Email apps usage  

If you use this connector in your environment, you won’t be able to monitor or wipe Exchange Active Sync Only devices in Intune after connectors have been disabled in February. There is no anticipated impact to your end users during this change.
 
#### What can I do to prepare for this change?
If you have the Service to Service connector set up and have Exchange Active Sync Only devices, switch to other methods of managing your devices. You have the following options:
•	Enroll devices in Mobile Device Management (MDM) 
•	Use Intune App Protection Policies to manage your devices
•	Use Exchange controls as outlined in documentation here
  
#### Additional Information
https://docs.microsoft.com/intune/exchange-service-connector-configure
 


### Plan for change: Performance updates to Intune for Education <!--1750215-->
We’re adding some updates to Intune for Education to increase speed and reliability when you assign settings to your users or devices. As part of this change, towards the end of November, we’ll be moving your policies or settings assignments to new groups.

#### How does this affect me?

As an Intune for Education customer, you have two dynamic Azure Active Directory (Azure AD) groups: “All Users” and “All Devices”. With these updates, these “All Users” and “All devices” Azure AD groups will not be visible in the Intune for Education console. They will, however, still be visible in the Intune on Azure console and will be renamed as “All Users (Obsolete, do not use)” and “All Devices (Obsolete, do not use)”.

When the updates roll out, you will no longer need to use Azure AD groups to assign apps and settings in Intune. Instead, we will move your Settings assignments to new groups in the Intune for Education console that we’ll create for you that will still show up as “All Users” and “All Devices” as before. These changes are in the backend, so you will not notice anything different in the Intune for Education console. There is no impact anticipated to your end users or enrolled devices. 

#### What do I need to do to prepare for this change?
You do not need to do anything while we move your policy assignments. If you currently assign policies in the Intune for Education console, continue doing so.

If you currently assign policies to the Azure AD groups mentioned above in Intune on Azure, start assigning these to the All Users and All Devices group in the Intune for Education console instead. When you see the Azure AD groups renamed as obsolete in the console, stop assigning policies in Azure AD. If you are not currently using the renamed groups for any other purpose, you should delete them.


### Take action: Please update your Android device restriction or compliance policy password settings in Intune
Intune will be removing the available password type “device default” for Android 4.4 and higher devices. Due to differences in Android platforms and device defaults, that policy is often treated as optional by the device. To clear up confusion on when this setting is enforced on Android, we’ll remove this setting from the UI in an upcoming release. 
#### How does this affect me?
- If your intent is to require a password on the devices, we recommend instead of using “device default” you edit your Android platform profile(s) to clearly articulate the required password type.
- If your intent is to let your end user to decide on whether to create a password, select the “Not configured” button. 
When we remove this setting from the UI, if the setting is still set, you will be prompted to choose a value other than “Device default” on your next edit of the profile.
What do I need to do to prepare for this change?
Review the password settings in your Android and Android enterprise device restriction and compliance policies. These are listed under System security for Compliance policies and under either Device password or Work profile settings for Device restrictions. Additional information has a link to more details and screenshots for where these settings are configured.
#### Additional information
https://aka.ms/PasswordSettings 

