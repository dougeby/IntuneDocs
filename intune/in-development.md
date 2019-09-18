---
# required metadata

title: In development - Microsoft Intune
titleSuffix: 
description: Microsoft Intune features in development
keywords:
author: ErikjeMS 
ms.author: erikje
manager: dougeby
ms.date: 08/30/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.technology:
ms.assetid: 

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: seodec18
ms.collection: M365-identity-device-management
---

# In development for Microsoft Intune - September 2019

To assist in your readiness and planning, this page lists Intune UI updates and features that are in development but not yet released. In addition:

- If we anticipate that you'll need to take action before a change, we’ll publish a complementary Office Message Center post.
- When a feature is launched in production, either as a preview or generally available, the feature description will move off this page and onto the [What's New page](whats-new.md).
- This page and the [What's New page](whats-new.md) are updated periodically. Check back for additional updates.
- Refer to the [M365 roadmap](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS) for strategic deliverables and timelines.

> [!Note]
> These items reflect Microsoft’s current expectations about Intune capabilities coming in a future release. Dates and individual features may change. Not all items in development have a feature description on this page.

**RSS feed**: Get notified when this page is updated by copying and pasting the following URL into your feed reader: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`

<!--
## What's coming to Intune in the Azure portal 
## What's coming to Intune apps
## Notices
-->

<!-- Common categories:  
#### App management
#### Device configuration
#### Device enrollment
#### Device management
#### Intune apps
#### Monitor and troubleshoot
#### Role-based access control
#### Security

-->
 
<!-- ***********************************************-->
## App management

### Managed Google Play private LOB apps <!-- 1464182  -->
Intune will allow IT admins to publish private Android LOB apps to Managed Google Play via an iframe embedded in the Intune console.  Currently, IT admins need to publish LOB apps directly to Google's Play publishing console, which requires many steps and is very time consuming.  This new feature allows for easy publishing of LOB apps with a minimal set of steps without needing to leave the Intune console.  Any of the Android Enterprise management scenarios that use Managed Google Play can take advantage of this feature (work profile, dedicated, fully managed, and non-enrolled devices).  From Intune, select **Client apps** > **Apps** > **Add**. Then, select **Managed Google Play** from the **App type** list. For more information about Managed Google Play apps, see [Add Managed Google Play apps to Android Enterprise devices with Intune](apps-add-android-for-work.md).

### Company Portal app installation status messages <!-- 2514416  -->
The Company Portal app will show additional app installation status messages to end users. The following conditions will apply to new Win32 dependency features:
- App failed to install. Dependencies defined by the admin were not met.
- App installed successfully but requires a restart.
- App is in the process of installing, but requires a restart to continue.

### Managed Google Play iframe support <!-- 2871756  -->
Intune will provide support for adding and managing web links directly in the  Intune console, via the Managed Google Play iframe.  This lets IT admins submit a URL and icon graphic, and then deploy those links to devices just like regular Android apps. Any of the Android Enterprise management scenarios that use Managed Google Play can take advantage of this feature (work profile, dedicated, fully managed, and non-enrolled devices).  From Intune, select **Client apps** > **Apps** > **Add**. Then, select **Managed Google Play** from the **App type** list. For more information about Managed Google Play apps, see [Add Managed Google Play apps to Android Enterprise devices with Intune](apps-add-android-for-work.md).

### macOS support for VPP apps <!-- 3173501  -->
macOS apps you have purchased using Apple Business Manager will be displayed in the console when Apple VPP tokens are synced in Intune. You can assign, revoke and reassign device and user-based licenses for groups using the console. Microsoft Intune helps you manage VPP apps purchased for use at your company by:
- Reporting license information from the app store.
- Tracking how many of the licenses you have used.
- Helping you to not install more copies of the app than you own.
For more information about Intune and VPP, see [Manage volume-purchased apps and books with Microsoft Intune](vpp-apps.md).

### macOS support for web apps <!-- 3174427  -->
You'll be able to install Web apps, which allow you to add a shortcut to a URL on the web, to the Dock using the macOS Company Portal. End-users can access the **Install** action from the app details page for a web app in the macOS Company Portal. For more information about the **Web link** app type, see [Add apps to Microsoft Intune](apps-add.md).

#### Assign Microsoft Edge beta for macOS <!-- 4678761  -->
You'll be able to add and assign the latest version of Microsoft Edge beta to Intune for macOS devices. From Intune, select **Client apps** > **Apps** > **Add app** > **Microsoft Edge - macOS**. Then, assign Microsoft Edge beta to the intended groups. Microsoft AutoUpdate (MAU) keeps Microsoft Edge up-to-date. For more information about Microsoft Edge, see [Manage web access by using Microsoft Edge with Microsoft Intune](manage-microsoft-edge.md).

### Read and write Graph API operations for Intune apps <!-- 5031704  -->
Applications will be able to call the Intune Graph API with both read and write operations using app identity without user credentials. For more information about accessing the Microsoft Graph API for Intune, see [Working with Intune in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/intune-graph-overview?view=graph-rest-1.0).

### Configure app notification content for organization accounts <!-- 2576686 -->
Intune app protection policies (APP) on Android and iOS devices will allow you to control app notification content for Org accounts. This feature will require support from applications and may not be available for all APP enabled applications. For more about APP, see [What are app protection policies?](app-protection-policy.md).

### Available Google Play app reporting for Android work profiles <!-- 3041956  -->
For available app installs on Android work profile devices, you can view app installation status and the installed version of managed Google Play apps. For more information, see [How to monitor app protection policies](app-protection-policies-monitor.md), [Manage Android work profile devices with Intune](android-enterprise-overview.md) and [Managed Google Play app type](apps-add-android-for-work.md#managed-google-play-app-type).

<!-- ***********************************************-->
## Device configuration

### Device features, device restrictions, and extension profiles for iOS and macOS settings are shown by enrollment type <!-- 4886161  -->

In Intune, you create profiles for iOS and macOS devices (**Device configuration** > **Profiles** > **Create profile** > **iOS** or **macOS** for platform > **Device features**, **Device restrictions**, or **Extensions** for profile type). Currently, the available settings in these profiles are listed. 

In a future update, the available settings in the Intune portal will be categorized by the enrollment type that they apply to:

- iOS
  - All enrollment types
  - Device enrollment and automated device enrollment
  - Automated device enrollment

- macOS
  - All enrollment types
  - Device enrollment
  - User approved and automated device enrollment
  - Automated device enrollment

Applies to:

- iOS
  - [Device features](ios-device-features-settings.md)
  - [Device restrictions](device-restrictions-ios.md)

- macOS
  - [Device features](macos-device-features-settings.md)
  - [Device restrictions](device-restrictions-macos.md)
  - [Extensions](kernel-extensions-settings-macos.md)

### New voice control settings for supervised iOS devices running in kiosk mode <!-- 4892835  -->

In Intune, you can create policies to run supervised iOS devices as a kiosk, or dedicated device (**Device configuration** > **Profiles** > **Create profile** > **iOS** for platform > **Device restrictions** for profile type > **Kiosk (supervised only)**). 

In a future update, there will be new settings you can control:

- **Voice control**: Enables Voice Control on the device while in kiosk mode.
- **Modification of voice control**: Allow users to change the Voice Control setting on the device while in kiosk mode.

To see the current settings, go to [iOS Kiosk (supervised only) settings](device-restrictions-ios.md#kiosk-supervised-only).

Applies to:

- iOS 13.0 and later

### Use single sign-on for apps and websites on your iOS and macOS devices <!-- 4893175  -->
In a future update, there will be some new single sign-on settings for iOS and macOS devices (**Device configuration** > **Profiles** > **Create profile** > **iOS** or **macOS** for platform > **Device features** for profile type).

Use these settings to configure a single sign-on experience, especially for apps and websites that use Kerberos authentication. You can choose between a generic credential single sign-on app extension, and Apple's built-in Kerberos extension.

To see the current device features you can configure, go to [iOS device features](ios-device-features-settings.md) and [macOS device features](macos-device-features-settings.md).

Applies to:

- iOS 13.0 and newer
- macOS 10.15 and newer

### Associate domains to apps on macOS 10.15+ devices <!-- 4898079  -->
On macOS devices, you can configure different features, and push these features to your devices using a policy (**Device configuration** > **Profiles** > **Create profile** > **macOS** for platform > **Device features** for profile type). In a future update, you'll be able to associate domains to your apps. This feature helps share credentials with websites related to your app, and can be used with Apple’s single sign-on extension, universal links, and password autofill. 

To see the current features you can configure, go to [macOS device feature settings in Intune](macos-device-features-settings.md).

Applies to:

- macOS 10.15 and newer

### Use "itunes" and "apps" in the iTunes App store URL when showing or hiding apps on iOS supervised devices <!-- 4928474  --> 
In Intune, you can create policies to show or hide apps on your supervised iOS devices (**Device configuration** > **Profiles** > **Create profile** > **iOS** for platform > **Device restrictions** for profile type > **Show or hide apps (supervised only)**). 
​
You can enter the iTunes App store URL, such as `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8`. In a future update, you'll be able to use both `apps` and `itunes` in the URL, such as:​
​
- `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8​`
- `https://apps.apple.com/us/app/work-folders/id950878067?mt=8​`
​
For more information on these settings, see [Show or hide apps (supervised only)](device-restrictions-ios.md#show-or-hide-apps-supervised-only).

Applies to:

- iOS

### Support for IKEv2 VPN profiles for iOS <!-- 1943438 -->
You'll be able to create VPN profiles for the iOS native VPN client using the IKEv2 protocol. IKEv2 is a new connection type in **Device configuration** > **Profiles** > **Create profile** > **iOS** for platform > **VPN** for profile type > **Settings**.

These VPN profiles configure the native VPN client. So, no VPN client apps are installed or pushed to managed devices. This feature requires devices be enrolled in Intune (MDM enrollment).

To see the current VPN settings you can configure, go to [Configure VPN settings on iOS devices in Microsoft Intune](vpn-settings-ios.md).

Applies to: iOS


<!-- ***********************************************-->
## Device enrollment

### New tenants will default away from Android device administrator management <!-- 4869790  -->
Android's device administrator capabilities have been superseded by Android Enterprise. Therefore, we recommend using Android Enterprise for new enrollments instead. In a future update, new tenants will need to complete the following prerequisite steps in Android enrollment to use device administrator management: Go to **Intune** > **Device enrollment** > **Android enrollment** > **Personal and corporate-owned devices with device administration privileges** > **Use device administrator to manage devices**.

Existing tenants will experience no change in their environments. 

For more information about Android device administrator in Intune, see [Android device administrator enrollment](android-enroll-device-administrator.md).

### For iOS devices, customize the enrollment process privacy screen of the Company Portal <!-- 4394993  -->
Using markdown, you'll be able to customize the Company Portal's privacy screen that end users see during iOS enrollment. Specifically, you'll be able to customize the list of things that your organization can't see or do on the device.

<!-- ***********************************************-->
## Device management

### Deploy Software Updates to macOS devices <!-- 3194876 -->
You'll be able to deploy Software Updates to groups of macOS devices. This feature includes critical, firmware, configuration file, and other updates. You'll be able to send updates on the next device check-in or select a weekly schedule to deploy updates in or out of time windows that you set. This helps when you want to update devices outside standard work hours or when your help desk is fully staffed. You'll also get a detailed report of all macOS devices with updates deployed. You can drill into the report on a per-device basis to see the statuses of particular updates.

### Send custom notifications to a device <!-- 4928910  -->
You'll be able to send custom notifications to specific devices that have the Company Portal or Intune app installed. To do so, go to **Intune** > **Devices** > **All devices** > choose a device > **More** > **Send custom notification**. 

### Updates to Android Enterprise Fully Managed features <!-- 3464667, 5227935, 4062195, 4631425, 4631440 -->

We'll be adding the following support for Android Fully Managed devices:

- SCEP certificates for fully managed Android will be available for cert authentication on devices managed as Device Owner. SCEP certificates are already supported on Work Profile devices.  With SCEP certificates for Device Owner, you will be able to: <!-- 5227935 -->
    - create SCEP profile under DO section of Android Enterprise
    - link SCEP certificates to DO Wi-Fi profile for authentication
    - link SCEP certificates to DO VPN profiles for authentication
    - link SCEP certificates to DO Email profiles for authentication (via AppConfig)
- System apps will be supported on Android Enterprise devices. In Intune, you will add an Android Enterprise system app by selecting **Client apps** > **Apps** > **Add**. In the **App type** list, select **Android Enterprise system app**. For more information about adding apps to Intune, see [Add apps to Microsoft Intune](apps-add.md). <!-- 4062195 -->
- In **Device compliance** > **Android Enterprise** > **Device Owner**, you'll be able to create a compliance policy that sets the Google SafetyNet attestation level.   <!-- 4631425 -->
- On Android Enterprise fully managed devices, the mobile threat defense providers will be supported. In **Device compliance** > **Android Enterprise** > **Device Owner**, you can choose an acceptable threat level. <!-- 4631440 --> [Android Enterprise settings to mark devices as compliant or not compliant using Intune](compliance-policy-create-android-for-work.md#device-owner) lists the current settings.


Applies to: 
- Android Enterprise fully managed devices

<!-- ***********************************************-->
## Monitor and troubleshoot

### Updated support experience   <!--  5012398    -->
As part of continuing improvements, we’ll be updating the in-console support experience for Intune.  We’ll be improving the in-console search and feedback for common issues, and streamlining the workflow to contact support.     

<!-- ***********************************************-->
## Security

### Tamper Protection for Windows Defender Antivirus  <!-- 4705448       -->
We'll be adding *Tamper Protection* to the settings that Intune can manage for Windows Defender Antivirus. You'll be able to use a device configuration profile for Windows 10 endpoint protection to turn Tamper Protection on or off.  For more information about Tamper Protection, see [Prevent security settings changes with tamper protection](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection) in the Windows documentation. 


<!-- ***********************************************-->
## Notices

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

## See also
See [What’s New in Microsoft Intune](whats-new.md) for details on recent developments.




