---
# required metadata

title: What's new archive | Microsoft Intune
description:
keywords:
author: barlanmsft
manager: angrobe
ms.date: 10/12/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: ed2db991-4729-49a7-a1e6-be2ffa0d03d1

# optional metadata

ROBOTS: noindex,nofollow
#audience:
#ms.devlang:
#ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---
## September 2016
## New features, announcements and information
* [Windows conditional access](#windows-conditional-access)
* [iOS 10 support](#ios-10-support)
* [App Wrapping Tool supports MAM without device enrollment for Android and iOS](#app-wrapping-tool-supports-mam-without-device-enrollment-for-android-and-ios)
* [Intune groups begin transitioning to Azure Active Directory in September](#intune-groups-begin-transitioning-to-azure-active-directory-in-september)
* [Lookout integration to protect Android devices](#lookout-integration-to-protect-android-devices)
* [Company Portal updates for Android, iOS and Windows](#company-portal-updates)
* [Intune glossary](#intune-glossary)
* [What's coming](#whats-coming)

## Windows conditional access
You can now create conditional access policies through the Intune admin console to block Windows PCs from accessing Exchange Online and SharePoint Online. You can also create conditional access policies to block access to Office desktop and universal applications.

## iOS 10 support
Existing Intune MDM and MAM scenarios are compatible with iOS 10. For tips, refer to the [Intune Support Team Blog](https://blogs.technet.microsoft.com/intunesupport/2016/09/13/support-tip-intune-support-for-ios-10/).

## App Wrapping Tool supports MAM without device enrollment for Android and iOS
The Intune App Wrapping Tool is a command line tool used to enable Intune MAM on line-of-business (LOB) apps for iOS and Android. It is the simplest way to incorporate the Intune MAM SDK into your app, so that your app can enforce MAM policies deployed through Intune. Using MAM policies, you can:

1. Encrypt the app's data.
2. Require the information worker to enter a PIN when launching the app.
3. Allow the app to transfer data only to other managed apps.
4. Prevent the app from backing up data to Android, iTunes, and iCloud.
5. Only allow Cut, Copy, and Paste into and out of other managed apps.

The public preview of the updated Intune App Wrapping Tool now supports MAM without device enrollment on internal LOB apps on iOS and Android. This means your end-users are not required to enroll their devices with Intune to use MAM-enabled LOB apps.

Anyone can test the public preview software and read helpful documentation, located in msintuneappsdk's GitHub:

http://www.github.com/msintuneappsdk/intune-app-wrapper-ios-preview

http://www.github.com/msintuneappsdk/intune-app-wrapper-android-preview

Before you install and use Microsoft Intune App Wrapper for Android and iOS Pre-Release you must:

* Review the Microsoft License Terms for Microsoft Intune App Wrapping Tool for Android and iOS Pre-Release
* Print and retain a copy of the license terms for your records. By downloading and using Microsoft Intune App Wrapping Tool for Android Pre-Release you agree to such license terms. If you do not accept them, do not use the software.
<!---TFS 1235607--->

## Intune groups begin transitioning to Azure Active Directory in September
Some new Intune accounts will use Azure Active Directory security groups rather than Intune user groups. You will know that you’re working with security groups, as the Intune portal groups page will have a link directing you to the Azure management portal.

## Lookout integration to protect Android devices
Microsoft is integrating with Lookout’s mobile threat protection solution to protect Android mobile devices by detecting malware, risky apps, and more, on devices. Lookout’s solution helps you determine the threat level, which is configurable. You can create a compliance policy rule in Intune to determine device compliance based on the risk assessment by Lookout. Using conditional access policies, you can allow or block access to company resources based on the device compliance status.

End users of noncompliant devices will be prompted to enroll, and will be required to install the Lookout for Work application on Android devices, activate the app, and remediate threats reported in the Lookout for Work application to gain access. To learn more, see [Restrict access based on device, network, and application risk](restrict-access-based-on-device-network-app-risk.md).


## Company Portal updates

### Android

**Addition of "Notifications" to the Company Portal for Android**<br/>
A new Notifications icon has been added to the Company Portal for Android on the homepage. Tapping this icon accesses the Notifications page, which shows your end users all items that require attention in the Company Portal app, such as device noncompliance, enrollment update, and enrollment activation. The iOS Company Portal app already has this notifications experience. Having the new Notifications page means that user won’t see the Company Access Setup page every time they launch or resume the Company Portal as long as the device is already enrolled. If you create your own end-user guidance, you might want to update your documentation to reflect this change. Find updated screenshots [here](https://aka.ms/androidcpupdate).  
<!---TFS 1095560--->

**Providing feedback in the Company Portal for Android**</br>
A new item has been added to the menu of the Company Portal for Android. Tapping **Help & Feedback** shows three actions:
* Use **Get Help** to report an issues to your IT department about the Company Portal. IT will create an email using your  email client and attach the Company Portal logs to it. **Get Help** replaces the **Send Data** feature on the **Settings** page.
* Use **Give Feedback** to provide feedback to the Company Portal team.
* Use **Rate our app** to leave the Company Portal app a rating or review on Google Play.

### iOS
**Changes in support for the iOS Company Portal app**<br/>
All users of the Microsoft Intune Company Portal app for iOS are now required to use its latest version. New users are able to download only the latest version, and current users are required to update to it. The latest version requires iOS 8.0 or later, so devices running older iOS versions cannot use the Company Portal or enroll until they update their device to iOS 8.0 or later and then update the Company Portal app to the latest version. Enrolled devices running versions below iOS 8.0 will continue to be managed and listed in the Intune Admin Console.
<!---TFS 1283165--->

**Improvements in how iOS end users get their apps**<br/>
The following changes have been made to the apps tiles in the Company Portal app for iOS to point users to different views in a single location, the Company Portal website, for all of their apps. Apple restrictions prohibit line-of-business and managed app store apps from being listed in the Company Portal app, and require users to visit different views to find all of their apps.

- The **Company Apps** tile previously pointed to a list of all apps in the ALL tab of the Company Portal website, and it will continue to work the same way. The tile name has changed to **All Apps**.
- The **Other Apps** tile previously pointed to a view, inside the Company Portal app, that lists all apps that Apple permits the Company Portal app to show. The tile name has changed to **Featured Apps**, and tapping the tile will take users to the FEATURED tab of the Company Portal website.
-  The **Categories** tile previously pointed to a view, inside the Company Portal app, that lists categories of apps. The tile name has not changed, but it now points to the CATEGORIES tab of the Company Portal website.
You can find updated screenshots [here](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186).
<!---TFS 1317133--->

**Prompt to install the iOS Managed Browser app if IT Pro sets that requirement for an app**<br/>
If you have configured a web clip to open only in the managed browser, and the managed browser is not installed on a device, the Company Portal app on the device will prompt the user to install the managed browser before the web clip can be installed.
<!---TFS 1228570--->

### Windows
**Feedback button added to Windows Phone 8.1 Company Portal app**<br/>
The Windows Phone 8.1 Company Portal app enables end users to send feedback about the app by using a new "send feedback" button. To find the button, users tap the “three dots” menu at the bottom right of the Company Portal app screen and then tap **send feedback**. The collected, anonymized feedback will help Microsoft improve the Company Portal app experience for users.
<!---TFS 1317806--->

## Intune glossary</br>
We’ve added a new [glossary topic](https://docs.microsoft.com/intune/understand-explore/intune-glossary) to the library to help you understand some of the terms used in the Intune product.
