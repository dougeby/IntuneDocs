---
# required metadata

title: In development - Microsoft Intune
titleSuffix: 
description: Microsoft Intune features in development
keywords:
author: ErikjeMS 
ms.author: erikje
manager: dougeby
ms.date: 03/29/2019
ms.topic: conceptual
ms.prod:
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

# In development for Microsoft Intune - April 2019

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

<!-- 1904 start-->

### Set login settings and control restart options on macOS devices <!-- 1210083 -->
On macOS devices, you can create a device configuration profile (**Device configuration** > **Profiles** > **Create profile** > choose **macOS** for platform > **Device features** for profile type). New login window settings will include items such as showing a custom banner, choose how users sign in, show or hide the power settings, and more.

To see the current settings, go to [macOS device feature settings](macos-device-features-settings.md).

Applies to: 
macOS

### Advanced settings for Windows Defender Firewall <!-- 1311949 -->
You'll soon be able to use Intune to manage the custom firewall rules on clients for Windows Defender. Rules can specify inbound and outbound behavior to applications, network addresses, and ports. 

### Require App Protection Conditional Access  <!--1634317 -->
You'll be able to use *Require App Protection policy*, which confirms policy is applied to a user’s app before sign in completes to prevent users from accessing data you protect with conditional access. While policy assurance might slow down the first use experience, it helps to protect against network issues, administrative misconfigurations, or intentional efforts to foil application protection policies. 

### Deployment of online licensed Microsoft Store for Business apps <!-- 16726660 -->
You'll be able to assign required online licensed Microsoft Store for Business apps in the device context. Deploying a Microsoft Store for Business app this way will enable the app to be installed for all users on the device. This is only applicable on Windows 10 RS4+ desktop devices. The option to install in the device context is available in the Client Apps assignment page for MSFB Online Licensed apps.

### Include and exclude mixture of user groups and device groups when assigning policies and profiles <!-- 1807547 -->
When assigning compliance policies or configuration profiles, you can assign them to security groups with users or devices. Currently, you can include and exclude only user groups, *or* include and exclude only device groups. You can't include and exclude a mixture of groups, such as include user groups *and* exclude a devices group.

You'll be able to include and exclude a mix of user groups and device groups. You can include a group of users, and exclude a group of devices. For example, you can assign or deploy a device configuration profile to a group of users, but exclude personal devices.

[Assign device configuration profiles](device-profile-assign.md) includes more information on assigning profiles to user groups and device groups.

Applies to: 
All platforms

### Retire noncompliant devices <!-- 1827291 -->
We're going to add a new compliance action to retire a noncompliant device. Retiring a noncompliant device removes all company data from it, and also removes the device from being managed by Intune. This action runs when the configured value in days is reached. The minimum value is 30 days. 

### Configure settings for kernel extensions on macOS devices <!-- 2043024 -->
On macOS devices, you can create a device configuration profile (**Device configuration** > **Profiles** > **Create profile** > choose **macOS** for platform). A new group of settings will let you configure and use kernel extensions on your devices.

Applies to: 
macOS 10.13.2 and later

### Configure profile to skip some screens during Setup Assistant <!-- 2276470 -->
When you create a macOS enrollment profile, you'll be able to configure it to skip any of the following screens when a user goes through the Setup Assistant:
- Android Migration
- Display Tone
- Privacy
- iCloudStorage
If you create a new profile or edit a profile, the selected skip screens need to sync with the Apple MDM server. Users can issue a manual sync of the devices so that there is no delay in picking up the profile changes.
For more information, see [Automatically enroll macOS devices with the Device Enrollment Program or Apple School Manager](device-enrollment-program-enroll-macos.md).

### Device users can view all managed apps they've installed or tried to install <!-- 2352913 -->
Company Portal for Windows will list all managed apps&ndash; both required and available&ndash; that are installed on a user's device. Users will be able to view attempted and pending app installations, and their current statuses. If your organization doesn't make apps required or available, users will see a message explaining that no company apps have been installed. Users will also be able to sort or filter their apps by installation status.

### Scope tags for Apple VPP tokens <!--2371886 -->
You'll be able to add scope tags to Apple VPP tokens. Only users assigned with the same scope tag will have access to the Apple VPP token with that tag. VPP apps and ebooks purchased with that token inherit its scope tags. For more information about scope tags, see [Use RBAC and scope tags](scope-tags.md).

