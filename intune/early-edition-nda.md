---
# required metadata

title: Early edition - Microsoft Intune
titlesuffix: 
description: Microsoft Intune early edition
keywords:
author: ErikjeMS  
ms.author: erikje
manager: dougeby
ms.date: 02/04/2019
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
ms.collection: M365-identity-device-management
---

# The early edition for Microsoft Intune - February 2019

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
<!-- 1902 start-->

### PowerShell scripts can run in a 64-bit host on 64-bit devices <!-- 1862675  -->
When you add a PowerShell script to a device configuration profile, the script always executes in 32-bit, even on 64-bit operating systems. With this update, an administrator can run the script in a 64-bit PowerShell host on 64-bit devices (**Device configuration** > **PowerShell scripts** > **Add** > **Configure** > **Run script in 64 bit PowerShell Host**).
For more details on using PowerShell, see [PowerShell scripts in Intune](intune-management-extension.md).
Applies to:
Windows 10 and later

### Rename an enrolled Windows device <!-- 1911112  -->
You'll be able to rename an enrolled Windows 10 device (RS4 or later). To do, choose **Intune** > **Devices** > **All devices** > choose a device > **Rename device**.

### Assign SCEP certificates to a userless macOS device    <!-- 2340521   -->
You'll be able to assign Simple Certificate Enrollment Protocol (SCEP) certificates to a userless macOS device, and associate the certificate with Wi-Fi or VPN profiles. This expands on the existing support we already have to [assign certificates to userless devices that run Windows, iOS, and Android](certificates-scep-configure.md#create-a-scep-certificate-profile).

### Find out which devices support eSIM <!-- 2432018 -->
There will be a new **eSIM Inventory** field on the Hardware page for devices. To see the filed, choose **Intune** > **Devices** > choose a device > **Hardware**.

### Intune conditional access UI update   <!-- 2432313  -->
We're making improvements to the UI for conditional access in the Intune console. These include:
- Replace the Intune *Conditional access* blade with the blade from Azure Active Directory. This ensures you'll have access to the full range of settings and configurations for conditional access which remains an Azure AD technology.
- Relocate the *Exchange service connector* setup to what is currently the *On-premises access* blade. We are also renaming that blade to *Exchange access*. This change will consolidate where you configure and monitor details related to Exchange online and on-premises.

### Intune will leverage Google Play Protect APIs on Android devices <!-- 2577355  -->
Some IT admins are faced with a BYOD landscape where end users may end up rooting or jailbreaking their mobile phone. This behavior, while sometimes not ill-intentioned, results in a bypass of many Intune policies that are set in order to protect the organization's data on end user devices. Thus, Intune provides root and jailbreak detection for both enrolled and unenrolled devices. With this release, Intune will now leverage Google Play Protect APIs to add to our existing root detection checks for unenrolled devices. While Google does not share the entirety of the root detection checks that occur, we expect these APIs to detect users who have rooted their devices for any reason from device customization to being able to get newer OS updates on older devices. These users can then be blocked from accessing corporate data, or their corporate accounts can be wiped from their policy enabled apps. For additional value, the IT admin will now have several reporting updates within the Intune App Protection blade - the "Flagged Users" report will show which users are detected via Google Play Protect's SafetyNet API scan, the "Potentially Harmful Apps" report will show which apps are detected via Google's Verify Apps API scanning. This feature is available on Android. 

### Win32 app information available in Troubleshooting blade <!-- 2617342    -->
You will be able to collect failure log files for a Win32 app installation from the Intune app **Troubleshooting** blade. For more information about app installation troubleshooting, see [Troubleshoot app installation issues](troubleshoot-app-install.md).

### Kiosk Browser and Microsoft Edge Browser apps can run on Windows 10 devices in kiosk mode <!-- 2935135  -->
You can use Windows 10 devices in kiosk mode to run one app, or multiple apps. This update includes several changes to using browser apps in kiosk mode, including:

