---
# required metadata

title: What's coming | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 06/10/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d

# optional metadata

ROBOTS: NOINDEX,NOFOLLOW
#audience:
#ms.devlang:
ms.reviewer: mamoriss
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# What's coming in Microsoft Intune - July
This information is provided under NDA on an extremely limited basis and is subject to change. Some features listed here are at risk of not making the cutoff dates and may be delayed until a future release. Other features are being tested in a pilot (flighting) to ensure they're customer-ready. Please reach out to your Intune/PM buddy if you have any questions or concerns.

This page is updated periodically. Check back for new What’s Coming updates.

The following changes are under development for Intune. All of these features will also be supported for hybrid customers deployments (Configuration Manager with Intune). For more information about new hybrid features, check out our [hybrid What’s New page](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).

<!--- New stuff
- 1280247 Rob. Done
- 1252335 Karthika. 1608
- 1252336 Karthika. 1608
- 1061478 Karthika. Done
- 1289896 Barnett. Done
- 1295328 Bigman. Still in list. Confirmed for 1607 WC; waiting on blurb
- 1295330 Bigman. Still in list. Confirmed for 1607 WC; waiting on blurb
- 1228570 Rob. 1608
- 1284856 Rob. 1608
- 1290248 Stacie. OOB
- 1142641 Closed. Dupe. Already shipped
- 1199558 Stacie? Waiting on
- 1299082 Stacie? Waiting on --->

## Group management
- **Intune Groups transitioning to Azure Active Directory Groups.** Waiting on blurb

## App management
- **Improve the app provisioning profile update experience.** <br/>Apple iOS line of business mobile apps are built with a provisioning profile included and code signed with a certificate. When the app is run on an iOS device, iOS confirms the integrity of the iOS app and enforces policies defined by the provisioning profile.<br/>
The enterprise signing certificate you use to sign apps typically lasts for 3 years. However, the provisioning profile expires after 1 year. With this update, Intune will provide you the tools to proactively deploy a new provisioning profile policy to devices that have apps that are near expiry while the certificate is still valid.
<!--- TFS 1280247--->

### Xamarin support
The Microsoft Intune app SDK will support Xamarin apps in these scenarios:

- Writing new apps, or modifying the code of existing line of business apps using the Intune SDK. You will be able to get the plugin on the [Microsoft Intune Github](https://github.com/msintuneappsdk) page.
- Adding MAM support to existing line of business apps using the Intune app wrapping tool

For help choosing which method to use, see [Decide how to prepare apps for mobile application management with Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune).

<!--- TFS 1061478 & TFS 1152340--->

## Device management

- **Increased device enrollment limits.** <br/>Intune will increase the maximum configurable device enrollment limit from 5 to 15 devices per user.
<!---TFS 1289896 --->



## Company Portal
**Changes to Device Enrollment Managers accounts in the iOS Company Portal app.** To improve performance and scale, Intune will no longer show all Device Enrollment Managers (DEM) devices in the My Devices pane of the iOS Company Portal app. Only the local device running the app will be displayed, and only if it is enrolled via the Company Portal app. The DEM user may perform actions on the local device, but remote management of other enrolled devices will only be performed from the Intune admin console.  Additionally, Intune is deprecating use of DEM accounts with either the Apple Device Enrollment Program or the Apple Configurator tool. Both these enrollment methods already support user-less enrollment for shared iOS devices. Only use DEM accounts when user-less enrollment for shared devices is unavailable.
<!---TFS 1233681--->

## Service deprecation
**Company Portal apps for Windows 8 and Windows Phone 8 are being deprecated from Sept, 2016.** Starting in Sept 2016, Microsoft Intune will end support for the Microsoft Intune Company Portal apps for Windows Phone 8 and Windows 8 platforms. Update devices to Windows 8.1 and Windows Phone 8.1 and use the corresponding Windows 8.1 and Windows Phone 8.1 Company Portal apps to continue distributing apps to these devices.
<!---TFS 1255391--->

**Custom Group Targeting of Notification Rules Removal.**
Intune notification rules define who an email alert will be sent to from Intune. Currently, you can configure notification rules to send emails to all users of devices in an Intune device group that you created. From around June 1st 2016 moving forward, targeting user-created groups will no longer be supported.

The preliminary timeline for this change is as follows:
- In August, 2016, new tenants will not see step two of the Create Notification Rule Wizard. Exiting tenants are unaffected.
- Around September, 2016, some existing tenants will not see the “select device groups” in the wizard.
- Around November, 2016, we expect that all tenants will not see the “select device groups” in the wizard.
<!---	TFS 1278864--->

**Changes in support for the iOS Company Portal app.**
In July, all users of the Microsoft Intune Company Portal app for iOS will be required to use its latest version. New users will only be able to download the latest version and current users will be required to update to it. The latest version requires iOS 8.0 or later, so devices running older iOS versions won’t be able to use the Company Portal or enroll until they update their device to iOS 8.0 or later and then update the Company Portal app to the latest version. Enrolled devices running versions below iOS 8.0 will continue to be managed and listed in the Intune Admin Console.  

**Intune Viewer apps.** With the release of the new RMS sharing app, we are removing the following Intune Viewer apps, beginning August, 2016:
- Intune AV Viewer
- Intune PDF Viewer
- Intune Image Viewer for Android from Google Play

Instead of using the Intune Viewer apps, we recommend using the new Rights Management app (RMS sharing) for Android, which allows you to deploy one app instead of three separate apps to securely view corporate files on Android devices. Learn more about the RMS sharing app (with link to documentation).


### See also
See [What’s New in Microsoft Intune](whats-new-in-microsoft-intune.md) for  details on recent developments.
