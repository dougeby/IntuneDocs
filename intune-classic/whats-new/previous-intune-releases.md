---
# required metadata

title: Previous releases 
description:
keywords:
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/13/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 45dad14a-d412-488d-bb1e-ad990ea503df
ROBOTS: NOINDEX,NOFOLLOW

# optional metadata

#audience:
#ms.devlang:
#ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Previous Intune releases

This page is a list of announcements made in [What’s New in Microsoft Intune](whats-new-in-microsoft-intune.md).

[!INCLUDE[wit_nextref](../includes/whats-new-last-six-months.md)]

## July 2016

### App management

__Improve the app provisioning profile update experience__
Apple iOS line of business mobile apps are built with a provisioning profile included and code signed with a certificate. When the app runs on an iOS device, iOS confirms the integrity of the iOS app and enforces policies defined by the provisioning profile.

The enterprise signing certificate you use to sign apps typically lasts for 3 years. However, the provisioning profile expires after 1 year. With this update, Intune gives you the tools to proactively deploy a new provisioning profile policy to devices that have apps that are near expiry while the certificate is still valid. For more information, see [Use iOS mobile provisioning profile policies to keep your line-of-business apps up-to-date](/intune-classic/deploy-use/ios-mobile-app-provisioning-profiles).
<!--- TFS 1280247--->

