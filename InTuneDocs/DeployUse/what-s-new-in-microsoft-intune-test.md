---
title: What's new in Microsoft Intune -- March 2016
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: get-started-article
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
author: Lindavr
---
# What's new in Microsoft Intune -- March 2016
## What's new as of March 29, 2016
With the exception of the update to the Windows 10 general configuration policy, all of the features releasing on March 29, 2016, are also supported for hybrid customers (Configuration Manager integrated with Intune). Hybrid support for the Windows 10 general configuration policy update is coming soon. Please note that some of these features may require the latest version of Configuration Manager.

### App management
- **MAM controls to prevent Outlook contacts sync (iOS).** A new setting is available for mobile application management without device enrollment. This setting allows you to prevent an application from syncing contacts to the native address book on iOS devices. When this setting is enabled, the app will no longer be able to save contacts to the native address book. When this setting is disabled, the app will be able to save contacts to the native address book. When you selectively wipe a device, all contacts that have already been saved to the native address book will be removed. This new setting is supported by the Outlook application on iOS devices. For more details about this and other settings, see [Create and deploy MAM policies](https://technet.microsoft.com/en-us/library/dn292747.aspx).

### Access control
- **Skype for Business Online supports conditional access.** You can set a conditional access policy for Skype for Business Online so that it can only be accessed by managed and compliant iOS and Android devices. End users who try to sign in to the Skype for Business mobile app on iOS and Android will be prompted to enroll with Intune as well as fix any non-compliance issues before sign-in can complete. For details, see [Manage access to Skype for Business Online](https://technet.microsoft.com/en-us/library/mt695297.aspx).

### Device management
- **Intune support for iOS 9.3.** On Monday March 21st, Apple announced the availability of iOS 9.3. We have been busy working to ensure that Microsoft Intune is compatible with the latest version of Apple's mobile operating system, and [we are pleased to announce that Intune supports managing iOS 9.3 devices](https://blogs.technet.microsoft.com/microsoftintune/2016/03/23/microsoft-intune-provides-support-for-ios-9-3/).

  All existing Intune features currently available for managing iOS devices will continue to work seamlessly as users upgrade their devices to iOS 9.3. In addition, iOS 9.3 is also supported today for hybrid customers (Configuration Manager integrated with Intune).

- **The Windows 10 general configuration policy now contains settings to manage Windows Defender on enrolled Windows 10 PC's.** For details, see [Windows 10 configuration policy settings in Microsoft Intune](https://technet.microsoft.com/en-us/library/mt404697.aspx.


### Company portal

- **Windows app packages available directly from the Company Portal website.** Users of Windows 8, Windows 8.1, and Windows RT PCs can now install Windows app packages (with the .appx extension) directly from the Company Portal website. Previously, you had to deploy, or users had to install the Company Portal app on their devices to install apps.

- **Users can remotely lock their device from the Company Portal website.** A new Remote Lock option has been added to the Company Portal website to enable users to remotely lock their device from the Portal if their device is lost or stolen. See the [end-user instructions](https://technet.microsoft.com/library/mt590895.aspx/?wt.mc_id=ui#BKMK_iwp_remote_lock). The following table lists the platform support for Remote Lock for Intune Standalone and Intune with Configuration Manager.

|Platform | Support details|
|---------|----------------|
|Android |Supported|
|iOS |Supported|
|Windows 10 Mobile |Supported only if the phone has a passcode set|
|Windows 10 Desktop |Not supported|
|Windows Phone 8.1 |Supported only if the phone has a passcode set|
|Windows Phone 8.0 |Not supported|
|PC (Windows 8.0 and earlier) |Not supported|
|PC (Windows 8.1) |Not supported|

## What's new as of March 10, 2016


### App management

- **Take advantage of iOS "Open-in" management for devices that are enrolled in a third-party MDM solution**

You can use your third-party mobile device management (MDM) vendor to take advantage of iOS "Open-In" management. You can set the restrictions in the configuration profile settings and deploy the app using your MDM software. When the user installs the managed app, the restrictions are applied. Read the details: [Microsoft Intune mobile app management policies and iOS Open In](microsoft-intune-mobile-app-management-policies-and-ios-open-in.md).

This approach has two main benefits:

1. Users are required to log in with their work account before they get access to any corporate data from Cloud Services or other apps. This ensures that mobile app management (MAM) policies are in place when the data is accessed.

2. Managed  email profiles and other managed apps deployed through a third-parter MDM solution can share files and data with the apps that have Intune MAM policies.

- **Manage the Microsoft Outlook app with MAM policies for devices not enrolled in Intune**
You can now manage the Microsoft Outlook app on devices that are not enrolled in Intune with the Intune mobile application management policy. The updated Microsoft Outlook app with the MAM capabilities is available for both [iOS](https://itunes.apple.com/us/app/microsoft-outlook-email-calendar/id951937596?mt=8) and [Android](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook) devices. Use the instructions in the [Create and deploy mobile app management policies](https://technet.microsoft.com/library/mt627829.aspx) topic to create a MAM policy.  

- **Mobile app configuration policies give you more flexibility to specify user details for iOS apps**
You can supply user settings that an iOS app might need when it is opened. For example, you can supply a network port, or a user name. For details, see [enter link description here](Configure%20iOS%20apps%20with%20mobile%20app%20configuration%20policies%20in%20Microsoft%20Intune.md).


- **Deploy Adobe Reader for Microsoft Intune to Intune-managed iOS devices in your enterprise**
The Adobe Reader app for iOS can now be managed on enrolled devices with the Intune mobile application management policy.

- **Microsoft apps that support MAM**
The list of [Microsoft apps you can use with Intune mobile application management policies](Microsoft%20apps%20you%20can%20use%20with%20Microsoft%20Intune%20mobile%20application%20management%20policies.md) has been updated to include the latest apps (for devices that are enrolled with Intune only).

- **Ensure deployed web clips are opened in the managed browser**
You can deploy targeted web clips that can only be opened using the managed browser on iOS and Android devices. For example, you deploy links to corporate resources through the Company Portal, and when users navigate to the links, they open directly into the managed browser where they can be protected by MAM policy. For details, see [Deploy apps to mobile devices](Deploy%20apps%20to%20mobile%20devices%20in%20Microsoft%20Intune.md).


- **Find, manage, and distribute Windows Store for Business apps for Windows 10 devices from the Intune administrator console**
Support for Windows Store for Business is available in Intune to help you find, manage, and distribute apps to the Windows 10 devices you’re managing. Windows Store for Business lets you manage the process of deploying and monitoring these apps from the Intune administrator console—the same console you use to manage your other apps. Specifically, Windows Store for Business manages the content and licensing  of “online licensed apps”. For details, see [Manage apps you purchased from the Windows Store for Business](Manage%20apps%20you%20purchased%20from%20the%20Windows%20Store%20for%20Business%20with%20Microsoft%20Intune.md).

### Device management
- **PFX certificates distribution for iOS devices**
Intune administrators can create and deploy iOS PFX certificates for Wi-Fi, email, and VPN authentication on iOS devices. This feature is already available for Android and Windows 10 devices. For details, see [Enable access to company resources using certificate profiles ](Enable%20access%20to%20company%20resources%20using%20certificate%20profiles%20with%20Microsoft%20Intune.md).


- **Apply apps and policies to different device groups based on user category selection**
Intune administrators can now define custom device categories for users to select from during enrollment. For example, administrators might want their users to specify if they're enrolling a device used for the "Cash Register" or "Delivery Truck" or "Inventory Room." The category selected will cause the device to become a member of an Intune device group, which can be used for deploying different apps and policies to the enrolled device. For details, see [Categorize devices with device group mapping](Categorize%20devices%20with%20device%20group%20mapping%20in%20Microsoft%20Intune.md).

### Changes and updates to Microsoft Company Portal
The following changes have been made to the Company Portal in this release.

**Android Company Portal app**

* When your users launch an app that is managed by mobile application management (MAM), they will see a message notifying them that the app is managed by their company. Users can now tap a “Learn More” link to get [more information](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_use_mgd_apps) here about what “managed apps” means. They can also tap “Don’t Show Again” so that the message no longer appears when they launch the app.
* New screens have been added to guide users through the enrollment process and provide more information about why users should enroll and what IT administrators can and can’t see on their enrolled devices. See the [enrollment instructions](https://technet.microsoft.com/library/mt502762(TechNet.10).aspx#BKMK_andr_enroll_devc) for details.
* Enrollment error messages are now displayed in the Company Portal app. Previously, these messages appeared in the Company Portal website. Making this change means that all error messages now appear in just one place instead of two different places.


**iOS Company Portal app**
* When your users launch an app that is managed by mobile application management (MAM), they will see a message notifying them that the app is managed by their company. Users can now tap a “Learn More” link to get [more information](https://technet.microsoft.com/library/mt598622.aspx#BKMK_ios_use_mgd_apps) here about what “managed apps” means. They can also tap “Don’t Show Again” so that the message no longer appears when they launch the app.
* New screens have been added to guide users through the enrollment process and provide more information about why users should enroll and what IT administrators can and can’t see on their enrolled devices. See the [enrollment instructions](https://technet.microsoft.com/library/mt598622(TechNet.10).aspx#BKMK_enroll_ios_device) for details.
* Enrollment error messages are now displayed in the Company Portal app. Previously, these messages appeared in the Company Portal website. Making this change means that all error messages now appear in just one place instead of two different places.

## What’s coming
Keep informed about upcoming developments for Intune with the [Cloud Platform roadmap](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune).

## Previous Intune releases
> [!div class="op_single_selector"]
- [February 2016](previous-intune-releases.md)
- [January 2016](previous-intune-releases.md)
- [December 2016](previous-intune-releases.md)
- [November 2015](previous-intune-releases.md)
- [October 2015](previous-intune-releases.md)
- [September 2015](previous-intune-releases.md)
- [August 2015](previous-intune-releases.md)
- [July 2015](previous-intune-releases.md)

### See also
* [Start using Microsoft Intune](start-using-microsoft-intune.md)
* [Microsoft Intune TechNet Library](http://go.microsoft.com/fwlink/?LinkID=247636)
* [Microsoft Intune Product Information](http://go.microsoft.com/fwlink/?LinkID=249135)
* [Microsoft Intune Blog](http://go.microsoft.com/fwlink/?LinkID=273882)