### Use "applicability rules" when creating Windows 10 device configuration profiles <!-- 2549910 -->
You create Windows 10 device configuration profiles (**Device configuration** > **Profiles** > **Create profile** > **Windows 10** for platform). You'll be able to create an **applicability rule** so the profile only applies to a specific edition or specific version. For example, you create a profile that enables some BitLocker settings. Once you add the profile, use an applicability rule so the profile only applies to devices running Windows 10 Enterprise.

Applies to: 
- Windows 10 and later

### Enable Win32 app dependencies <!-- 2617348 -->
Public preview - As the admin, you'll be able to require that other apps are installed as dependencies before installing your Win32 app. Specifically, the device must install the dependent app(s) before it installs the Win32 app. This functionality will be available only after the Intune Management agent has been upgraded to 1904 version (greater than 1.18.120.0) which could take 1 or 2 additional weeks after we upgrade the service to 1904. In Intune, select **Client apps** > **Apps** > **Add** to display the **Add app** blade. Select **Windows app (Win32)** as the **App type**. For more information, see [Intune Standalone - Win32 app management](apps-win32-app-management.md).

### New device restriction setting for Android Enterprise, Device Owner: let users connect to Wi-Fi networks on Android Enterprise dedicated devices running multi-app kiosk mode <!--3041940 -->
Admins will be able to toggle a new setting that lets users configure Bluetooth on their Android Enterprise dedicated devices running multi-app kiosk mode. To see this setting in the Intune console, choose **Intune** > **Device configuration** > **Profiles** > **Create profile** > choose **Android Enterprise** for platform > **Device owner only, Device restrictions** for profile type > **Settings** > **Dedicated devices** > select **Multi-app** from the **Kiosk mode** setting drop down. An option called **Wi-Fi configuration** will be available to enable. 

Applies to: Android Enterprise dedicated devices running multi-app kiosk mode. 

### New device restriction setting for Android Enterprise, Device Owner: let users configure Bluetooth and pairing on Android Enterprise dedicated devices <!--3041941 -->
Admins will be able to toggle a new setting that lets users configure Bluetooth on their Android Enterprise dedicated devices running multi-app kiosk mode. To see this setting in the Intune console, choose **Intune** > **Device configuration** > **Profiles** > **Create profile** > choose **Android Enterprise** for platform > **Device owner only, Device restrictions** for profile type > **Settings** > **Dedicated devices** > select **Multi-app** from the **Kiosk mode** setting drop down. An option called **Bluetooth configuration** will be available to enable. 

Applies to: Android Enterprise dedicated devices running multi-app kiosk mode. 

### Monitor Security Baseline status (public preview) <!-- 3082047 --> 
When you monitor the *Device status* for your security baselines, the view will organize the status by the baseline categories, like *Above lock*, *BitLocker*, and *Browser*. All available baseline categories will be represented. For each category, you'll see how many devices do not match a specific baseline category, are misconfigured, or are not applicable.

###  Intune security tasks for Defender ATP (In public preview) <!-- 3208597 -->
Coming as a public preview, Intune will soon add security tasks for the newly announced Microsoft Defender Threat & Vulnerability Management.  With this integration, security operations admins in Windows Defender ATP (WDATP) can more effectively communicate the recommended remediations for emerging threats to Intune administrators. The addition of security tasks adds a risk-based approach to discover, prioritize, and remediate endpoint vulnerabilities and misconfigurations.

