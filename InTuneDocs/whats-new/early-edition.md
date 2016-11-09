

---
# required metadata

title: The Early Edition | Microsoft Intune
description:
keywords:
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/8/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d

# optional metadata

ROBOTS: NOINDEX,NOFOLLOW
#audience:
#ms.devlang:
ms.reviewer: cacampbell
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# The Early Edition for Microsoft Intune - November

The **Early Edition** provides a list of features that are coming in upcoming releases of Microsoft Intune. This information is provided under NDA on an extremely limited basis and is subject to change. Some features listed here are at risk of not making the cutoff dates and may be delayed until a future release. Other features are being tested in a pilot (flighting) to ensure they're customer-ready. Please reach out to your Intune/PM buddy if you have any questions or concerns.

This page is updated periodically. Check back for additional updates.

The following changes are under development for Intune. All of these features will eventually be supported for hybrid customers' deployments (Configuration Manager with Intune). For more information about new hybrid features, check out our [hybrid What’s New page](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).

## New Capabilities

<!--### View App States for All Platforms in Real Time
App installation status is now shown in real-time in the console. When you previously deployed an app, you had to wait for a targeted device to report back before the app install status was displayed in the Intune console.

### Streamline iOS App Management for your End Users
Intune can now automatically take over management of the previously installed app and no end user action is required.

Previously, if the end user of an enrolled iOS device installed an app from the App Store before you deployed that same app with a deployment action of __Available__, then the end user had to:

1. Open the __Company Portal__.
2. Select the app.
3. Tap __Install__ to enable Intune to take over management of the app.-->

### New Microsoft Intune Company Portal App for Windows 10 devices
Microsoft is releasing a new Intune Company Portal for Windows 10 devices. This app, which leverages the new Windows 10 Universal format, will provide the user with an updated user experience within the app and identical experiences across all Windows 10 devices, PC and Mobile alike - while still enabling all the same functionality that they are using today.

The new app will also allow users to leverage additional platform features like single sign-on and certificate-based authentication on Windows 10 devices. The app will be made available as an upgrade to the existing Windows 8.1 Company Portal and Windows Phone 8.1 Company Portal installs from the Windows Store. It will also be available for sideloading.

### Support for Windows Store for Business Apps Being Deployed as Available
You can now deploy apps you synchronized from the Windows Store for Business (WSfB) with a deployment action of __Available__ or __Required__. After syncing WSfB apps into Intune, administrators will be able to target those apps as available installs to groups of users. End users will see the deployed WSfB apps as available for install in the Universal Company Portal, where they can choose whether they would like to acquire the apps.

<!--### Conditional Access for MAM with SharePoint Online

You can block apps that are not supported by Intune mobile app management (MAM) policies from accessing SharePoint online.  You can get started in Intune mobile app management via the Azure portal. Look for the  Conditional Access section in the “Settings” blade which now includes the option for SharePoint online.-->

### Intune App SDK for Cordova Plugin Now Supports MAM without Enrollment
App developers can now use the Intune App SDK for Cordova plugin to enable MAM functionality without device enrollment in their Cordova-based apps for Android and iOS. The Intune App SDK for Cordova plugin can be found [here](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam).

### Intune App SDK Xamarin Component Now Supports MAM without Enrollment
App developers can now use the Intune App SDK Xamarin component to enable MAM functionality without device enrollment in their Xamarin-based apps for Android and iOS. The Intune App SDK Xamarin component can be found [here](https://github.com/msintuneappsdk/intune-app-sdk-xamarin).

## Notices

### Symantec Signing Certificate No Longer Required for Windows Phone 8 Company Portal
The Windows Phone 8 Company Portal app will no longer require a Symantec signing certificate to be uploaded in the Intune Admin Console.

## Deprecations

### Support for the Windows Phone 8 Company Portal
Support for Windows Phone 8 Company Portal will now be deprecated. Support for the Windows Phone 8 and WinRT platforms was deprecated in October 2016. Support for the Windows 8 Company Portal was also deprecated in October 2016.

### See also
See [What’s New in Microsoft Intune](whats-new-in-microsoft-intune.md) for details on recent developments.
