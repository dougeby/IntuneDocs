---
# required metadata

title: In development - Microsoft Intune
titleSuffix: 
description: Microsoft Intune features in development
keywords:
author: ErikjeMS 
ms.author: erikje
manager: dougeby
ms.date: 07/30/2019
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

# In development for Microsoft Intune - August 2019

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

### Control iOS app uninstall behavior at device unenrollment <!-- 3504144 -->
Admins will be able to manage whether an app is removed or retained on a device when the device is unenrolled at a user or device group level. 

### Categorize Microsoft Store for Business apps <!-- 3926922 -->
You'll be able to categorize Microsoft Store for Business apps. To do so, choose **Intune** > **Client apps** > **Apps** > Select a Microsoft Store for Business app > **App Information** > **Category**. On the drop-down menu, assign a category.
### Configure app notification content for organization accounts <!-- 2576686 -->
Intune app protection policies (APP) on Android and iOS devices will allow you to control app notification content for Org accounts. This feature will require support from applications and may not be available for all APP enabled applications. For more about APP, see [What are app protection policies?](app-protection-policy.md).

### Available Google Play app reporting for Android work profiles <!-- 3041956  -->
For available app installs on Android work profile devices, you can view app installation status and the installed version of managed Google Play apps. For more information, see [How to monitor app protection policies](app-protection-policies-monitor.md), [Manage Android work profile devices with Intune](android-enterprise-overview.md) and [Managed Google Play app type](apps-add-android-for-work.md#managed-google-play-app-type).

<!-- ***********************************************-->
## Device configuration

### Some unsupervised iOS device restrictions will become supervised-only with the iOS 13.0 release <!-- 4867809  -->
Some settings will apply to supervised devices starting with the iOS 13.0 release. These settings include:

- App Store, Doc Viewing, Gaming
  - App store
  - Explicit iTunes, music, podcast, or news content
  - Adding Game Center friends
  - Multiplayer gaming
- Built-in Apps
  - Camera
    - FaceTime
  - Safari
    - Autofill
- Cloud and Storage
  - Backup to iCloud
  - Block iCloud Document sync
  - Block iCloud Keychain sync

If these settings are configured and assigned to unsupervised devices prior to the iOS 13.0 release, the settings are still applied to those unsupervised devices. They also still apply after the devices upgrade to iOS 13.0. These restrictions are removed on unsupervised devices that are backed up and restored. 

To see the current settings, go to [iOS device settings to allow or restrict features using Intune](device-restrictions-ios.md).

Applies to:  
- iOS 13.0 and newer

### New settings, and changes to existing settings to restrict features on iOS and macOS devices <!-- 4867699 4867709  -->
You'll be able to create profiles to restrict settings on devices running iOS and macOS (**Device configuration** > **Profiles** > **Create profile** > **iOS** or **macOS** for platform type > **Device restrictions**). The following features will be added:

- On **macOS** > **Device restrictions** > **Cloud and storage**, use the new **Handoff** setting to block users from starting work on one macOS device, and continue working on another macOS or iOS device.
  To see the current settings, go to [macOS device settings to allow or restrict features using Intune](device-restrictions-macos.md).
- On **iOS** > **Device restrictions**, there are a few changes:
  - **Built-in apps** > **Find my iPhone (supervised only)**: New setting that blocks this feature in the Find My app feature. 
  - **Built-in apps** > **Find my Friends (supervised only)**: New setting that blocks this feature in the Find My app feature. 
  - **Wireless** > **Modification of Wi-Fi state (supervised only)**: New setting that prevents users from turning on or turning off Wi-Fi on the device.
  - **Keyboard and Dictionary** > **QuickPath (supervised only)**: New setting that blocks the QuickPath feature.
  - **Cloud and storage**: **Activity continuation** is renamed to **Handoff**.

  To see the current settings, go to [iOS device settings to allow or restrict features using Intune](device-restrictions-ios.md).

Applies to:  
- macOS 10.15 and newer
- iOS 13 and newer

### Control the apps, files, documents, and folders that open when user signs in to macOS devices <!--3914202  -->
You'll be able to enable and configure features on macOS devices (**Device configuration** > **Profiles** > **Create profile** > **macOS** for platform > **Device features** for profile type). 

There will be new Login Items settings to control which apps, files, documents, and folders open when a user signs in to the enrolled device. 

To see the current settings, go to [macOS device feature settings in Intune](macos-device-features-settings.md).

Applies to:  
- macOS

### New features for Android Enterprise dedicated devices in multi-app mode <!-- 3755304 3041943 3041946  -->
You'll be able to control features and settings in a kiosk-style experience on your Android Enterprise dedicated devices. To do so, choose **Device configuration** > **Profiles** > **Create profile** > **Android Enterprise** for platform > **Device Owner only, Device restrictions** for profile type.

The following features will be added:
- **Dedicated devices** > **Multi-app**: The **Virtual home button** can be shown by swiping up on the device, or floating on the screen so users can move it.
- **Dedicated devices** > **Multi-app**: **Flashlight access** allows users to use the flashlight. 
- **Dedicated devices** > **Multi-app**: **Media volume control** allows users to control the device's media volume using a slider. 
- **Dedicated devices** > **Multi-app**:  Enable a screensaver, upload a custom image, and control when the screensaver is shown.

To see the current settings, go to [Android Enterprise device settings to allow or restrict features using Intune](device-restrictions-android-for-work.md#dedicated-device-settings).

Applies to:  
- Android Enterprise dedicated devices

### New app and configuration profiles for Android Enterprise fully managed devices <!-- 3574215  -->
Using profiles, you'll be able to configure settings that apply VPN, email, and Wi-Fi settings to your Android Enterprise fully managed devices. You'll be able to:
- Use app profiles to deploy Outlook, Gmail, and Nine Work email settings.
- Use device configuration profiles to deploy trusted root certificate settings.
- Use device configuration profiles to deploy VPN and Wi-Fi settings.

Users will authenticate with their username and password for VPN, Wi-Fi, and e-mail profiles. Currently, certificate-based authentication isn't available. 

Applies to:  
- Android Enterprise fully managed

### Support for IKEv2 VPN profiles for iOS <!-- 1943438 -->
You'll be able to create VPN profiles for the iOS native VPN client using the IKEv2 protocol. IKEv2 is a new connection type in **Device configuration** > **Profiles** > **Create profile** > **iOS** for platform > **VPN** for profile type > **Settings**.

These VPN profiles configure the native VPN client. So, no VPN client apps are installed or pushed to managed devices. This feature requires devices be enrolled in Intune (MDM enrollment).

To see the current VPN settings you can configure, go to [Configure VPN settings on iOS devices in Microsoft Intune](vpn-settings-ios.md).

Applies to: iOS

<!-- ***********************************************-->
## Device enrollment

### Skip more screens in Setup Assistant <!--4877451 -->
You'll be able to set Device Enrollment Program profiles to skip the following Setup Assistant screens: 
- Screen Time
- Touch ID Setup

To do so, go to **Device enrollment** > **Apple enrollment** > **Enrollment program tokens** > choose a token > **Profiles** > choose a profile > **Properties** > **Edit** next to **Setup Assistant Customization**.
For more information about Setup Assistant customization, see [Create an Apple enrollment profile ](device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile).

### Android enrollment device administrator support <!-- 4869749  -->
The Android device administrator enrollment option will be added to the Android enrollment page (**Intune** > **Device enrollment** > **Android enrollment**). Android device administrator will still be enabled by default for all tenants.  

### For iOS devices, customize the enrollment process privacy screen of the Company Portal <!-- 4394993  -->
Using markdown, you'll be able to customize the Company Portal's privacy screen that end users see during iOS enrollment. Specifically, you'll be able to customize the list of things that your organization can't see or do on the device.

<!-- ***********************************************-->
## Device management

### Build number included on Android device Hardware page <!-- 4461910  -->
A new entry on the Hardware page for each Android device will include the device's operating system build number.

### Configure automatic device clean-up time limit down to 30 days <!--4231059  -->
You'll be able to set the automatic device clean-up time limit as short as 30 days (instead of current limit of 90 days) after the last sign-in. To do so, go to **Intune** > **Devices** > **Setup** > **Device Clean Up Rules**.

<!-- ***********************************************-->
## Role-based access control

### Default scope tag <!-- 3702875 -->
A new built-in default scope tag will be available. All untagged Intune objects that support scope tags will be automatically assigned to the default scope tag. The **Default** scope tag will be added to all existing role assignments to maintain parity with the admin experience today. If you don't want an admin to see Intune objects with default scope tags, remove the default scope tag from the role assignment. This feature is similar to the security scopes feature in System Center Configuration Manager.

<!-- ***********************************************-->
## Security

### Import and export security baselines    <!--3408610          -->  
We’re adding the capability to export and import security baselines. This feature will let you take your customizations with you and share them between Intune environments.

<!-- ***********************************************-->
## Notices

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

## See also
See [What’s New in Microsoft Intune](whats-new.md) for details on recent developments.




