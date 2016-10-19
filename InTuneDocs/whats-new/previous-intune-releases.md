---
# required metadata

title: Previous releases | Microsoft Intune
description:
keywords:
author: barlanmsft
manager: angrobe
ms.date: 10/19/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 45dad14a-d412-488d-bb1e-ad990ea503df

# optional metadata

ROBOTS: noindex,nofollow
#audience:
#ms.devlang:
#ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Previous Intune releases

## September 2016
### New features, announcements and information
* [Windows conditional access](#windows-conditional-access)
* [iOS 10 support](#ios-10-support)
* [App Wrapping Tool supports MAM without device enrollment for Android and iOS](#app-wrapping-tool-supports-mam-without-device-enrollment-for-android-and-ios)
* [Intune groups begin transitioning to Azure Active Directory in September](#intune-groups-begin-transitioning-to-azure-active-directory-in-september)
* [Lookout integration to protect Android devices](#lookout-integration-to-protect-android-devices)
* [Company Portal updates for Android, iOS and Windows](#company-portal-updates)
* [Intune glossary](#intune-glossary)
* [What's coming](#whats-coming)

### Windows conditional access
You can now create conditional access policies through the Intune admin console to block Windows PCs from accessing Exchange Online and SharePoint Online. You can also create conditional access policies to block access to Office desktop and universal applications.

### iOS 10 support
Existing Intune MDM and MAM scenarios are compatible with iOS 10. For tips, refer to the [Intune Support Team Blog](https://blogs.technet.microsoft.com/intunesupport/2016/09/13/support-tip-intune-support-for-ios-10/).

### App Wrapping Tool supports MAM without device enrollment for Android and iOS
The Intune App Wrapping Tool is a command line tool used to enable Intune MAM on line-of-business (LOB) apps for iOS and Android. It is the simplest way to incorporate the Intune MAM SDK into your app, so that your app can enforce MAM policies deployed through Intune. Using MAM policies, you can:

1. Encrypt the app's data.
2. Require the information worker to enter a PIN when launching the app.
3. Allow the app to transfer data only to other managed apps.
4. Prevent the app from backing up data to Android, iTunes, and iCloud.
5. Only allow Cut, Copy, and Paste into and out of other managed apps.

The public preview of the updated Intune App Wrapping Tool now supports MAM without device enrollment on internal LOB apps on iOS and Android. This means your end-users are not required to enroll their devices with Intune to use MAM-enabled LOB apps.

Anyone can test the public preview software and read helpful documentation, located in msintuneappsdk's GitHub:

http://www.github.com/msintuneappsdk/intune-app-wrapper-ios-preview

http://www.github.com/msintuneappsdk/intune-app-wrapper-android-preview

Before you install and use Microsoft Intune App Wrapper for Android and iOS Pre-Release you must:

* Review the Microsoft License Terms for Microsoft Intune App Wrapping Tool for Android and iOS Pre-Release
* Print and retain a copy of the license terms for your records. By downloading and using Microsoft Intune App Wrapping Tool for Android Pre-Release you agree to such license terms. If you do not accept them, do not use the software.
<!---TFS 1235607--->

### Intune groups begin transitioning to Azure Active Directory in September
Some new Intune accounts will use Azure Active Directory security groups rather than Intune user groups. You will know that you’re working with security groups, as the Intune portal groups page will have a link directing you to the Azure management portal.

### Lookout integration to protect Android devices
Microsoft is integrating with Lookout’s mobile threat protection solution to protect Android mobile devices by detecting malware, risky apps, and more, on devices. Lookout’s solution helps you determine the threat level, which is configurable. You can create a compliance policy rule in Intune to determine device compliance based on the risk assessment by Lookout. Using conditional access policies, you can allow or block access to company resources based on the device compliance status.

End users of noncompliant devices will be prompted to enroll, and will be required to install the Lookout for Work application on Android devices, activate the app, and remediate threats reported in the Lookout for Work application to gain access. To learn more, see [Restrict access based on device, network, and application risk](restrict-access-based-on-device-network-app-risk.md).


### Company Portal updates

### Android
**Addition of "Notifications" to the Company Portal for Android**<br/>
A new Notifications icon has been added to the Company Portal for Android on the homepage. Tapping this icon accesses the Notifications page, which shows your end users all items that require attention in the Company Portal app, such as device noncompliance, enrollment update, and enrollment activation. The iOS Company Portal app already has this notifications experience. Having the new Notifications page means that user won’t see the Company Access Setup page every time they launch or resume the Company Portal as long as the device is already enrolled. If you create your own end-user guidance, you might want to update your documentation to reflect this change. Find updated screenshots [here](https://aka.ms/androidcpupdate).  
<!---TFS 1095560--->

**Providing feedback in the Company Portal for Android**</br>
A new item has been added to the menu of the Company Portal for Android. Tapping **Help & Feedback** shows three actions:
* Use **Get Help** to report an issues to your IT department about the Company Portal. IT will create an email using your  email client and attach the Company Portal logs to it. **Get Help** replaces the **Send Data** feature on the **Settings** page.
* Use **Give Feedback** to provide feedback to the Company Portal team.
* Use **Rate our app** to leave the Company Portal app a rating or review on Google Play.

### iOS
**Changes in support for the iOS Company Portal app**<br/>
All users of the Microsoft Intune Company Portal app for iOS are now required to use its latest version. New users are able to download only the latest version, and current users are required to update to it. The latest version requires iOS 8.0 or later, so devices running older iOS versions cannot use the Company Portal or enroll until they update their device to iOS 8.0 or later and then update the Company Portal app to the latest version. Enrolled devices running versions below iOS 8.0 will continue to be managed and listed in the Intune Admin Console.
<!---TFS 1283165--->

**Improvements in how iOS end users get their apps**<br/>
The following changes have been made to the apps tiles in the Company Portal app for iOS to point users to different views in a single location, the Company Portal website, for all of their apps. Apple restrictions prohibit line-of-business and managed app store apps from being listed in the Company Portal app, and require users to visit different views to find all of their apps.

- The **Company Apps** tile previously pointed to a list of all apps in the ALL tab of the Company Portal website, and it will continue to work the same way. The tile name has changed to **All Apps**.
- The **Other Apps** tile previously pointed to a view, inside the Company Portal app, that lists all apps that Apple permits the Company Portal app to show. The tile name has changed to **Featured Apps**, and tapping the tile will take users to the FEATURED tab of the Company Portal website.
-  The **Categories** tile previously pointed to a view, inside the Company Portal app, that lists categories of apps. The tile name has not changed, but it now points to the CATEGORIES tab of the Company Portal website.
You can find updated screenshots [here](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186).
<!---TFS 1317133--->

**Prompt to install the iOS Managed Browser app if IT Pro sets that requirement for an app**<br/>
If you have configured a web clip to open only in the managed browser, and the managed browser is not installed on a device, the Company Portal app on the device will prompt the user to install the managed browser before the web clip can be installed.
<!---TFS 1228570--->

#### Windows
**Feedback button added to Windows Phone 8.1 Company Portal app**<br/>
The Windows Phone 8.1 Company Portal app enables end users to send feedback about the app by using a new "send feedback" button. To find the button, users tap the “three dots” menu at the bottom right of the Company Portal app screen and then tap **send feedback**. The collected, anonymized feedback will help Microsoft improve the Company Portal app experience for users.
<!---TFS 1317806--->

### Intune glossary</br>
We’ve added a new [glossary topic](https://docs.microsoft.com/intune/understand-explore/intune-glossary) to the library to help you understand some of the terms used in the Intune product.


## August 2016
## App management
<!---@Barry, I created the buckets of App management, Device management, etc but am not tied to them. Just wanted to break up and organize the feature list. If you're going to take over the Company Portal section, please talk to Stacie about how she's been organizing it. --->

### Hidden and shown apps for iOS 9.3
For supervised devices running iOS 9.3 or later, you can use the hidden and shown apps list in the iOS general configuration policy to:
- Specify a list of apps that will be hidden from users. Users cannot view, or launch these apps.
- Specify a list of apps that users can view and launch. No other apps can be viewed or launched.

The apps you can specify include both apps you have deployed, and the built-in iOS apps like Messages and Notes. For details, see [iOS policy settings in Microsoft Intune]( /intune/deploy-use/ios-policy-settings-in-microsoft-intune)
<!---TFS 1279009 checked--->
### Allowed and blocked apps policy for Samsung KNOX devices
You can now configure a custom policy for Samsung KNOX devices that lets you create one of the following:
- A list of apps that are blocked from running on the device. Even if installed, an app defined in the blocked list cannot be activated on the device.
- A list of apps that users of the device are allowed to install from the Google Play store. No other apps can be installed from the store.

These settings can only be used by devices that run Samsung KNOX.
For details, see [Use custom policies to allow and block apps for Samsung KNOX devices](/intune/deploy-use/custom-policy-to-allow-and-block-samsung-knox-apps).
<!---TFS 1311629 checked --->
### New apps compatible with mobile application management (MAM) policies
The Yammer app for [iOS](https://itunes.apple.com/app/yammer/id289559439?mt=8) and [Android](https://play.google.com/store/apps/details?id=com.yammer.v1) is now compatible with [Intune mobile application management (MAM) policies](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune), whether or not the device is enrolled.

For a full list of MAM compatible apps, see the [Microsoft Intune application partners](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners) site.
<!--- TFS 1252335 & 1252336 checked--->

<!--- I started putting TFS numbers in the What's Coming topic and found it helpful when updating the What's New. Up to you if you want to continue. --->

### Intune Viewer apps
With the release of the new RMS sharing app, we are removing the following Intune Viewer apps, beginning in August, 2016:
- Intune AV Viewer
- Intune PDF Viewer
- Intune Image Viewer for Android from Google Play

Instead of using the Intune Viewer apps, we recommend using the new [Rights Management app (RMS sharing) for Android](/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app), which allows you to deploy one app instead of three separate apps to securely view corporate files on Android devices. When the Intune viewer app is no longer supported, it will be removed from the Google Store and will not be available for future use.

## Device management
### Android 7.0 support
Intune provides “day 0” support for the forthcoming Android 7.0 operating system for mobile devices.
<!---TFS 1262053--->

### Google removal of remote passcode reset capability on Android 7.0 devices
Google is removing the ability of IT administrators and end users to remotely reset the passcode of Android 7.0 devices. Previously, IT administrators could remotely reset a user’s passcode, and end users could reset their passcodes from the Company Portal website.

## Company Portal updates
### Company Portal website
- **Feedback link from the Company Portal to Microsoft** <br/>
The Company Portal website enables end users to tap a new "Feedback" link, at the bottom of the page, to send feedback to Microsoft about their experience with the site. The collected, anonymized feedback will help Microsoft improve the Company Portal website experience for users.
<!--- TFS 1313657 checked--->

### iOS
- **Minimum iOS Managed Browser version updated to 8.0**<br/>
The Microsoft Intune Managed Browser app for iOS has been updated to support devices running iOS 8.0 or later. While iOS 7.1 devices can still use the existing Managed Browser app, encourage your users to update to iOS 8.0 or later to access and take full advantage of new Managed Browser features.  
<!---TFS 1313253 checked--->

### What's coming

__iOS 10 support__
Intune will fully support iOS 10. More information will follow the iOS 10 public release.

__Intune Groups transitioning to Azure Active Directory Groups beginning in September 2016__
Intune is creating a new group management experience that uses Azure Active Directory (AAD) security groups as user and device groups in Intune. These groups will be used for all group management, policy deployment, and profile deployment **when we introduce the new Azure-based Intune admin portal**.

This new experience will keep you from having to duplicate groups between services, **allow you access to some new Azure Active Directory Premium (AADP) group features**, and provide extensibility using PowerShell and Graph. This will also unify the group management experience across enterprise mobility management.

To enable the move to Security Groups, the experience in the **current admin console** will undergo some modifications. **These changes, and the use of AAD security groups, will be recorded in the Intune documentation**.

Customers who are new to Intune will see **some of the security group changes before current tenants do**.

In addition to changes in group management, **the following functionality will be deprecated**:
- Excluding members or groups while creating a new group
- **Ungrouped Users** and **Ungrouped Devices** groups
- **Manage Groups** in the Service Admin role
- Custom group-based alerts for Notification Rules
- Pivoting with groups in reports
<!--- TFS 1295329--->

__Addition of 'Notifications' to the Company Portal for Android__
We are releasing an update to the Company Portal for Android in September that will introduce a new **Notifications** icon on the homepage. Tapping this icon will access the **Notifications** page that will show your end user all the items that require attention in the Company Portal app such as device non-compliance, enrollment update, and enrollment activation. If you also use the iOS Company Portal app, you’ll already see the notifications experience. With the introduction of the **Notifications** page, you will not see the **Company Access Setup** page every time you launch or resume the Company Portal for Android as long as the device is already enrolled. We hear many of you have created end-user guidance and appreciate advanced notice when your guidance/screen shots may need updating. Please update your documentation to reflect the upcoming change in experience. Find updated screenshots here: https://aka.ms/androidcpupdate.  

__Improvements in how iOS end users get their apps__
The following changes are being made in September to the apps tiles in the Company Portal app for iOS to point users to different views in a single location, the Company Portal website, for all of their apps. Currently, Apple restrictions prohibit line-of-business and managed app store apps from being listed in the Company Portal app, and require users to visit different views to find all of their apps.

- The **Company Apps** tile currently points to a list of all apps in the ALL tab of the Company Portal website, and it will continue to work the same way. The tile name will change to **All Apps**.
- The **Other Apps** tile currently points to a view, inside the Company Portal app, that lists all apps that Apple permits the Company Portal app to show. The tile name will change to **Featured Apps**, and tapping the tile will take users to the FEATURED tab of the Company Portal website.
-  The **Categories** tile currently points to a view, inside the Company Portal app, that lists categories of apps. The tile name will not change, but it will now point to the CATEGORIES tab of the Company Portal website. You can find updated screenshots [here](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186).
<!---TFS 1317133--->

### Cloud roadmap
Keep informed about upcoming developments for Intune with the [Cloud Platform roadmap](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune).

### Service deprecation
<!---@Barry, we started listing service deprecations earlier this summer. --->
- **Changes in support for the iOS Company Portal app**<br/>
In September, all users of the Microsoft Intune Company Portal app for iOS will be required to use its latest version. New users will only be able to download the latest version and current users will be required to update to it. The latest version requires iOS 8.0 or later, so devices running older iOS versions won’t be able to use the Company Portal or enroll until they update their device to iOS 8.0 or later and then update the Company Portal app to the latest version. Enrolled devices running versions below iOS 8.0 will continue to be managed and listed in the Intune Admin Console.  

- **Minimum iOS Managed Browser version updated to 8.0**<br/>
In August, Intune will release an updated Microsoft Intune Managed Browser app for iOS that will only support devices running iOS 8.0 or later. While iOS 7.1 devices will still be able to use the existing Managed Browser app, please encourage your users to update to iOS 8.0 or later to access and take full advantage of new Managed Browser features.  
<!---TFS 1313253--->

- **Company Portal apps for Windows 8 and Windows Phone 8 are being deprecated** <br/>
Starting in October 2016, Microsoft Intune will deprecate support for Windows 8 and Windows Phone 8 Company Portal apps. Microsoft Intune will also deprecate support for the Windows Phone 8 platform. As a consequence, you will not be able to enroll or update any Windows Phone 8 devices. You can continue to manage Windows Phone 8 and Windows 8 devices that are already enrolled. Update Windows Phone 8 and Windows 8 devices to Windows 8.1 and Windows Phone 8.1, and use the corresponding Windows 8.1 and Windows Phone 8.1 Company Portal apps to continue distributing apps to these devices without disruptions.
<!---TFS 1255391--->

<!--- - **Custom Group Targeting of Notification Rules Removal.**<br/>
Intune notification rules define who an email alert will be sent to from Intune. Currently, you can configure notification rules to send emails to all users of devices in an Intune device group that you created. From around June 1st 2016 moving forward, targeting user-created groups will no longer be supported.

	Today, to target a notification rule to a group you created from the Microsoft Intune administration console, you would take the following steps:

	In the **Admin** workspace, click **Notification Rules** > **Create New Rule**

	In step two of the Create Notification Rule Wizard, select the device groups which the rule will target. This step, “select device groups”, is being removed from the Intune Console.

	The preliminary timeline for this change is as follows:
	- In August, 2016, new tenants will not see step two of the Create Notification Rule Wizard. Exiting tenants are unaffected.
	- Around September, 2016, some existing tenants will not see the “select device groups” in the wizard.
	- Around November, 2016, we expect that all tenants will not see the “select device groups” in the wizard.

--->

## July 2016
### App management

__Improve the app provisioning profile update experience__
Apple iOS line of business mobile apps are built with a provisioning profile included and code signed with a certificate. When the app runs on an iOS device, iOS confirms the integrity of the iOS app and enforces policies defined by the provisioning profile.

The enterprise signing certificate you use to sign apps typically lasts for 3 years. However, the provisioning profile expires after 1 year. With this update, Intune gives you the tools to proactively deploy a new provisioning profile policy to devices that have apps that are near expiry while the certificate is still valid. For more information, see [Use iOS mobile provisioning profile policies to keep your line of business apps up to date](/intune/deploy-use/ios-mobile-app-provisioning-profiles).
<!--- TFS 1280247--->

__Xamarin SDK for Intune apps is available__
The Intune App SDK Xamarin component allows you to enable the Intune mobile app management features in your mobile iOS and Android apps built with Xamarin. You can find the component in the [Xamarin store](https://components.xamarin.com/view/Microsoft.Intune.MAM) or on the [Microsoft Intune Github page](https://github.com/msintuneappsdk).
<!--- TFS 1061478 --->

### Device management
__Increased device enrollment limits__
Intune increased the maximum configurable device enrollment limit from 5 to 15 devices per user.
<!---TFS 1289896 --->

__TeamViewer Integration for Windows PCs running the Intune client software__
[TeamViewer](https://www.teamviewer.com) integration for Windows PCs that run the Intune client lets you establish remote assistance sessions with Windows PCs to help support end-user helpdesk departments. This includes Windows 7, 8, 8.1 and Windows 10. For details, see [Common Windows PC management tasks with the Microsoft Intune computer client](/intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client).
<!---TFS 1284856--->

### Company Portal updates
__Company Portal website__
- **Improved end-user experience when enrolling Windows devices**<br/>
When you are using conditional access, the enrollment steps for Windows 8.1, Windows 10 Desktop, and Windows 10 Mobile have been clarified in the Company Portal website. Users will now see separate “Device enrollment” and “Workplace Join” steps, making it easier for them to see the status of their device and to complete the process if they experience a Workplace Join (WPJ) failure. The separate steps are also expected to simplify the troubleshooting process for IT administrators. Previously, when end users tried to enroll and all enrollment steps succeeded except for WPJ, the enrolled device would not appear on the list of devices for users to identify, causing confusion for users.

__* ### Android__
- **Android Company Portal app**<br/>
If Android end users see an error message that says their device is missing a required certificate, they can tap a "How to resolve this" button to get [steps](/intune/enduser/your-device-is-missing-a-required-certificate-android#your-device-is-missing-a-certificate-required-by-your-it-administrator) for installing the missing certificate. If users complete the steps, but see an additional "missing certificate" error message, they are asked to contact their IT administrator and provide this [link](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues), which contains steps that IT administrators can use to fix the certificate issue.

- **Restrict side-loaded app installations to enrolled devices**<br/>
Android devices can no longer install applications through the Company Portal website unless the devices have been enrolled in Intune by using the Intune Company Portal app for Android.
<!---TFS 1299082--->

__* ### iOS__
- **Changes to Device Enrollment Managers accounts in the iOS Company Portal app**<br/>
To improve performance and scale, Intune no longer displays all Device Enrollment Managers (DEM) devices in the **My Devices** pane of the iOS Company Portal app. Only the local device running the app is displayed, and only if it is enrolled via the Company Portal app.

The DEM user may perform actions on the local device, but remote management of other enrolled devices can only be performed from the Intune admin console. Additionally, Intune is deprecating use of DEM accounts with either the Apple Device Enrollment Program or the Apple Configurator tool. Both these enrollment methods already support user-less enrollment for shared iOS devices.

Only use DEM accounts when user-less enrollment for shared devices is unavailable. For more information, see [Enroll corporate-owned devices with the Device Enrollment Manager in Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).
<!---TFS 1233681--->

### Change of names for Windows features
- [Microsoft Passport for Windows](/intune/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune) is now known as **Windows Hello for Business**.
- [Enterprise data protection](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) is now known as **Windows Information Protection**.

## June 2016
### Intune service health
Service health information for Intune has been moved to a central location with other Microsoft services. You'll now find this information in the Office 365 management portal under Service Health. For more information, see [this blog post](https://blogs.technet.microsoft.com/enterprisemobility/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).

### App management
- **Enhanced Windows 10 enterprise data policy configuration experience.** We have made enhancements to the Windows 10 enterprise data protection policy configuration experience around creating app rules, specifying network boundary definition, and other enterprise data protection settings. To learn more, see [Create an enterprise data protection (EDP) policy using Microsoft Intune](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune).


### Device management
- **Windows Defender policy setting to protect against potentially unwanted apps.** A new Windows Defender setting named **Potentially Unwanted Application Detection** has been added to the general configuration policy for Windows 10 Desktop and Mobile. You can use this setting to protect enrolled Windows desktop computers against running software classed by Windows Defender as potentially unwanted. You can protect against these applications running, or use audit mode to report when a potentially unwanted application is installed. See [Windows 10 policy settings in Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune) for more information.
<!---TFS 1244478--->

### Conditional access
- **Cisco ISE network access control policy for Intune.**  Customers who use the Cisco Identity Service Engine (ISE) 2.1 and also use Microsoft Intune can set a network access control policy in ISE.

	Using this policy, devices that need to connect to the network using WiFi or VPN must meet following conditions before they are allowed access:

	* Must be managed by Intune
	* Must be compliant with any deployed Intune compliance policies

 End users of noncompliant devices will be prompted to enroll, and remediate any compliance issues to gain access.
- **Conditional access for browser.** You can set a conditional access policy for [Exchange Online](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune) and [SharePoint Online](/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune) so that they can only be accessed from supported web browsers on managed and compliant iOS and Android devices. End users who try to sign in to Outlook Web Access (OWA) and SharePoint sites with iOS and Android devices will be prompted to enroll their device with Intune as well as to fix any non-compliance issues before they can complete sign-in.
<!---TFS 1175844--->

- **Dynamics CRM Online supports conditional access.** You can set a conditional access policy for [Dynamics CRM Online](/intune/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune) so that it can only be accessed by managed and compliant iOS and Android devices. End users who try to sign in to the Dynamics CRM mobile app on iOS and Android will be prompted to enroll with Intune as well as remediate any non-compliance issues before sign-in can complete.
<!---TFS1295358--->

##Intune Company Portal updates

#### Android Company Portal app

- When IT administrators apply the new "Require that devices disallow installation of apps from unknown sources (Android 4.0+)" policy, end users with Android 4.0 or later devices will see the message, "Installation from Unknown sources must be disabled." Users will need to go to  **Settings** > **Security**, and turn off **Unknown sources**. A link in the compliance message lets users get more [information](/Intune/EndUser/you-are-asked-to-turn-off-unknown-sources-android) about the message and why they are being required to turn off the setting.

- When IT administrators apply the new "Require that devices have enabled scanning of apps for security threats (Android 4.0+)" policy, end users with Android 4.0 or later devices will see the message, "Scan device for security threats." Users will need to go to **Settings** > **Google** > **Security**, and turn on **Scan device for security threats**. A link in the compliance message lets users get more [information](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) about the message and why they are being required to turn on the setting.

- When IT administrators apply the new "Require that USB debugging is disabled (Android 4.2+)" policy, end users with Android 4.2 or later devices will see the message, "USB debugging must be disabled." Users will need to go to **Settings** > **Developer options**, and turn off **USB debugging**." A link in the compliance message lets users get more [information](/Intune/EndUser/you-are-asked-to-turn-off-usb-debugging-android) about the message and why they are being required to turn off the setting.

- When IT administrators apply the new "Minimum Android security patch level (Android 6.0+)" policy, end users with Android 6.0 or later devices will see the message, "This device does not meet the minimum Android security patch level." Users will need to install the required security patch. A link in the compliance message lets users get [information](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) about how to install the required security patch and to see which security patch they currently have installed.

#### iOS Company Portal app

- When end users are installing line-of-business apps, they will now see an improved app installation experience. If the app installation is taking a long time, users can manually sync their device to force the sync process to resume. To review the end-user instructions, see [Sync your iOS device manually](/Intune/EndUser/sync-your-device-manually-ios).

- The Microsoft Intune Company Portal app for iOS has been updated to support iOS version 8.0 and later. This update means that end users can install the Company Portal app and enroll new devices in Intune only if the device is running iOS version 8.0 or later. Users who have already enrolled devices that are running on an unsupported version of iOS can continue to use the Company Portal app that is on their device.


## May 2016
All of these features are also supported for hybrid deployments (Configuration Manager with Intune). For more information about new hybrid features, check out the [Hybrid What’s New](https://technet.microsoft.com/en-us/library/mt718155.aspx) page.

### Documentation
Welcome to the preview version of [docs.microsoft.com](https://docs.microsoft.com/en-us/intune)!
This is a completely new, modern content platform designed to make it easier for you, our customers to understand and use Intune.
To read about all of the new features, see [Introducing docs.microsoft.com](https://docs.microsoft.com/teamblog/introducing-docs-microsoft-com/)

### Intune service health
Service health information for Intune has been moved to a central location with other Microsoft services. You'll now find this information in the [Office 365 management portal](https://portal.office.com/Admin/Default.aspx) under **Service Health**.
For more information, see [this blog post](https://blogs.technet.microsoft.com/microsoftintune/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).


### App management
- **MAM SDK: Support PIN length configuration.** You will be able to specify the length of the PIN for MAM apps similar to a device PIN. This will require end users to comply with the new restrictions you set. They will see a slightly modified PIN screen to account for the longer input. For details, see [MAM policy settings for Android](/intune/deploy-use/android-mam-policy-settings), and [MAM policy settings for iOS](/intune/deploy-use/ios-mam-policy-settings).

- **Skype for Business for iOS and Android.** You can now target Skype for business with [MAM without enrollment policies](/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune). Once users log in, the MAM policies will be applied.

- **New apps available for management with MAM policies.** The Microsoft Word, Excel, and PowerPoint apps for Android can now be associated with MAM policies on devices that are not enrolled with Intune. For a full list of supported apps, go the Microsoft Intune mobile application gallery on the [Microsoft Intune application partners](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx) page.


### Company Portal updates

#### Android Company Portal app
- **End user toast notifications**: End users will now see toast notifications from the Android Company Portal app when they are enrolling their devices or removing their devices from the Company Portal.

- **Changes to Device Enrollment Managers accounts in the Android Company Portal app.** To improve performance and scale, Intune is no longer showing all Device Enrollment Managers (DEM) devices in the My Devices pane of the Android Company Portal app. Only the local device running the app is displayed, and only if it is enrolled via the Company Portal app. The DEM user may perform actions on the local device, but remote management of other enrolled devices can only be performed from the Intune admin console.

#### Company Portal website
- **Company Portal website: Device identification banner will provide more information to end users.** End users can now more easily identify the device they’ve selected when they are using the Company Portal website. If the wrong device is selected, they will be able to select the correct device by tapping the **Tap here** link in the home page banner.

### Service deprecation
- **Intune Viewer apps.** With the release of the new RMS sharing app, we are removing the following Intune Viewer apps, beginning August, 2016:
	- Intune AV Viewer
	- Intune PDF Viewer
	- Intune Image Viewer for Android from Google Play

  Instead of using the Intune Viewer apps, we recommend using the new Rights Management app (RMS sharing) for Android, which allows you to deploy one app instead of three separate apps to securely view corporate files on Android devices. Learn more about the RMS sharing app (with link to documentation).

- **Custom Group Targeting of Notification Rules Removal.**
Intune notification rules define who an email alert will be sent to from Intune. Currently, you can configure notification rules to send emails to all users of devices in an Intune device group that you created. From around June 1st 2016 moving forward, targeting user-created groups will no longer be supported.

	Today, to target a notification rule to a group you created from the Microsoft Intune administration console, you would take the following steps:

	In the **Admin** workspace, click **Notification Rules** > **Create New Rule**

	In step two of the Create Notification Rule Wizard, select the device groups which the rule will target. This step, “select device groups”, is being removed from the Intune Console.

	The preliminary timeline for this change is as follows:
	- In June, 2016, new tenants will not see step two of the Create Notification Rule Wizard. Exiting tenants are unaffected.
	- Around August, 2016, some existing tenants will not see the “select device groups” in the wizard.
	- Around October, 2016, we expect that all tenants will not see the “select device groups” in the wizard.


- **Changes in support for the iOS Company Portal app**. In the coming months, there will be an update for the Microsoft Intune Company Portal app for iOS that will only support devices running iOS 8.0 or later. Users won’t be able to enroll new devices running versions below iOS 8.0. Enrolled devices running versions below iOS 8.0 will continue to be managed and will, for a limited time, be able to continue using the Company Portal app. However, devices must be on iOS 8.0 or later to access the latest versions of the Company Portal app. We encourage you to notify users to update to iOS 8.0 or later to take full advantage of new Intune features.  


## April 2016
All of these features are also supported for hybrid customers (Configuration Manager integrated with Intune).

### App management
- **MAM user compliance.**
You can now view the [status](/intune/deploy-use/monitor-mobile-app-management-policies-with-Microsoft-Intune) of your application management policies for any user in your Azure Active Directory (AAD) tenant. This includes:
   - Devices
   - Apps on the device

   Status values:

   **Checked in**: Indicates the policy was deployed to the user, and app was used in work context, and successfully received the policy.

    **Not checked in**: Indicates the policy was deployed to the user, but app has not been used in the work context since then.


- **MAM controls to prevent Outlook contacts sync (Android).**
A new setting is available for [mobile application management](/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) without device enrollment. This setting  allows you to prevent an application from syncing contacts to the native address book on Android devices. When this setting is enabled, targeted applications will no longer be able to save contacts to the native address book. When this setting is disabled, targeted applications will be able to save contacts to the native address book. When you [remotely wipe a device or app](/intune/deploy-use/wipe-managed-company-app-data-with-Microsoft-Intune), contacts that have already been saved to the native address book will be removed. This new setting is supported initially by the Outlook application on Android devices.

### Device management
- **Phone number identification for corporate-owned devices.** Phones that are categorized as "Corporate" are now identified with their full phone number when, for example, you run a mobile device inventory report. BYOD phone numbers continue to be masked with ****, with only the last 4 digits displayed.


### Company portal updates
**Android Company portal app**
Users who have not enrolled their device in Intune and who do not have the correct certificate installed will not be able to sign in to the Android Company Portal app and will see the message, “You cannot sign in because your device is missing a required certificate.” The message includes a “How to resolve this” link that users can tap to see instructions for installing the certificate. To see the steps that end users follow to resolve the issue, see [Your device is missing a required certificate](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_cert_missing).

**iOS Company Portal app**
Support has been added for the pull-to-refresh action to refresh the content on the home screen, which includes listed apps, listed devices, and IT contact information. The pull-to-refresh action does not check compliance or policy information, which can be done by selecting the tile for your current device and tapping the **Sync** button.

**Windows 10 Mobile and Windows Phone 8.1 Company Portal app**
When end users are installing line-of-business apps, they will now see an improved app installation experience. If the app installation is taking a long time, users can manually sync their device to force the sync process to resume. To review the end-user instructions, see [Sync your device manually to speed up app installations](https://technet.microsoft.com/library/mt427782.aspx#BKMK_win10m_wp81_sync_manually).

**Company Portal website**
When Windows 10 Mobile and Windows Phone 8.1 users are installing line-of-business apps, they will now see the following new statuses, which provide them with more detail about the status of their installation:

* **Waiting for device to sync** – the user has tapped “Install” and the device now tries to sync with the Intune infrastructure. The sync is required before the installation can complete. The "Waiting for device to sync" message is also a link that users can tap to see [instructions](https://technet.microsoft.com/library/mt590895.aspx#BKMK_iwp_sync_manually) on how to manually sync their device with Intune if the sync process is taking a long time or gets stalled.
* **Downloading** – the user’s download request is being processed and the device is downloading and installing the app.

Before these statuses were added, users got confused if an app installation took a long time, because they saw only an “Installing” status, which might remain on the screen for hours. Adding the new statuses means that, instead of calling support, users can now tap the "Waiting for device to sync" link and follow the instructions to force the sync process to resume.

>[!div class="step-by-step"]

>[&larr; **What's new in Intune**](whats-new-in-microsoft-intune.md)    
