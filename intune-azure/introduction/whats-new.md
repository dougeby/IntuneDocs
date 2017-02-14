---
# required metadata
title: What's new in the Microsoft Intune Preview | Intune Azure preview | Microsoft Docs
description: Intune Azure preview: Find out what's new in the Intune Azure preview
keywords:
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/15/2017
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# What's new in the Microsoft Intune preview


[!INCLUDE[azure_preview](../includes/azure_preview.md)]


As the public preview progresses, and more features are added, we'll let you know about them here.

## February 2017

### Ability to restrict mobile device enrollment <!--747600, 795782-->
Intune is adding new enrollment restrictions that control which mobile device platforms are allowed to enroll. Intune separates mobile device platforms as iOS, macOS, Android, Windows and Windows Mobile.

* Restricting mobile device enrollment does not restrict PC client enrollment.  
* For iOS and Android only, there is one additional option to block the enrollment of personally owned devices.

Intune marks all new devices as personal unless the IT admin takes action to mark them as corporate owned, as explained in [this article](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices).

### View all actions on managed devices <!--677150-->
A new __Device Actions__ report shows who has performed remote actions like factory reset on devices, and additionally shows the status of that action.

### Non-managed devices can access assigned apps <!--664691-->
As part of the design changes on the Company Portal website, iOS and Android users will be able to install apps assigned to them as "available without enrollment" on their non-managed devices. Using their Intune credentials, users will be able to log into the Company Portal website and see the list of apps assigned to them. The app packages of the "available without enrollment" apps are made available for download via the Company Portal website. Apps which require enrollment for installation are not affected by this change, as users will be prompted to enroll their device if they wish to install those apps.

### Custom app categories <!--748805-->
You can now create, edit, and assign categories for apps you add to Intune. Currently, categories can only be specified in English.
See [How to add an app to Intune](/intune-azure/manage-apps/add-apps).

### Display device categories <!--814654-->
You can now view the device category as a column in the device list. You can also edit the category from the properties section of the device properties blade.

## January 2017

### Assign line of business apps whether or not devices are enrolled <!--748823-->
You can now assign line of business and apps from the store to users whether or not their devices are enrolled with Intune. If the users device is not enrolled with Intune, they must go to the Company Portal website to install it, instead of the Company Portal app. See [What is app management](/intune-azure/manage-apps/what-is-app-management).

### Resolve issue where iOS devices are inactive, or the admin console cannot communicate with them
When users’ devices lose contact with Intune, you can give them new troubleshooting steps to help them regain access to company resources. See [Devices are inactive, or the admin console cannot communicate with them](/intune-azure/enroll-devices/troubleshoot-device-enrollment#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).

## December 2016 (initial release)

### Telecom expense management integration in public preview of Azure portal<!--747605-->
We are now beginning to preview integration with third-party telecom expense management (TEM) services within the Azure portal. You can use Intune to enforce limits on domestic and roaming data usage. We are beginning these integrations with [Saaswedo](http://www.saaswedo.com). To enable this feature in your trial tenant, please [contact Microsoft support](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

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
