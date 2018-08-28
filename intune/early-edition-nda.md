---
# required metadata

title: Early edition
description:
keywords:
author: ErikjeMS  
ms.author: erikje
manager: dougeby
ms.date: 08/06/2018
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
#ms.tgt_pltfrm:
ms.custom: intune-classic
---

# The early edition for Microsoft Intune - August 2018

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

<!-- 1808 start -->



### Apple VPP token used by another MDM <!-- 1488946 -->
Intune will detect and show details if an Apple volume-purchased program (VPP) token is in use by both Intune and another MDM.

### iOS version number and build number are shown <!-- 1892471 -->
In **Device compliance** > **Device compliance**, the iOS operating system version is shown. In a future update, the build number will also be shown.
When security updates are released, Apple typically leaves the version number as-is, but updates the build number. By showing the build number, you can easily check if a vulnerability update is installed.

### Retired devices in the device compliance dashboard <!-- 1981119 -->
In a future update, retired devices will be removed from the device compliance dashboard. This will change your compliance numbers.

### New user experience update for the Company Portal website <!--2000968 -->
New features will be added, based on feedback from customers, to the Company Portal website. You'll experience a significant improvement in existing functionality and usability from your Android, iOS, and Windows devices. Areas of the site--such as device details, feedback and support, and device overview--will receive a new, modern, responsive design. You'll also see:
- Streamlined workflows across all device platforms
- Improved device identification and enrollment flows
- More helpful error messages
- Friendlier language, less tech jargon
- Ability to share direct links to apps
- Improved performance for large app catalogs
- Increased accessibility for all users

### Configure profile to skip some screens during Setup Assistant <!-- 2276470 -->
When you create a macOS enrollment profile, you'll be able to configure it to skip any of the following screens when a user goes through the Setup Assistant:
- Android Migration
- Display Tone
- Privacy
- iCloudStorage

### Change in the update process for on-premises connectors <!-- 2277554 -->
Based on feedback from customers, the way updates are made to on-premises connectors will be changed. After you initially install an on-premises connector, updates will happen automatically. This change will begin with the new PFX Certificate Connector for Microsoft Intune and will subsequently roll out to other types of on-premises connectors. 



<!-- 1807 start -->

### More sync opportunities in the Company Portal app for Windows <!-- 2683177 -->
The Company Portal app for Windows is adding a device sync action to the Windows taskbar and Start menu jump lists. Click from either locations to quickly sync your devices and get access to corporate resources.  

### Reset device passcodes from Company Portal app for Windows 10 <!-- 2101282 --> 
Your employees will soon be able to reset their device's PIN or passcode directly from the Company Portal app for Windows 10. This functionality will be available on both remote and local Intune-managed devices that support passcode resets. Depending on the type of device, a request made for a remote device will either remove the device's current passcode or create a temporary passcode. Users that request a reset for a local device will be redirected to the device's Settings app.  

### New browsing experiences in the Company portal app for Windows <!-- 2317227 -->  
When browsing or searching for apps in the Company Portal app for Windows, you'll be able to toggle between the existing **Tiles** view and the newly added **Details** view. The new view lists application details such as name, publisher, publication date, and installation status.  

The **Apps** page will introduce an **Installed** view that lets you see details about completed and in-progress app installations. Want to share feedback or thoughts on the new changes? Send us your feedback in the Company Portal app.

### Improved Company Portal app experience for device enrollment manager users <!-- 675800 -->
When a device enrollment manager (DEM) signs in to the Company Portal app for Windows, the app will only list the DEM's current, running device. This improvement will reduce timeouts that previously occurred when the app tried to load all DEM-enrolled devices.  

### Use VPP device licenses to pre-provision the Company Portal during DEP enrollment <!-- 1608345 -->
You'll be able to use Volume Purchase Program (VPP) device licenses to pre-provision the Company Portal during Device Enrollment Program (DEP) enrollments. To do so, when you create or edit an enrollment profile, specify the VPP token that you want to use to install the Company Portal. Make sure that your token doesn't expire and that you have enough licenses for the Company Portal app. In cases where the token expires or runs out of licenses, Intune will push the App Store Company Portal instead (this will prompt for an Apple ID).

### Check for SCCM compliance <!-- 2192052 -->
A future update will include a new System Center Configuration Manager (SCCM) compliance setting (**Device compliance** > **Policies** > **Create policy** > **Windows 10**). SCCM sends signals to Intune compliance. Using the Intune setting, you can require all SCCM signals to return "compliant".

For example, you require all software updates to be installed on devices. In SCCM, this requirement has the “Installed” state. If any programs on the device are in unknown state, then the device will be non-compliant in Intune.

Applies to Windows 10 and later

### Alerts for expiring VPP token or Company Portal license running low <!-- 2237572 -->
If you use the Volume Purchase Program (VPP) to pre-provision the Company Portal during DEP enrollment, Intune will alert you when the VPP token is about to expire and when the licenses for the Company Portal are running low.

### Confirmation required to delete VPP token that is being used for Company Portal pre-provisioning <!-- 2237634 -->
A confirmation will be required to delete a Volume Purchase Program (VPP) token if it is being used to pre-provision the Company Portal during DEP enrollment.