__Xamarin SDK for Intune apps is available__
The Intune App SDK Xamarin component allows you to enable the Intune mobile app management features in your mobile iOS and Android apps built with Xamarin. You can find the component in the [Xamarin store](https://components.xamarin.com/view/Microsoft.Intune.MAM) or on the [Microsoft Intune Github page](https://github.com/msintuneappsdk).
<!--- TFS 1061478 --->

### Device management
__Increased device enrollment limits__
Intune increased the maximum configurable device enrollment limit from 5 to 15 devices per user.
<!---TFS 1289896 --->

__TeamViewer Integration for Windows PCs running the Intune client software__
[TeamViewer](/intune-classic/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client).
<!---TFS 1284856--->

### Company Portal updates

__Company Portal website__
- **Improved end-user experience when enrolling Windows devices**<br/>
When you are using conditional access, the enrollment steps for Windows 8.1, Windows 10 Desktop, and Windows 10 Mobile have been clarified in the Company Portal website. Users will now see separate “Device enrollment” and “Workplace Join” steps, making it easier for them to see the status of their device and to complete the process if they experience a Workplace Join (WPJ) failure. The separate steps are also expected to simplify the troubleshooting process for IT administrators. Previously, when end users tried to enroll and all enrollment steps succeeded except for WPJ, the enrolled device would not appear on the list of devices for users to identify, causing confusion for users.

__Android__
- **Android Company Portal app**<br/>
If Android end users see an error message that says their device is missing a required certificate, they can tap a "How to resolve this" button to get [steps](/intune-classic/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues), which contains steps that IT administrators can use to fix the certificate issue.

- **Restrict side-loaded app installations to enrolled devices**<br/>
Android devices can no longer install applications through the Company Portal website unless the devices have been enrolled in Intune by using the Intune Company Portal app for Android.
<!---TFS 1299082--->

__iOS__
- **Changes to Device Enrollment Managers accounts in the iOS Company Portal app**<br/>
To improve performance and scale, Intune no longer displays all Device Enrollment Managers (DEM) devices in the **My Devices** pane of the iOS Company Portal app. Only the local device running the app is displayed, and only if it is enrolled via the Company Portal app.

The DEM user may perform actions on the local device, but remote management of other enrolled devices can only be performed from the Intune admin console. Additionally, Intune is deprecating use of DEM accounts with either the Apple Device Enrollment Program or the Apple Configurator tool. Both these enrollment methods already support user-less enrollment for shared iOS devices.

Only use DEM accounts when user-less enrollment for shared devices is unavailable. For more information, see [Enroll corporate-owned devices with the Device Enrollment Manager in Microsoft Intune](/intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).
<!---TFS 1233681--->

### Change of names for Windows features
- [Microsoft Passport for Windows](/intune-classic/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune) is now known as **Windows Hello for Business**.
- [Enterprise data protection](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) is now known as **Windows Information Protection**.


## June 2016
### Intune service health
Service health information for Intune has been moved to a central location with other Microsoft services. You'll now find this information in the Office 365 management portal under Service Health. For more information, see [this blog post](https://blogs.technet.microsoft.com/enterprisemobility/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).

### App management
- **Enhanced Windows 10 enterprise data policy configuration experience.** We have made enhancements to the Windows 10 enterprise data protection policy configuration experience around creating app rules, specifying network boundary definition, and other enterprise data protection settings. To learn more, see [Create an enterprise data protection (EDP) policy using Microsoft Intune](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune).


### Device management
- **Windows Defender policy setting to protect against potentially unwanted apps.** A new Windows Defender setting named **Potentially Unwanted Application Detection** has been added to the general configuration policy for Windows 10 Desktop and Mobile. You can use this setting to protect enrolled Windows desktop computers against running software classed by Windows Defender as potentially unwanted. You can protect against these applications running, or use audit mode to report when a potentially unwanted application is installed. See [Windows 10 policy settings in Microsoft Intune](/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune) for more information.
<!---TFS 1244478--->

### Conditional access
- **Cisco ISE network access control policy for Intune.**  Customers who use the Cisco Identity Service Engine (ISE) 2.1 and also use Microsoft Intune can set a network access control policy in ISE.

	Using this policy, devices that need to connect to the network using WiFi or VPN must meet following conditions before they are allowed access:

	* Must be managed by Intune
	* Must be compliant with any deployed Intune compliance policies

 End users of noncompliant devices will be prompted to enroll, and remediate any compliance issues to gain access.
- **Conditional access for browser.** You can set a conditional access policy for [Exchange Online](/intune-classic/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune) so that they can only be accessed from supported web browsers on managed and compliant iOS and Android devices. End users who try to sign in to Outlook Web Access (OWA) and SharePoint sites with iOS and Android devices will be prompted to enroll their device with Intune as well as to fix any non-compliance issues before they can complete sign-in.
<!---TFS 1175844--->

- **Dynamics CRM Online supports conditional access.** You can set a conditional access policy for [Dynamics CRM Online](/intune-classic/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune) so that it can only be accessed by managed and compliant iOS and Android devices. End users who try to sign in to the Dynamics CRM mobile app on iOS and Android will be prompted to enroll with Intune as well as remediate any non-compliance issues before sign-in can complete.
<!---TFS1295358--->

### Intune Company Portal updates

__Android Company Portal app__

- When IT administrators apply the new "Require that devices disallow installation of apps from unknown sources (Android 4.0+)" policy, end users with Android 4.0 or later devices will see the message, "Installation from Unknown sources must be disabled." Users will need to go to  **Settings** > **Security**, and turn off **Unknown sources**. A link in the compliance message lets users get more [information](/intune-user-help/you-are-asked-to-turn-off-unknown-sources-android) about the message and why they are being required to turn off the setting.

- When IT administrators apply the new "Require that devices have enabled scanning of apps for security threats (Android 4.0+)" policy, end users with Android 4.0 or later devices will see the message, "Scan device for security threats." Users will need to go to **Settings** > **Google** > **Security**, and turn on **Scan device for security threats**. A link in the compliance message lets users get more [information](/intune-user-help/you-are-asked-to-turn-on-scan-device-for-security-threats-android) about the message and why they are being required to turn on the setting.

- When IT administrators apply the new "Require that USB debugging is disabled (Android 4.2+)" policy, end users with Android 4.2 or later devices will see the message, "USB debugging must be disabled." Users will need to go to **Settings** > **Developer options**, and turn off **USB debugging**." A link in the compliance message lets users get more [information](/intune-user-help/you-are-asked-to-turn-off-usb-debugging-android) about the message and why they are being required to turn off the setting.

- When IT administrators apply the new "Minimum Android security patch level (Android 6.0+)" policy, end users with Android 6.0 or later devices will see the message, "This device does not meet the minimum Android security patch level." Users will need to install the required security patch. A link in the compliance message lets users get [information](/intune-user-help/you-are-asked-to-turn-on-scan-device-for-security-threats-android) about how to install the required security patch and to see which security patch they currently have installed.

__iOS Company Portal app__

- When end users are installing line-of-business apps, they will now see an improved app installation experience. If the app installation is taking a long time, users can manually sync their device to force the sync process to resume. To review the end-user instructions, see [Sync your iOS device manually](/intune-user-help/sync-your-device-manually-ios).

- The Microsoft Intune Company Portal app for iOS has been updated to support iOS version 8.0 and later. This update means that end users can install the Company Portal app and enroll new devices in Intune only if the device is running iOS version 8.0 or later. Users who have already enrolled devices that are running on an unsupported version of iOS can continue to use the Company Portal app that is on their device.

## May 2016
All of these features are also supported for hybrid deployments (Configuration Manager with Intune). For more information about new hybrid features, check out the [Hybrid What’s New](https://technet.microsoft.com/library/mt718155.aspx) page.

### Documentation
Welcome to the preview version of [docs.microsoft.com](https://docs.microsoft.com/intune)!
This is a completely new, modern content platform designed to make it easier for you, our customers to understand and use Intune.
To read about all of the new features, see [Introducing docs.microsoft.com](https://docs.microsoft.com/teamblog/introducing-docs-microsoft-com/)

### Intune service health
Service health information for Intune has been moved to a central location with other Microsoft services. You'll now find this information in the [Office 365 management portal](https://portal.office.com/Admin/Default.aspx) under **Service Health**.
For more information, see [this blog post](https://blogs.technet.microsoft.com/microsoftintune/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).

### App management
- **MAM SDK: Support PIN length configuration.** You will be able to specify the length of the PIN for MAM apps similar to a device PIN. This will require end users to comply with the new restrictions you set. They will see a slightly modified PIN screen to account for the longer input. For details, see [MAM policy settings for Android](/intune-classic/deploy-use/ios-mam-policy-settings).

- **Skype for Business for iOS and Android.** You can now target Skype for business with [MAM without enrollment policies](/intune-classic/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune). Once users log in, the MAM policies will be applied.

- **New apps available for management with MAM policies.** The Microsoft Word, Excel, and PowerPoint apps for Android can now be associated with MAM policies on devices that are not enrolled with Intune. For a full list of supported apps, go the Microsoft Intune mobile application gallery on the [Microsoft Intune application partners](https://www.microsoft.com/server-cloud/products/microsoft-intune/partners.aspx) page.


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
You can now view the [status](/intune-classic/deploy-use/monitor-mobile-app-management-policies-with-Microsoft-Intune) of your application management policies for any user in your Azure Active Directory (AAD) tenant. This includes:
   - Devices
   - Apps on the device

   Status values:

   **Checked in**: Indicates the policy was deployed to the user, and app was used in work context, and successfully received the policy.

    **Not checked in**: Indicates the policy was deployed to the user, but app has not been used in the work context since then.


- **MAM controls to prevent Outlook contacts sync (Android).**
A new setting is available for [mobile application management](/intune-classic/deploy-use/wipe-managed-company-app-data-with-Microsoft-Intune), contacts that have already been saved to the native address book will be removed. This new setting is supported initially by the Outlook application on Android devices.

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
