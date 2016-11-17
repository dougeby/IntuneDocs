---
# required metadata

title: What's New Archive | Microsoft Intune
description: Archived What's New announcements for Microsoft Intune
keywords:
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/11/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: ed2db991-4729-49a7-a1e6-be2ffa0d03d1

# optional metadata

ROBOTS: noindex,nofollow
#audience:
#ms.devlang:
#ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---
# What's New - Archive

This page is an archive of recent announcements made in [What’s New in Microsoft Intune](whats-new-in-microsoft-intune.md).

## October 2016

### Conditional access for mobile application management
You will be able to restrict access to Exchange Online so that access can come only from apps that support Intune mobile application management policies such as Outlook. [This new feature](/intune/deploy-use/allow-policy-managed-apps-access-to-o365) pairs up perfectly with Intune mobile app management (MAM) policies as you can block access to built-in mail clients or other apps that have not been configured with the Intune MAM policies. This ensures your users are accessing your organization’s data with apps that can be protected using Intune MAM. You can get started in Intune mobile app management via the Azure portal. Look for the new Conditional Access section in the “Settings” blade.

### Conditional access for Windows PCs
You can now create conditional access policies through the Intune admin console to block Windows PCs from accessing [Exchange Online](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune) and [SharePoint Online](/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune). You can also create conditional access policies to block access to Office desktop and universal applications.

### Android for Work support

> [!IMPORTANT]

> While you can deploy Android for Work apps with an action of __Required__, you can only deploy apps as __Available__ if your Intune groups have been migrated to the new Azure AD groups experience.

Intune is now part of the Android for Work (AfW) program. We will begin rolling out support for AfW features starting this month and continuing over the next few months. Note that  available app deployment of AfW leverages the new grouping and targeting experience. Newly provisioned Intune Service accounts will be able to use this feature once AfW is available to them.

<!--Existing Intune customers can use this feature in production once their tenant has been migrated. Existing customers are welcome to create a trial Intune account to plan for and test this feature until their tenant has been migrated. Any questions on grouping and targeting timelines, please contact our [migration team](mailto:intunegrps@microsoft.com).-->

[Read Microsoft’s announcement about Intune support for Android for Work](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/12/microsoft-intune-support-for-android-for-work/).

The following Intune topics are new, or updated with Android for Work information:

