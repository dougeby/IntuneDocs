---
# required metadata

title: What's new | Microsoft Intune
description: Find out what’s new in this month’s, and past releases of Microsoft Intune
keywords:
author: barlanmsftms.author: barlan
manager: angrobe
ms.date: 11/11/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: priyar
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---
# What's new in Microsoft Intune - November 2016
Learn what’s new in this release of Microsoft Intune. You can also find out about upcoming changes that you should be planning for, as well as information about past releases.

All of these features will eventually be supported for hybrid customers' deployments (Configuration Manager with Intune). For more information about new hybrid features, check out our [hybrid What’s New page](https://technet.microsoft.com/library/mt718155.aspx).
<!---@Barry, the above blurb stays in each version, but make sure Tyler signs off each time. Also, remember to set the ms.date in the metadata to the sprint release. --->

## New Capabilities

<!--### View App States for All Platforms in Real Time
App installation status is now shown in real-time in the console. When you previously deployed an app, you had to wait for a targeted device to report back before the app install status was displayed in the Intune console.

### Streamline iOS App Management for your End Users
Intune can now automatically take over management of the previously installed app and no end user action is required.

Previously, if the end user of an enrolled iOS device installed an app from the App Store before you deployed that same app with a deployment action of __Available__, then the end user had to:

1. Open the __Company Portal__.
2. Select the app.
3. Tap __Install__ to enable Intune to take over management of the app.-->

<!--### New Microsoft Intune Company Portal App for Windows 10 Devices
Microsoft is releasing a new Intune Company Portal for Windows 10 devices. This app, which leverages the new Windows 10 Universal format, will provide the user with an updated user experience within the app and identical experiences across all Windows 10 devices, PC and Mobile alike - while still enabling all the same functionality that they are using today.

The new app will also allow users to leverage additional platform features like single sign-on and certificate-based authentication on Windows 10 devices. The app will be made available as an upgrade to the existing Windows 8.1 Company Portal and Windows Phone 8.1 Company Portal installs from the Windows Store. It will also be available for sideloading.-->

<!--### Support for Windows Store for Business Apps Being Deployed as Available
You can now deploy apps you synchronized from the Windows Store for Business (WSfB) with a deployment action of __Available__ or __Required__. After syncing WSfB apps into Intune, administrators will be able to target those apps as available installs to groups of users. End users will see the deployed WSfB apps as available for install in the Universal Company Portal, where they can choose whether they would like to acquire the apps.

### Conditional Access for MAM with SharePoint Online

You can block apps that are not supported by Intune mobile app management (MAM) policies from accessing SharePoint online.  You can get started in Intune mobile app management via the Azure portal. Look for the  Conditional Access section in the “Settings” blade which now includes the option for SharePoint online.-->

> [!IMPORTANT]

> __An Update on Intune and Android for Work__

> While you can deploy Android for Work apps with an action of __Required__, you can only deploy apps as __Available__ if your Intune groups have been migrated to the new Azure AD groups experience.

### Intune App SDK for Cordova Plugin Now Supports MAM without Enrollment
App developers can now use the Intune App SDK for Cordova plugin to enable MAM functionality without device enrollment in their Cordova-based apps for Android and iOS. The Intune App SDK for Cordova plugin can be found [here](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam).

### Intune App SDK Xamarin Component Now Supports MAM without Enrollment
App developers can now use the Intune App SDK Xamarin component to enable MAM functionality without device enrollment in their Xamarin-based apps for Android and iOS. The Intune App SDK Xamarin component can be found [here](https://github.com/msintuneappsdk/intune-app-sdk-xamarin).

## Notices

### Symantec Signing Certificate No Longer Requires Signed Windows Phone 8 Company Portal for Upload
Uploading the Symantec signing certificate will no longer require a signed Windows Phone 8 Company Portal app. The certificate can be uploaded independently.

## Deprecations

### Support for the Windows Phone 8 Company Portal
Support for Windows Phone 8 Company Portal will now be deprecated. Support for the Windows Phone 8 and WinRT platforms was deprecated in October 2016. Support for the Windows 8 Company Portal was also deprecated in October 2016.


### See also
* [Microsoft Intune Blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Cloud Platform roadmap](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Previous Intune releases](previous-intune-releases.md)
