---
# required metadata
title: What's new in Microsoft Intune
titlesuffix: "Azure portal"
description: Find out what's new in the Intune Azure portal
keywords:
author: brenduns  
ms.author: brenduns
manager: angrobe
ms.date: 11/15/2017
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---

# What's new in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Learn what’s new each week in Microsoft Intune. You can also find out about [upcoming changes](#whats-coming), [important notices](#notices) about the service, and information about [past releases](whats-new-archive.md).

> [!Note]
> Many of these features will eventually be supported for hybrid deployments with Configuration Manager. For more information about new hybrid features, check out our [hybrid What’s New page](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).


<!-- Common categories:  
  ### Device enrollment
  ### Device management
  ### App management
  ### Device configuration
  ### Role-based access control
  ### Intune apps
  ### Monitor and troubleshoot

-->   

## Week of November 13, 2017

### Intune Apps
#### Company Portal app for macOS is available <!--1541700-->
The Intune Company Portal on macOS has an updated experience, which has been optimized to cleanly display all the information and compliance notifications your users need for all the devices they have enrolled. And, once the Intune Company Portal has been deployed to a device, Microsoft AutoUpdate for macOS will provide updates to it. You can download the new Intune Company Portal for macOS by logging into the Intune Company Portal website from a macOS device.