To learn more about security tasks in Intune, see the blog post about [using Intune security tasks to extend Microsoft Defender ATP’s Threat and Vulnerability Management](https://techcommunity.microsoft.com/t5/Enterprise-Mobility-Security/Microsoft-Intune-security-tasks-extend-Microsoft-Defender-ATP-s/ba-p/369857). 

### Create and use OEMConfig device configuration profiles in Intune <!-- 3305883 -->
Intune will support configuring Android Enterprise devices with OEMConfig. Specifically, you can create a device configuration profile, and apply settings to Android Enterprise devices using OEMConfig (**Device configuration** > **Profiles** > **Create profile** > **Android enterprise** for platform).

Support for OEMs is currently on a per-OEM basis. If an OEMConfig app you want isn't available in the list of OEMConfig apps, contact `IntuneOEMConfig@microsoft.com`.

Applies to: 
- Android enterprise

### New device restriction settings for Android Enterprise, Device Owner <!-- 3574254 -->
On Android Enterprise devices, you can create a device restriction profile to allow or restrict features, set password rules, and more (**Device configuration** > **Profiles** > **Create profile** > choose **Android Enterprise** for platform > **Device owner only > Device restrictions** for profile type). 

New settings, including password settings, allowing full access to apps in Google Play Store for fully managed devices, and more will be available. 

To see the current list of settings, go to [Android Enterprise device settings to allow or restrict features](device-restrictions-android-for-work.md). 

Applies to: 
Android Enterprise fully managed devices

### Check for a TPM chipset in a Windows 10 device compliance policy <!-- 3617671 -->
Many Windows 10 and later devices have Trusted Platform Module (TPM) chipsets. A new compliance setting will check if a TPM is on the device.

[Windows 10 and later compliance policy settings](compliance-policy-create-windows.md) lists the current settings.

Applies to: 
- Windows 10 and later

### Configure your Win32 apps to be installed on Intune enrolled Azure AD joined devices <!-- 3695227 -->
You'll be able to assign your Win32 apps to be installed on Intune enrolled Azure AD joined devices. For more information about Win32 apps in Intune, see [Win32 app management](apps-win32-app-management.md).

### Windows Defender Advanced Threat Protection baseline <!-- 3754134 -->
We're going to add new baseline to help you configure Windows Defender Advanced Threat Protection settings.

### Device overview shows Primary User <!--794259 -->
The Device overview page will show the Primary User, also called the User Device Affinity User (UDA). To see the Primary User for a device, choose **Intune** > **Devices** > **All devices** > choose a device. The Primary User will appear near the top of the **Overview** page.

### Expanded support for Android Enterprise fully managed devices <!-- 3903241, 3903244, 3903246 -->
We're going to expand the support of Android Enterprise fully managed devices ([first announced in January of 2019](whats-new.md#week-of-january-14-2019) to include the following:
- Compliance
- Conditional access
- New end user App

To set up Android fully managed devices, go to **Device enrollment** > **Android enrollment** > **Corporate-owned, fully managed user devices**. 
Support for fully managed Android devices remains in preview, and some Intune features might not be fully functional. 

### Additional Managed Google Play app reporting for Android Enterprise work profile devices <!-- 4105925 -->
For Managed Google Play apps deployed to Android Enterprise work profile devices, it will be possible to view the specific version number of the app installed on a device. This applies to required apps only. The same functionality for available apps will be enabled in a future release.

### iOS Third Party Keyboards <!-- 4111843 -->
Support for the Intune app protection policy (APP) for the **Third Party Keyboards** setting will end due to an iOS platform change. You will not be able to configure this setting in the Intune Admin Console and it will not be enforced on the client in the Intune App SDK.

<!-- 1903 start-->

### Block users from scanning for Windows updates <!-- 3316758 -->
We're adding a new Windows update ring setting that you can use to block users from scanning for Windows updates. This setting won't be available from within the portal, but can be configured by using the Intune Graph API.

### Windows Update notifications <!-- 3316782 -->
We're adding support to the Windows Update ring configurations so you'll be able to configure the Windows Update notifications your users see. This setting won't be available from within the portal, but can be configured by using the Intune Graph API.

### Changes to Company Portal enrollment for iOS 12 device users <!--3448635 --> 
Company Portal for iOS will be updating the app enrollment screens and steps to align with the MDM enrollment changes released in Apple iOS 12.2. The updated workflow will now prompt users to:

- Allow Safari to open the Company Portal website (via Safari) and download the management profile before returning to the Company Portal app.
- Open the Settings app to install the management profile on their device.
- Return to the Company Portal app to complete enrollment.

For more information about how you can prepare for these changes, see the [Microsoft Tech Community post](https://aka.ms/CP_changes_iOS12). In the meantime, to support new iOS enrollments in Company Portal, we've updated the steps in [Enroll iOS device in Intune](https://docs.microsoft.com/en-us/intune/ios-enroll). These doc changes will be live after Apple releases iOS version 12.2. 

### Easier access to Diagnostic Settings <!-- 3804627 -->
We’re adding a new option to the **Audit logs** blade in every Audit Log workload in the Intune console that you can use to directly open the *Diagnostic Settings* page.

## Notices

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

### See also
See [What’s New in Microsoft Intune](whats-new.md) for details on recent developments.


