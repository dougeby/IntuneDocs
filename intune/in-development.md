---
# required metadata

title: In development - Microsoft Intune
titleSuffix: 
description: Microsoft Intune features in development
keywords:
author: ErikjeMS 
ms.author: erikje
manager: dougeby
ms.date: 06/03/2019
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

# In development for Microsoft Intune - June 2019

To assist in your readiness and planning, this page lists Intune UI updates and features that are in development but not yet released. In addition:

- If we anticipate that you'll need to take action prior to a change, we’ll publish a complementary Office Message Center post.
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
 
## Intune in the Azure portal

<!-- ***********************************************-->
### App management

#### Device users can view all managed apps they've installed or tried to install <!-- 2352913 -->
Company Portal for Windows will list all managed apps (both required and available) that are installed on a user's device. Users will be able to view attempted and pending app installations, and their current statuses. If your organization doesn't make apps required or available, users will see a message explaining that no company apps have been installed. Users will also be able to sort or filter their apps by installation status.

#### Available Google Play app reporting for Android work profiles <!-- 3041956 -->
For available app installs on Android work profile devices, you will be able to view app installation status as well as the installed version of managed Google Play apps. For more information, see [How to monitor app protection policies](app-protection-policies-monitor.md), [Manage Android work profile devices with Intune](android-enterprise-overview.md) and [Managed Google Play app type](apps-add-android-for-work.md#managed-google-play-app-type).

#### Configure which browser is allowed to link to organization data <!-- 3145939 -->
Intune App Protection Policies (APP) on Android and iOS devices will allow you to transfer Org web links to a specific browser beyond the Intune Managed Browser or Microsoft Edge.  For more about APP, see [What are app protection policies?](app-protection-policy.md).

#### Installed apps page on the Company Portal website  <!-- 4224326 -->
The [Company Portal website](https://portal.manage.microsoft.com/) will include a new page to show users all of the apps that have been installed on their device. This list includes both the available apps and those apps required by their organization. From this page, users will be able to see the installation and requirement statuses of the apps on their device. For more information about the Company Portal website, see [Using the Intune Company Portal website](/intune-user-help/using-the-intune-company-portal-website) and [How to configure the Microsoft Intune Company Portal app](company-portal-app.md).

#### Call Graph API read operations from an application without user credentials <!-- 4655885 -->
Applications will be able to call Intune Graph API read operations with app identity without user credentials. To learn more, see [Get access without a user](https://docs.microsoft.com/graph/auth-v2-service).

<!-- ***********************************************-->
### Device configuration


#### Support for IKEv2 VPN profiles for iOS <!-- 1943438 -->
You'll be able to create VPN profiles for the iOS native VPN client using the IKEv2 protocol. IKEv2 is a new connection type in **Device configuration** > **Profiles** > **Create profile** > **iOS** for platform > **VPN** for profile type > **Settings**.

These VPN profiles configure the native VPN client. So, no VPN client apps are installed or pushed to managed devices. This feature requires devices be enrolled in Intune (MDM enrollment).

To see the current VPN settings you can configure, go to [Configure VPN settings on iOS devices in Microsoft Intune](vpn-settings-ios.md).

Applies to: iOS

#### Configure settings for kernel extensions on macOS devices <!-- 20430240 -->
On macOS devices, you can create a device configuration profile (**Device configuration** > **Profiles** > **Create profile** > choose **macOS** for platform). A future update will include a new group of settings that let you configure and use kernel extensions on your devices.

Applies to: macOS 10.13.2 and later

#### Baseline support for keyword search  <!-- 3082036         -->
While creating or editing a security baseline profile, you’ll soon be able to use *search* to filter the settings that display in the console.   

#### Use "applicability rules" when creating Windows 10 device configuration profiles <!-- 2549910 -->
You create Windows 10 device configuration profiles (**Device configuration** > **Profiles** > **Create profile** > **Windows 10** for platform). You'll be able to create an **applicability rule** so the profile only applies to a specific edition or specific version. For example, you create a profile that enables some BitLocker settings. Once you add the profile, use an applicability rule so the profile only applies to devices running Windows 10 Enterprise.

Applies to: 
- Windows 10 and later

#### Apps from the store only setting for Windows 10 devices includes more configuration options <!-- 2697002  -->

When you create a device restrictions profile for Windows devices, you can use the **Apps from the store only** setting so users only install apps from the Windows App Store (**Device configuration** > **Profiles** > **Create profile** > **Windows 10 and later** for platform > **Device restrictions** for profile type). In a future update, this setting will be expanded to support more options. 

To see the current settings, go to [Windows 10 (and newer) device settings to allow or restrict features using Intune](device-restrictions-windows-10.md#app-store).

Applies to: Windows 10 and later

#### Deploy multiple Zebra mobility extensions device profiles to a device, same user group, or same devices group <!-- 4089955 -->
In Intune, you can use Zebra mobility extensions (MX) in a device configuration profile to customize settings, or add settings not built-in to Intune. Currently, you can deploy one profile to a single device. In a future update, you'll be able to deploy multiple profiles to:

- The same user group
- The same devices group
- A single device

[Use and manage Zebra devices with Zebra Mobility Extensions in Microsoft Intune](android-zebra-mx-overview.md) shows how to use MX in Intune.

Applies to: Android

#### Some kiosk settings on iOS devices are set using "Block", replacing "Allow" <!-- 4404075  -->
When you create a device restrictions profile on iOS devices (**Device configuration** > **Profiles** > **Create profile** > **iOS** for platform > **Device restrictions** for profile type > **Kiosk**), you set the **Auto lock**, **Ringer switch**, **Screen rotation**, **Screen sleep button**, and **Volume buttons**. 

Currently, these settings are configured using **Allow** (blocks the feature) or **Not configured** (allows the feature). In a future update, the values will be **Block** (blocks the feature) or **Not configured** (allows the feature).

To see the current settings, go to [iOS device settings to allow or restrict features](device-restrictions-ios.md). 

Applies to: iOS

#### Use Face ID for password authentication on iOS devices <!-- 4490704  -->
When you create a device restrictions profile for iOS devices, you can use a fingerprint for a password. In a future update, the fingerprint password settings will also allow facial recognition (**Device configuration** > **Profiles** > **Create profile** > **iOS** for platform > **Device restrictions** for profile type > **Password**). As a result, the following settings are changing:

- **Fingerprint unlock** is now **Touch ID and Face ID unlock**.
- **Fingerprint modification (supervised only)** is now **Touch ID and Face ID modification (supervised only)**.

Face ID is available in iOS 11.0 and later. To see the current settings, go to [iOS device settings to allow or restrict features using Intune](device-restrictions-ios.md#password).

Applies to: iOS

#### Apps feature is dependent on ratings region when restricting gaming and app store features on iOS devices <!-- 4593948  -->
On iOS devices, you can allow or restrict features related to gaming, the app store, and viewing documents (**Device configuration** > **Profiles** > **Create profile** > **iOS** for platform > **Device restrictions** for profile type > **App Store, Doc Viewing, Gaming**). You can also choose the Ratings region, such as the United States. In a future update, the **Apps** feature will move to be a child to **Ratings region**, and is dependent on **Ratings region**.

To see the current settings, go to [iOS device settings to allow or restrict features using Intune](device-restrictions-ios.md#app-store-doc-viewing-gaming).

Applies to: iOS

#### Administrative templates for Group Policy     <!--  3510695 -->
To help improve security for devices in the cloud, we will be releasing administrative templates that will let you use Intune to configure select Group Policy settings for Windows PCs.  These templates use the Policy Configuration Service Provider (CSP) to provide up to 2500 additional settings from Office, Windows, and OneDrive.

####  New settings for the Windows security baseline  <!-- 3534649, 4217151          -->
We're adding new settings to the Windows security baseline. The first setting is for Virtualization Based Security, which requires Secure Boot. The second setting will let you manage voice activation of Windows apps when the screen is locked.

#### Security Baselines will be generally available  <!--  3785395       -->
The Security Baselines feature will soon be out of preview, and generally available. 

#### The Windows Security Baseline template will be generally available   <!--  3794072       -->
The Windows Security Baseline template will soon be out of preview, and generally available. The preview version of the template will be retired and a new template will be available.

<!-- ***********************************************-->
### Device management

#### Assign scope tags to all managed devices in a security group <!-- 3173810 -->
Currently, you can assign a scope tag to a device by going into each individual device's **Properties** page and selecting the scope tags. In a future update, you'll be able to assign scope tags to a security group and all devices in the security group will also be associated with those scope tags. To do this, choose **Intune** > **Roles** > **Scope (Tags)** > **Create** > **Scope (Tags)** > choose the groups that you want to assign the scope tag to. All devices in these groups will also be assigned the scope tag. The scope tags set with this feature will overwrite the scope tags set with the current device scope tags flow. (In a future update, the current flow to assign scope tags to devices will be made read only.)

#### See the security patch level for Android devices <!-- 4461911  -->
You'll be able to see the security patch level for Android devices. To do so, choose **Intune** > **Devices** > **All devices** > choose a device > **Monitor** > **Hardware**.


<!-- ***********************************************-->
## Notices

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

### See also
See [What’s New in Microsoft Intune](whats-new.md) for details on recent developments.


