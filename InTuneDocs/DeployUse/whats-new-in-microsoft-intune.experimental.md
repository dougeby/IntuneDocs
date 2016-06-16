---
# required metadata

experiment_id: lindavr-abtest-20160527
title: What's new | Microsoft Intune
description:
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
The following are new in this release. Except for the Windows Defender policy setting update, all of these features are also supported for hybrid customers' deployments (Configuration Manager with Intune). For more information about new hybrid features, check out our [hybrid What’s New page](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).

## June 2016
### Intune service health
Service health information for Intune has been moved to a central location with other Microsoft services. You'll now find this information in the Office 365 management portal under Service Health. For more information, see [this blog post](https://blogs.technet.microsoft.com/enterprisemobility/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).

## App management
- **Enhanced Windows 10 enterprise data policy configuration experience.** We have made enhancements to the Windows 10 enterprise data protection policy configuration experience around creating app rules, specifying network boundary definition, and other enterprise data protection settings. To learn more, see [Create an enterprise data protection (EDP) policy using Microsoft Intune](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune).


## Device management
- **Windows Defender policy setting to protect against potentially unwanted apps.** A new Windows Defender setting named **Potentially Unwanted Application Detection** has been added to the general configuration policy for Windows 10 Desktop and Mobile. You can use this setting to protect enrolled Windows desktop computers against running software classed by Windows Defender as potentially unwanted. You can protect against these applications running, or use audit mode to report when a potentially unwanted application is installed. See [Windows 10 policy settings in Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune) for more information.
<!---TFS 1244478--->

## Conditional access
- **Cisco ISE network access control policy for Intune.**  Customers who use the Cisco Identity Service Engine (ISE) 2.1 and also use Microsoft Intune can set a network access control policy in ISE.

	Using this policy, devices that need to connect to the network using WiFi or VPN must meet following conditions before they are allowed access:

	* Must be managed by Intune
	* Must be compliant with any deployed Intune compliance policies

 End users of noncompliant devices will be prompted to enroll, and remediate any compliance issues to gain access.
- **Conditional access for browser.** You can set a conditional access policy for [Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md) and [SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md) so that they can only be accessed from supported web browsers on managed and compliant iOS and Android devices. End users who try to sign in to Outlook Web Access (OWA) and SharePoint sites with iOS and Android devices will be prompted to enroll their device with Intune as well as to fix any non-compliance issues before they can complete sign-in.
<!---TFS 1175844--->

- **Dynamics CRM Online supports conditional access.** You can set a conditional access policy for [Dynamics CRM Online](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md) so that it can only be accessed by managed and compliant iOS and Android devices. End users who try to sign in to the Dynamics CRM mobile app on iOS and Android will be prompted to enroll with Intune as well as remediate any non-compliance issues before sign-in can complete.
<!---TFS1295358--->


## Company Portal updates

### Android Company Portal app

- When IT administrators apply the new "Require that devices disallow installation of apps from unknown sources (Android 4.0+)" policy, end users with Android 4.0 or later devices will see the message, "Installation from Unknown sources must be disabled." Users will need to go to  **Settings** > **Security**, and turn off **Unknown sources**. A link in the compliance message lets users get more [information](/Intune/EndUser/you-are-asked-to-turn-off-unknown-sources-android) about the message and why they are being required to turn off the setting.

- When IT administrators apply the new "Require that devices have enabled scanning of apps for security threats (Android 4.0+)" policy, end users with Android 4.0 or later devices will see the message, "Scan device for security threats." Users will need to go to **Settings** > **Google** > **Security**, and turn on **Scan device for security threats**. A link in the compliance message lets users get more [information](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) about the message and why they are being required to turn on the setting.

- When IT administrators apply the new "Require that USB debugging is disabled (Android 4.2+)" policy, end users with Android 4.2 or later devices will see the message, "USB debugging must be disabled." Users will need to go to **Settings** > **Developer options**, and turn off **USB debugging**." A link in the compliance message lets users get more [information](/Intune/EndUser/you-are-asked-to-turn-off-usb-debugging-android) about the message and why they are being required to turn off the setting.

- When IT administrators apply the new "Minimum Android security patch level (Android 6.0+)" policy, end users with Android 6.0 or later devices will see the message, "This device does not meet the minimum Android security patch level." Users will need to install the required security patch. A link in the compliance message lets users get [information](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) about how to install the required security patch and to see which security patch they currently have installed.

### iOS Company Portal app

- When end users are installing line-of-business apps, they will now see an improved app installation experience. If the app installation is taking a long time, users can manually sync their device to force the sync process to resume. To review the end-user instructions, see [Sync your iOS device manually](/Intune/EndUser/sync-your-device-manually-ios.md).

- The Microsoft Intune Company Portal app for iOS has been updated to support iOS version 8.0 and later. This update means that end users can install the Company Portal app and enroll new devices in Intune only if the device is running iOS version 8.0 or later. Users who have already enrolled devices that are running on an unsupported version of iOS can continue to use the Company Portal app that is on their device.


## What's coming

### Cloud roadmap
Keep informed about upcoming developments for Intune with the [Cloud Platform roadmap](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune).

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



## Previous Intune releases
If you want to see what's released in Intune during the last six months, they are listed in the [Previous Intune releases](previous-intune-releases.md) article.
> [!div class="op_single_selector"]
- [April 2016](previous-intune-releases.md)
- [March 2016](previous-intune-releases.md)
- [February 2016](previous-intune-releases.md)
- [January 2016](previous-intune-releases.md)
- [December 2015](previous-intune-releases.md)
- [November 2015](previous-intune-releases.md)




### See also
* [Microsoft Intune Blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Cloud Platform roadmap](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
