---
# required metadata

title: In development - Microsoft Intune
titleSuffix: 
description: Microsoft Intune features in development
keywords:
author: ErikjeMS 
ms.author: erikje
manager: dougeby
ms.date: 09/27/2019
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

# In development for Microsoft Intune - October 2019

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
## App management
## Device configuration
## Device enrollment
## Device management
## Intune apps
## Monitor and troubleshoot
## Role-based access control
## Security

-->
 
<!-- ***********************************************-->
## App management

### Additional app configuration variable available <!-- 4969237  -->
When creating an app configuration policy, you'll be able to include the `AAD Device ID` configuration variable as part of your configuration settings. In Intune, select **Client apps** > **App configuration policies** > **Add**. Enter your configuration policy details and select **Configuration settings** to view the **Configuration settings** blade.

### Dark Mode for iOS Company Portal <!-- 4911422  -->
Dark Mode is planned for the iOS Company Portal. Download company apps, manage your devices, and get IT support in the color scheme of your choice. For more information about the iOS Company Portal, see [How to configure the Microsoft Intune Company Portal app](company-portal-app.md).

### Prevent installation of apps from Unknown Sources on Android Enterprise devices <!-- 4760025  -->
For an Android Enterprise work profile device, it is never possible for end users to install apps from unknown sources into the work profile. You'll be able to optionally extend this restriction to the personal profile as well. If you enable this restriction, end users on Android Enterprise work profile devices will also be prevented from side-loading apps from unknown sources into the personal side of their device. 

### Update to app protection UI and iOS app provisioning UI <!-- 4102027, 4102029  -->
The UI to create and edit app protection policies and iOS app provisioning profiles in Intune will be updated. UI changes include:
- A simplified experience by using a wizard-style format condensed within one blade. 
- An update to the create flow to include assignments.
- A summarized page of all things set when viewing properties, prior to creating a new policy or when editing a property. Also, when editing properties, the summary will only show a list of items from the category of properties being edited.

### Create groups of management objects called Policy sets <!-- 3762880  -->
Policy sets allow you to create a bundle of references to already existing management entities that need to be identified, targeted, and monitored as a single conceptual unit. Policy sets do not replace existing concepts or objects. An admin can continue to assign individual objects as they do today. Individual objects are referenced by a Policy set. Therefore, any changes to those individual objects will be reflected in the Policy set. ​ In Intune, you will select **Policy sets** > **Create** to create a new Policy set. 

### Win32 apps on Windows 10 S mode devices <!-- 3747604  --> 
You'll be able to install and run Win32 apps on Windows 10 S mode-managed devices. You'll be able to create one or more supplemental policies for S mode using the Windows Defender Application Control (WDAC) PowerShell tools. Sign the supplemental policies with the Device Guard Signing Portal and then upload and distribute the policies via Intune. In Intune, you will find this capability by selecting **Client apps** > **Windows 10 S supplemental policies**. 

### Set app availability based on a date and time <!-- 3510685  -->
As an admin, you'll be able to configure the start time and deadline time for a required app. At the start time, Intune management extension will start the app content download and cache it. The app will be installed at the deadline time. For available apps, start time will dictate when the app is visible in Company Portal. In Intune, select **Client apps** > **Apps**. Then, select a specific app from the list or select **Add** to add a new app. From the app blade, select **Assignments** > **Add group**. Set the **Assignment type** to **Required** and then select **Included Groups**. Set **Make this app required for all users** to **Yes** and select **Edit** to modify the **End user experience** options. In the **End user experience** blade, set the **Software available time** as needed. For more information about adding apps, see [Add apps to Microsoft Intune](apps-add.md).


### Require Win32 apps to restart <!-- 3136567  -->
You'll be able to require that a Win32 app must restart after a successful install. Also, you'll be able to choose the amount of time (the grace period) before the restart must occur.

### Company Portal app on Windows <!-- 1808082  -->
The Company Portal app on Windows devices will be updated to display toast notifications to users, even when the application is closed. The update will only show notifications for available apps when the install status is completed or failed. The Company Portal app will not show notifications for required applications.

### Company Portal app installation status messages <!-- 2514416  -->
The Company Portal app will show additional app installation status messages to end users. The following conditions will apply to new Win32 dependency features:
- App failed to install. Dependencies defined by the admin were not met.
- App installed successfully but requires a restart.
- App is in the process of installing, but requires a restart to continue.

### Assign Microsoft Edge beta for macOS <!-- 4678761  -->
You'll be able to add and assign the latest version of Microsoft Edge beta to Intune for macOS devices. From Intune, select **Client apps** > **Apps** > **Add app** > **Microsoft Edge - macOS**. Then, assign Microsoft Edge beta to the intended groups. Microsoft AutoUpdate (MAU) keeps Microsoft Edge up-to-date. For more information about Microsoft Edge, see [Manage web access by using Microsoft Edge with Microsoft Intune](manage-microsoft-edge.md).

