---
# required metadata

title: Early edition
description:
keywords:
author: ErikjeMS  
ms.author: erikje
manager: dougeby
ms.date: 10/03/2018
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

# The early edition for Microsoft Intune - October 2018

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

<!-- 1810 start -->

### Use Microsoft-recommended settings with Security Baselines <!-- 2055484 -->
Intune integrates with other services that focus on security, including Windows Defender ATP and Office 365 ATP. Customers are asking for a common strategy and a cohesive set of end-to-end security workflows across the Microsoft 365 services. Our goal is to align strategies to build solutions that bridge security operations and common administrator tasks. 
In Intune, we aim to accomplish this goal by publishing a set of Microsoft recommended “Security baselines” (**Intune** > **Security baselines**).  An administrator will be able to create security policies directly from these baselines, and then deploy them to their users. They can also customize the best practice recommendations to meet the needs of their organization. Intune makes sure that devices stay in compliance with these baselines, and notifies administrators of users or devices that aren't in compliance.

### Remove ability for admins to wipe personal devices and reset passcodes <!-- 2934699 -->
To ease user fears about company admins having the ability to wipe their personal devices, the [wipe](devices-wipe.md#wipe) and [Reset passcode](device-passcode-reset.md) remote actions will no longer apply to personal devices. Switch the device ownership type to corporate to enable these actions for devices your organization owns.

### Autopilot support for hybrid Azure Active Directory joined devices <!-- 1048100 -->
You'll be able to set up hybrid Azure Active Directory joined devices by using Autopilot. Devices must be joined to your organization's network to use the hybrid Autopilot feature.

### Scope tags for apps <!--1081941 -->
You’ll be able to create scope tags to limit access to Intune resources. Add a scope tag to a role assignment and then add the scope tag to a configuration profile. The role will only have access to resources with configuration profiles that have matching scope tags (or no scope tag).
To create a scope tag, choose **Intune roles** > **Scope (Tags)** > **Create**.
To add a scope tag to a role assignment, choose **Intune roles** > **All roles** > **Policy and Profile Manager** > **Assignments** > **Scope (Tags)**.
To add a scope tag to a configuration profile, choose **Device configuration** > **Profiles** > choose a profile > **Properties** > **Scope (Tags)**.

## Tenant Health dashboard <!-- 1124854 -->
The Tenant Status page in Intune will provide you with tenant status information in a single place. The page is divided into 4 sections:  
- **Tenant Details**: Contains information, such as your MDM Authority, the total enrolled devices in your tenant, and your license counts. This section also provides the current service release for your tenant.
- **Connector Status**: Contains information for configured connectors, such as Apple VPP, Windows Store for Business, and Certificate connectors. Based on their current state, the connectors are flagged as *Healthy*, *Warning*, or *Unhealthy*.
- **Intune Service Health**: Contains active incidents or outages for your tenant. The information in this section is retrieved directly from the Office Message Center ([https://portal.office.com](https://portal.office.com)).
- **Intune News**: Contains active messages for your tenant, which include things like notifications that your tenant has received the latest Intune features. The information in this section is retrieved directly from the Office Message Center ([https://portal.office.com](https://portal.office.com)).

### Enrollment abandonment report <!-- 1382924 -->
A new report that provides details on abandoned enrollments will be available under **Device enrollment** > **Monitor**.

### Deployed WIP policies without user enrollment <!-- 1434452 -->
Windows Information Protection (WIP) policies will be able to be deployed without requiring MDM users to enroll their Windows 10 device. This configuration allows companies to protect their corporate documents based on the WIP configuration, while allowing the user to maintain management of their own Windows devices. Once documents are protected with a WIP policy, the protected data can be selectively wiped by an Intune administrator. By selecting the user and device, and sending a wipe request, all data that was protected via the WIP policy will become unusable. From the Intune in the Azure portal, select **Mobile app** > **App selective wipe**.


### Add custom brand image for Company Portal app <!-- 1916266 -->
As the Microsoft Intune admin, you'll be able to upload a custom brand image which will be displayed as a background image on user's profile page in the Company Portal app. For more information about configuring the Company Portal app, see [How to configure the Microsoft Intune Company Portal app](company-portal-app.md).

### Group Windows Autopilot-enrolled devices by correlator ID <!-- 2075110 -->
Intune will support grouping Windows devices by a correlator ID when enrolled using [Autopilot for existing devices](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/New-Windows-Autopilot-capabilities-and-expanded-partner-support/ba-p/260430) through Configuration Manager. The correlator ID is a parameter of the Autopilot configuration file. Intune will automatically set the [Azure AD device attribute enrollmentProfileName](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#using-attributes-to-create-rules-for-device-objects) to equal "OfflineAutopilotprofile-<correlator ID>". This allows arbitrary Azure AD dynamic groups to be created based off correlator ID via the enrollmentprofileName attribute for offline Autopilot enrollments. 


### Support for iOS 12 OAuth in iOS email profiles <!--2155106 -->
Intune's iOS email profiles will support iOS 12 OAuth. To see this feature, choose **Intune** > **Device Configuration** > **Profiles** > **Create profile** > **OAuth**. If this setting is turnd on, two things will happen:
1. Devices that are already targeted will be issued a new profile.
2. End users will be prompted for their credentials again.

### New "Required password type" default setting for Android, Android enterprise<!-- 2649963 -->
When you create a new compliance policy (**Intune** > **Device compliance** > **Policies** > **Create policy** > **Android** or **Android enterprise** for Platform > System Security), the default value for **Required password type** will change:
Current default: Device default
New default: At least numeric
Applies to: Android, Android Enterprise

### Assign Autopilot profiles to the All devices virtual group <!--2715522 -->
You'll be able to assign Autopilot profiles to the All devices virtual group. To do so, choose **Device enrollment** > **Windows enrollment** > **Deployment Profiles** > choose a profile > **Assignments** > under **Assign to** choose **All devices**.

### New Azure Active Directory terms of use feature <!-- 2870393 -->
Azure Active Directory will have a terms of use feature that you can use instead of existing Intune terms and conditions. The Azure AD terms of use feature provides more flexibility on which terms to show and when to show them, better localization support, more control in how terms are rendered and improved reporting. The Azure AD terms of use feature does require Azure Active Directory Premium P1 which is also part of the Enterprise Mobility + Security E3 suite.


### Intune will maintain the Office localized language when updating Office on end users machines <!-- 2971030 -->
When Intune installs Office on your end user's machines, end users will automatically get the same language packs that they had with previous .MSI Office installations. 

<!-- 1809 start -->

### User account access of Intune apps on managed Android and iOS devices <!-- ! 1248496  -->

As the Microsoft Intune admin, you'll be able to control which user accounts are added to Microsoft Office applications on managed devices. You'll be able to limit access to only allowed organization user accounts and block personal accounts on enrolled devices. 

### Create DNS suffixes in VPN configuration profiles on devices running Windows 10 <!-- 1333668 -->
When you create a VPN device configuration profile (**Device configuration** > **Profiles** > **Create profile** > **Windows 10 and later** platform > **VPN** profile type), you enter some DNS settings. You'll also be able too enter multiple **DNS suffixes** in Intune. When using DNS suffixes, you can search for a network resource using its short name, instead of the fully qualified domain name (FQDN). This update also lets you change the order of the DNS suffixes in Intune.
[Windows 10 VPN settings](vpn-settings-windows-10.md#dns-settings) lists the current DNS settings.
Applies to: Windows 10 devices

### Support for always-on VPN for Android enterprise work profiles <!-- 1333705 -->
You'll be able to use Always-on VPN connections on Android enterprise devices with managed work profiles. Always-on VPN connections stay connected, or immediately reconnect when the user unlocks their device, when the device restarts, or when the wireless network changes. You can also put the connection in "lockdown" mode, which blocks all network traffic until the VPN connection is active.
The Always-on VPN setting will be in **Device configuration** > **Profiles** > **Create profile** > **Android enterprise** for platform > **Device restrictions** under **Work Profiles Only** for Profile type > **Connectivity** settings. 

### Outlook for iOS and Android app configuration policy <!--1828527 -->
You'll be able to create an Outlook for iOS and Android app configuration policy for iOS. Additional configuration settings will be added as they are enabled for Outlook for iOS and Android.

###  Windows line-of-business (LOB) app file extensions <!-- 1884873 -->
The file extensions for Windows LOB apps will include *.msi*, *.appx*, *.appxbundle*, *.msix* and *.msixbundle*. you'll be able to add an app in Microsoft Intune by selecting **Client apps** > **Apps** > **Add**. The **Add app** pane will be displayed which will allow you to select the **App type**. For Windows LOB apps, you'll select **Line-of-business** app as the app type, select the **App package file**, and then enter an installation file with the appropriate extension.

### Remotely lock noncompliant devices <!-- 2064495 -->
When a device isn't compliant, you'll be able to create an action on the compliance policy that locks the device remotely. In Intune > **Device compliance**, create a new policy, or select an existing policy. Select **Actions for noncompliance** > **Add**, and choose to remotely lock the device.
Supported on: 
- Android
- iOS
- macOS
- Windows 10 Mobile 
- Windows Phone 8.1 and later 

### Intune APP data transfer settings on iOS MDM enrolled devices <!-- 2244713 -->
You'll be able to separate the control of Intune APP data transfer settings on iOS MDM enrolled devices from specifying the enrolled user's identity. Admins not using the IntuneMAMUPN will not observe a behavior change. When this functionality is available, admins using the IntuneMAMUPN to control data transfer behavior on enrolled devices should review the new settings and update their APP settings as needed.

### Use a pre-shared key in a Windows 10 Wi-Fi profile <!-- 2662938 -->
You'll be able to use a pre-shared key (PSK) with the WPA/WPA2-Personal security protocol to authenticate a Wi-Fi configuration profile for Windows 10.
Currently, you must import a Wi-Fi profile, or create a custom profile to use a pre-shared key. [Wi-Fi settings for Windows 10](wi-fi-settings-windows.md) lists the current settings. 

### App Protection Policy (APP) settings for web data <!-- 2662995 -->
APP policy settings for web content on both Android and iOS devices will be updated to better handle both http and https web links, as well as data transfer via iOS Universal Links and Android App Links.  

### Autopilot device sync frequency increasing to every 12 hours <!-- 2753673 -->
Autopilot devices will synchronize every 12 hours instead of every 24 hours.

### Apply Autopilot profile to enrolled Win 10 devices not already registered for Autopilot <!-- 1558983 -->
You can apply Autopilot profiles to enrolled Win 10 devices that have not already been registered for Autopilot. In the Autopilot profile, choose the **Convert all targeted devices to Autopilot** option to automatically register non-Autopilot devices with the Autopilot deployment service. Allow 48 hours for the registration to be processed. When the device is unenrolled and reset, Autopilot will provision it. 

### Create and assign multiple Enrollment Status  Page profiles to Azure AD groups <!-- 2526564-->
You'll be able to create and assign multiple Enrollment Status Page profiles to Azure AAD user groups.

### Intune landing page updates and node rename <!--2867309 -->
Updates to the Intune landing page will include new and changed monitoring tiles and charts for better data visualization. The **Mobile apps** node will change to **Client apps**.

### Increased end-user access using the Company portal app <!-- 772203 -->
End users will be able to access key account actions, such as password reset and their AAD profile, from the Company portal app.

### Issue SCEP certificates to user-less devices <!-- 1744554 -->
Currently, certificates are issued to users. you'll be able to issue SCEP certificates to devices, including user-less devices such as kiosks (**Device configuration** > **Profiles** > **Create profile** > **Windows 10 and later** for platform > **SCEP certificate** for profile). 
Other updates will include:
- The **Subject** property in an SCEP profile is now a custom textbox and can include new variables. 
- The **Subject alternative name (SAN)** property in an SCEP profile is now a table format and can include new variables. In the table, an admin can add an attribute and fill out the value in a custom textbox. The SAN will support the following attributes: 
  - DNS
  - Email address
  - UPN
  These new variables can be added with static text in a custom value textbox. For example, the DNS attribute can be added as `DNS = {{AzureADDeviceId}}.domain.com`.
  > [!NOTE]
  > Curly brackets, semicolons, and pipe symbols “ { } ; | ” will not work in the static text of the SAN. Curly brackets must only enclose one of the new device certificate variables to be accepted for either `Subject` or `Subject alternative name`. 
New device certificate variables:  
```
"{{AAD_Device_ID}}",
"{{Device_Serial}}",
"{{Device_IMEI}}",
"{{SerialNumber}}",
"{{IMEINumber}}",
"{{AzureADDeviceId​}}",
"{{WiFiMacAddress}}",
"{{IMEI}}",
"{{DeviceName}}",
"{{FullyQualifiedDomainName}}",
"{{MEID}}",
```

> [!NOTE]
>  - `{{FullyQualifiedDomainName}}` only works for Windows and domain-joined devices. 
>  -  When specifying device properties such as IMEI, Serial Number, and Fully Qualified Domain Name in the subject or SAN for a device certificate, be aware that these properties could be spoofed by a person with access to the device. 

[Create a SCEP certificate profile](certificates-scep-configure.md#create-a-scep-certificate-profile) lists the current variables when creating an SCEP configuration profile. 

Applies to: Windows 10 and later and iOS, supported for Wi-Fi



<!-- 1808 start -->

### Apple VPP token used by another MDM <!-- 1488946 -->
Intune will detect and show details if an Apple volume-purchased program (VPP) token is in use by both Intune and another MDM.

### iOS version number and build number are shown <!-- 1892471 -->
In **Device compliance** > **Device compliance**, the iOS operating system version is shown. In a future update, the build number will also be shown.
When security updates are released, Apple typically leaves the version number as-is, but updates the build number. By showing the build number, you can easily check if a vulnerability update is installed.

### Retired devices in the device compliance dashboard <!-- 1981119 -->
In a future update, retired devices will be removed from the device compliance dashboard. This will change your compliance numbers.


### Change in the update process for on-premises connectors <!-- 2277554 -->
Based on feedback from customers, the way updates are made to on-premises connectors will be changed. After you initially install an on-premises connector, updates will happen automatically. This change will begin with the new PFX Certificate Connector for Microsoft Intune and will subsequently roll out to other types of on-premises connectors. 

### Windows 10 and later Kiosk profile improvements in the Azure portal <!-- 2748224 -->
The Windows 10 Kiosk device configuration profile (**Device configuration** > **Profiles** > **Create profile** > **Windows 10 and later** for platform > **Kiosk preview** for profile type) will be improved: 
- Currently, you can create multiple kiosk profiles on the same device. With this update, Intune will support only one kiosk profile per device. If you still need multiple kiosk profiles on a single device, you can use a Custom URI.
-In a **Multi-app kiosk** profile, you can select the application tile size and order for the **Start menu layout** in the application grid. If you prefer more customization, you can continue to upload an XML file.
- The Kiosk Browser settings are moving into the **Kiosk** settings. Currently, the **Kiosk web browser** settings have their own category in the Azure portal.
Applies to: Windows 10 and later

<!-- 1807 start -->

### Improved Company Portal app experience for device enrollment manager users <!-- 675800 -->
When a device enrollment manager (DEM) signs in to the Company Portal app for Windows, the app will only list the DEM's current, running device. This improvement will reduce timeouts that previously occurred when the app tried to load all DEM-enrolled devices.  

### Check for Configuration Manager compliance <!-- 2192052 -->
A future update will include a new System Center Configuration Manager compliance setting (**Device compliance** > **Policies** > **Create policy** > **Windows 10**). Configuration Manager sends signals to Intune compliance. Using the Intune setting, you can require all Configuration Manager signals to return "compliant".

For example, you require all software updates to be installed on devices. In Configuration Manager, this requirement has the “Installed” state. If any programs on the device are in unknown state, then the device will be non-compliant in Intune.

Applies to Windows 10 and later

### Alerts for expiring VPP token or Company Portal license running low <!-- 2237572 -->
If you use the Volume Purchase Program (VPP) to pre-provision the Company Portal during DEP enrollment, Intune will alert you when the VPP token is about to expire and when the licenses for the Company Portal are running low.

<!-- 1806 start -->

### 3rd-party keyboards can be blocked by APP settings on iOS <!-- 1248481 -->
On iOS devices, Intune admins will be able to block the use of 3rd-party keyboards when accessing organization data in policy protected apps. When the Application Protection Policy (APP) is set to block 3rd-party keyboards, the device user will receive a message the first time they interact with corporate data when using a 3rd-party keyboard. All options, other than the native keyboard, will be blocked and device users will not see them. Device users will only see the dialog message once. 

### Office 365 Pro Plus language packs <!-- 1833450 -->
As the Intune admin, you'll be able to deploy additional languages for Office 365 Pro Plus apps managed through Intune. The list of available languages includes the **Type** of language pack (core, partial, and proofing). In the Azure portal, select **Microsoft Intune** > **Mobile apps** > **Apps** > **Add**. In the **App type** list of the **Add app** blade, select **Windows 10** under **Office 365 Suite**. Select **Languages** in the **App Suite Settings** blade.

<!-- 1805 start -->

### Require non-biometric after specified timeout <!-- 1506985 --> 

By requiring a non-biometric PIN after admin-specified timeout, Intune will provide improved security for Mobile Application Management (MAM) enabled apps by restricting the use of biometric identification for access to corporate data. The settings will affect users who rely on Touch ID (iOS), Face ID (iOS), Android Biometric, or other future biometric authentication methods to access their APP/MAM-enabled applications. These settings will enable Intune admins to have more granular control over user access, eliminating cases where a device with multiple fingerprints or other biometric access methods can reveal corporate data to an incorrect user. In the Azure portal, open **Microsoft Intune**. Select **Mobile apps** > **App protection policies** > **Add a policy** > **Settings**. Locate the **Access** section for specific settings.

<!-- 1803 start -->

### Updating the Help and Feedback experience on Company Portal app for Android <!--1631531 -->

The Help and Feedback experience on the Company Portal app for Android will be updated to align with best practices for Android apps. The Company Portal app for Android will be updated over the next few months to divide the **Help and Feedback** menu item to distinct **Help** and **Send Feedback** menu items. The **Help** page will feature a **Frequently Asked Questions** section and **Email Support** button to lead end users to upload logs to Microsoft and send email to company support describing the issue. **Send Feedback** will lead the user through a standard Microsoft feedback submission, which will prompt the user to choose whether, "I like something," "I don't like something," or "I have an idea."



<!-- the following are present prior to 1711 -->

## Notices

There are no active notices at this time.

### See also
See [What’s New in Microsoft Intune](whats-new.md) for details on recent developments.



