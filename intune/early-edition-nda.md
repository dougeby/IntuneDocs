---
# required metadata

title: Early edition
description:
keywords:
author: ErikjeMS  
ms.author: erikje
manager: dougeby
ms.date: 06/28/2018
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

# The early edition for Microsoft Intune - July 2018

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

### Use S/MIME to encrypt and sign a user's multiple devices  <!-- 1333642 -->
A future update will include an S/MIME email encryption using a new imported certificate profile (**Device configuration** > **Profiles** > **Create profile** > select the platform > **PKCS imported certificate** profile type). In Intune, you can import certificates in PFX format. Intune can then deliver those same certificates to multiple devices enrolled by a single user. This also includes:

- The native iOS email profile supports enabling S/MIME encryption using imported certificates in PFX format.
- The native mail app on Windows Phone 10 devices automatically use the S/MIME certificate.
- The private certificates can be delivered across multiple platforms. But, not all email apps support S/MIME.
- On other platforms, you may need to manually configure the mail app to enable S/MIME.  
- Email apps that support S/MIME encryption may handle retrieving certificates for S/MIME email encryption in a way that an MDM cannot support, such as reading from their publisher's certificate store.

Supported on: Windows, Windows Phone 10, macOS, iOS, Android

### Use VPP device licenses to pre-provision the Company Portal during DEP enrollment <!-- 1608345 -->
You'll be able to use Volume Purchase Program (VPP) device licenses to pre-provision the Company Portal during Device Enrollment Program (DEP) enrollments. To do so, when you create or edit an enrollment profile, specify the VPP token that you want to use to install the Company Portal. Make sure that your token doesn't expire and that you have enough licenses for the Company Portal app. In cases where the token expires or runs out of licenses, Intune will push the App Store Company Portal instead (this will prompt for an Apple ID).

### Bulk delete devices on devices blade <!-- 1793693 -->
You'll be able to delete multiple devices at a time on the Devices blade. Choose **Devices** > **All devices** > select the devices you want to delete > **Delete**. For devices that can't be deleted, an alert will be displayed.

### New Wi-Fi device configuration profile for Windows 10 and later <!-- 1879077 -->
Currently, you can import and export Wi-Fi profiles using XML files. You'll be able to create a Wi-Fi device configuration profile directly in Intune, just like some other platforms.

To create the profile, open **Device configuration** > **Profiles** > **Create Profile** > **Windows 10 and later** > **Wi-Fi**. 

Applies to Windows 10 and later.

###  Windows line-of-business (LOB) apps file extensions <!-- 1884873 -->
The file extensions for Windows LOB apps will now include *.appx*, *.appxbundle*, *.msix* and *.msixbundle*. You can add an app in Microsoft Intune by selecting **Mobile apps** > **Apps** > **Add**. The **Add app** pane is displayed which allows you to select the **App type**. For Windows LOB apps, select **Line-of-business** app as the app type, select the **App package file**, and then enter an installation file with the appropriate extension.