### Configure app notification content for organization accounts <!-- 2576686 -->
Intune app protection policies (APP) on Android and iOS devices will allow you to control app notification content for Org accounts. This feature will require support from applications and may not be available for all APP enabled applications. For more about APP, see [What are app protection policies?](app-protection-policy.md).

### Available Google Play app reporting for Android work profiles <!-- 3041956  -->
For available app installs on Android work profile devices, you can view app installation status and the installed version of managed Google Play apps. For more information, see [How to monitor app protection policies](app-protection-policies-monitor.md), [Manage Android work profile devices with Intune](android-enterprise-overview.md) and [Managed Google Play app type](apps-add-android-for-work.md#managed-google-play-app-types).

<!-- ***********************************************-->
## Device configuration

### New device configuration settings for supervised iOS and iPadOS devices <!-- 5199328  -->
On iOS and iPadOS devices, you can create a profile to restrict features and settings on devices (**Device configuration** > **Profiles** > **Create profile** > **iOS/iPadOS** for platform > **Device restrictions** for profile type). There will be new settings you can control: 
- Access to network drive in Files app  
- Access to USB drive in Files app 
- Wi-Fi always turned on 

To see the current settings, go to [iOS device settings to allow or restrict features using Intune](device-restrictions-ios.md).

Applies to:
- iOS 13.0 and newer
- iPadOS 13.0 and newer

### Connect automatically setting is removed in Wi-Fi profiles on Android and Android Enterprise <!-- 5021055  -->
On Android and Android Enterprise devices, you can create a Wi-Fi profile to configure different settings (**Device configuration** > **Profiles** > **Create profile** > **Android** or **Android Enterprise** for platform > **Wi-Fi** for profile type). The **Connect automatically** setting will be removed, as it's [not support by Android](https://developer.android.com/reference/android/net/wifi/WifiManager.html#enableNetwork%28int%2c%20boolean%29). 

If you use this setting in a Wi-Fi profile, you may notice that **Connect automatically** won't work. You don't need to take any action, but be aware this setting is removed in the Intune user interface.

To see the current settings, go to [Android Wi-Fi settings](wi-fi-settings-android.md) or [Android Enterprise Wi-Fi settings](wi-fi-settings-android-enterprise.md).

Applies to:
- Android
- Android Enterprise

### Create a global HTTP proxy on Android Enterprise device owner devices <!-- 4816339  -->
On Android Enterprise devices, you can create a VPN profile with different VPN clients (**Device configuration** > **Profiles** > **Create profile** > **Android Enterprise** for platform > **Device owner > Device restrictions** for profile type > **Connectivity**). You'll be able to configure a global HTTP proxy to meet your organization's web browsing standards. All apps that go to HTTP web sites use this proxy.

Applies to:
- Android Enterprise Device Owner

### New device firmware configuration interface profile for Windows 10 and later devices <!-- 2266073  -->
On Windows 10 and later, you can create a device configuration profile to control settings and features (**Device configuration** > **Profiles** > **Create profile** > **Windows 10 and later** for platform). There will be a new device firmware configuration interface profile type that allows Intune to manage UEFI (BIOS) settings.

To see an overview of all the settings you can configure, see [Apply features and settings on your devices using device profiles in Microsoft Intune](device-profiles.md).

Applies to:
- Windows 10 RS5 (1809) and newer on some OEMs

### PKCS certificates for macOS  <!-- 1333650                -->
We'll be adding full support for PKCS certificates on devices that run macOS. Users will be able to deploy user and device certificates with customization subject and subject alternative name fields. We also will have a new setting Allow All Apps Access, which by enabling gives all associated apps access to the private key. For more details on this setting, visit the following Apple documentation: https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf.

###   Derived Credentials to provision mobile devices with certificates      <!--  1736036, 1736037, 1772050      --> 
We’ll be adding support for Derived Credentials, which support the *National Institute of Standards and Technology (NIST) 800-157* standard for deploying certificates to devices.  Derived credentials rely on the use of a Personal Identity Verification (PIV)  or Common Access Card (CAC) card, like a smart card. Users authenticate with their smart card on a computer, and then submit a request for a certificate for their managed device following the process required by the derived credential provider.   

The process to use Derived Credentials to get a certificate is different than using SCEP or PKCS certificate profiles, but the end result is the same – mobile devices with certificates for authentication that can be used for app authentication, VPN, Wi-Fi, or email profiles.   

For more information, see [Derived PIV Credentials](https://www.nccoe.nist.gov/projects/building-blocks/piv-credentials) at www.nccoe.nist.gov.

The initial release of derived credentials will support Entrust Datacard, Intercede, and DISA Purebred on iOS. Additional platforms and derived credential providers will be supported in later releases.   

<!-- ***********************************************-->
## Device enrollment

### Specify which Android device operating system versions enroll with work profile or device administrator enrollment <!-- 4350697 -->
Using Intune device type restrictions, you'll be able to use the device's OS version to specify which user devices will use Android Enterprise work profile enrollment or Android device administrator enrollment. To do so, go to **Intune** > **Device enrollment** > **Enrollment restrictions** > **Create restriction** > **Device type restriction** > **Platform settings**.

### Edit device name value for Autopilot devices <!-- 4816775 -->
You'll be able to edit the Device Name value for Azure AD Joined Autopilot devices. To do so, go to **Intune** > **Device enrollment** > **Windows enrollment** > **Windows Autopilot** > **Devices** > choose the device > change the Device Name value in the right pane > **Save**.

### For iOS devices, customize the enrollment process privacy screen of the Company Portal <!-- 4394993  -->
Using markdown, you'll be able to customize the Company Portal's privacy screen that end users see during iOS enrollment. Specifically, you'll be able to customize the list of things that your organization can't see or do on the device.

<!-- ***********************************************-->
## Device management

### Edit Group Tag value for Autopilot devices<!-- 4816775 -->
You'll be able to edit the Group Tag value for Autopilot devices. To do so, go to **Intune** > **Device enrollment** > **Windows enrollment** > **Windows Autopilot** > **Devices** > choose the device > change the Group Tag value in the right pane > **Save**.

### UI update for creating and editing Windows 10 Update Rings  <!-- 4099089          -->   
We’ll be rolling out an updated create and edit UI experience for Windows 10 Update Rings for Intune.  Changes to UI will include:  
- Simplify the existing experience by using a wizard-style format condensed within one blade. This UI update will do away with blade sprawl that requires IT Pros to drill down into deep blade journeys.   
- Revise the create flow to include Assignments.  
- The addition of a summarized page of all things set when viewing Properties, prior to creating a new update ring, and when editing a property. When editing, the summary will only show the list of items set within the one category of properties being edited.

### UI update for creating and editing iOS Software Updates  <!-- 4099090        -->   
We’ll be rolling out an updated create and edit UI experience for iOS Software Updates to Intune. Changes to UI will include:
- Simplify the existing experience by using a wizard-style format condensed within one blade. This UI update will do away with blade sprawl that requires IT Pros to drill down into deep blade journeys.  
- The iOS Software Update policy create flow will update to include Assignments 
- The iOS Software Update policy will include a summarized page of all things set when viewing Properties, prior to creating a new policy and when editing a property. When editing, the summary will only show the list of items set within the one category of properties being edited.

### Target macOS user groups to require Jamf management <!-- 4061739 -->
You’ll be able to target specific groups of users to require that their macOS devices are managed by Jamf. This targeting will enable you to apply the Jamf compliance integration to a subset of macOS devices while other devices continue to be managed by Intune. It will also let you gradually migrate users' devices from one MDM to the other.

### New restrictions for renaming Windows devices <!-- 3478938 -->
Device names will have to follow these rules:
- 15 characters or less (must be less than or equal to 63 bytes, not including trailing NULL)
- Not null or empty string
- Allowed ASCII: Letters (a-z, A-Z), numbers (0-9), and hyphens
- Allowed Unicode: characters >= 0x80, must be valid UTF8, must be IDN-mappable (RtlIdnToNameprepUnicode succeeds; see RFC 3492)
- Names must not contain only numbers or start with a number
- No spaces in the name
- Disallowed characters: { | } ~ [ \ ] ^ ' : ; < = > ? & @ ! " # $ % ` ( ) + / , . _ *)

### Deploy Software Updates to macOS devices <!-- 3194876 -->
You'll be able to deploy Software Updates to groups of macOS devices. This feature includes critical, firmware, configuration file, and other updates. You'll be able to send updates on the next device check-in or select a weekly schedule to deploy updates in or out of time windows that you set. This feature helps when you want to update devices outside standard work hours or when your help desk is fully staffed. You'll also get a detailed report of all macOS devices with updates deployed. You can drill into the report on a per-device basis to see the statuses of particular updates.

<!-- ***********************************************-->
## Monitor and troubleshoot

### New Android report on Devices overview page <!-- 2984353  -->
We'll be adding a new report to the Devices overview page that displays how many Android devices have been enrolled in each device management solution. This chart will show work profile, fully managed, dedicated, and device administrator enrolled device counts. To see the report, choose **Intune** > **Devices** > **Overview**.

### Windows Autopilot deployment reports <!-- 3856172  -->
A new report will detail each device deployed through Windows Autopilot. This data will be available for 30 days after deployment. To see the report, go to **Intune** > **Device enrollment** > **Monitor** > **Autopilot deployments**.

### Updated support experience   <!--  5012398    -->
As part of continuing improvements, we’ll be updating the in-console support experience for Intune.  We’ll be improving the in-console search and feedback for common issues, and streamlining the workflow to contact support.     

<!-- ***********************************************-->
<!--## Security-->


<!-- ***********************************************-->
## Notices

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

## See also
See [What’s New in Microsoft Intune](whats-new.md) for details on recent developments.




