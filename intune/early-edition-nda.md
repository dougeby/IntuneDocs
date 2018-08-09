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

### Windows Hello will target users and devices <!-- 1106609 -->
When you create a [Windows Hello for Business](windows-hello.md) policy, it applies to all users within the organization (tenant-wide). With this update, the policy can also be applied to specific users or specific devices using a device configuration policy (**Device Configuration** > **Profiles** > **Create profile** > **Identity Protection** > **Windows Hello for Business**).

In Intune in the Azure portal, the Windows Hello configuration and settings will exist in both **Device enrollment** and **Device configuration**. **Device enrollment** targets the entire organization (tenant-wide), and supports Windows AutoPilot (OOBE). **Device configuration** targets devices and users using a policy that's applied during check-in.

Applies to:  
- Windows 10 and later
- Windows Holographic for Business

### Control S-mode on Windows 10 and later devices - public preview <!-- 1958649 -->
You'll be able to create a device configuration profile that switches a Windows 10 device out of S-mode, or prevent users from switching the device out of S-mode. This feature will be in Intune > **Device configuration** > **Profiles** >  **Windows 10 and later** > **Edition upgrade and mode switch**.
[Introducing Windows 10 in S mode](https://www.microsoft.com/windows/s-mode) provides more information on S mode.
Applies to: Windows 10 and later (1809 and later)

### Modern VPN support updates for iOS <!-- 2459928, 1819876, and 2650856 -->
A future update will support the following iOS VPN clients: 
- F5 Access (version 3.0.1 and higher)
- Citrix SSO
- Palo Alto Networks GlobalProtect (version 5.0 and higher)
Also in a future update:
- Existing **F5 Access** connection types will be renamed to **F5 Access Legacy** (per F5 branding updates)
- Existing **Palo Alto Networks GlobalProtect** connection types will be renamed to **Legacy Palo Alto Networks GlobalProtect** (per Palo Alto branding updates). 

Existing profiles with these connection types continue to work with the legacy VPN client. If you're using Cisco Legacy AnyConnect, F5 Access Legacy, Citrix VPN, or Legacy Palo Alto Networks GlobalProtect with iOS, you should move to the new apps. Do this as soon as possible to ensure that VPN access is available for iOS devices as they update to iOS 12.

### Lock the Company Portal in single app mode until user sign-in <!--1067692 --> 
You’ll have the option to run Company Portal in Single App mode if you authenticate a user through the Company Portal instead of Setup Assistant during DEP enrollment. This option locks the device immediately after Setup Assistant completes so that a user must sign in to access the device. This process makes sure that the device completes onboarding and is not orphaned in a state without any user tied.

### Scope tags for policies <!--1081974 eeready-->

You’ll be able to create scope tags to limit access to Intune resources. Add a scope tag to a role assignment and then add the scope tag to a configuration profile. The role will only have access to resources with configuration profiles that have matching scope tags (or no scope tag).
To create a scope tag, choose **Intune roles** > **Scope (Tags)** > **Create**.
To add a scope tag to a role assignment, choose **Intune roles** > **All roles** > **Policy and Profile Manager** > **Assignments** > **Scope (Tags)**.
To add a scope tag to a configuration profile, choose **Device configuration** > **Profiles** > choose a profile > **Properties** > **Scope (Tags)**.

### Assign a user and friendly name to an Autopilot device <!--1346521 -->
A future public preview will let admins assign a user to a single Autopilot device.  Admins will also be able to give friendly names to greet the user when setting up their device with Autopilot.

Applies to: Windows Insider 1809 or later build (while in preview).

### Apple VPP token used by another MDM <!-- 1488946 -->
Intune will detect and show details if an Apple volume-purchased program (VPP) token is in use by both Intune and another MDM.

### Packet tunnel support for iOS per-app VPN profiles for custom and Pulse Secure connection types <!-- 1520957 -->
When using iOS per-app VPN profiles, you'll be able to use app-layer tunneling (app-proxy) or packet-level tunneling (packet-tunnel). These options will be available with the following connection types:
- Custom VPN
- Pulse Secure
If you are not sure which value to use, consult your VPN provider's documentation.
Applies to: iOS

### Zscaler is an available connection for VPN profiles on iOS <!-- 1769858 eeready -->
When you create an iOS VPN device configuration profile (**Device configuration** > **Profiles** > **Create profile** > **iOS** platform > **VPN** profile type), there are several connection types, including Cisco, Citrix, and more. A future update adds Zscaler as a connection type. 
[VPN settings for devices running iOS](vpn-settings-ios.md) lists the available connection types.

### Block Windows personal device enrollments <!-- 1849498 -->
You'll be able to block Windows personal devices from enrolling with [mobile device management](windows-enroll.md) in Intune. Devices enrolled with [Intune PC agent](manage-windows-pcs-with-microsoft-intune.md) can't be blocked with this feature.
To see this feature, choose **Device enrollment** > **Device restrictions**.
Turning on this restriction has no effect on devices already enrolled.
After a restriction is turned on, Intune will check to make sure that each each new Windows enrollment request has been authorized as a corporate enrollment. The following methods qualify as being authorized as a corporate enrollment:
- The enrolling user is using a [device enrollment manager account]( device-enrollment-manager-enroll.md).
- The device enrolls through [Windows Autopilot](enrollment-autopilot.md).
- The device’s IMEI number is listed in **Device enrollment** > **[Corporate device identifiers]( corporate-identifiers-add.md)**).
- The device enrolls through a [bulk provisioning package](windows-bulk-enroll.md).
- The device enrolls through [automatic enrollment from SCCM for co-management](https://docs.microsoft.com/sccm/core/clients/manage/co-management-overview#how-to-configure-co-management).

Unauthorized enrollments will be blocked. The following enrollments are marked as corporate by Intune, but since they do not offer the Intune administrator per-device control, they will be blocked:
- [Automatic MDM enrollment](windows-enroll.md#enable-windows-10-automatic-enrollment) with [Azure Active Directory join during Windows setup](https://docs.microsoft.com/azure/active-directory/device-management-azuread-joined-devices-frx.md).
- [Automatic MDM enrollment](windows-enroll.md#enable-windows-10-automatic-enrollment) with [Azure Active Directory join from Windows setup](https://docs.microsoft.com/azure/active-directory/device-management-azuread-joined-devices-frx.md).

The following personal enrollment methods will also be blocked:
- [Automatic MDM enrollment](windows-enroll.md#enable-windows-10-automatic-enrollment) with [Add Work Account from Windows Settings](https://docs.microsoft.com/azure/active-directory/user-help/device-management-azuread-registered-devices-windows10-setup).
- [MDM enrollment only]( https://docs.microsoft.com/windows/client-management/mdm/mdm-enrollment-of-windows-devices#connecting-personally-owned-devices-bring-your-own-device) option from Windows Settings.

### Specify machine name patterns in an Autopilot profile <!--1849855-->
You'll be able to specify a computer name template to generate and set the [computer name](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) during Autopilot enrollment. You'll need to specify this in the Autopilot profile located at **Device enrollment** > **Windows enrollment** > **Windows Autopilot Deployment service** > **Profiles**. Only alphanumeric and hyphen characters can be used.
Applies to: Windows Insider 1809 or later build (while in preview).

### iOS version number and build number are shown <!-- 1892471 -->
In **Device compliance** > **Device compliance**, the iOS operating system version is shown. In a future update, the build number will also be shown.
When security updates are released, Apple typically leaves the version number as-is, but updates the build number. By showing the build number, you can easily check if a vulnerability update is installed.

### For Windows Autopilot profiles, hide the change account options on the company sign-in page and domain error page <!--1901669 -->
A public preview will include new Windows Autopilot profile options for admins to hide the change account options on the company sign-in and domain error pages. Hiding these options requires  Company Branding to be configured in Azure Active Directory. 
Applies to:  Windows Insider 1809 or later build (while in preview).

### Delay when iOS software updates are shown on the device <!-- 1949583 -->
In Intune > **Software Updates** > **Update policies for iOS**, you can configure the days and times when you don't want devices to install any updates. In a future update, you'll be able to delay when a software update is visibly shown on the device, from 1-90 days. 
[Configure iOS update policies in Microsoft Intune](software-updates-ios.md) lists the current settings.

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

### Office 365 ProPlus version <!-- 2213968 eeready -->
When assigning the Office 365 ProPlus apps to Windows 10 devices using Intune, you'll be able to select the version of Office. In the Azure portal, select **Microsoft Intune** > **Apps** > **Add App**. Then, select **Office 365 ProPlus Suite (Windows 10)** from the **Type** dropdown list. Select **App Suite Settings** to display the associated blade. Set the **Update Channel** to a value, such as **Monthly**. Optionally, remove other version of Office (msi) from end user devices by selecting **Yes**. Select **Specific** to install a specific version of Office for the selected channel on end user devices. At this point, you can select the **Specific version** of Office to use. The available versions will change over time. Therefore, when creating a new deployment, the versions available may be newer and not have certain older versions available. Current deployments will continue to deploy the older version, but the version list will be continually updated per channel. For more information, see [Overview of update channels for Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus).

### Configure profile to skip some screens during Setup Assistant <!-- 2276470 -->
When you create a macOS enrollment profile, you'll be able to configure it to skip any of the following screens when a user goes through the Setup Assistant:
- Android Migration
- Display Tone
- Privacy
- iCloudStorage

### Change in the update process for on-premises connectors <!-- 2277554 -->
Based on feedback from customers, the way updates are made to on-premises connectors will be changed. After you initially install an on-premises connector, updates will happen automatically. This change will begin with the new PFX Certificate Connector for Microsoft Intune and will subsequently roll out to other types of on-premises connectors. 

### Support for Register DNS setting for Windows 10 VPN <!-- 2282852 -->
You'll be able to configure Windows 10 VPN profiles to dynamically register the IP addresses assigned to the VPN interface with the internal DNS, without needing to use custom profiles.
[Windows 10 VPN settings](vpn-settings-windows-10.md) lists the current VPN profile settings available. 

### Restricts apps, and block access to company resources on iOS and Android for Work devices <!-- 2451462 -->
In **Device compliance** > **Policies** > **Create policy** > **Android for Work** > **System Security**, there will be a new **Restricted applications** setting. This new setting uses a compliance policy to block access to company resources if certain apps are installed on the device. The device is considered non-compliant until the restricted apps are removed from the device.
Applies to: 
- iOS

### Export Azure classic portal compliance policies to .csv file <!-- 2469637 -->
Compliance policies created in the Azure classic portal will be deprecated.  When this happens, you can review and delete any existing policies; you can't update them. You can export the policies as a comma-separated file (.csv file). Then, use the details in the file to recreate these policies in Intune Azure portal.
> [!IMPORTANT]
> When the Azure classic portal retires, you can't access your policies, including not being able to see them. So, be sure to export them, and recreate them in the Azure portal before the Azure classic portal retires.

### Change terminology to "retire" and "wipe" <!-- 2175759 -->
To be consistent with the Graph API, the Intune user interface and documentation will change the following terms:
- **Remove company data** will be changed to **retire**
- **Factory reset** will be changed to **wipe**



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

###  Windows line-of-business (LOB) apps file extensions <!-- 1884873 -->
The file extensions for Windows LOB apps will now include *.msi*, *.appx*, *.appxbundle*, *.msix* and *.msixbundle*. You can add an app in Microsoft Intune by selecting **Mobile apps** > **Apps** > **Add**. The **Add app** pane is displayed which allows you to select the **App type**. For Windows LOB apps, select **Line-of-business** app as the app type, select the **App package file**, and then enter an installation file with the appropriate extension.

### Windows Defender ATP configuration package automatically added to configuration profile <!-- 2144658 -->
When using [Advanced Threat Protection and onboarding](advanced-threat-protection.md#onboard-devices-using-a-configuration-profile) devices in Intune, you currently download a configuration package, and add it to your configuration profile. In a future update, Intune automatically gets the package from Windows Defender Security Center, and adds it to your profile.

Applies to Windows 10 and later.

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