- Add the Microsoft Edge Browser or Kiosk Browser to run as apps on the kiosk device (**Device configuration** > **Profiles** > **New profile** > **Windows 10 and later** for platform > **Kiosk** for profile type).
- Restrict Microsoft Edge so it can (or can't) run in kiosk mode (**Device configuration** > **Profiles** > **New profile** > **Windows 10 and later** for platform > **Device restrictions** for profile type > **Microsoft Edge Browser**). When not run in kiosk mode, the Microsoft Edge settings can be changed by end users.

For a list of the current settings, see:

- [Windows 10 and later device settings to run as a kiosk](kiosk-settings-windows.md)
- [Microsoft Edge Browser device restrictions](device-restrictions-windows-10.md#microsoft-edge-browser)

Applies to:
Windows 10 and later

### Auto-assign scope tags to resources created by an admin with that scope <!-- 3173823  -->
When an admin creates a resource, any scope tags assigned to the admin will automatically be assigned to those new resources.

### New device restriction settings for iOS and macOS devices <!-- 3448774 -->
You can restrict some settings and features on devices running iOS and macOS (**Device configuration** > **Profiles** > **New profile** > **iOS** or **macOS** for platform > **Device restrictions** for profile type). This update adds more features and settings you can control, including setting screen time, changing eSIM settings and cellular plans, delaying the user's visibility of software updates, blocking content caching, and more.
To see the current features and settings you can restrict, see:
- [iOS device restriction settings](device-restrictions-ios.md)
- [macOS device restriction settings](device-restrictions-macos.md)

Applies to:
- iOS
- macOS

### Failed enrollment report moves to the Device Enrollment blade <!-- 3560202 -->
The **Failed enrollments** report will move to the **Monitor** section of the **Device enrollment** blade. Two new columns (Enrollment Method and OS Version) are also added.

### Change "Kiosk" to "Dedicated devices" <!-- 3598402  -->
To align with Android terminology, **Kiosk** will be changed to **Dedicated devices** under Device configuration profiles, **Android enterprise** > **Device Owner** > **Device Restrictions**.

### Safari and Delaying user software update visibility iOS settings are moving in the Intune UI <!-- 3640850, , 3803313  -->
For iOS devices, you can set Safari settings and configure Software Updates. In this update, these settings are moving to different parts of the Intune UI:

- The Safari settings are moving from **Safari** (**Device configuration** > **Profiles** > **New profile** > **iOS** for platform > **Device restrictions** for profile type) to **Built-in Apps**. 
- The **Delaying user software update visibility for supervised iOS devices** setting (**Software updates** > **Update policies for iOS**) is moving to **Device restrictions** > **General**.

For a list of the current settings, see [iOS device restrictions](device-restrictions-ios.md) and [iOS software updates](software-updates-ios.md).

Applies to: 
- iOS

### Enabling restrictions in the device settings is renamed to Screen Time on iOS devices <!-- 3699164  -->
You can configure the **Enabling restrictions in the device settings** on supervised iOS devices (**Device configuration** > **Profiles** > **New profile** > **iOS** for platform > **Device restrictions** for profile type > **General**). In this update, this setting is renamed to **Screen Time (supervised only)**. 
The behavior is the same. Specifically: 

- iOS 11.4.1 and earlier: **Block** prevents end users from setting their own restrictions in the device settings. 
- iOS 12.0 and later: **Block** prevents end users from setting their own **Screen Time** in the device settings, including content & privacy restrictions. Devices upgraded to iOS 12.0 won't see the restrictions tab in the device settings anymore. These settings are in **Screen Time**. 

For a list of the current settings, see [iOS device restrictions](device-restrictions-ios.md).

Applies to: 
- iOS

### App status details for iOS apps <!-- 3761235  -->
There will be new app installation error messages related to the following:
- Failure for VPP apps when installing on shared iPad
- Failure when app store is disabled
- Failure to find VPP license for app
- Failure to install system apps with MDM provider
- Failure to install apps when device is in lost mode or kiosk mode
- Failure to install app when user is not signed in to the App Store

In Intune, select **Client apps** > **Apps** > "App name" > **Device install status**. New error messages will be available in the **Status details** column.

<!-- 1901 start -->

### Deployment of online licensed Microsoft Store for Business apps <!-- 1672660  -->
You will be able to assign required online licensed Microsoft Store for Business apps in the device context. Deploying a Microsoft Store for Business app this way will enable the app to be installed for all users on the device. This is only applicable on Windows 10 RS4+ desktop devices. The option to install in the device context is available in the Client Apps assignment page for MSFB Online Licensed apps.

<!-- 1812 start -->

### Android Enterprise APP-WE app deployment <!-- 1171203 -->
For Android devices in a non-enrolled App Protection Policy Without Enrollment (APP-WE) deployment scenario, you'll be able to use managed Google Play to deploy store apps and LOB apps to users. Specifically, IT can provide end users with an app catalog and installation experience that no longer requires end users to loosen the security posture of their devices by allowing installations from unknown sources. In addition, this deployment scenario will provide an improved end user experience.

### Intune policies update authentication method and Company Portal app installation  <!-- 1927359 -->
On devices already enrolled via Setup Assistant through one of Apple’s corporate device enrollment methods, Intune will no longer support the Company Portal when it is manually installed by end users from the app store. This change is only relevant when you authenticate with Apple Setup Assistant during enrollment. This change also only affects iOS devices enrolled through:  
* Apple configurator
* Apple Business Manager
* Apple School Manager
* Apple Device Enrollment Program (DEP)

If users install the Company Portal app from the App store, and then try to enroll these devices through it, they will receive an error. These devices will be expected to only use Company Portal when it's been pushed, automatically, by Intune during enrollment. Enrollment profiles in Intune in the Azure portal will be updated so that you can specify how devices authenticate and if they receive the Company Portal app. If you want your DEP device users to have the Company Portal, you will need to specify your preferences in an enrollment profile. 
In addition, the **Identify your device** screen in the Company Portal app will soon become obsolete.  
To install Company Portal on already-enrolled DEP devices, you will need to go to Intune > Client apps, and push it as a managed app with app configuration policies. Details about how to do these steps will be outlined in future docs.

### Administrative templates are in public preview, and moved to their own configuration profile <!-- 3322847 -->
Administrative templates in Intune (**Device configuration** > **Administrative templates**) are currently in private preview. With this update:
Administrative templates includes about 300 settings that can be managed in Intune. Previously, these settings only existed in the group policy editor.
Administrative templates are available in public preview
Administrative templates are moving from **Device configuration** > **Administrative templates** to **Device configuration** > **Profiles** >**Create profile** > In **Platform**, choose **Windows 10 and later**, In **Profile type**, choose **Administrative templates**.
Reporting is enabled
Applies to: Windows 10 and later

### Intune macOS Company Portal Dark Mode <!-- 3300524 -->
The Intune macOS Company Portal now supports Dark Mode for macOS. When you enable Dark Mode on a macOS 10.14+ device, the Company Portal will adjust its appearance to colors that reflect that mode.

<!-- 1809 start -->  

### App Protection Policy (APP) settings for web data <!-- 2662995 -->
APP policy settings for web content on both Android and iOS devices will be updated to better handle both http and https web links, as well as data transfer via iOS Universal Links and Android App Links.  

<!-- 1808 start -->

### Apple VPP token used by another MDM <!-- 1488946 -->
Intune will detect and show details if an Apple volume-purchased program (VPP) token is in use by both Intune and another MDM.

### Retired devices in the device compliance dashboard <!-- 1981119 -->
In a future update, retired devices will be removed from the device compliance dashboard. This will change your compliance numbers.

## Notices

There are no active notices at this time.

### See also
See [What’s New in Microsoft Intune](whats-new.md) for details on recent developments.
