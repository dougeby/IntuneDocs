---
# required metadata

title: What's new archirve | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service:
ms.technology:
ms.assetid: ed2db991-4729-49a7-a1e6-be2ffa0d03d1

# optional metadata

ROBOTS: noindex,nofollow
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


## September 2015
### Mobile device and app management updates
**All Intune iOS management features now support iOS 9**
For details about iOS 9 management capabilities, see [this blog post](http://blogs.technet.com/b/microsoftintune/archive/2015/09/09/day-zero-support-for-ios-9-with-intune.aspx).

**New mobile app configuration policy for iOS**
Use the new mobile app configuration policy to automatically supply settings that an iOS app might need when it is run. For example, you could supply a network port, or a user name. For details, see [Configure apps with mobile app configuration policies in Microsoft Intune](https://technet.microsoft.com/library/mt481447.aspx).

**Easier app management for iOS 9 users**
 In this release, you can bring already-deployed apps under Intune management for iOS 9 users. For earlier versions of iOS, when you deploy an app and an unmanaged version of the app is already installed on a device, you still have to ask the user to uninstall the app manually before Intune can install the managed app.

 But starting with this release of Intune, you can now prompt users of iOS 9 devices to allow Intune to take over management of the app and apply any relevant mobile application management policies.

 **Windows 10 management** Use the new [Windows 10 general configuration policy](https://technet.microsoft.com/library/mt404697.aspx) to configure password, device, browser and other settings for enrolled devices that run Windows 10 and Windows 10 Mobile.

 **Create and deploy apps to enrolled Windows 10 devices** A new software installer type, Windows Installer through MDM (&#42;.msi) lets you create and deploy Windows Installer apps to enrolled devices that run Windows 10. For details, see [Get started with app deployment in Microsoft Intune](https://technet.microsoft.com/library/dn646955.aspx).

### Changes and updates to Microsoft Company Portal apps
The following changes have been made to the company portal apps in this release:

**iOS**
* Microsoft automatically collects anonymous data about the performance and use of the company portal to improve Microsoft products and services. End users can turn off data collection by using the Usage Data setting on their device, but administrators have no control over the data collection and cannot change the end user’s selection for this setting.
* Full screen resolution support on iPhone 6 and 6 Plus
* Bug fixes to improve security

### What's new in Intune documentation -- September 2015
**New topics**

|Name|Details|
|----|--------|
|[Windows 10 configuration policy settings in Microsoft Intune](https://technet.microsoft.com/library/mt404697.aspx)|This is a new configuration policy that lets you manage settings and features on devices that run Windows 10 and Windows 10 Mobile.
| [Configure apps with mobile app configuration policies in Microsoft Intune](https://technet.microsoft.com/library/mt481447.aspx)|This is a new policy type that lets you automatically supply settings that might be required when the user runs an iOS app. |

**Updated topics**

|Name|Details|
|----|-------|
|[Use policies to manage computers and mobile devices with Microsoft Intune](https://technet.microsoft.com/library/dn743712.aspx)|Updated to include the latest information to help you understand and create policies.|

## August 2015
### Mobile device and app management updates
* **Terms and conditions** for Intune enrollment and company access are [now managed using policies](https://technet.microsoft.com/library/mt405893.aspx). You can target different sets of terms and conditions to meet specific user group requirements. For example, you can  deploy terms and conditions in different languages to geographically defined user groups. You can also [edit your terms and conditions](https://technet.microsoft.com/library/mt405893.aspx#BKMK_TCVers) and specify whether to increment the version numbers, requiring users to agree to the new terms and conditions before they can use the company portal.
* **A number of Intune policies have been renamed** to make them more consistent across the product and easier for you to find. For a list of all available Intune policies, see [Use policies to manage computers and mobile devices with Microsoft Intune](https://technet.microsoft.com/library/dn743712.aspx).
* **PKCS #12 (.PFX) Certificate Profiles** are available for Android 4.0 or later, and Windows 10 (desktop and mobile) and later. Using .PFX does not require an NDES server. Learn how to use .PFX certificate profiles in [Enable access to company resources using certificate profiles with Microsoft Intune](http://technet.microsoft.com/library/dn818904.aspx)
* **Corporate Boundaries settings for Windows 10 Desktop and Mobile** enable granular VPN settings, as described in [Help users connect to their work using VPN profiles with Microsoft Intune](https://technet.microsoft.com/library/dn818905.aspx)
* **The OneDrive app for Android now supports multi-identity**. This and other updates to mobile app management policies are described in the [list of Microsoft applications you can manage](https://technet.microsoft.com/library/dn708489.aspx).
* **iOS Activation Lock bypass**. If company-owned iOS devices are protected by Activation Lock, you must enter the user's Apple ID and password before you can erase or reactivate the device. This can present a challenge when users leave the company and return a company-owned device without turning off Activation Lock. To help solve this problem, you can use [Intune Activation Lock Bypass](https://technet.microsoft.com/library/mt414176.aspx)

### Conditional access for PCs
You can now configure conditional access policies for PCs. This allows Office desktop apps to access Exchange Online and SharePoint online services.
To enable conditional access policy for PCs, the PC must either be domain joined or be complaint.
* See the **Getting started** section in  [Manage access to email and SharePoint with Microsoft Intune](http://technet.microsoft.com/library/dn818907).aspx) for the full list of requirements to enable conditional access for PCs.
* See [Manage email access with Microsoft Intune](https://technet.microsoft.com/library/dn705841.aspx) for options you can set to enable conditional access for email access.
* See [Manage SharePoint Online access with Microsoft Intune](https://technet.microsoft.com/library/dn705844.aspx) for options you can set to enable conditional access for SharePoint Online.

### Changes and updates to Microsoft Company Portal apps
The following changes have been made to the company portal apps in this release:

**Android**

Users will now see device enrollment instructions after signing in if they have not yet enrolled their device for management.

### What's new in Intune documentation -- August 2015
**New topics**

|Title|Details|
|-----|-------|
|[Help protect iOS devices with Activation Lock bypass for Microsoft Intune](https://technet.microsoft.com/library/mt414176.aspx)|Learn about how you can use Intune to bypass iOS Activation lock when a user leaves the company and returns a locked device.|

**Updated topics**

|Title|Details|
|-----|-------|
|[Microsoft apps you can use with Microsoft Intune mobile application management policies](https://technet.microsoft.com/library/dn708489.aspx)|Updated with the latest information about apps you can manage with mobile application management policies.
|[Use policies to manage computers and mobile devices with Microsoft Intune](http://technet.microsoft.com/library/dn743712.aspx)|Updated with the newest policies added to Intune.|
<!---
## July 2015
July updates for Intune are limited to behind-the-scenes enhancements that allow us to continue providing you with a high-quality service experience. New features are not included in this service update.

### Intune Onboarding benefit
Microsoft offers the Intune Onboarding benefit for eligible plans. The Onboarding benefit lets you work remotely with Microsoft specialists to get your Intune environment ready for use. For more information, see [Microsoft Intune Onboarding benefit description](https://technet.microsoft.com/library/mt228266.aspx)
### Changes and updates to Microsoft Company Portal apps
The following changes have been made to the company portal apps in this release.

**Android**

Microsoft automatically collects anonymous data about the performance and use of the company portal to improve Microsoft products and services. End users can turn off data collection by using the Usage Data setting on their device, but administrators have no control over the data collection and cannot change the end user’s selection for this setting.--->
