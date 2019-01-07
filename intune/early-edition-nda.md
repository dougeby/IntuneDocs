---
# required metadata

title: Early edition - Microsoft Intune
titlesuffix: 
description: Microsoft Intune early edition
keywords:
author: ErikjeMS  
ms.author: erikje
manager: dougeby
ms.date: 12/3/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d

# optional metadata

ROBOTS: NOINDEX,NOFOLLOW
#audience:
#ms.devlang:
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: seodec18
---

# The early edition for Microsoft Intune - December 2018

> [!Note]
> NDA notification: The following changes are under development for Intune. This information is shared under NDA on a very limited basis. Do not post any of this information on social media or public websites such as Twitter, UserVoice, Reddit, and so on. 

The **early edition** provides a list of features, shared under NDA, that are coming in upcoming releases of Microsoft Intune. This information is provided on a limited basis and is subject to change. Do not tweet, post on UserVoice, or otherwise share this information outside of your company. Some features listed here are at risk of not making the cutoff dates and may be delayed until a future release. Other features are being tested in a pilot (flighting) to ensure they're customer-ready. Reach out to your Microsoft product group contact if you have any questions or concerns.

This page is updated periodically. Check back for additional updates.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## Intune in the Azure portal

<!-- 1812 start -->

### Android Enterprise APP-WE app deployment <!-- 1171203 -->
For Android devices in a non-enrolled App Protection Policy Without Enrollment (APP-WE) deployment scenario, you'll be able to use managed Google Play to deploy store apps and LOB apps to users. Specifically, IT can provide end users with an app catalog and installation experience that no longer requires end users to loosen the security posture of their devices by allowing installations from unknown sources. In addition, this deployment scenario will provide an improved end user experience.

### New options to automatically connect and persist rules when using DNS settings on Windows 10 and later devices <!-- 1333665, 2999078 -->
On Windows 10 and later devices, you'll be able to create a VPN configuration profile that includes a list of DNS servers to resolve domains, such as contoso.com. This will include new settings for name resolution (**Device configuration** > **Profiles** > **Create profile** > Choose **Windows 10 and later** for platform > Choose **VPN** for profile type > **DNS settings** >**Add**): 

- **Automatically connect**: When **Enabled**, the device automatically connects to the VPN when a device contacts a domain you enter, such as contoso.com.
- **Persistent**: By default, all Name Resolution Policy table (NRPT) rules are active as long as the device is connected using this VPN profile. When this setting is **Enabled** on an NRPT rule, the rule remains active on the device, even when the VPN disconnects. The rule stays until the VPN profile is removed or until the rule is manually removed, which can be done using PowerShell.

[Windows 10 VPN settings](vpn-settings-windows-10.md) describes the current list of settings. 

### Use S/MIME to encrypt and sign multiple devices for a user <!-- 1333642 eeready -->
S/MIME email encryption using a new imported certificate profile will be supported (**Device configuration** > **Profiles** > **Create profile** > select the platform > **PKCS imported certificate** profile type). In Intune, you can import certificates in PFX format. Intune can then deliver those same certificates to multiple devices enrolled by a single user. This also includes:

- The native iOS email profile supports enabling S/MIME encryption using imported certificates in PFX format.
- The native mail app on Windows Phone 10 devices automatically use the S/MIME certificate.
- The private certificates can be delivered across multiple platforms. But, not all email apps support S/MIME.
- On other platforms, you may need to manually configure the mail app to enable S/MIME.  
- Email apps that support S/MIME encryption may handle retrieving certificates for S/MIME email encryption in a way that an MDM cannot support, such as reading from their publisher's certificate store.

Supported on: Windows, Windows Phone 10, macOS, iOS, Android

### Help and Support page in the Windows Company Portal App <!-- 1488939 -->
A new page will be added to the Windows Company Portal App. The help and support page will provide Helpdesk contact information. Also, end users will be able to send Company Portal logs in the event that they are having issues. The page also provides an FAQ section to assist end users.

### Use trusted network detection for VPN profiles on Windows 10 devices <!-- 1500165 -->
When using trusted network detection, you'll be able to prevent VPN profiles from automatically creating a VPN connection when the user is already on a trusted network. You'll be able to add DNS suffixes to enable trusted network detection on devices running Windows 10 and later (**Device configuration** > **Profiles** > **Create profile** > **Windows 10 and later** for platform > **VPN** for profile type).
[Windows 10 VPN settings](vpn-settings-windows-10.md) lists the current VPN settings.

