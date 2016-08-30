---
# required metadata

title: What's new | Microsoft Intune
description: Find out what’s new in this month’s, and past releases of Microsoft Intune
keywords:
author: Lindavr
manager: angrobe
ms.date: 08/10/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mamoriss
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# What's new in Microsoft Intune
Learn what’s new in this release of Microsoft Intune. You can also find out about upcoming changes that you should be planning for, as well as information about past releases.

All of these features will eventually be supported for hybrid customers' deployments (Configuration Manager with Intune). For more information about new hybrid features, check out our [hybrid What’s New page](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).
<!---@Barry, the above blurb stays in each version, but make sure Tyler signs off each time. Also, remember to set the ms.date in the metadata to the sprint release. --->

>[!IMPORTANT] 
>Blog post - Ensuring mobile devices are up to date using Microsoft Intune<br>
>In light of the recent "Trident" malware attacks on iOS devices, we've published a new blog post, [Ensuring mobile devices are up to date using Microsoft Intune](https://blogs.technet.microsoft.com/enterprisemobility/2016/08/26/ensuring-mobile-devices-are-up-to-date-using-microsoft-intune/) to help you learn about the different ways that Intune can help keep your devices secure and up to date.


## August 2016
## App management
<!---@Barry, I created the buckets of App management, Device management, etc but am not tied to them. Just wanted to break up and organize the feature list. If you're going to take over the Company Portal section, please talk to Stacie about how she's been organizing it. --->

### Hidden and shown apps for iOS 9.3
For supervised devices running iOS 9.3 or later, you can use the hidden and shown apps list in the iOS general configuration policy to:
- Specify a list of apps that will be hidden from users. Users cannot view, or launch these apps.
- Specify a list of apps that users can view and launch. No other apps can be viewed or launched.

The apps you can specify include both apps you have deployed, and the built-in iOS apps like Messages and Notes. For details, see [iOS policy settings in Microsoft Intune]( https://docs.microsoft.com/intune/deploy-use/ios-policy-settings-in-microsoft-intune)
<!---TFS 1279009 checked--->
### Allowed and blocked apps policy for Samsung KNOX devices
You can now configure a custom policy for Samsung KNOX devices that lets you create one of the following:
- A list of apps that are blocked from running on the device. Even if installed, an app defined in the blocked list cannot be activated on the device.
- A list of apps that users of the device are allowed to install from the Google Play store. No other apps can be installed from the store.

These settings can only be used by devices that run Samsung KNOX.
For details, see [Use custom policies to allow and block apps for Samsung KNOX devices]( custom-policy-to-allow-and-block-samsung-knox-apps.md).
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

Instead of using the Intune Viewer apps, we recommend using the new [Rights Management app (RMS sharing) for Android](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app), which allows you to deploy one app instead of three separate apps to securely view corporate files on Android devices. When the Intune viewer app is no longer supported, it will be removed from the Google Store and will not be available for future use.

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

## What's coming
### Intune Groups transitioning to Azure Active Directory Groups beginning in September 2016
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

### Addition of 'Notifications' to the Company Portal for Android
We are releasing an update to the Company Portal for Android in September that will introduce a new **Notifications** icon on the homepage. Tapping this icon will access the **Notifications** page that will show your end user all the items that require attention in the Company Portal app such as device non-compliance, enrollment update, and enrollment activation. If you also use the iOS Company Portal app, you’ll already see the notifications experience. With the introduction of the **Notifications** page, you will not see the **Company Access Setup** page every time you launch or resume the Company Portal for Android as long as the device is already enrolled. We hear many of you have created end-user guidance and appreciate advanced notice when your guidance/screen shots may need updating. Please update your documentation to reflect the upcoming change in experience. Find updated screenshots here: https://aka.ms/androidcpupdate.  

### Improvements in how iOS end users get their apps
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



## Previous Intune releases
If you want to see what's released in Intune during the last six months, they are listed in the [Previous Intune releases](previous-intune-releases.md) article.

### See also
* [Microsoft Intune Blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Cloud Platform roadmap](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
