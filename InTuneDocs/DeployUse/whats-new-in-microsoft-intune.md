---
# required metadata

title: What's new | Microsoft Intune
description: Find out what’s new in this month’s, and past releases of Microsoft Intune
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 07/18/2016
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

The following changes are under development for Intune. All of these features will eventually be supported for hybrid customers' deployments (Configuration Manager with Intune). For more information about new hybrid features, check out our [hybrid What’s New page](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).


## July 2016
## App management
### Improve the app provisioning profile update experience
Apple iOS line of business mobile apps are built with a provisioning profile included and code signed with a certificate. When the app runs on an iOS device, iOS confirms the integrity of the iOS app and enforces policies defined by the provisioning profile.

The enterprise signing certificate you use to sign apps typically lasts for 3 years. However, the provisioning profile expires after 1 year. With this update, Intune gives you the tools to proactively deploy a new provisioning profile policy to devices that have apps that are near expiry while the certificate is still valid. For more information, see [Use iOS mobile provisioning profile policies to keep your line of business apps up to date](/intune/deploy-use/ios-mobile-app-provisioning-profiles).
<!--- TFS 1280247--->

## Device management
### Increased device enrollment limits
Intune increased the maximum configurable device enrollment limit from 5 to 15 devices per user.
<!---TFS 1289896 --->



## Company Portal updates
### Company Portal website
- **Improved end-user experience when enrolling Windows devices**<br/>
When you are using conditional access, the enrollment steps for Windows 8.1, Windows 10 Desktop, and Windows 10 Mobile have been clarified in the Company Portal website. Users will now see separate “Device enrollment” and “Workplace Join” steps, making it easier for them to see the status of their device and to complete the process if they experience a Workplace Join (WPJ) failure. The separate steps are also expected to simplify the troubleshooting process for IT administrators. Previously, when end users tried to enroll and all enrollment steps succeeded except for WPJ, the enrolled device would not appear on the list of devices for users to identify, causing confusion for users.

### Android
- **Android Company Portal app**<br/>
If Android end users see an error message that says their device is missing a required certificate, they can tap a "How to resolve this" button to get [steps](/intune/enduser/your-device-is-missing-a-required-certificate-android#your-device-is-missing-a-certificate-required-by-your-it-administrator) for installing the missing certificate. If users complete the steps, but see an additional "missing certificate" error message, they are asked to contact their IT administrator and provide this [link](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues), which contains steps that IT administrators can use to fix the certificate issue.

- **Restrict side-loaded app installations to enrolled devices**<br/>
Android devices can no longer install applications through the Company Portal website unless the devices have been enrolled in Intune by using the Intune Company Portal app for Android.
<!---TFS 1299082--->

### iOS
- **Changes to Device Enrollment Managers accounts in the iOS Company Portal app**<br/>
To improve performance and scale, Intune no longer displays all Device Enrollment Managers (DEM) devices in the **My Devices** pane of the iOS Company Portal app. Only the local device running the app is displayed, and only if it is enrolled via the Company Portal app.

	The DEM user may perform actions on the local device, but remote management of other enrolled devices can only be performed from the Intune admin console. Additionally, Intune is deprecating use of DEM accounts with either the Apple Device Enrollment Program or the Apple Configurator tool. Both these enrollment methods already support user-less enrollment for shared iOS devices.

	Only use DEM accounts when user-less enrollment for shared devices is unavailable. For more information, see [Enroll corporate-owned devices with the Device Enrollment Manager in Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).
<!---TFS 1233681--->

## Change of names for Windows features
- [Microsoft Passport for Windows](/intune/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune) is now known as **Windows Hello for Business**.
- [Enterprise data protection](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) is now known as **Windows Information Protection**.

## What's coming
### Intune Groups transitioning to Azure Active Directory Groups beginning in August 2016
Intune is creating a new group management experience that uses Azure Active Directory (AAD) security groups. These Azure AD based security groups can contain both users and devices, and will be used for all group management, policy deployment, and profile deployment when we introduce the new Azure-based Intune admin portal.

This new experience will:
- Free you from having to duplicate groups between services.
- Allow you access to some new Azure Active Directory Premium (AADP) group features.
- Provide extensibility using PowerShell and Graph.
- Unify the group management experience across enterprise mobility management.

To enable the move to Security Groups, the experience in the current admin console will undergo some modifications. These changes, and the use of Azure AD security groups, will be recorded in the Intune documentation.

Customers who are new to Intune will see some of the security group changes before current tenants do.

In addition to changes in group management, the following functionality will be deprecated:
- Excluding members or groups while creating a new group
- **Ungrouped Users** and **Ungrouped Devices** groups
- **Manage Groups** in the Service Admin role
- Custom group-based alerts for Notification Rules
- Pivoting with groups in reports

More information on how these deprecations can be mitigated will be released in August.




### Cloud roadmap
Keep informed about upcoming developments for Intune with the [Cloud Platform roadmap](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune).

### Service deprecation
- **Changes in support for the iOS Company Portal app**<br/>
In July, all users of the Microsoft Intune Company Portal app for iOS will be required to use its latest version. New users will only be able to download the latest version and current users will be required to update to it. The latest version requires iOS 8.0 or later, so devices running older iOS versions won’t be able to use the Company Portal or enroll until they update their device to iOS 8.0 or later and then update the Company Portal app to the latest version. Enrolled devices running versions below iOS 8.0 will continue to be managed and listed in the Intune Admin Console.  

- **Minimum iOS Managed Browser version updated to 8.0**<br/>
In August, Intune will release an updated Microsoft Intune Managed Browser app for iOS that will only support devices running iOS 8.0 or later. While iOS 7.1 devices will still be able to use the existing Managed Browser app, please encourage your users to update to iOS 8.0 or later to access and take full advantage of new Managed Browser features.  
<!---TFS 1313253--->

- **Company Portal apps for Windows 8 and Windows Phone 8 are being deprecated from Sept, 2016** <br/>
Starting in Sept 2016, Microsoft Intune will end support for the Microsoft Intune Company Portal apps for Windows Phone 8 and Windows 8 platforms. Update devices to Windows 8.1 and Windows Phone 8.1 and use the corresponding Windows 8.1 and Windows Phone 8.1 Company Portal apps to continue distributing apps to these devices.
<!---TFS 1255391--->

- **Intune Viewer apps** <br/>
With the release of the new RMS sharing app, we are removing the following Intune Viewer apps, beginning August, 2016:
	- Intune AV Viewer
	- Intune PDF Viewer
	- Intune Image Viewer for Android from Google Play

  Instead of using the Intune Viewer apps, we recommend using the new [Rights Management app (RMS sharing) for Android](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app), which allows you to deploy one app instead of three separate apps to securely view corporate files on Android devices. When the Intune viewer app is no longer supported, it will be removed from the Google Store and will not be available for future use.

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
