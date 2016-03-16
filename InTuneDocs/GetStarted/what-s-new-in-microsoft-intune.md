---
title: What's new in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: get-started-article
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
author: Lindavr
---
# What's new in Microsoft Intune

## March 2016

### App management

- **Take advantage of iOS "Open-in" management for devices that are enrolled in a third-party MDM solution**
You can use your third-partgity mobile device management (MDM) vendor to take advantage of iOS "Open-In" management. You can set the restrictions in the configuration profile settings and deploy the app using your MDM software. When the user installs the managed app, the restrictions are applied. Read the details: [Microsoft Intune mobile app management policies and iOS Open In](Microsoft%20Intune%20mobile%20app%20management%20policies%20and%20iOS%20Open%20In.md).

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




### What’s coming
Keep informed about upcoming developments for Intune with the [Cloud Platform roadmap](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune).


## Archive
> [!div class="op_single_selector"]
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
