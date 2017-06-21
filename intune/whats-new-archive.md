---
# required metadata
title: What's new in previous months in the Microsoft Intune
titleSuffix: "Intune on Azure"
description: Review older announcements from the Intune what's new page
keywords:
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 06/08/2017
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 9ba01d60-4a03-4e3e-9aba-8be905c0054c

# optional metadata

ROBOTS: NOINDEX,NOFOLLOW
#audience:
#ms.devlang:
ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---

# What's new in the Microsoft Intune - previous months

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## April 2017

### Support for managing the Apple Classroom app

You can now manage the iOS Classroom app on iPad devices. Set up the Classroom app on the teachers iPad with the correct class and student data, then configure student iPads registered to a class, so that you can control them using the app.
For details, see [Configure iOS education settings](education-settings-configure-ios.md).

### Support for managed configuration options for Android apps <!-- 621621 -->

Android apps in the Play store that support managed configuration options can now be configure by Intune.  This feature lets IT view the list of configuration values supported by an app, and provides a guided, first-class UI to allow them to configure those values.

### New Android policy for complex PINs <!-- 722069 -->

You can now set a required [password](device-restrictions-android.md#password) type of Numeric complex in an Android device profile for devices that run Android 5.0 and above.  Use this setting to prevent device users from creating a PIN that contains repeating, or consecutive numbers, like 1111, or 1234.

### Additional support for Android for Work devices

- **Manage password and work profile settings** <!-- 612808 -->

  This new Android for Work device restriction policy now lets you manage password and work profile settings on Android for Work devices you manage.

- **Allow data sharing between work and personal profiles** <!-- 1045102 -->

This Android for Work device restriction profile now has new options to help you configure data sharing between work and personal profiles.

- **Restrict copy and paste between work and personal profiles** <!-- 1046094 -->

  A new custom device profile for Android for Work devices now lets you restrict whether copy and paste actions between work and personal apps are allowed.

For more information, see [Device restrictions for Android for Work](device-restrictions-android-for-work.md).

### Assign LOB apps to iOS and Android devices <!-- 1057568 -->

You can now assign line of business (LOB) apps for [iOS](lob-apps-ios.md) (.ipa files) and [Android](lob-apps-android.md) (.apk files) to users or devices.

###  New device policies for iOS <!-- 723774, 723815, 723826, 723830 -->

- **Apps on Home screen** - Controls which apps users see on the [Home screen of their iOS device](home-screen-settings-ios.md). This policy changes the layout of the Home screen, but does not deploy any apps you specified that are not installed.

- **Connections to AirPrint devices** - Controls which [AirPrint devices](air-print-settings-ios-macos.md) (network printers) that end users of iOS device can connect to.

- **Connections to AirPlay devices** - Controls which [AirPlay devices](airplay-settings-ios.md) (like Apple TV) that end users of iOS device can connect to.

- **Custom lock screen message** - Configures a custom message that users will see on the lock screen of their iOS device, that replaces the default lock screen message. For more information, see [Activate lost mode on iOS devices](device-lost-mode.md)

### Restrict push notifications for iOS apps <!-- 723767 -->

In an Intune device restriction profile, you can now configure the following [notification settings](app-notification-settings-ios.md) for iOS devices:

- Fully turn on or off notification for a specified app.
- Turn on or off, the notification in the notification center for a specified app.
- Specify the alert type, either **None**, **Banner**, or **Modal Alert**.
- Specify whether badges are allowed for this app.
- Specify whether notification sounds are allowed.

### Configure iOS apps to run in single app mode autonomously <!-- 737837 -->

You can now use an Intune device profile to configure iOS devices to run specified apps in [autonomous single app mode](device-restrictions-ios.md#autonomous-single-app-mode-supervised-only). When this mode is configured, and the app is run, the device is locked so that it can only run that app. An example of this is when you configure an app that lets users take a test on the device. When the app's actions are complete, or you remove this policy, the device returns to its normal state.

### Configure trusted domains for email and web browsing on iOS devices <!-- 723765 -->

From an iOS device restriction profile, you can now configure the following [domain settings](device-restrictions-ios.md#domains):

- **Unmarked email domains** - Emails that the user sends or receives which don't match the domains you specify here will be marked as untrusted.

- **Managed web domains** - Documents downloaded from the URLs you specify here will be considered managed (Safari only).  

- **Safari password auto-fill domains** - Users can save passwords in Safari only from URLs matching the patterns you specify here. To use this setting, the device must be in supervised mode and not configured for multiple users. (iOS 9.3+)


### VPP apps available in iOS Company Portal <!-- 748782 -->

You can now assign iOS volume-purchased (VPP) apps as **Available** installs to end users. End users will need an Apple Store account to install the app.

### Synchronize eBooks from Apple VPP Store <!-- 800878 -->

You can now [synchronize books](vpp-apps-ios.md) you purchased from the Apple volume-purchase program store with Intune, and assign these to users.

### Multi-user management for Samsung KNOX Standard devices <!-- 971988 -->

Devices that run Samsung KNOX Standard are now supported for [multi-user management](android-enroll.md) by Intune. This means that end users can sign in and out of the device with their Azure Active Directory credentials, and the device is centrally managed whether it’s in use or not.  When end users sign-in, they have access to apps and additionally get any policies applied to them. When users sign out, all app data is cleared.

### Additional Windows device restriction settings <!-- 818566 -->

We've added support for additional [Windows device restriction settings](device-restrictions-windows-10.md) like additional Edge browser support, device lock screen customization, start menu customizations, Windows Spotlight search set wallpaper, and proxy setting.

### Multi-user support for Windows 10 Creators Update <!-- 822547 -->

We've added support for [multi-user management](windows-enroll.md) for devices that run the Windows 10 Creators Update and are Azure Active Directory domain-joined. This means that when different standard users log onto the device with their Azure AD credentials, they will receive any apps and policies that were assigned to their user name. Users cannot currently use the Company Portal for self-service scenarios like installing apps.

### Fresh Start for Windows 10 PCs<!-- 1004830 -->

A new [Fresh Start device action](device-fresh-start.md) for Windows 10 PCs is now available.  When you issue this action, any apps that were installed on the PC are removed, and the PC is automatically updated to the latest version of Windows. This can be used to help remove pre-installed OEM apps that are often delivered with a new PC. You can configure if user data is retained when this device action is issued.

### Additional Windows 10 upgrade paths <!-- 903672 -->

You can now create an [edition upgrade policy to upgrade devices](edition-upgrade-configure-windows-10.md) to the following additional Windows 10 editions:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N

### Bulk Enroll Windows 10 devices <!-- 747607 -->

You can now join large numbers of devices that run the Windows 10 Creators update to Azure Active Directory and Intune with Windows Configuration Designer (WCD). To enable [bulk MDM enrollment](windows-bulk-enroll.md) for your Azure AD tenant, create a provisioning package that joins devices to your Azure AD tenant using Windows Configuration Designer, and apply the package to corporate-owned devices you'd like to bulk enroll and manage. Once the package is applied to your devices, they will Azure AD join, enroll in Intune, and be ready for your Azure AD users to log on.  Azure AD users are standard users on these devices and receive assigned policies and required apps. Self-service and Company Portal scenarios are not supported at this time.

### New MAM settings for PIN and managed storage locations <!-- 581122, 736644 -->

Two new app settings are now available to help you with mobile application management (MAM) scenarios:

- **Disable app PIN when device PIN is managed** - Detects if a device PIN is present on the enrolled device, and if so, bypasses the app PIN triggered by the app protection policies. This setting will allow for a reduction in the number of times a PIN prompt is displayed to users opening a MAM-enabled application on an enrolled device. This feature is available for both Android and iOS.

- **Select which storage services corporate data can be saved to** -Allows you to specify which storage locations in which to save corporate data. Users can save to the selected storage location services, which means all other storage location services not listed will be blocked.

  List of supported storage location services:

  - OneDrive
  - Business SharePoint Online
  - Local storage

### Help desk troubleshooting portal <!-- 907448 -->

The new [troubleshooting portal](help-desk-operators.md) lets help desk operators and Intune administrators view users and their devices, and perform tasks to resolve Intune technical problems.

## March 2017

### Support for iOS Lost Mode <!--431695-->

For iOS 9.3 and later devices, Intune added support for **Lost Mode**. You can now lock down a device to prevent all use and display a message and contact phone number of the device lock screen.

The end user will not be able to unlock the device until an admin disables Lost Mode. When Lost Mode is enabled, you can use the **Locate device** action to display the geographical location of the device on a map in the Intune console.

The device must be a corporate-owned iOS device, enrolled through DEP, that is in supervised mode.

For more information, see [What is Microsoft Intune device management](device-management.md)?

### Improvements to Device Actions report <!--677150-->

We’ve made improvements to the Device Actions report to improve performance. Additionally, you can now filter the report by state. For example, you could filter the report to show only device actions that were completed.”

### Custom app categories <!--748805-->

You can now create, edit, and assign categories for apps you add to Intune. Currently, categories can only be specified in English.
See [How to add an app to Intune](apps-add.md).

### Assign LOB apps to users with unenrolled devices <!--748823-->

You can now assign line of business apps from the store to users whether or not their devices are enrolled with Intune. If the user's device is not enrolled with Intune, they must go to the Company Portal website to install it, instead of the Company Portal app.

### New compliance reports <!--846671-->

You now have compliance reports that give you the compliance posture of devices in your company and allow you to quickly troubleshoot compliance-related issues encountered by your users. You can view information about

- Overall compliance state of devices
- Compliance state for an individual setting
- Compliance state for an individual policy

You can also use these reports to drill-down into an individual device to view specific settings and policies that affect that device.

<!--- You can now create an edition upgrade policy to upgrade devices to the following additional Windows 10 editions:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N --->

### Direct access to Apple enrollment scenarios <!--951869-->

For Intune accounts created after January 2017, Intune has enabled direct access to Apple enrollment scenarios using the Enroll Devices workload in the Azure portal. Previously, the Apple enrollment preview was only accessible from links in the classic Intune portal. Intune accounts created before January 2017 will require a one-time migration before these features are available in Azure. The schedule for migration has not been announced yet, but details will be made available as soon as possible. We strongly recommend creating a trial account to test out the new experience if your existing account cannot access the preview.


## February 2017

### Ability to restrict mobile device enrollment <!--747600, 795782-->
Intune is adding new enrollment restrictions that control which mobile device platforms are allowed to enroll. Intune separates mobile device platforms as iOS, macOS, Android, Windows and Windows Mobile.

* Restricting mobile device enrollment does not restrict PC client enrollment.  
* For iOS and Android only, there is one additional option to block the enrollment of personally owned devices.

Intune marks all new devices as personal unless the IT admin takes action to mark them as corporate owned, as explained in [this article](https://docs.microsoft.com/intune-classic/deploy-use/manage-corporate-owned-devices).

### View all actions on managed devices <!--677150-->
A new __Device Actions__ report shows who has performed remote actions like factory reset on devices, and additionally shows the status of that action. See [What is device management?](device-management.md).

### Non-managed devices can access assigned apps <!--664691-->
As part of the design changes on the Company Portal website, iOS and Android users will be able to install apps assigned to them as "available without enrollment" on their non-managed devices. Using their Intune credentials, users will be able to log into the Company Portal website and see the list of apps assigned to them. The app packages of the "available without enrollment" apps are made available for download via the Company Portal website. Apps which require enrollment for installation are not affected by this change, as users will be prompted to enroll their device if they wish to install those apps.

### Custom app categories <!--748805-->
You can now create, edit, and assign categories for apps you add to Intune. Currently, categories can only be specified in English.
See [How to add an app to Intune](apps-add.md).

### Display device categories <!--814654-->
You can now view the device category as a column in the device list. You can also edit the category from the properties section of the device properties blade. See [How to add an app to Intune](apps-add.md).

### Configure Windows Update for Business settings <!--776716-->

Windows as a Service is the new way of providing updates for Windows 10. Starting with Windows 10, any new Feature Updates and Quality Updates will contain the contents of all previous updates. This means that as long as you've installed the latest update, you know that your Windows 10 devices are completely up-to-date. Unlike with previous versions of Windows, you now must install the entire update instead of part of an update.

By using Windows Update for Business, you can simplify the update management experience so that you don’t need to approve individual updates for groups of devices. You can still manage risk in your environments by configuring an update rollout strategy and Windows Update will make sure that updates are installed at right time. Microsoft Intune provides the ability to configure update settings on devices and gives you the ability to defer update installation. Intune doesn’t store the updates, but only the update policy assignment. Devices access Windows Update directly for the updates.Use Intune to configure and manage **Windows 10 update rings**. An update ring contains a group of settings that configure when and how Windows 10 updates get installed. For details, see [Configure Windows Update for Business settings](windows-update-for-business-configure.md).

## January 2017

### Assign line of business apps whether or not devices are enrolled <!--748823-->
You can now assign line of business and apps from the store to users whether or not their devices are enrolled with Intune. If the users device is not enrolled with Intune, they must go to the Company Portal website to install it, instead of the Company Portal app. See [What is app management](app-management.md).

### Resolve issue where iOS devices are inactive, or the admin console cannot communicate with them
When users’ devices lose contact with Intune, you can give them new troubleshooting steps to help them regain access to company resources. See [Devices are inactive, or the admin console cannot communicate with them](enrollment-troubleshoot.md#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).

## December 2016 (initial release)

### Telecom expense management integration in Azure portal<!--747605-->
We are now beginning to preview integration with third-party telecom expense management (TEM) services within the Azure portal. You can use Intune to enforce limits on domestic and roaming data usage. We are beginning these integrations with [Saaswedo](http://www.saaswedo.com). To enable this feature in your trial tenant, please [contact Microsoft support](https://docs.microsoft.com/intune-classic/troubleshoot/get-support).

- Deploy and manage apps from a store to iOS, Android, and Windows devices
- Deploy and manage line of business (LOB) apps to iOS, Android, and Windows devices
- Deploy and manage volume-purchased apps to iOS, and Windows devices
- Deploy and manage web apps for Android, iOS, and Windows devices
- iOS managed app configuration profiles
- Configure app protection policies, and deploy line of business apps to devices that are not enrolled with Intune
- VPN profiles, per-app VPN, Wi-Fi, email, and certificate profiles
- Compliance policies
- Conditional access for Azure AD
- Conditional access for On-Premises Exchange
- Device enrollment
- Role-based access control

## Deprecated features in the Azure portal

### Support for row-by-row review of hardware identifiers
The Azure portal does not support row-by-row review of hardware identifiers for IMEI numbers and Apple serial numbers. In the classic Intune console, you can import details from a comma-separated-values (.csv) file and overwrite the existing details for individual hardware identifiers. The Azure portal features a single, streamlined option that automatically overwrites details for all hardware identifiers or ignores new details for existing identifiers.

#### How this affects you
In the Azure portal, you will not be able to decide, row by row, which International Mobile Equipment Identity (IMEI) devices to update. The classic Intune console will continue to support this functionality.

#### How to get ready for this change
We are providing this information in advance so, if it affects you, you can make your support admins aware of this change. This change will coincide with the move to the Azure portal, anticipated for the first half of 2017.


### Support for default Corporate Device Enrollment profiles in Apple DEP
The Azure portal does not support the “default” Corporate Device Enrollment profile for Apple Device Enrollment Program (DEP) device serial numbers. This functionality, available in the classic Intune console, is being discontinued to prevent unintentionally assigned profiles. In the Azure portal, serial numbers synchronized from an Apple DEP account will initially have no Corporate Device Enrollment profile assigned.

#### How this affects you
In the Azure portal, you will not be able to set a default profile policy across all Apple devices. The classic Intune console will continue to support this functionality.

#### How to get ready for this change
We are providing this information in advance so, if it affects you, you can make your support admins aware of this change. This will coincide with the move to the Azure portal, anticipated for the first half of 2017.

### See also
See [What’s New in Microsoft Intune](whats-new.md) for details on recent developments.