### Windows Defender ATP configuration package automatically added to configuration profile <!-- 2144658 -->
When using [Advanced Threat Protection and onboarding](advanced-threat-protection.md#onboard-devices-using-a-configuration-profile) devices in Intune, you currently download a configuration package, and add it to your configuration profile. In a future update, Intune automatically gets the package from Windows Defender Security Center, and adds it to your profile.

Applies to Windows 10 and later.

### Kiosk - obsolete is grayed out, and can't be changed <!-- 2149998 -->
The [Kiosk feature](device-restrictions-windows-10.md#kiosk-preview---obsolete) (**Device configuration** > **Profiles** > **Create profile** > **Windows 10 and later** > **Device restrictions**) will be obsolete, and replaced with [Kiosk settings for Windows 10 and later](kiosk-settings.md). The **Kiosk - Obsolete** feature will be grayed out, and the user interface can't be changed or updated. 

To enable kiosk mode, see [Kiosk settings for Windows 10 and later](kiosk-settings.md).

Applies to Windows 10 and later, Windows Holographic for Business

### APIs to use 3rd party certification authorities <!-- 2184013 -->
There will be a Java API that enables third-party certificate authorities to integrate with Intune and SCEP. Then, users can add the SCEP certificate to a profile, and apply it to devices using MDM.

Currently, Intune supports [SCEP requests using Active Directory Certificate Services](certificates-scep-configure.md).

### Check for SCCM compliance <!-- 2192052 -->
A future update will include a new System Center Configuration Manager (SCCM) compliance setting (**Device compliance** > **Policies** > **Create policy** > **Windows 10**). SCCM sends signals to Intune compliance. Using the Intune setting, you can require all SCCM signals to return "compliant".

For example, you require all software updates to be installed on devices. In SCCM, this requirement has the “Installed” state. If any programs on the device are in unknown state, then the device will be non-compliant in Intune.

Applies to Windows 10 and later

### Alerts for expiring VPP token or Company Portal license running low <!-- 2237572 -->
If you use the Volume Purchase Program (VPP) to pre-provision the Company Portal during DEP enrollment, Intune will alert you when the VPP token is about to expire and when the licenses for the Company Portal are running low.

### Confirmation required to delete VPP token that is being used for Company Portal pre-provisioning <!-- 2237634 -->
A confirmation will be required to delete a Volume Purchase Program (VPP) token if it is being used to pre-provision the Company Portal during DEP enrollment.

### Automatically mark Android devices enrolled by using Samsung Knox Mobile Enrollment as "corporate" <!-- 2404851 -->
By default, Android devices enrolled using Samsung Knox Mobile Enrollment will be marked as **corporate** under **Device Ownership**. You won't need to manually identify corporate devices using IMEI or serial numbers prior to enrolling using Knox Mobile Enrollment.

### Toggle to show or not show the End Session button on a Kiosk browser <!-- 2455253 -->
You'll be able to configure whether or not Kiosk browsers show the End Session button. You can see the control at **Device configuration** > **Kiosk (preview)** > **Kiosk Web Browser**. If turned on, when a user clicks the button, the app prompts for confirmation to end the session. When confirmed, the browser clears all browsing data and navigates back to the default URL.

### Create an eSIM cellular configuration profile <!-- 2564077 -->
In **Device configuration**, you'll be able to create an eSIM cellular profile. You can import a file that contains cellular activation codes provided by your mobile operator. You can then deploy these profiles to your eSIM LTE enabled Windows 10 devices, such as the Surface Pro LTE and other eSIM capable devices.

Check to see if your [devices support eSIM profiles](https://support.microsoft.com/help/4020763/windows-10-use-esim-for-cellular-data).

Applies to Windows 10 and later. 




<!-- 1806 start -->


### 3rd-party keyboards can be blocked by APP settings on iOS <!-- 1248481 -->
On iOS devices, Intune admins will be able to block the use of 3rd-party keyboards when accessing organization data in policy protected apps. When the Application Protection Policy (APP) is set to block 3rd-party keyboards, the device user will receive a message the first time they interact with corporate data when using a 3rd-party keyboard. All options, other than the native keyboard, will be blocked and device users will not see them. Device users will only see the dialog message once. 

### Create device compliance policy using Firewall settings on macOS devices <!-- 1497640 -->
When you create a new macOS compliance policy (**Device compliance** > **Policies** > **Create policy** > **Platform: macOS** > **System security**), there will be some new **Firewall** settings available: 
- **Firewall**: Configure how incoming connections are handled in your environment.
- **Incoming connections**: **Block** all incoming connections except those required for basic internet services, such as DHCP, Bonjour, and IPSec. This setting also blocks all sharing services.
- **Stealth Mode**: **Enable** stealth mode to prevent the device from responding to probing requests. The device continues to answer incoming requests for authorized apps.

Applies to: macOS 10.12 and later

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


### Edit your Office 365 Pro Plus app deployments <!-- 2150145 -->
As the Microsoft Intune admin, you will have greater ability to edit your Office 365 Pro Plus app deployments. In the Azure portal, select **Microsoft Intune** > **Mobile apps** > **Apps**. From the list of apps, select your Office 365 Pro Plus Suite.  

<!-- 1805 start -->

### Require non-biometric passcode on cold app launch and timeout <!-- 1506985 --> 

By requiring a non-biometric passcode on cold app launch and after admin-specified timeout, Intune will provide improved security for Mobile Application Management (MAM) enabled apps by restricting the use of biometric identification for access to corporate data. The settings will affect users who rely on Touch ID (iOS), Face ID (iOS), Android Biometric, or other future biometric authentication methods to access their APP/MAM-enabled applications. These settings will enable Intune admins to have more granular control over user access, eliminating cases where a device with multiple fingerprints or other biometric access methods can reveal corporate data to an incorrect user. In the Azure portal, open **Microsoft Intune**. Select **Mobile apps** > **App protection policies** > **Add a policy** > **Settings**. Locate the **Access** section for specific settings.

### Block app access based on unapproved device vendors and models  <!-- 1425689 ! -->
The Intune IT admin will be able to enforce a specified list of Android manufacturers, and/or iOS models through Intune App Protection Policies. The IT admin can provide a semicolon separated list of manufacturers for Android policies and device models for iOS policies. Intune App Protection Policies are for Android and iOS only. There will be two separate actions that can be performed on this specified list:
- A block from app access on devices that are not specified.
- Or, a selective wipe of corporate data on devices that are not specified. 

The user will be unable to access the targeted application if the requirements through the policy are not met. Based on settings, the user may either be blocked, or selectively wiped of their corporate data within the app. On iOS devices, this feature requires the participation of applications (i.e WXP, Outlook, Managed Browser, Yammer) to integrate the Intune APP SDK for the minimum version settings to be enforced for the targeted applications. This integration happens on a rolling basis and is dependent on the specific application teams. On Android, this feature requires the latest Company Portal. 

On end-user devices, the Intune client would take action based on a simple matching of the strings specified in the Intune blade for Application Protection Policies. This depends entirely on the value that the device reports. As such, the IT administrator is encouraged to ensure that the intended behavior is accurate. This can be accomplished by testing this setting based on a variety of device manufacturers and models targeted to a small user group. In Microsoft Intune, select **Mobile apps** > **App protection policies** to view and add app protection policies. For more information about app protection policies, see [What are app protection policies](app-protection-policy.md).


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