For IT professionals:
- [Set up Android for Work](/intune/deploy-use/set-up-android-for-work)
<!--- [Nathan Bigman's resource access topics]()-->
- [Restrict email access to Exchange Online and new Exchange Online Dedicated with Intune](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)
- [Restrict email access to Exchange on-premises and legacy Exchange Online Dedicated with Intune](/intune/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)
- [Android for Work compliance policy settings](/intune/deploy-use/afw-compliance-policy-settings-in-microsoft-intune)
- [How to deploy Android for Work apps](/intune/deploy-use/android-for-work-apps)
- [Configure Android for Work apps with mobile app configuration policies](/intune/deploy-use/afw-app-configuration-policy)
- [Android for Work policy settings](/intune/deploy-use/android-for-work-policy-settings-in-microsoft-intune)

For end users:
- [What happens when you create a work profile](/intune/enduser/what-happens-when-you-create-a-work-profile-android)
- [Create a work profile and enroll your device in Intune](/intune/enduser/create-a-work-profile-and-enroll-your-device-in-intune-android)

### Lookout integration to protect iOS devices
In October, Microsoft is integrating with Lookout’s mobile threat protection solution to protect iOS mobile devices by detecting malware, risky apps, and more, on devices. Lookout’s solution helps you determine the threat level, which is configurable. You can create a compliance policy rule in Intune to determine device compliance based on the risk assessment by Lookout. Using conditional access policies, you can allow or block access to company resources based on the device compliance status.

End users of noncompliant iOS devices will be prompted to enroll, and will be required to install the Lookout for Work app on their devices, activate the app, and remediate threats reported in the Lookout for Work application to gain access to company data. Learn how to [Configure and deploy Lookout for Work apps](/intune/deploy-use/configure-and-deploy-lookout-for-work-apps).
<!--TFS 1319493-->

<!--### New Microsoft Intune Company Portal available for Windows 10 devices
Microsoft is releasing a new [Microsoft Intune Company Portal for Windows 10 devices](https://go.microsoft.com/fwlink/?linkid=830663). This app, which leverages the new Windows 10 Universal format, will provide the user with an updated user experience within the app and identical experiences across all Windows 10 devices, PC and Mobile alike, while still enabling all the same functionality that they are using today.

The new app will also allow users to leverage additional platform features like single sign-on (SSO) and certificate-based authentication on Windows 10 devices. The app will be made available as an upgrade to the existing Windows 8.1 Company Portal and Windows Phone 8.1 Company Portal installs from the Windows Store.-->

### Intune App Wrapping Tool for Android
You can enable your apps to use Intune mobile application management (MAM) policies by using the Intune App Wrapping Tool. Support for Intune MAM policies without requiring device enrollment is now available.

### Manage printing from apps managed using MAM policies
You can now prevent printing company data from apps that have MAM policies. This setting is available on the [Azure portal](/Intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) and is supported on both [iOS](/Intune/deploy-use/ios-mam-policy-settings) and [Android](/Intune/deploy-use/android-mam-policy-settings) devices.
<!--TFS 1014328-->

### Support for fingerprints on Android devices
Android mobile app management (MAM) policies now allow users to access an app with their fingerprint instead of typing out their PIN. See this and other [mobile app management policy settings for Android here](/Intune/deploy-use/android-mam-policy-settings).

### Notices

__Android Samsung KNOX compatibility with Intune__
Certain models of the Samsung Galaxy Ace phone cannot be managed by Intune as Samsung KNOX devices. When you enroll these devices with Intune, they will instead be managed as standard Android devices.

The model numbers affected are:

* SM-G313HU
* SM-G313HY
* SM-G313M
* SM-G313MY
* SM-G313U

You and your end users need take no further action. For more information, visit the [Samsung KNOX](https://www.samsungknox.com) website.

__Company Portal app for Windows 8 is deprecated; support for Windows Phone 8 and Windows RT platforms are being deprecated__
Starting in October 2016, Microsoft Intune will deprecate support for the Windows 8 Company Portal. Microsoft Intune will also deprecate support for the Windows Phone 8 and Windows RT platforms. As a consequence, you will not be able to enroll or update any Windows Phone 8 or Windows RT devices.

You can continue to manage Windows Phone 8, Windows RT  and Windows 8 devices that are already enrolled. Update Windows Phone 8 and Windows 8 devices to Windows 8.1 and Windows Phone 8.1, and use the corresponding Windows 8.1 and Windows Phone 8.1 Company Portal apps to continue distributing apps to these devices without disruptions.

Starting in November 2016, we will deprecate support for the Windows Phone 8 Company Portal.
<!--TFS 1255391-->

### What's coming

__New Microsoft Intune Company Portal available for Windows 10 devices__
Microsoft is releasing a new Microsoft Intune Company Portal for Windows 10 devices. This app, which leverages the new Windows 10 Universal format, will provide the user with an updated user experience within the app and identical experiences across all Windows 10 devices, PC and Mobile alike, while still enabling all the same functionality that they are using today.

The new app will also allow users to leverage additional platform features like single sign-on (SSO) and certificate-based authentication on Windows 10 devices. The app will be made available as an upgrade to the existing Windows 8.1 Company Portal and Windows Phone 8.1 Company Portal installs from the Windows Store. For more details, go to [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp).
<!--TFS 1016502-->

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

<p style="margin-left: 40px">http://www.github.com/msintuneappsdk/intune-app-wrapper-ios-preview

<p style="margin-left: 40px">http://www.github.com/msintuneappsdk/intune-app-wrapper-android-preview

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

__Android__

<p style="margin-left: 40px">**Addition of "Notifications" to the Company Portal for Android**<br/>
<p style="margin-left: 40px">A new Notifications icon has been added to the Company Portal for Android on the homepage. Tapping this icon accesses the Notifications page, which shows your end users all items that require attention in the Company Portal app, such as device noncompliance, enrollment update, and enrollment activation. The iOS Company Portal app already has this notifications experience. Having the new Notifications page means that user won’t see the Company Access Setup page every time they launch or resume the Company Portal as long as the device is already enrolled. If you create your own end-user guidance, you might want to update your documentation to reflect this change. Find updated screenshots [here](https://aka.ms/androidcpupdate).  

__iOS__
<p style="margin-left: 40px">**Changes in support for the iOS Company Portal app**<br/>
<p style="margin-left: 40px">All users of the Microsoft Intune Company Portal app for iOS are now required to use its latest version. New users are able to download only the latest version, and current users are required to update to it. The latest version requires iOS 8.0 or later, so devices running older iOS versions cannot use the Company Portal or enroll until they update their device to iOS 8.0 or later and then update the Company Portal app to the latest version. Enrolled devices running versions below iOS 8.0 will continue to be managed and listed in the Intune Admin Console.
<!---TFS 1283165--->

<p style="margin-left: 40px">**Improvements in how iOS end users get their apps**<br/>
<p style="margin-left: 40px">The following changes have been made to the apps tiles in the Company Portal app for iOS to point users to different views in a single location, the Company Portal website, for all of their apps. Apple restrictions prohibit line-of-business and managed app store apps from being listed in the Company Portal app, and require users to visit different views to find all of their apps.

<p style="margin-left: 40px">The **Company Apps** tile previously pointed to a list of all apps in the ALL tab of the Company Portal website, and it will continue to work the same way. The tile name has changed to **All Apps**.

<p style="margin-left: 40px">The **Other Apps** tile previously pointed to a view, inside the Company Portal app, that lists all apps that Apple permits the Company Portal app to show. The tile name has changed to **Featured Apps**, and tapping the tile will take users to the FEATURED tab of the Company Portal website.

<p style="margin-left: 40px">The **Categories** tile previously pointed to a view, inside the Company Portal app, that lists categories of apps. The tile name has not changed, but it now points to the CATEGORIES tab of the Company Portal website. You can find updated screenshots [here](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186).
  <!---TFS 1317133--->

<p style="margin-left: 40px">**Prompt to install the iOS Managed Browser app if IT Pro sets that requirement for an app**<br/>
<p style="margin-left: 40px">If you have configured a web clip to open only in the managed browser, and the managed browser is not installed on a device, the Company Portal app on the device will prompt the user to install the managed browser before the web clip can be installed.
  <!---TFS 1228570--->

__Windows__
<p style="margin-left: 40px">**Feedback button added to Windows Phone 8.1 Company Portal app**<br/>
<p style="margin-left: 40px">The Windows Phone 8.1 Company Portal app enables end users to send feedback about the app by using a new "send feedback" button. To find the button, users tap the “three dots” menu at the bottom right of the Company Portal app screen and then tap **send feedback**. The collected, anonymized feedback will help Microsoft improve the Company Portal app experience for users.
<!---TFS 1317806--->

### Intune glossary</br>
We’ve added a new [glossary topic](https://docs.microsoft.com/intune/understand-explore/intune-glossary) to the library to help you understand some of the terms used in the Intune product.

## August 2016
### App management
<!---@Barry, I created the buckets of App management, Device management, etc but am not tied to them. Just wanted to break up and organize the feature list. If you're going to take over the Company Portal section, please talk to Stacie about how she's been organizing it. --->

__Hidden and shown apps for iOS 9.3__
For devices running iOS 9.3 or later, you can use the hidden and shown apps list in the iOS general configuration policy to:
- Specify a list of apps that will be hidden from users. Users cannot view, or launch these apps.
- Specify a list of apps that users can view and launch. No other apps can be viewed or launched.

The apps you can specify include both apps you have deployed, and the built-in iOS apps like Messages and Notes. For details, see [iOS policy settings in Microsoft Intune]( https://docs.microsoft.com/intune/deploy-use/ios-policy-settings-in-microsoft-intune)
<!---TFS 1279009 checked--->
__Allowed and blocked apps policy for Samsung KNOX devices__
You can now configure a custom policy for Samsung KNOX devices that lets you create one of the following:
- A list of apps that are blocked from running on the device. Even if installed, an app defined in the blocked list cannot be activated on the device.
- A list of apps that users of the device are allowed to install from the Google Play store. No other apps can be installed from the store.

These settings can only be used by devices that run Samsung KNOX.
For details, see [Use custom policies to allow and block apps for Samsung KNOX devices]( custom-policy-to-allow-and-block-samsung-knox-apps.md).
<!---TFS 1311629 checked --->
__New apps compatible with mobile application management (MAM) policies__
The Yammer app for [iOS](https://itunes.apple.com/app/yammer/id289559439?mt=8) and [Android](https://play.google.com/store/apps/details?id=com.yammer.v1) is now compatible with [Intune mobile application management (MAM) policies](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune), whether or not the device is enrolled.

For a full list of MAM compatible apps, see the [Microsoft Intune application partners](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners) site.
<!--- TFS 1252335 & 1252336 checked--->


<!--- I started putting TFS numbers in the What's Coming topic and found it helpful when updating the What's New. Up to you if you want to continue. --->

__Intune Viewer apps__
With the release of the new RMS sharing app, we are removing the following Intune Viewer apps, beginning in August, 2016:
- Intune AV Viewer
- Intune PDF Viewer
- Intune Image Viewer for Android from Google Play

Instead of using the Intune Viewer apps, we recommend using the new [Rights Management app (RMS sharing) for Android](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app), which allows you to deploy one app instead of three separate apps to securely view corporate files on Android devices. When the Intune viewer app is no longer supported, it will be removed from the Google Store and will not be available for future use.

### Device management
__Android 7.0 support__
Intune provides “day 0” support for the forthcoming Android 7.0 operating system for mobile devices.
<!---TFS 1262053--->
### Google removal of remote passcode reset capability on Android 7.0 devices
Google is removing the ability of IT administrators and end users to remotely reset the passcode of Android 7.0 devices. Previously, IT administrators could remotely reset a user’s passcode, and end users could reset their passcodes from the Company Portal website.



### Company Portal updates
__Company Portal website__
- **Feedback link from the Company Portal to Microsoft** <br/>
The Company Portal website enables end users to tap a new "Feedback" link, at the bottom of the page, to send feedback to Microsoft about their experience with the site. The collected, anonymized feedback will help Microsoft improve the Company Portal website experience for users.
<!--- TFS 1313657 checked--->

__iOS__
- **Minimum iOS Managed Browser version updated to 8.0**<br/>
The Microsoft Intune Managed Browser app for iOS has been updated to support devices running iOS 8.0 or later. While iOS 7.1 devices can still use the existing Managed Browser app, encourage your users to update to iOS 8.0 or later to access and take full advantage of new Managed Browser features.  
<!---TFS 1313253 checked--->

### What's coming
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

### Service deprecation
<!---@Barry, we started listing service deprecations earlier this summer. --->
- **Changes in support for the iOS Company Portal app**<br/>
In September, all users of the Microsoft Intune Company Portal app for iOS will be required to use its latest version. New users will only be able to download the latest version and current users will be required to update to it. The latest version requires iOS 8.0 or later, so devices running older iOS versions won’t be able to use the Company Portal or enroll until they update their device to iOS 8.0 or later and then update the Company Portal app to the latest version. Enrolled devices running versions below iOS 8.0 will continue to be managed and listed in the Intune Admin Console.  

- **Minimum iOS Managed Browser version updated to 8.0**<br/>
In August, Intune will release an updated Microsoft Intune Managed Browser app for iOS that will only support devices running iOS 8.0 or later. While iOS 7.1 devices will still be able to use the existing Managed Browser app, please encourage your users to update to iOS 8.0 or later to access and take full advantage of new Managed Browser features.  
<!---TFS 1313253--->

- **Company Portal apps for Windows 8 and Windows Phone 8 are being deprecated from September 2016** <br/>
Starting in September 2016, Microsoft Intune will end support for the Microsoft Intune Company Portal apps for Windows Phone 8 and Windows 8 platforms. Update devices to Windows 8.1 and Windows Phone 8.1 and use the corresponding Windows 8.1 and Windows Phone 8.1 Company Portal apps to continue distributing apps to these devices.
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

### See also
See [What’s New in Microsoft Intune](whats-new-in-microsoft-intune.md) for details on recent developments.