#### Microsoft Planner is now part of the mobile app management (MAM) list of approved apps  <!-- 1248473 -->
The Microsoft Planner app for iOS and Android is now part of the approved apps for mobile app management (MAM). The app can be configured through the Intune App Protection blade in the Azure portal to all tenants.
- Learn more the [MAM list of approved apps](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

#### Per-App VPN requirement update frequency on iOS devices   <!-- 1547061 -->  
Administrators may now remove Per-App VPN requirements for apps on iOS devices; affected devices will after their next Intune check-in, which generally occurs within 15 minutes.  

### Monitor and troubleshoot
#### Support for System Center Operations Manager management pack for Exchange connector <!-- 885457 -->
The System Center Operations Manager (SCOM) management pack for Exchange connector is now available to help you parse the Exchange connector logs. This gives you different ways of monitoring the service when you need to troubleshoot issues.

## Week of November 6, 2017

### Device enrollment
#### Co-management for Windows 10 devices  <!-- 1243445 -->
Co-management is a solution that provides a bridge from traditional to modern management, and it provides you with a path to make the transition using a phased approach. At its foundation, co-management is a solution where Windows 10 devices are concurrently managed by Configuration Manager and Microsoft Intune, as well as joined to Active Directory (AD) and Azure Active Directory (Azure AD).  This configuration provides you with a path to modernize over time, at the pace that’s right for your organization if you can’t move all at once.  

#### New enrollment status page for Windows 10 enrollments <!--1063201-->    
You can now configure a greeting that appears when your users enroll Windows 10 devices. Use the **Enrollment Status Screen** to configure a custom message and a hyperlink to be displayed to your end users when they enroll their Windows 10 devices.  The **Enrollment Status Screen** will also give end users a view into the progress of policy settings that are being applied to their device.  

#### Restrict Windows Enrollment by OS version <!-- 245498 -->
As an Intune administrator, you can now specify a minimum and maximum version of Windows 10 for device enrollments. You can set these restrictions in the **Platform Configurations** blade.

Intune will continue to support enrolling Windows 8.1 PCs and phones. However, only Windows 10 versions can be set with minimum and maximum limits. To permit enrollment of 8.1 devices, leave the minimum limit empty.

#### Alerts for Windows AutoPilot unassigned devices  <!-- 1631236 -->
A new alert is available for Windows AutoPilot unassigned devices on the **Microsoft Intune** > **Device enrollment** > **Overview** page. This alert shows how many devices from the AutoPilot program do not have AutoPilot deployment profiles assigned. Use the information in the alert to create profiles and assign them to the unassigned devices. When you click the alert, you see a full list of Windows AutoPilot devices and detailed information about them. For more information, see [Enroll Windows devices using Windows AutoPilot deployment program](https://docs.microsoft.com/intune/enrollment-autopilot).

### Device management

#### Refresh button for Devices list    <!-- 1333581 -->
Because the Device list does not refresh automatically, you can use the new Refresh button to update the devices that display in the list.

#### Support for Symantec Cloud Certification Authority (CA)  <!-- 1333638 -->    
Intune now supports Symantec Cloud CA which allows the Intune Certificate Connector to issue PKCS certificates from the Symantec Cloud CA to Intune managed devices. If you're already using the Intune Certificate Connector with Microsoft Certification Authority (CA), you can leverage the existing Intune Certificate Connector setup to add the Symantec CA support.

#### New items added to device inventory   <!--1404455 -->
In this release, we've added the following new items to the [inventory taken by enrolled devices](device-inventory.md):

- Wi-Fi MAC address
- Total storage space
- Total free space
- MEID
- Subscriber carrier


### App management
#### Set access for apps by minimum Android security patch on the device<!-- 1278463 -->   
An administrator will be able to define the minimum Android security patch that must be installed on the device in order to gain access to a managed application under a managed account.

> [!Note]  
> This feature only restricts security patches released by Google on Android 6.0+ devices.

#### App-conditional launch support <!-- 1193313 -->
IT admins can now set a requirement through the Azure admin portal to enforce a passcode instead a numeric PIN through the mobile app management (MAM) when the application launch. If configured, the user will be required to set and use a passcode when prompted before getting access to MAM-enlightened applications. A passcode is defined as a numeric PIN with at least one special character or upper/lowercase alphabet. This release of Intune will enable this feature **on iOS only**. Intune supports passcode in a similar way to numeric PIN, it sets a minimum length, allowing repeat characters and sequences. This feature requires the participation of applications (i.e., WXP, Outlook, Managed Browser, Yammer) to integrate the Intune App SDK with the code for this feature in place for the passcode settings to be enforced in the targeted applications.

#### App Version number for line-of-business in device install status report <!-- 1233999 -->
With this release, the Device install status report displays the app version number for the line-of-business apps for iOS and Android. You may use this information to troubleshoot your apps, or find devices that are running outdated app versions.


### Device configuration
#### Admins can now configure the Firewall settings on a device using a device configuration profile <!-- 951708 -->   
Admins can turn on firewall for devices, and also configure various protocols for domain, private, and public networks.  These firewall settings can be found in the "Endpoint protection" profile.

#### Windows Defender Application Guard helps protect devices from untrusted websites, as defined by your organization <!-- 958257 -->   
Admins can define sites as "trusted" or "corporate" using a Windows Information Protection workflow or the new "Network boundary" profile under device configurations. Any sites that aren't listed in on a 64-bit Windows 10 device’s trusted network boundary, if they are viewed with Microsoft Edge, open instead in a browser within a Hyper-V virtual computer.

Application Guard can be found in the device configuration profiles, in the "Endpoint protection" profile. From there, admins can configure interaction between the virtualized browser and the host machine, nontrusted sites and trusted sites, and storing data generated in the virtualized browser. To use Application Guard on a device, a network boundary first must be configured. It's important to define only one network boundary for a device.  

#### Windows Defender Application Guard on Windows 10 Enterprise provides mode to trust only authorized apps <!-- 1031096 -->    
With thousands of new malicious files created every day, using antivirus signature-based detection to fight against malware might no longer provide an adequate defense against new attacks. Using Windows Defender Application Guard on Windows 10 Enterprise, you can change device configuration from a mode where apps are trusted unless blocked by an antivirus or other security solution, to a mode where the operating system trusts only apps authorized by your enterprise. You assign trust to apps in Windows Defender Application Guard.

Using Intune, you can configure the application control policies either in "audit only" mode or enforce mode. Apps will not be blocked when running in “audit only” mode. “Audit only” mode logs all events in local client logs. You can also configure whether only Windows components and Windows Store apps are allowed to run or whether additional apps with good reputations as defined by the Intelligent Security Graph will be allowed to run.

#### Window Defender Exploit Guard is a new set of intrusion prevention capabilities for Windows 10 <!-- 1063615 -->   
Window Defender Exploit Guard includes custom rules to reduce the exploitability of applications, prevents macro and script threats, automatically blocks network connections to low reputation IP addresses, and can secure data from ransomware and unknown threats. Windows Defender Exploit Guard consists of the following components:

- **Attack Surface Reduction (ASR)** provides rules that allow you to prevent macro, script, and email threats.
- **Controlled Folder access** automatically blocks access to content to protected folders.
- **Network Filter** blocks outbound connection from any app to low rep IP/domain
- **Exploit Protection** provides memory, control flow, and policy restrictions that can be used to protect an application from exploits.


#### Manage PowerShell scripts in Intune for Windows 10 devices <!-- 790537 -->

> [!Note]
> This feature is rolling out so it is not yet available for all customers.

The Intune management extension lets you upload PowerShell scripts in Intune to run on Windows 10 devices. The extension supplements Windows 10 mobile device management (MDM) capabilities and makes it easier for you to move to modern management. For details, see [Manage PowerShell scripts in Intune for Windows 10 devices](intune-management-extension.md).

#### New device restriction settings for Windows 10      <!-- 1308850 -->
-    Messaging (mobile only) - disable testing or MMS messages
-    Password - settings to enable FIPS and the use of Windows Hello devices secondary devices for authentication 
-    Display - settings to turn on or off GDI Scaling for legacy apps

#### Windows 10 kiosk mode device restrictions <!-- 1308872 -->   
You can restrict Windows 10 device users to kiosk mode, which limits users to a set of predefined apps.  To do so, create a Windows 10 device restriction profile and set the Kiosk settings.

Kiosk mode supports two modes: **single app** (allows a user to run just one app) or **multi app** (permits access to a set of apps).  You define the user account and device name, which determines the supported apps).  When the user is logged in, they're limited to the defined apps.  To learn more, see [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp). 

Kiosk mode requires:

- Intune must be the MDM authority.
- The apps must already be installed on the target device.
- The device must be [properly provisioned](https://docs.microsoft.com/windows/configuration/set-up-a-kiosk-for-windows-10-for-desktop-editions).

#### New device configuration profile for creating network boundaries <!-- 1311967 -->   
We have created a device configuration profile called **Network boundary** that can be found with your other device configuration profiles. Use this profile to define online resources that you want to be considered corporate and trusted. You must define a network boundary for a device *before* features such as Windows Defender Application Guard and Windows Information Protection can be used on the device. It’s important to define only one network boundary for each device.

You can define enterprise cloud resources, IP address ranges, and internal proxy servers that you want to be considered trusted. Once defined, the network boundary can be consumed by other features such as Windows Defender Application Guard and Windows Information Protection.

####  Two additional settings for Windows Defender Antivirus <!-- 1338409 -->  
**File blocking level**

| | |
|---|---|
| Not Configured | **Not Configured** uses the default Windows Defender Antivirus blocking level and provides strong detection without increasing the risk of detecting legitimate files. |
| High | **High** applies a strong level of detection.
| High +  | **High +** provides the High level with additional protection measures that might impact client performance.
| Zero tolerance  | **Zero tolerance** blocks all unknown executables. |

While unlikely, setting to **High** may cause some legitimate files to be detected.
We recommend you set File blocking level to the default, **Not configured**.

**Timeout extension for file scanning by the cloud**  

| | |
|--|--|
| Number of seconds (0-50) | Specify the maximum amount of time that Windows Defender Antivirus should block a file while waiting for a result from the cloud. The default amount is 10 seconds: any additional time specified here (up to 50 seconds) is added to those 10 seconds. In most cases, the scan takes much less time than the maximum. Extending the time allows the cloud to thoroughly investigate suspicious files. We recommend that you enable this setting and specify at least 20 additional seconds. |

#### Citrix VPN added for Windows 10 devices <!-- 1512457 -->  
You can configure Citrix VPN for their Windows 10 devices. You can choose the Citrix VPN in the *Select a connection type* list in the **Base VPN** blade when configuring a VPN for Windows 10 and later.

> [!Note]
> Citrix configuration existed for iOS and Android.

#### Wi-Fi connections support pre-shared keys on iOS <!-- 1550823 -->
Customers can configure Wi-Fi profiles to use pre-shared keys (PSK) for WPA/WPA2 Personal connections on iOS devices. These profiles are pushed to user's device when the device is enrolled into Intune.

When the profile has been pushed to the device, the next step depends on the profile configuration.  If set to connect automatically, it does so when the network is next needed.  When the profile is connects manually, the user must activate the connection manually.  

### Intune apps

#### Access to managed app logs for iOS <!-- 1469920 -->
End users with the managed Browser installed can now view the management status of all Microsoft published apps and send logs for troubleshooting their managed iOS apps.

Learn how to enable the troubleshooting mode in the Managed Browser on an iOS device, see [How to access to managed app logs using the Managed Browser on iOS](app-configuration-managed-browser.md#how-to-access-to-managed-app-logs-using-the-managed-browser-on-ios).

#### Improvements to device setup workflow in the Company Portal for iOS in version 2.9.0 <!---1417174--->

We've improved the device setup workflow in the Company Portal app for iOS. The language is more user-friendly and we've combined screens where possible. We have also made the language more specific to your company by using your company name throughout the setup text. You can see this updated workflow on the [what's new in app UI page](whats-new-app-ui.md).

### Monitor and troubleshoot

#### User entity contains latest user data in Data Warehouse data model <!-- 1544273 -->
The first version of the Intune Data Warehouse data model only contained recent, historical Intune data. Report makers could not capture the current state of a user. In this update, the **User entity** will be populated with the latest user data.


## Week of October 30, 2017

### App management

#### iOS and Android line-of-business app version number is visible <!-- 1380712 -->

Apps in Intune now display the version number for iOS and Android line-of-business apps. The number displays in the Azure portal in the app list and in the app overview blade. End users can see the app number in the Company Portal app and in the web portal.

__Full version number__
The full version number identifies a specific release of the app. The number appears as _Version_(_Build_). For example, 2.2(2.2.17560800)

The full version number has two components:

 - **Version**  
   The version number is the human-readable release number of the app. This is used by end users to identify different releases of the app.

 - **Build Number**  
    The build number is an internal number that can be used in app detection and to programmatically manage the app. The build number refers to an iteration of the app that references changes in the code.

Learn more about version numbers and developing line-of-business apps in [Get started with the Microsoft Intune App SDK](app-sdk-get-started.md#line-of-business-app-version-numbers).

#### Device and app management integration <!-- 677972 -->   
Now that Intune’s mobile device management (MDM) and mobile application management (MAM) are both accessible from the Azure portal, Intune started integrating the IT admin experience around application and device management. These changes are geared to simplify your device and app management experience.

Learn more about the MDM and MAM changes announced in the [Intune support team blog](https://blogs.technet.microsoft.com/intunesupport/2017/09/19/support-tip-setting-up-communication-between-mam-managed-and-mdm-managed-apps/).

#### New enrollment alerts for Apple devices <!-- 1471790 -->
The overview page for enrollment will show useful alerts for IT admins regarding management of Apple devices. Alerts will show up on Overview page when the Apple MDM push certificate is expiring or has already expired; when the Device Enrollment Program token is expiring or has already expired; and when there are unassigned devices in the Device Enrollment Program.

#### Support token replacement for app configuration without device enrollment <!-- 1080364 -->

You can use tokens for dynamic values in app configurations for apps on devices that are not enrolled. For more information, see [Add app configuration policies for managed apps without device enrollment](app-configuration-policies-managed-app.md).

### Intune apps

#### Updates to the Company Portal app for Windows 10 <!--1299474-->
The Settings page in the Company Portal app for Windows 10 has been updated to make the settings and intended user actions to be more consistent across all settings. It has also been updated to match the layout of other Windows apps. You can find before/after images in the [what's new in app UI](whats-new-app-ui.md) page.

#### Inform end users what device information can be seen for Windows 10 devices <!--1337920-->
We have added **Ownership Type** to the Device Details screen on the Company Portal app for Windows 10. This will allow users to find out more about privacy directly from this page from the Intune end user docs. They will also be able to locate this information on the **About** screen.

#### Feedback prompts for the Company Portal app for Android <!--1165249-->
The Company Portal app for Android now requests end user feedback. This feedback will be sent directly to Microsoft, and provide end users with an opportunity to review the app in the public Google Play store. Feedback is not required, and can easily be dismissed so users can continue using the app.

#### Update to what device details an organization can see <!--1616825-->
The Company Portal app for Android can now use geofencing to protect access to company resources. It uses network details such as IP address, default gateway address, and Domain Name System (DNS) to determine whether to allow access to protected company resources.

#### Helping your users help themselves with the Company Portal app for Android <!---1573324, 1573150, 1558616, 1564878--->

The Company Portal app for Android has added instruction for end users to help them understand and, where possible, self-solve on new use cases.
- End users will be guided to the (Azure Active Directory portal)[https://account.activedirectory.windowsazure.com/r/#/profile] to remove a device if they have reached the maximum number of devices that they are allowed to add.
- End users are given steps to follow to help them [fix activation errors on Samsung KNOX devices](https://go.microsoft.com/fwlink/?linkid=859718) or to [turn off power-saving mode](/intune-user-help/power-saving-mode-android). If neither of those solutions resolve their issue, we will provide an explanation of how to [submit logs to Microsoft](/intune-user-help/send-logs-to-microsoft-ios).

#### New 'Resolve' action available for Android devices <!---1583480--->

The Company Portal app for Android is introducing a 'Resolve' action on the _Update device settings_ page. Selecting this option will take the end user directly to the setting that is causing their device to be noncompliant. The Company Portal app for Android currently supports this action for the [device passcode](/intune-user-help/set-your-pin-or-password-android), [device encryption](/intune-user-help/encrypt-your-device-android), [USB debugging](/intune-user-help/you-need-to-turn-off-usb-debugging-android), and [Unknown Sources](/intune-user-help/you-need-to-turn-off-unknown-sources-android) settings.

#### Device setup progress indicator in Android Company Portal <!---1565657--->
The Company Portal app for Android shows a device setup progress indicator when a user is enrolling their device. The indicator shows new statuses, beginning with "Setting up your device...", then "Registering your device...", then "Finishing registering your device...", then "Finishing setting up your device...".

## Week of October 23, 2017

### Intune apps
#### Certificate-based authentication support on the Company Portal for iOS <!--1029830-->
We have added support for certificate-based authentication (CBA) in the Company Portal app for iOS. Users with CBA enter their username, then tap the “Sign in with a certificate” link. CBA is already supported on the Company Portal apps for Android and Windows. You can learn more on the [sign in to the Company Portal app](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal) page.

#### Apps that are available with or without enrollment can now be installed without being prompted for enrollment. <!-- 1334712 -->

Company apps that have been made available with or without enrollment on the Android Company Portal app can now be installed without a prompt to enroll.

## Week of October 16, 2017
### Device enrollment
#### Windows AutoPilot Deployment Program support in Microsoft Intune  <!-- 747617  -->
You can now use Microsoft Intune with Windows AutoPilot Deployment Program to empower your users to provision their corporate devices without involving IT. You can customize the out-of-box experience (OOBE) and guide users to join their device to Azure AD and enroll in Intune. Working together, Microsoft Intune and Windows AutoPilot eliminate the need to deploy, maintain, and manage operating system images. For details, see [Enroll Windows devices using Windows AutoPilot Deployment Program](https://docs.microsoft.com/intune/enrollment-autopilot).

#### Quick start for device enrollment  <!-- 1425655 --> 
Quick start is now available in **Device enrollment** and provides a table of references for managing platforms and configuring the enrollment process. A brief description of each item and links to documentation with step-by-step instructions provides useful documentation to simplify getting started.

#### Device categorization <!-- 1427491 -->
The enrolled devices platform chart of the **Devices > Overview** blade organizes devices by platform, including Android, iOS, macOS, Windows, and Windows Mobile.  Devices running other operating systems are grouped into "Other."  This includes devices manufactured by Blackberry, NOKIA, and others.  

To learn which devices are affected in your tenant, choose **Manage > All devices** and then use **Filter** to limit the **OS** field.

### Device management
#### Zimperium - New Mobile Threat Defense partner   <!-- 954681 -->  
You can control mobile device access to corporate resources using conditional access based on risk assessment conducted by Zimperium, a Mobile Threat Defense solution that integrates with Microsoft Intune.

##### How integration with Intune works
Risk is assessed based on telemetry collected from devices running Zimperium. You can configure EMS conditional access policies based on Zimperium risk assessment enabled through Intune device compliance policies, which you can use to allow or block non-compliant devices to access corporate resources based on detected threats.

#### New settings for Windows 10 device restriction profile  <!--- 978575, 1308849, -->  
We are adding new settings to the Windows 10 device restriction profile in the Windows Defender SmartScreen category.

For details about the Windows 10 device restriction profile, see [Windows 10 and later device restriction settings]( device-restrictions-windows-10.md).

#### Remote support for Windows and Windows Mobile devices   <!-- 1070473 -->  
Intune can now use the [TeamViewer](https://www.teamviewer.com) software, purchased separately, to enable you to give remote assistance to your users who are running Windows, and Windows Mobile devices.

#### Scan devices with Windows Defender <!-- 1280988  1280990   -->
You can now run a **Quick scan**, **Full scan**, and **Update signatures** with Windows Defender Antivirus on managed Windows 10 devices. From the device's overview blade, choose the action to run on the device. You are prompted to confirm the action before the command is sent to the device. 

**Quick scan**: A quick scan scans locations where malware registers to start, such as registry keys and known Windows startup folders. A quick scan takes an average of five minutes. Combined with the **Always-on real-time protection** setting that scans files when they are opened, closed, and whenever a user navigates to a folder, a quick scan helps provide protection from malware that might be in the system or the kernel. Users see the scan results on their devices when it finishes. 

**Full scan**: A full scan can be useful on devices that have encountered a malware threat to identify if there are any inactive components that require a more thorough clean-up, and is useful for running on-demand scans. Full scan can take an hour to run. Users see the scan results on their devices when it finishes. 

**Update signatures**: The update signature command updates Windows Defender Antivirus malware definitions and signatures. This helps ensure Windows Defender Antivirus is effective in detecting malware. This feature is for Windows 10 devices only, pending device internet connectivity. 

#### The Enable/Disable button is removed from the Intune Certificate Authority page of the Intune Azure portal  <!-- 1400455 -->
 We are eliminating an extra step in setting up the certificate connector on Intune. Currently, you download the certificate connector and then enable it in the Intune console. However, if you disable the connector in the Intune console, the connector continues to issue certificates.

##### How does this affect me?
Starting in October, the Enable/Disable button will no longer appear on the Certificate Authority page in the Azure portal. Connector functionality remains the same. Certificates are still deployed to devices enrolled in Intune. You can continue to download and install the certificate connector. To stop certificates from being issued, you now uninstall the certificate connector rather than disable it.

##### What do I need to do to prepare for this change?
If you currently have the certificate connector disabled, you should uninstall it.

### Device configuration
#### New settings for Windows 10 Team device restriction profile   <!--- 1308838 -->
In this release, we’ve added many new settings to the Windows 10 Team device restriction profile to help you control Surface Hub devices.

For more information about this profile, see [Windows 10 Team device restriction settings](device-restrictions-windows-10-teams.md).

#### Prevent users of Android devices from changing their device date and time  <!-- 1333292 -->
You can use an [Android custom device policy](custom-settings-android.md) to prevent Android device users from changing the device date and time.

To do this, configure an Android custom policy with the setting URI ./Vendor/MSFT/PolicyManager/My/System/AllowDateTimeChange
Set this to **TRUE**, and then assign it to the required groups.

#### BitLocker device configuration <!-- 1397398 -->
The **Windows Encryption > Base Settings** include a new **Warning for another disk encryption** setting that lets you disable the [warning prompt](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#allowarningforotherdiskencryption) for other disk encryption that might be in use on the user's device.  The warning prompt requires end-user consent before setting up BitLocker on the device and blocks BitLocker setup until confirmed by the end-user.  The new setting disables the end-user warning.


### App management
#### Volume Purchase Program for Business apps will now sync to your Intune Tenant <!-- 800882 -->  
Third-party developers can privately distribute apps to authorized Volume Purchase Program (VPP) for Business members specified in iTunes Connect. These VPP for Business members can sign in to the Volume Purchase Program App Store and purchase their apps.

With this release, the VPP for Business apps purchased by the end user will now start syncing to their Intune tenants.

#### Select Apple country store to sync VPP apps  <!-- 1332311 -->  
You can configure the Volume Purchase Program (VPP) country store when uploading your VPP token. Intune synchronizes VPP apps for all locales from the specified VPP country store.

> [!NOTE]  
> Today, Intune only synchronizes VPP apps from the VPP country store that match the Intune locale in which the Intune tenant was created.


### Intune apps
#### Block copy and paste between work and personal profiles in Android for Work <!-- 1098994 -->
With this release, you are able to configure the work profile for  Android for Work to block copy and paste between work and personal apps. You can find this new setting in the **Device restrictions** profile for the **Android for Work** Platform in **Work profile settings**.

#### Create iOS apps limited to specific regional Apple App Stores <!-- 1281692 -->
You will be able to specify the country locale during the creation of an Apple App Store managed app.

> [!Note]  
> Currently, you can only create Apple App Store managed apps that are present in the US country store.

####  Update iOS VPP user and device licensed apps  <!-- 1305564 -->  
You will be able to configure the iOS VPP token to update all apps purchased for that token through the Intune service. Intune
will detect the VPP app updates inside the app store and automatically push them to the device when the device checks-in.

For steps to set an VPP token and enable automatic updates, see [How to manage iOS apps purchased through a volume-purchase program with Microsoft Intune]
(/intune/vpp-apps-ios).


### Monitor and troubleshoot
#### User device association entity Collection added to Intune Data Warehouse data model <!-- 1187917 -->
You can now build reports and data visualizations using the user device association information that associates user and device entity collections. The data model can be accessed through the Power BI file (PBIX) retrieved from the Data Warehouse Intune page, through the OData endpoint, or by developing a custom client.

#### Review policy compliance for Windows 10 update rings <!-- 1067886 -->
You will be able to review a policy report for your Windows 10 update rings from Software updates > Per update ring deployment state. The policy report includes deployment status for the update rings that you have configured. 

#### New report that lists iOS devices with older iOS versions   <!-- 1352223 -->
The **Out-of-date iOS Devices** report is available from the **Software updates** workspace. In the report, you can view a list of supervised iOS devices that were targeted by an iOS update policy and have available updates. For each device, you can view a status for why the device has not been automatically updated. 

#### View app protection policy assignments for troubleshooting <!--  1475003 -->
In this upcoming release, **App protection policy** option will be added to the **Assignments** drop-down list available on the troubleshooting blade. You can now select app protection policies to see app protection policies assigned to the selected users.



## Week of October 2, 2017
### Intune apps
#### Improvements to device setup workflow in Company Portal <!--1490692-->
We've improved the device setup workflow in the Company Portal app for Android. The language is more user-friendly and specific to your company, and we've combined screens where possible. You can see these on the [what's new in app UI](whats-new-app-ui.md#week-of-october-2-2017) page.

#### Improved guidance around the request for access to contacts on Android devices <!--1484985-->

The Company Portal app for Android often requires the end user to accept the Contacts permission. If an end user declines this access, they will now see an in-app notification that alerts them to grant it for conditional access. 

#### Secure startup remediation for Android <!--1490712-->

End users with Android devices will be able to tap the non-compliance reason in the Company Portal app. When possible, this will take them directly to the correct location in the settings app to fix the issue. 

#### Additional push notifications for end users on the Company Portal app for Android Oreo <!--1475932-->

End users will see additional notifications to indicate to them when the Company Portal app for Android Oreo is performing background tasks, such as retrieving policies from the Intune service. This increases transparency for end users about when the Company Portal is performing administrative tasks on their device. This is part of the overall [optimization of the Company Portal UI](https://blogs.technet.microsoft.com/intunesupport/2017/08/21/android-8-0-o-behaviour-changes-and-microsoft-intune) for the Company Portal app for Android Oreo. 

There are further optimizations for new UI elements that are enabled in Android Oreo.  End users will see additional notifications that will indicate to them when Company Portal is performing background tasks such as retrieving policy from the Intune service.  This increases transparency for end users about when Company Portal is performing administrative tasks on the device.

#### New behaviors for the Company Portal app for Android with work profiles <!---1485783--->

When you enroll an Android for Work device with a work profile, it's the Company Portal app in the work profile that performs management tasks on the device. 

Unless you are using a MAM-enabled app in the personal profile, the Company Portal app for Android no longer serves any use. To improve the work profile experience, Intune will automatically hide the personal Company Portal app after a successful work profile enrollment.

The Company Portal app for Android can be enabled at any time in the personal profile by browsing for [Company Portal in the Play Store](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and tapping **Enable**.

#### Company Portal for Windows 8.1 and Windows Phone 8.1 moving to sustaining mode <!--1428681-->

Beginning in October 2017, the Company Portal apps for Windows 8.1 and Windows Phone 8.1 will move to sustaining mode. This means that the apps and existing scenarios, such as enrollment and compliance, will continue to be supported for these platforms. These apps will continue to be available for download through existing release channels, such as the Microsoft Store. 

Once in sustaining mode, these apps will only will receive critical security updates. There will be no additional updates or features released for these apps. For new features, we recommend that you update devices to Windows 10 or Windows 10 Mobile. 


### Device enrollment

#### Block unsupported Samsung Knox device enrollment  <!--- 1490695 --->

The Company Portal app only attempts to enroll supported Samsung Knox devices. To avoid KNOX activation errors that prevent MDM enrollment, device enrollment is only attempted if the device appears in the [list of devices published by Samsung](https://www.samsungknox.com/knox-supported-devices/knox-workspace). Samsung devices can have model numbers that support KNOX while others that don't. Verify Knox compatibility with your device reseller before purchase and deployment. You can find the full list of verified devices in the [Android and Samsung KNOX Standard policy settings](/intune/supported-devices-browsers.md#intune-supported-devices).

#### End of support for Android 4.3 and lower <!---1171126, 1326920 --->
Managed apps and the Company Portal app for Android will require Android 4.4 and higher to access company resources. By December, all enrolled devices will be force retired in December, resulting in loss of access to company resources. If you are using app protection policies without MDM, apps will not receive updates, and the quality of their experience will diminish over time.

#### Inform end users what device information can be seen on enrolled devices <!--1165314-->
We are adding **Ownership Type** to the Device Details screen on all Company Portal apps. This will allow users to find out more about privacy directly from the [What information can your company see?](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune) article. This will be rolling out across all Company Portal apps in the near future. We announced this for iOS in [September](https://docs.microsoft.com/intune/whats-new#week-of-september-11-2017).


## Week of September 25, 2017

### Device enrollment

#### Intune supports iOS 11 <!--1428975-->
Intune supports iOS 11. This was previously announced on the [Intune Support blog](https://blogs.technet.microsoft.com/intunesupport/2017/09/12/support-tip-intune-support-for-ios-11/).

#### End of support for iOS 8.0 <!---1164477--->
Managed apps and the Company Portal app for iOS will require iOS 9.0 and higher to access company resources. Devices that aren't updated before this September will no longer be able to access the Company Portal or those apps. 

### Intune apps

#### Refresh action added to the Company Portal app for Windows 10 <!--1132468-->
The Company Portal app for Windows 10 allows users to refresh the data in the app by either pulling to refresh or, on desktops, pressing F5.



## Notices

### Deprecating support for OS X Mavericks 10.10 and previous versions of macOS <!--1489263, plan for change for 1802-->

We are announcing that we will begin deprecation of enrollment for devices with OS X Mavericks 10.10 and previous versions of macOS in February 2018. Intune fully supports OS X Yosemite 10.11 and newer.

### New path for managed devices in Graph API <!-- 1586728 -->
We are making a change to the path used to access managed devices in the beta version of the Graph API. 

| | |
|--|--|
| Current path |  https://graph.microsoft.com/beta/managedDevices |
| New path | https://graph.microsoft.com/beta/deviceManagement/managedDevices |

Both paths will work through the month of October. After the October service release, only the new path will work.  If you are using the Graph API to access managed devices, update and verify your scripts and applications with the new path. For additional changes, check the monthly [Graph API changelog](https://developer.microsoft.com/graph/docs/concepts/changelog).


### Direct access to Apple enrollment scenarios <!--951869-->
For Intune accounts created after January 2017, Intune has enabled direct access to Apple enrollment scenarios using the Enroll Devices workload in the Azure portal. Previously, the Apple enrollment preview was only accessible from links in the Intune classic portal. Intune accounts created before January 2017 require a one-time migration before these features are available in Azure. The schedule for migration has not been announced yet, but details will be made available as soon as possible. We strongly recommend creating a trial account to test out the new experience if your existing account cannot access the Azure portal.

### Administration roles being replaced in Azure portal
The existing mobile application management (MAM) administration roles (Contributor, Owner, and Read-Only) used in the Intune classic portal (Silverlight) are being replaced with a full set of new role-based administration controls (RBAC) in the Intune Azure portal. Once you are migrated to the Azure portal, you will need to reassign your admins to these new administration roles. For more information about RBAC and the new roles, see [Role-based access control for Microsoft Intune](/intune/role-based-access-control).



## What's coming

### Manage Jamf-enrolled macOS devices with Intune's device compliance engine <!---1592747--->
Beginning in early 2018, Jamf will send macOS device state information to Intune, which will then evaluate it for compliance with policies defined in the Intune console. Based on the device compliance state as well as other conditions (such as location, user risk, etc.), conditional access will enforce compliance for macOS devices accessing cloud and on-premises applications connected with Azure AD, including Office 365.

### Changes in support for the Intune iOS Company Portal app  <!-- 1164474  -->
Coming soon, there will be a new version of the Microsoft Intune Company Portal app for iOS that will support only devices running iOS 9.0 or later. The version of the Company Portal that supports iOS 8 will still be available for a very short period of time. However, note that if you also use MAM-enabled iOS apps we support iOS 9.0 and later, so you'll want to ensure your end users update to the latest OS. 

#### How does this affect me?
We are letting you know this in advance, even though we don't have specific dates, so you have time to plan. Ensure your users are updated to iOS 9+ and when the Company Portal app releases, request that your end users update their Company Portal app.

#### What do I need to do to prepare for this change?
Encourage your users to update to iOS 9.0 or later to take full advantage of new Intune features.  Encourage users to install the new
version of the Company Portal and take advantage of the new features it will offer.

Go to the Intune in the Azure portal and view Devices > All Devices and filter by iOS version to see any current devices with operating systems earlier than iOS 9.


### Apple to require updates for Application Transport Security <!--748318-->
Apple has announced that they will enforce specific requirements for Application Transport Security (ATS). ATS is used to enforce stricter security on all app communications over HTTPS. This change impacts Intune customers using the iOS Company Portal apps.

We have made available a version of the Company Portal app for iOS through the Apple TestFlight program that enforces the new ATS requirements. If you would like to try it so you can test your ATS compliance, email <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app">CompanyPortalBeta@microsoft.com</a> with your first name, last name, email address, and company name. Review our [Intune support blog](https://aka.ms/compportalats) for more details.

## See also
* [Microsoft Intune Blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Cloud Platform roadmap](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [What's new in the Company Portal UI](whats-new-app-ui.md)
* [What's new in previous months](whats-new-archive.md)
