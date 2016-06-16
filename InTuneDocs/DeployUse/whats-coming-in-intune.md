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

ROBOTS: noindex,nofollow
#audience:
#ms.devlang:
ms.reviewer: mamoriss
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# What's coming in Microsoft Intune
This information is provided under NDA on an extremely limited basis and is subject to change. Some features listed here are at risk of not making the cutoff dates and may be delayed until a future release. Other features are being tested in a pilot (flighting) to ensure they're customer-ready. Please reach out to your Intune/PM buddy if you have any questions or concerns.

This page is updated periodically. Check back for new What’s Coming updates.

The following changes are under development for Intune. All of these features will also be supported for hybrid customers deployments (Configuration Manager with Intune). For more information about new hybrid features, check out our [hybrid What’s New page](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).


## App management
- **Enhanced Windows 10 enterprise data policy configuration experience.** We have made enhancements to the Win 10 enterprise data protection policy configuration experience around creating app rules, specifying network boundary definition, and other enterprise data protection settings.
<!---TFS 1303011--->

- **Conditional access for browser.** You will be able to set a conditional access policy for Exchange Online and SharePoint Online so that they can only be accessed by managed and compliant iOS and Android devices. End users who try to sign in to Outlook Web Access (OWA) and SharePoint sites with iOS and Android devices will be prompted to enroll their device with Intune as well as to fix any non-compliance issues before they can complete sign-in.
<!---TFS 1175844--->

- **Dynamics CRM Online supports conditional access.** Customers will be able to set a conditional access policy for Dynamics CRM Online so that it can only be accessed by managed and compliant iOS and Android devices. End users who try to sign in to the Dynamics CRM mobile app on iOS and Android will be prompted to enroll with Intune as well as remediate any non-compliance issues before sign-in can complete.
<!---TFS1295358--->

### Xamarin support
The Microsoft Intune app SDK will support Xamarin apps in these scenarios:

- Writing new apps, or modifying the code of existing line of business apps using the Intune SDK. You will be able to get the plugin on the [Microsoft Intune Github](https://github.com/msintuneappsdk) page.
- Adding MAM support to existing line of business apps using the Intune app wrapping tool

For help choosing which method to use, see [Decide how to prepare apps for mobile application management with Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune).
<!--- TFS 1061478 & TFS 1152340--->

## Device management
- **Windows Defender policy setting to protect against potentially unwanted apps.** A new Windows Defender setting named **Potentially Unwanted Application Detection** has been added to the general configuration policy for Windows 10 Desktop and Mobile. You can use this setting to protect enrolled Windows desktop computers against running software classed by Windows Defender as potentially unwanted. You can protect against these applications running, or use audit mode to report when a potentially unwanted application is installed.
<!---TFS 1244478--->

## Conditional access
**Cisco ISE network access control policy for Intune.**  Customers who use the Cisco Identity Service Engine (ISE) 2.1 and also use Microsoft Intune can set a network access control policy in ISE.

Using this policy, devices that need to connect to the network using WiFi or VPN must meet following conditions before they are allowed access:

* Must be managed by Intune
* Must be compliant with any deployed Intune compliance policies

End users of noncompliant devices will be prompted to enroll, and remediate any compliance issues to gain access.
<!---TFS 1299144--->

## Company Portal
**Changes to Device Enrollment Managers accounts in the iOS Company Portal app.** To improve performance and scale, Intune will no longer show all Device Enrollment Managers (DEM) devices in the My Devices pane of the iOS Company Portal app. Only the local device running the app will be displayed, and only if it is enrolled via the Company Portal app. The DEM user may perform actions on the local device, but remote management of other enrolled devices will only be performed from the Intune admin console.  Additionally, Intune is deprecating use of DEM accounts with either the Apple Device Enrollment Program or the Apple Configurator tool. Both these enrollment methods already support user-less enrollment for shared iOS devices. Only use DEM accounts when user-less enrollment for shared devices is unavailable.
<!---TFS 1233681--->

## Service deprecation
**Company Portal apps for Windows 8 and Windows Phone 8 are being deprecated from Sept, 2016.** Starting in Sept 2016, Microsoft Intune will end support for the Microsoft Intune Company Portal apps for Windows Phone 8 and Windows 8 platforms. Update devices to Windows 8.1 and Windows Phone 8.1 and use the corresponding Windows 8.1 and Windows Phone 8.1 Company Portal apps to continue distributing apps to these devices.
<!---TFS 1255391--->

**Custom Group Targeting of Notification Rules Removal.**
Intune notification rules define who an email alert will be sent to from Intune. Currently, you can configure notification rules to send emails to all users of devices in an Intune device group that you created. From around June 1st 2016 moving forward, targeting user-created groups will no longer be supported.

The preliminary timeline for this change is as follows:
- In June, 2016, new tenants will not see step two of the Create Notification Rule Wizard. Exiting tenants are unaffected.
- Around August, 2016, some existing tenants will not see the “select device groups” in the wizard.
- Around October, 2016, we expect that all tenants will not see the “select device groups” in the wizard.
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
