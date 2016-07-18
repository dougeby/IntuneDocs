---
# required metadata

title: What's new | Microsoft Intune
description: Find out what’s new in this month’s, and past releases of Microsoft Intune
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 06/16/2016
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

### Xamarin support
The Microsoft Intune app SDK supports Xamarin apps in these scenarios:

- Writing new apps, or modifying the code of existing line of business apps using the Intune SDK. You will be able to get the plugin on the [Microsoft Intune Github](https://github.com/msintuneappsdk) page.
- Adding MAM support to existing line of business apps using the Intune app wrapping tool

For help choosing which method to use, see [Decide how to prepare apps for mobile application management with Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune).

<!--- TFS 1061478 & TFS 1152340--->

## Device management
### Increased device enrollment limits
Intune increased the maximum configurable device enrollment limit from 5 to 15 devices per user.
<!---TFS 1289896 --->

## Company Portal updates
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

- **Minimum iOS Managed Browser version is being updated to 8.0**<br/>
In August, Intune will release an updated Microsoft Intune Managed Browser app for iOS that will only support devices running iOS 8.0 or later. While iOS 7.1 devices will still be able to use the existing Managed Browser app, please encourage your users to update to iOS 8.0 or later to access and take full advantage of new Managed Browser features.  
<!---TFS 1313253--->

### Cloud roadmap
Keep informed about upcoming developments for Intune with the [Cloud Platform roadmap](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune).

### Service deprecation
- **Company Portal apps for Windows 8 and Windows Phone 8 are being deprecated from Sept, 2016.** <br/>
Starting in Sept 2016, Microsoft Intune will end support for the Microsoft Intune Company Portal apps for Windows Phone 8 and Windows 8 platforms. Update devices to Windows 8.1 and Windows Phone 8.1 and use the corresponding Windows 8.1 and Windows Phone 8.1 Company Portal apps to continue distributing apps to these devices.
<!---TFS 1255391--->

- **Intune Viewer apps.** <br/>
With the release of the new RMS sharing app, we are removing the following Intune Viewer apps, beginning August, 2016:
	- Intune AV Viewer
	- Intune PDF Viewer
	- Intune Image Viewer for Android from Google Play

  Instead of using the Intune Viewer apps, we recommend using the new [Rights Management app (RMS sharing) for Android](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app), which allows you to deploy one app instead of three separate apps to securely view corporate files on Android devices. When the Intune viewer app is no longer supported, it will be removed from the Google Store and will not be available for future use.

- **Custom Group Targeting of Notification Rules Removal.**<br/>
Intune notification rules define who an email alert will be sent to from Intune. Currently, you can configure notification rules to send emails to all users of devices in an Intune device group that you created. From around June 1st 2016 moving forward, targeting user-created groups will no longer be supported.

	Today, to target a notification rule to a group you created from the Microsoft Intune administration console, you would take the following steps:

	In the **Admin** workspace, click **Notification Rules** > **Create New Rule**

	In step two of the Create Notification Rule Wizard, select the device groups which the rule will target. This step, “select device groups”, is being removed from the Intune Console.

	The preliminary timeline for this change is as follows:
	- In August, 2016, new tenants will not see step two of the Create Notification Rule Wizard. Exiting tenants are unaffected.
	- Around September, 2016, some existing tenants will not see the “select device groups” in the wizard.
	- Around November, 2016, we expect that all tenants will not see the “select device groups” in the wizard.

## Previous Intune releases
If you want to see what's released in Intune during the last six months, they are listed in the [Previous Intune releases](previous-intune-releases.md) article.

### See also
* [Microsoft Intune Blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Cloud Platform roadmap](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