### The Intune App SDK will support 256-bit encryption keys <!-- 1832174 -->
The Intune App SDK for Android will use 256-bit encryption keys when encryption is enabled by App Protection Policies. The SDK will continue to provide support of 128-bit keys for compatibility with content and apps that use older SDK versions.

### Enabled Shared PC settings in Intune profile <!-- 1907917 -->
Currently, you can configure Shared PC settings on Windows 10 desktop devices using a custom OMA-URI setting. A new profile will be added to configure Shared PC settings (**Device configuration** > **Profiles** > **Create Profile** > **Windows 10 and later** > **Shared multi-user device**).
Applies to: Windows 10 and later, Windows Holographic for Business

### Intune policies update authentication method and Company Portal app installation  <!-- 1927359 -->
On devices already enrolled via Setup Assistant through one of Apple’s corporate device enrollment methods, Intune will no longer support the Company Portal when it is manually installed by end users from the app store. This change is only relevant when you authenticate with Apple Setup Assistant during enrollment. This change also only affects iOS devices enrolled through:  
* Apple configurator
* Apple Business Manager
* Apple School Manager
* Apple Device Enrollment Program (DEP)

If users install the Company Portal app from the App store, and then try to enroll these devices through it, they will receive an error. These devices will be expected to only use Company Portal when it's been pushed, automatically, by Intune during enrollment. Enrollment profiles in Intune in the Azure portal will be updated so that you can specify how devices authenticate and if they receive the Company Portal app. If you want your DEP device users to have the Company Portal, you will need to specify your preferences in an enrollment profile. 
In addition, the **Identify your device** screen in the Company Portal app will soon become obsolete.  
To install Company Portal on already-enrolled DEP devices, you will need to go to Intune > Client apps, and push it as a managed app with app configuration policies. Details about how to do these steps will be outlined in future docs.