#### Additional security settings for Windows installer <!-- 2282430 -->
You will be able to allow users to control app installs. If enabled, installations that may otherwise be stopped due to a security violation would be permitted to continue. You will be able to direct the Windows installer to use elevated permissions when it installs any program on a system. Additionally, you will be able to enabled Windows Information Protection (WIP) items to be indexed and the metadata about them stored in an unencrypted location. When the policy is disabled, the WIP protected items will not be indexed and will not show up in the results in Cortana or file explorer. The functionality for these options will be disabled by default. 

<!-- 1806 start -->

### 3rd-party keyboards can be blocked by APP settings on iOS <!-- 1248481 -->
On iOS devices, Intune admins will be able to block the use of 3rd-party keyboards when accessing organization data in policy protected apps. When the Application Protection Policy (APP) is set to block 3rd-party keyboards, the device user will receive a message the first time they interact with corporate data when using a 3rd-party keyboard. All options, other than the native keyboard, will be blocked and device users will not see them. Device users will only see the dialog message once. 

### Require non-biometric passcode on app launch and timeout <!-- 1506985 -->

By requiring a non-biometric passcode on app launch and after admin-specified timeout, Intune will provide improved security for Mobile Application Management (MAM) enabled apps by restricting the use of biometric identification for access to corporate data. The settings will affect users who rely on Touch ID (iOS), Face ID (iOS), Android Biometric, or other future biometric authentication methods to access their APP/MAM-enabled applications. These settings will enable Intune admins to have more granular control over user access, eliminating cases where a device with multiple fingerprints or other biometric access methods can reveal corporate data to an incorrect user. In the Azure portal, open **Microsoft Intune**. Select **Mobile apps** > **App protection policies** > **Add a policy** > **Settings**. Locate the **Access** section for specific settings.

### Office 365 Pro Plus language packs <!-- 1833450 -->
As the Intune admin, you will be able to deploy additional languages for Office 365 Pro Plus apps managed through Intune. The list of available languages includes the **Type** of language pack (core, partial, and proofing). In the Azure portal, select **Microsoft Intune** > **Mobile apps** > **Apps** > **Add**. In the **App type** list of the **Add app** blade, select **Windows 10** under **Office 365 Suite**. Select **Languages** in the **App Suite Settings** blade.

### Preview a new user experience update for the Company Portal website <!--2000968 -->
We’re adding new features, based on feedback from customers, to the Company Portal website/iOS app catalog. You'll experience a significant improvement in existing functionality and usability from your Android, iOS, and Windows devices. Areas of the site--such as device details, feedback and support, and device overview--will receive a new, modern, responsive design. You'll also see:

- Streamlined workflows across all device platforms
- Improved device identification and enrollment flows
- More helpful error messages
- Friendlier language, less tech jargon
- Ability to share direct links to apps
- Improved performance for large app catalogs
- Increased accessibility for all users

The update is currently in preview. You can register to join the preview at http://aka.ms/webcpflighting

<!-- 1805 start -->

### Require non-biometric passcode on cold app launch and timeout <!-- 1506985 --> 

By requiring a non-biometric passcode on cold app launch and after admin-specified timeout, Intune will provide improved security for Mobile Application Management (MAM) enabled apps by restricting the use of biometric identification for access to corporate data. The settings will affect users who rely on Touch ID (iOS), Face ID (iOS), Android Biometric, or other future biometric authentication methods to access their APP/MAM-enabled applications. These settings will enable Intune admins to have more granular control over user access, eliminating cases where a device with multiple fingerprints or other biometric access methods can reveal corporate data to an incorrect user. In the Azure portal, open **Microsoft Intune**. Select **Mobile apps** > **App protection policies** > **Add a policy** > **Settings**. Locate the **Access** section for specific settings.

<!-- 1803 start -->

### Ability to deploy required line-of-business (LOB) apps to All Users on Windows 10 Desktop devices <!-- 1627835 RS4 -->
Customers will be able to deploy required line-of-business Windows 10 apps to install in device contexts. This will enable these apps to be available to all users on the device. This is only applicable on Windows 10 Desktop devices.

### Updating the Help and Feedback experience on Company Portal app for Android <!--1631531 -->

The Help and Feedback experience on the Company Portal app for Android will be updated to align with best practices for Android apps. The Company Portal app for Android will be updated over the next few months to divide the **Help and Feedback** menu item to distinct **Help** and **Send Feedback** menu items. The **Help** page will feature a **Frequently Asked Questions** section and **Email Support** button to lead end users to upload logs to Microsoft and send email to company support describing the issue. **Send Feedback** will lead the user through a standard Microsoft feedback submission, which will prompt the user to choose whether, "I like something," "I don't like something," or "I have an idea."

<!-- the following are present prior to 1801 -->

### App Protection Policies  <!-- 679615 -->
Intune App Protection Policies will offer the ability to create global, default policies to quickly enable protection across all users in the entire tenant.

<!-- the following are present prior to 1711 -->

## Notices

There are no active notices at this time.

### See also
See [What’s New in Microsoft Intune](whats-new.md) for details on recent developments.



