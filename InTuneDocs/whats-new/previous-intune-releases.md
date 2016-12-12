---
# required metadata

title: Previous releases | Microsoft Docs
description:
keywords:
author: barlanmsftms.author: barlan
manager: angrobe
ms.date: 12/05/2016
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

This page is a list of announcements made in [What’s New in Microsoft Intune](whats-new-in-microsoft-intune.md).

[!INCLUDE[wit_nextref](../includes/whats-new-last-six-months.md)]

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