### Non-Administrators can enable BitLocker on Windows 10 devices joined to Azure AD<!-- 2147379 -->
When you enable BitLocker settings on Windows 10 devices (**Device configuration** > **Profiles** > **Create profile** > **Windows 10 and later** for platform > **Endpoint protection** for profile type > **Windows Encryption**), you add BitLocker settings. 
This update includes a new BitLocker setting to allow standard users (non-administrators) to enable encryption. 
To see the current settings, see [Endpoint protection settings for Windows 10](endpoint-protection-windows-10.md#windows-encryption).

### Intune app PIN <!-- 2298397 -->
As the IT admin, you'll be able to configure the number of days an end user can wait until their Intune app PIN must be changed. The new setting will be available in the Azure portal by selecting **Intune** > **Client apps** > **App protection policies** > **Create Policy** > **Settings** > **Access requirements**. This feature will be available on iOS and Android devices. This setting supports a positive integer value.

### New Windows 10 Update settings <!-- 2626030 2512994 -->
For your Windows 10 Update Rings, you'll be able to:
- restore the original auto update settings on a Windows 10 machine on machines running the *October 2018 Update*
- configure a new Software updates setting that lets you block or allow your users to pause update installation from the *Settings* of their machines. 



### iOS email profiles can use S/MIME signing and encryption <!-- 2662949 -->
You'll be able to create an email profile that includes different settings. This includes S/MIME settings that can be used for signing and encrypting email communications on iOS devices (**Device configuration** > **Profiles** > **Create profile** > Choose **iOS** for platform > **Email** for profile type).

[iOS email configuration settings](email-settings-ios.md) lists the current settings.

### Skip more Setup Assistant screens on an iOS DEP device <!-- 2687509 -->
In addition to the screens you can currently skip, you'll be able to set iOS DEP devices to skip the following screens in the Setup Assistant when a user enrolls the device: 
Display Tone, Privacy, Android Migration, Home Button, iMessage & FaceTime, Onboarding, Watch Migration, Appearance, Screen Time, Software Update, SIM Setup.
To choose which screens to skip, go to **Device enrollment** > **Apple enrollment** > **Enrollment program tokens** > choose a token > **Profiles** > choose a profile > **Properties** > **Setup Assistant customization** > choose **Hide** for any screens that you want to skip > **OK**.

### Some BitLocker settings support Windows 10 Pro edition<!-- 2727036 -->
You'll be able to create a configuration profile that sets endpoint protection settings on Windows 10 devices, including BitLocker. This adds support for Windows 10 Professional edition for some BitLocker settings. 
To see the current Windows 10 edition settings, see [Endpoint protection settings for Windows 10](endpoint-protection-windows-10.md#windows-encryption).


### Intune device reporting fields <!-- 2748738 -->
Intune will provide additional device reporting fields, including Android manufacturer, model, and security patch version, as well as iOS model. In Intune, these fields will be available by selecting **Client apps** > **App protection status** and choosing **App Protection Report: iOS, Android**. In addition, these parameters will help you configure the **Allow** list for device manufacturer (Android), the **Allow** list for device model (Android and iOS), and the minimum Android security patch version setting. 

### Intune device reporting fields <!-- 2748738 -->
Intune will provide additional device reporting fields, including Android manufacturer, model, and security patch version, as well as iOS model. In Intune, these fields will be available by selecting **Client apps** > **App protection status** and choosing **App Protection Report: iOS, Android**. In addition, these parameters will help you configure the **Allow** list for device manufacturer (Android), the **Allow** list for device model (Android and iOS), and the minimum Android security patch version setting. 

### Shared device configuration is renamed to Lock Screen Message for iOS devices in the Azure portal <!-- 2809362 -->
When you create a configuration profile for iOS devices, you'll be able to add **Shared Device Configuration** settings to show specific text on the lock screen. This includes the following changes: 

- The **Shared Device Configuration** settings in the Azure portal are renamed to "Lock Screen Message (supervised only)" (**Device configuration** > **Profiles** > **Create profile** > Choose **iOS** for platform > Choose **Device features** for profile type > **Lock Screen Message**).
- When adding lock screen messages, you can insert a serial number, a device name, or another device-specific value as a variable in **Asset tag information**. For example, you can enter `Device name: {{device name}}` or `Serial number is {{serial number}}` using curly brackets. [iOS tokens](app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) lists the available tokens that can be used.

[Settings to display messages on the lock screen](shared-device-settings-ios.md) lists the current settings.

### More detailed enrollment restriction failure messaging <!-- 3111564-->
More detailed error messages will be available when enrollment restrictions are not met. To see these messages, go to **Intune** > **Troubleshoot** > and check the Enrollment Failures table.

### New notification, hints, and keyguard settings to Android Enterprise device owner devices <!-- 3201839 3201843 -->
This update includes several new features on Android Enterprise devices when running as device owner. To use these features, go to **Device Configuration** > **Profiles** > **Create profile** > In **Platform**, choose **Android Enterprise** > In **Profile type**, choose **Device owner only** > **Device Restrictions**.
New features include: 
- Disable system notifications from showing, including incoming calls, system alerts, system errors, and more
- Suggests skip starting tutorials and hints for apps that are opened the first time
- Disable advanced keyguard settings, such as the camera, notifications, fingerprint unlock, and more

To see the current settings, go to [Android Enterprise device restriction settings](device-restrictions-android-for-work.md).

### Android enterprise device owner devices can use Always On VPN connections <!-- 3202194 -->
In this update, you can use Always-on VPN connections on Android enterprise device owner devices. Always-on VPN connections stay connected, or immediately reconnect when the user unlocks their device, when the device restarts, or when the wireless network changes. You can also put the connection in "lockdown" mode, which blocks all network traffic until the VPN connection is active.
You can enable Always-on VPN in **Device configuration** > **Profiles** > **Create profile** > **Android enterprise** for platform > **Device restrictions** for Device Owner Only > **Connectivity** settings. 
To see the current settings, go to [Android Enterprise device restriction settings](device-restrictions-android-for-work.md).

### New setting to end processes in Task manager on Windows 10 devices <!-- 3285177 --> 
This update includes a new setting to end processes using Task Manager on Windows 10 devices. Using a device configuration profile (**Device configuration** > **Profiles** > **Create profile** > In **Platform**, choose **Windows 10** > In **Profile type**, choose **Device restrictions** > **General** settings), you choose to allow or prevent this setting.
To see the current settings, go to [Windows 10 device restriction settings](device-restrictions-windows-10.md).
Applies to: Windows 10 and later

### Administrative templates are in public preview, and moved to their own configuration profile <!-- 3322847 -->
Administrative templates in Intune (**Device configuration** > **Administrative templates**) are currently in private preview. With this update:
Administrative templates includes about 300 settings that can be managed in Intune. Previously, these settings only existed in the group policy editor.
Administrative templates are available in public preview
Administrative templates are moving from **Device configuration** > **Administrative templates** to **Device configuration** > **Profiles** >**Create profile** > In **Platform**, choose **Windows 10 and later**, In **Profile type**, choose **Administrative templates**.
Reporting is enabled
Applies to: Windows 10 and later


<!-- 1810 start -->

### Use Microsoft-recommended settings with Security Baselines <!-- 2055484 -->
Intune integrates with other services that focus on security, including Windows Defender ATP and Office 365 ATP. Customers are asking for a common strategy and a cohesive set of end-to-end security workflows across the Microsoft 365 services. Our goal is to align strategies to build solutions that bridge security operations and common administrator tasks. 
In Intune, we aim to accomplish this goal by publishing a set of Microsoft recommended “Security baselines” (**Intune** > **Security baselines**).  An administrator will be able to create security policies directly from these baselines, and then deploy them to their users. They can also customize the best practice recommendations to meet the needs of their organization. Intune makes sure that devices stay in compliance with these baselines, and notifies administrators of users or devices that aren't in compliance.

### Scope tags for apps <!--1081941 -->
You’ll be able to create scope tags to limit access to Intune resources. Add a scope tag to a role assignment and then add the scope tag to a configuration profile. The role will only have access to resources with configuration profiles that have matching scope tags (or no scope tag).
To create a scope tag, choose **Intune roles** > **Scope (Tags)** > **Create**.
To add a scope tag to a role assignment, choose **Intune roles** > **All roles** > **Policy and Profile Manager** > **Assignments** > **Scope (Tags)**.
To add a scope tag to a configuration profile, choose **Device configuration** > **Profiles** > choose a profile > **Properties** > **Scope (Tags)**.

### Tenant Health dashboard <!-- 1124854 -->
The Tenant Status page in Intune will provide you with tenant status information in a single place. The page is divided into 4 sections:  
- **Tenant Details**: Contains information, such as your MDM Authority, the total enrolled devices in your tenant, and your license counts. This section also provides the current service release for your tenant.
- **Connector Status**: Contains information for configured connectors, such as Apple VPP, Windows Store for Business, and Certificate connectors. Based on their current state, the connectors are flagged as *Healthy*, *Warning*, or *Unhealthy*.
- **Intune Service Health**: Contains active incidents or outages for your tenant. The information in this section is retrieved directly from the Office Message Center ([https://portal.office.com](https://portal.office.com)).
- **Intune News**: Contains active messages for your tenant, which include things like notifications that your tenant has received the latest Intune features. The information in this section is retrieved directly from the Office Message Center ([https://portal.office.com](https://portal.office.com)).


### Deployed WIP policies without user enrollment <!-- 1434452 -->
Windows Information Protection (WIP) policies will be able to be deployed without requiring MDM users to enroll their Windows 10 device. This configuration allows companies to protect their corporate documents based on the WIP configuration, while allowing the user to maintain management of their own Windows devices. Once documents are protected with a WIP policy, the protected data can be selectively wiped by an Intune administrator. By selecting the user and device, and sending a wipe request, all data that was protected via the WIP policy will become unusable. From the Intune in the Azure portal, select **Mobile app** > **App selective wipe**.


<!-- 1809 start -->  

### App Protection Policy (APP) settings for web data <!-- 2662995 -->
APP policy settings for web content on both Android and iOS devices will be updated to better handle both http and https web links, as well as data transfer via iOS Universal Links and Android App Links.  

<!-- 1808 start -->

### Apple VPP token used by another MDM <!-- 1488946 -->
Intune will detect and show details if an Apple volume-purchased program (VPP) token is in use by both Intune and another MDM.

### Retired devices in the device compliance dashboard <!-- 1981119 -->
In a future update, retired devices will be removed from the device compliance dashboard. This will change your compliance numbers.


### Change in the update process for on-premises connectors <!-- 2277554 -->
Based on feedback from customers, the way updates are made to on-premises connectors will be changed. After you initially install an on-premises connector, updates will happen automatically. This change will begin with the new PFX Certificate Connector for Microsoft Intune and will subsequently roll out to other types of on-premises connectors. 

<!-- 1807 start -->

### Check for Configuration Manager compliance <!-- 2192052 -->
A future update will include a new System Center Configuration Manager compliance setting (**Device compliance** > **Policies** > **Create policy** > **Windows 10**). Configuration Manager sends signals to Intune compliance. Using the Intune setting, you can require all Configuration Manager signals to return "compliant".

For example, you require all software updates to be installed on devices. In Configuration Manager, this requirement has the “Installed” state. If any programs on the device are in unknown state, then the device will be non-compliant in Intune.

Applies to Windows 10 and later



## Notices

There are no active notices at this time.

### See also
See [What’s New in Microsoft Intune](whats-new.md) for details on recent developments.



