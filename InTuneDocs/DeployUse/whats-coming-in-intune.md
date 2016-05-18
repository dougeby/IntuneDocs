---
# required metadata

title: What's coming | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 05/17/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d

# optional metadata

ROBOTS: noindex,nofollow
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# What's coming in Microsoft Intune
This information is provided under NDA on an extremely limited basis and is subject to change. Some features listed here are at risk of not making the cutoff dates and may be delayed until a future release. Other features are being tested in a pilot (flighting) to ensure they're customer-ready. Please reach out to your Intune/PM buddy if you have any questions or concerns.

This page is updated periodically. Check back for new What’s Coming updates.

The following changes are under development for Intune. All of these features will also be supported for hybrid customers deployments (Configuration Manager with Intune). For more information about new hybrid features, check out our [hybrid What’s New page](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).

## Intune communications
- **Intune service health information.** for Intune has been moved to a central location with other Microsoft services. You'll now find this information in the [Office 365 management portal](https://portal.office.com/Admin/Default.aspx) under Service Health. For more information, see [this blog post](https://blogs.technet.microsoft.com/microsoftintune/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).

- **Message center UI onboarding.** As part of the migration of Intune into the [Office 365 Management portal](https://portal.office.com/), we will begin taking advantage of their Message Center to communicate new features and other notifications. Also, by installing the companion Office 365 Admin mobile app, you can receive notifications on your mobile phone and easily forward any messages to users or a distribution alias.
We will begin using the Message Center with our May release to notify you when updates are completed and will include information on new and improved Intune features. Check out the Message Center today by logging into the [Office 365 Management portal](https://portal.office.com/) and choosing the **Message Center** option in the left navigation pane.

## App management
- **New apps available for management with MAM policies.** The Microsoft Word, Excel, and PowerPoint apps for Android can now be associated with MAM policies on devices that are not enrolled with Intune. For a full list of supported apps, go the Microsoft Intune mobile application gallery on the [Microsoft Intune application partners page](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx).

<!--- New feature:
**Rights Management app for Android**
We just released the new Rights Management app for Android (RMS sharing). This new app allows you to deploy one app instead of three separate apps to securely view corporate files on Android devices. The RMS sharing app has added support for Intune mobile application management (MAM), as well as support for viewing audio video (AV), image, and PDF files protected by Intune. All files and formats supported by the Intune Viewer apps are fully supported by the RMS sharing app when used with Intune management. You can now deploy the RMS sharing app with Intune MAM policy so you can view images, AV, and PDF files using just a single app, through both Intune MDM and Intune MAM without device enrollment.

With the release of the new RMS sharing app, we are removing the following Intune Viewer apps, beginning August, 2016: 
- Intune AV Viewer
- Intune PDF Viewer
- Intune Image Viewer for Android from Google Play
- Intune administrators will no longer be able to deploy the Intune Viewer apps on Android devices when this change is implemented. 

Instead of using the Intune Viewer apps, we recommend using the new Rights Management app (RMS sharing) for Android, which allows you to deploy one app instead of three separate apps to securely view corporate files on Android devices.  --->

- **Conditional access for browser.** You will be able to set a conditional access policy for Exchange Online and SharePoint Online so that they can only be accessed by managed and compliant iOS and Android devices. End users who try to sign in to Outlook Web Access (OWA) and SharePoint sites with iOS and Android devices will be prompted to enroll their device with Intune as well as to fix any non-compliance issues before they can complete sign-in.
<!---TFS 1175844--->

- **MAM SDK: Support PIN length configuration.** You will be able to specify the length of the PIN for MAM apps similar to a device PIN. This will require end users to comply with the new restrictions you set. They will see a slightly modified PIN screen to account for the longer input.
<!--- TFS 1104753--->

- **Skype for Business for Android.** Intune Administrators can now target Skype for business with MAM without enrollment policies.  Once their users are logged in, the MAM policies will be applied.
<!--- TFS item 1248444 --->

- **Skype for Business for iOS.** Intune Administrators can now target Skype for business with MAM without enrollment policies.  Once their users are logged in, the MAM policies will be applied.
<!--- TFS item 1248443 --->

### Xamarin support
The Microsoft Intune app SDK now supports Xamarin apps in these scenarios:

- Writing new apps, or modifying the code of existing line of business apps using the Intune SDK. You can get the plugin on the [Microsoft Intune Github](https://github.com/msintuneappsdk) page.
- Adding MAM support to existing line of business apps using the Intune app wrapping tool

For help choosing which method to use, see [Decide how to prepare apps for mobile application management with Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune).
<!--- TFS 1061478 & TFS 1152340--->


## Device management
- **Remote assistance sessions for Windows PCs.** TeamViewer integration for Windows desktop agent-managed PCs will let you establish remote assistance sessions with Windows desktop agent-managed computers in support of end-user helpdesk departments. This includes Windows 7, 8, 8.1 and Windows 10.
<!--- TFS 1284856--->


<<<<<<< HEAD
=======
<!--- TFS item 1274326 --->



>>>>>>> c643dfe82ad0696e9e0cd67743ca127ec52ca44e
## Company Portal
- **End user toast notifications.** End users will now see toast notifications from the Android Company Portal app when they are enrolling their devices or removing their devices from the Company Portal.
-
* **Device identification banner will provide more information to end users.** End users will be able to easily identify the device they’ve selected when they are using the Company Portal website. If the wrong device is selected, they will be able to select the correct device by tapping the “Tap here” link in the home page banner.
<!--- TFS 1231157--->

<<<<<<< HEAD
=======



|Platform  |Support details|
|---------|---------|
|iOS | Supported|
|Android | Supported|
|Windows Phone 8.1 | Supported|
|Windows 10 Mobile | Supported only if the phone has a passcode set|
|PC (Windows 8.0 and earlier) | Not supported|
|PC (Windows 8.1) | Not supported|
|Windows Phone 8.0 | Not Supported|
|Windows 10 Desktop | Not supported|

>>>>>>> c643dfe82ad0696e9e0cd67743ca127ec52ca44e
## Service deprecation
**Custom Group Targeting of Notification Rules Removal.**
Intune notification rules define who an email alert will be sent to from Intune. Currently, you can configure notification rules to send emails to all users of devices in an Intune device group that you created. From around June 1st 2016 moving forward, targeting user-created groups will no longer be supported.

Today, to target a notification rule to a group you created from the Microsoft Intune administration console, you would take the following steps:

In the **Admin** workspace, click **Notification Rules** > **Create New Rule**

In step two of the Create Notification Rule Wizard, select the device groups which the rule will target. This step, “select device groups”, is being removed from the Intune Console.

The preliminary timeline for this change is as follows:
- In June, 2016, new tenants will not see step two of the Create Notification Rule Wizard. Exiting tenants are unaffected.
- Around August, 2016, some existing tenants will not see the “select device groups” in the wizard.
- Around October, 2016, we expect that all tenants will not see the “select device groups” in the wizard.

<!---	TFS 1278864--->
**Changes in support for the iOS Company Portal app.**
In the coming months, there will be an update for the Microsoft Intune Company Portal app for iOS that will only support devices running iOS 8.0 or later. Users won’t be able to enroll new devices running versions below iOS 8.0. Enrolled devices running versions below iOS 8.0 will continue to be managed and will, for a limited time, be able to continue using the Company Portal app. However, devices must be on iOS 8.0 or later to access the latest versions of the Company Portal app. We encourage you to notify users to update to iOS 8.0 or later to take full advantage of new Intune features.  







### See also
See [What’s New in Microsoft Intune](whats-new-in-microsoft-intune.md) for  details on recent developments.
