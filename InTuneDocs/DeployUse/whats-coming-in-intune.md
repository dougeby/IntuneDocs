---
# required metadata

title: What's coming | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 05/03/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d

# optional metadata

#ROBOTS:
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


## App management
- **Conditional access for browser.** You will be able to set a conditional access policy for Exchange Online and SharePoint Online so that they can only be accessed by managed and compliant iOS and Android devices. End users who try to sign in to Outlook Web Access (OWA) and SharePoint sites with iOS and Android devices will be prompted to enroll their device with Intune as well as to fix any non-compliance issues before they can complete sign-in.
<!---TFS 1175844--->

- **MAM SDK: Support PIN length configuration.** You will be able to specify the length of the PIN for MAM apps similar to a device PIN. This will require end users to comply with the new restrictions you set. They will see a slightly modified PIN screen to account for the longer input.
<!--- TFS 1104753--->

- **MAM controls to prevent Outlook contacts sync (iOS).** A new setting is available for mobile application management without device enrollment. This setting  allows the Intune administrator to prevent an application from syncing contacts to the native address book on iOS devices. When this setting is enabled, the app will no longer be able to save contacts to the native address book. When this setting is disabled, the app will be able to save contacts to the native address book. When an Intune administrator selectively wipes a device, all contacts that have already been saved to the native address book will be removed. This new setting is now supported by the Outlook application on iOS devices.
<!---TFS item 1276166--->

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


<!--- TFS item 1274326 --->



## Company Portal
* **Device identification banner will provide more information to end users.** End users will be able to easily identify the device they’ve selected when they are using the Company Portal website. If the wrong device is selected, they will be able to select the correct device by tapping the “Tap here” link in the home page banner.
<!--- TFS 1231157--->




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

## Service deprecation
**Custom Group Targeting of Notification Rules Removal.**
Intune notification rules define who an email alert will be sent to from Intune. Currently, you can configure notification rules to send emails to all users of devices in an Intune device group that you created. From around June 1st 2016 moving forward, targeting user-created groups will no longer be supported.

Today, to target a notification rule to a group you created from the Microsoft Intune administration console, you would take the following steps:

In the **Admin** workspace, click **Notification Rules** > **Create New Rule**

In step two of the Create Notification Rule Wizard, select the device groups which the rule will target. This step, “select device groups”, is being removed from the Intune Console.

The preliminary timeline for this change is as follows:
•	In June, 2016, new tenants will not see step two of the Create Notification Rule Wizard. Exiting tenants are unaffected. 
•	Around August, 2016, some existing tenants will not see the “select device groups” in the wizard. 
•	Around October, 2016, we expect that all tenants will not see the “select device groups” in the wizard. 

<!---	TFS 1278864--->







### See also
See [What’s New in Microsoft Intune](whats-new-in-microsoft-intune.md) for  details on recent developments.
