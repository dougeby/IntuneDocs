
---
# required metadata

title: The early edition | Microsoft Intune
description:
keywords:
author: barlanmsft
manager: angrobe
ms.date: 10/05/2016
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

# The Early Edition for Microsoft Intune - October
The **Early Edition** provides a list of features that are coming in upcoming releases of Microsoft Intune. This information is provided under NDA on an extremely limited basis and is subject to change. Some features listed here are at risk of not making the cutoff dates and may be delayed until a future release. Other features are being tested in a pilot (flighting) to ensure they're customer-ready. Please reach out to your Intune/PM buddy if you have any questions or concerns.

This page is updated periodically. Check back for new What’s Coming updates.

The following changes are under development for Intune. All of these features will eventually be supported for hybrid customers' deployments (Configuration Manager with Intune). For more information about new hybrid features, check out our [hybrid What’s New page](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).

## New capabilities

### Conditional access for mobile application management
You can now create a conditional access policy to block unmanaged mobile applications from accessing [Exchange Online](/intune/deployuse/restrict-access-to-exchange-online-with-microsoft-intune.md). You can block the built-in mail clients and apps that are not MAM enabled with Intune App SDK.  This can be done by creating a conditional access policy and specifying the applications that you want to have access to Exchange Online using the Azure portal.
<!--TFS 1317673-->

### Android for Work support
Intune is now part of the [Android for Work program](https://enterprise.google.com/android/partners/). We will begin rolling out support for Android for Work features to Intune starting this month.

[Read Microsoft’s announcement about Intune support for Android for Work](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/12/microsoft-intune-support-for-android-for-work/).

<!---This month, some newly provisioned Intune tenants will start seeing the Android for Work features. We will announce later when existing tenants will begin to see this feature.--->
<!--TFS 1043303-->

### Lookout integration to protect iOS devices
In October, Microsoft is integrating with Lookout’s mobile threat protection solution to protect iOS mobile devices by detecting malware, risky apps, and more, on devices. Lookout’s solution helps you determine the threat level, which is configurable. You can create a compliance policy rule in Intune to determine device compliance based on the risk assessment by Lookout. Using conditional access policies, you can allow or block access to company resources based on the device compliance status.

End users of noncompliant iOS devices will be prompted to enroll, and will be required to install the Lookout for Work app on their devices, activate the app, and remediate threats reported in the Lookout for Work application to gain access to company data.
<!--TFS 1319493-->

### New Microsoft Intune Company Portal available for Windows 10 devices
Microsoft is releasing a new Microsoft Intune Company Portal for Windows 10 devices. This app, which leverages the new Windows 10 Universal format, will provide the user with an updated user experience within the app and identical experiences across all Windows 10 devices, PC and Mobile alike, while still enabling all the same functionality that they are using today.

The new app will also allow users to leverage additional platform features like single sign-on (SSO) and certificate-based authentication on Windows 10 devices. The app will be made available as an upgrade to the existing Windows 8.1 Company Portal and Windows Phone 8.1 Company Portal installs from the Windows Store. For more details, go to [aka.ms/universal-app](https://aka.ms/universal-app).
<!--TFS 1016502-->

### Manage printing from apps managed using MAM policies
You can now prevent printing company data from apps that have MAM policies. This setting is available on the [Azure portal](InTune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) and is supported on both [iOS](..deployuse/ios-mam-policy-settings) and [Android](InTune/deploy-use/android-mam-policy-settings) devices.
<!--TFS 1014328-->

## Notices

### Android Samsung KNOX compatibility with Intune
Certain models of the Samsung Galaxy Ace phone cannot be managed by Intune as Samsung KNOX devices. When you enroll these devices with Intune, they will instead be managed as standard Android devices.
The model numbers affected are:

* SM-G313HU
* SM-G313HY
* SM-G313M
* SM-G313MY
* SM-G313U

You and your end users need take no further action. For more information, visit the [Samsung KNOX](https://www.samsungknox.com) website.

<!--TFS 1173566 iX blurb provided by Barry; requires PM signoff

### Multi-factor authentication for Android and iOS enrollment

In addition to Windows 8.1 and later, administrators can now enable multi-factor authentication for Android and iOS devices in the Microsoft Intune Enrollment application. -->    

### Company Portal app for Windows 8 is deprecated; support for Windows Phone 8 and Windows RT platforms are being deprecated
Starting in October 2016, Microsoft Intune will deprecate support for the Windows 8 Company Portal. Microsoft Intune will also deprecate support for the Windows Phone 8 and Windows RT platforms. As a consequence, you will not be able to enroll or update any Windows Phone 8 or Windows RT devices.

You can continue to manage Windows Phone 8, Windows RT  and Windows 8 devices that are already enrolled. Update Windows Phone 8 and Windows 8 devices to Windows 8.1 and Windows Phone 8.1, and use the corresponding Windows 8.1 and Windows Phone 8.1 Company Portal apps to continue distributing apps to these devices without disruptions.

Starting in November 2016, we will deprecate support for the Windows Phone 8 Company Portal.
<!--TFS 1255391-->

<!--TFS 1318014; awaiting approval in notes as to whether to proceed

### "Default" policy is deprecated

To minimize unintentionally assigned profiles, Intune is removing support for the "default" Corporate Device Enrollment profile for Apple Device Enrollment Program (DEP) device serial numbers in the new Azure console. Serial numbers synchronized from an Apple DEP account will initially have no Corporate Device Enrollment profile assigned.  A profile must be assigned manually after synchronization. This change will apply to the new console only. Until the existing Admin console is retired, no change will take place.
-->

<!--TFS 1318023; awaiting approval in notes as to whether to proceed

### Deprecation of row-by-row iOS Details review for iOS device CSV uploads

In order to streamline uploading IMEI numbers for Corporate devices and Apple serial numbers for Configurator enrollment, Intune is removing the row by row review of hardware identifiers already found in the system. This review allows the IT Pro to accept associated Details from the CSV to overwrite the existing details for a hardware identifier already in the system. The review will be replaced by a single option to automatically overwrite Details for all hardware identifiers or ignore new details for existing identifiers. This change will apply to the new console only. Until the existing Admin console is retired, no change will take place.
-->



### Intune App SDK and App Wrapping Tool for Android
You can enable your apps to use Intune mobile application management (MAM) policies by using either the Intune App Wrapping Tool or the Intune App SDK. New updates for the App Wrapping Tool and SDK will include:

* Support for Android N
* Support for Intune MAM policies without requiring device enrollment
* Support for Xamarin-based Android apps

You can test MAM without device enrollment and Xamarin support in the public preview of the Android App Wrapping Tool here: [https://github.com/msintuneappsdk/intune-app-wrapper-android-preview](https://github.com/msintuneappsdk/intune-app-wrapper-android-preview)
<!--TFS 1319511; please create new TFS entry for WN text associated with this TFS item-->

<!--TFS 1319613; no iX review on PM text blurb

### Private preview customers using MAM Conditional Access will have their policies reset

Due to changes in the policy structure for Conditional Access for Mobile App Management, any existing policies that were set by customers through the private preview will be removed. Customers will need to set new policies once the change is made. The timing will coincide with the October service update.
-->

### See also
See [What’s New in Microsoft Intune](whats-new-in-microsoft-intune.md) for details on recent developments.
