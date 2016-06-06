---
# required metadata

experiment_id: lindavr-abtest-20160527
experimental: true
title: What's new | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# What's new in Microsoft Intune


## June 2016

### Company portal updates

#### iOS Company Portal app

- When end users are installing line-of-business apps, they will now see an improved app installation experience. If the app installation is taking a long time, users can manually sync their device to force the sync process to resume. To review the end-user instructions, see [Sync your iOS device manually](/Intune/EndUser/sync-your-device-manually-ios.md).

- The Microsoft Intune Company Portal app for iOS has been updated to support iOS version 8.0 and later. This update means that end users can install the Company Portal app and enroll new devices in Intune only if the device is running iOS version 8.0 or later. Users who have already enrolled devices that are running on an unsupported version of iOS can continue to use the Company Portal app that is on their device.

## May 2016


With the exception of TeamViewer integration, all of these features are also supported for hybrid deployments (Configuration Manager with Intune). For more information about new hybrid features, check out the [Hybrid What’s New](https://technet.microsoft.com/en-us/library/mt718155.aspx) page.

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

### Device management

- **Remote assistance sessions for Windows PCs.** TeamViewer integration for Windows PCs managed by the Intune client software will let you establish remote assistance sessions with Windows PCs to support your help desk department. Supported PCs include Windows 7, 8, 8.1 and Windows 10.
For details, see [Common Windows PC management tasks with the Microsoft Intune computer client](/intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client#respond-to-a-remote-assistance-request)

### Company Portal updates

#### Android Company Portal app

- **End user toast notifications**: End users will now see toast notifications from the Android Company Portal app when they are enrolling their devices or removing their devices from the Company Portal.

- **Changes to Device Enrollment Managers accounts in the Android Company Portal app.** To improve performance and scale, Intune is no longer showing all Device Enrollment Managers (DEM) devices in the My Devices pane of the Android Company Portal app. Only the local device running the app is displayed, and only if it is enrolled via the Company Portal app. The DEM user may perform actions on the local device, but remote management of other enrolled devices can only be performed from the Intune admin console.

#### Company Portal website

- **Company Portal website: Device identification banner will provide more information to end users.** End users can now more easily identify the device they’ve selected when they are using the Company Portal website. If the wrong device is selected, they will be able to select the correct device by tapping the **Tap here** link in the home page banner.


## What's coming

- **Message center UI onboarding**. As part of the migration of Intune into the [Office 365 Management portal](https://portal.office.com/), we will begin taking advantage of their Message Center to communicate new features and other notifications. Also, by installing the companion Office 365 Admin mobile app, you can receive notifications on your mobile phone and easily forward any messages to users or a distribution alias.
We will begin using the Message Center with our May release to notify you when updates are completed and will include information on new and improved Intune features. Check out the Message Center today by logging into the [Office 365 Management portal](https://portal.office.com/) and choosing the MESSAGE CENTER option in the left navigation pane.

- **Changes to Device Enrollment Managers accounts**. To improve performance and scale, Intune is no longer showing **all** Device Enrollment Managers (DEM) devices in the **My Devices** pane of the iOS Company Portal app. Only the local device running the app is displayed, and only if it is enrolled via the Company Portal app. The DEM user may perform actions on the local device, but remote management of other enrolled devices can only be performed from the Intune admin console. Additionally, Intune is deprecating use of DEM accounts with either the Apple Device Enrollment Program or the Apple Configurator tool. Both these enrollment methods already support user-less enrollment for shared iOS devices. Only use DEM accounts when user-less enrollment for shared devices is unavailable.

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



### See also
* [Microsoft Intune Blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Cloud Platform roadmap](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
