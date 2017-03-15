---
# required metadata
title: What's new in the Microsoft Intune PreviewtitleSuffix: "Intune Azure preview"
description: Find out what's new in the Intune Azure preview
keywords:
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 03/15/2017
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
ms.custom: intune-azure
---

# What's new in the Microsoft Intune preview

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

As the public preview progresses, and more features are added, we'll let you know about them here.

> [!Note]
> We’re rolling out the changes listed on this page for the Azure portal preview. However, the changes may not be available right away due to how the Intune service is updated.  Several components of the service must be updated sequentially over a period of days, and this process can cause delays in the availability of new portal features. Look for these changes as they roll out later this month. 

## March 2017

### Improvements to Device Actions report <!--677150-->

We’ve made improvements to the Device Actions report to improve performance. Additionally, you can now filter the report by state. For example, you could filter the report to show only device actions that were completed.”

### Actions for non-compliance <!--730266-->

**Actions for non-compliance** is a new feature of compliance policies that lets you take action on devices that are out of compliance. You can specify single or multiple actions and specify the time period at which those actions must occur. For example, you can notify users of non-compliant devices immediately after the devices become non-compliant through email, or you can block non-compliant devices from accessing corporate resources after a 3-day grace period via Conditional Access.

### Custom app categories <!--748805-->

You can now create, edit, and assign categories for apps you add to Intune. Currently, categories can only be specified in English.
See [How to add an app to Intune](/intune-azure/manage-apps/add-apps).

### Assign LOB apps to users with unenrolled devices <!--748823-->

You can now assign line of business apps from the store to users whether or not their devices are enrolled with Intune. If the user's device is not enrolled with Intune, they must go to the Company Portal website to install it, instead of the Company Portal app.

### New compliance reports <!--846671-->

You now have compliance reports that give you the compliance posture of devices in your company and allow you to quickly troubleshoot compliance-related issues encountered by your users. You can view information about

- Overall compliance state of devices
- Compliance state for an individual setting
- Compliance state for an individual policy

You can also use these reports to drill-down into an individual device to view specific settings and policies that affect that device.

You can now create an edition upgrade policy to upgrade devices to the following additional Windows 10 editions:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N

### Direct access to Apple enrollment scenarios <!--951869-->

For Intune accounts created after January 2017, Intune has enabled direct access to Apple enrollment scenarios using the Enroll Devices workload in the Azure Preview portal. Previously, the Apple enrollment preview was only accessible from links in the classic Intune portal. Intune accounts created before January 2017 will require a one-time migration before these features are available in Azure. The schedule for migration has not been announced yet, but details will be made available as soon as possible. We strongly recommend creating a trial account to test out the new experience if your existing account cannot access the preview.


## February 2017

### Ability to restrict mobile device enrollment <!--747600, 795782-->
Intune is adding new enrollment restrictions that control which mobile device platforms are allowed to enroll. Intune separates mobile device platforms as iOS, macOS, Android, Windows and Windows Mobile.

* Restricting mobile device enrollment does not restrict PC client enrollment.  
* For iOS and Android only, there is one additional option to block the enrollment of personally owned devices.

Intune marks all new devices as personal unless the IT admin takes action to mark them as corporate owned, as explained in [this article](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices).

### View all actions on managed devices <!--677150-->
A new __Device Actions__ report shows who has performed remote actions like factory reset on devices, and additionally shows the status of that action. See [What is device management?](https://docs.microsoft.com/intune-azure/manage-devices/what-is).

### Non-managed devices can access assigned apps <!--664691-->
As part of the design changes on the Company Portal website, iOS and Android users will be able to install apps assigned to them as "available without enrollment" on their non-managed devices. Using their Intune credentials, users will be able to log into the Company Portal website and see the list of apps assigned to them. The app packages of the "available without enrollment" apps are made available for download via the Company Portal website. Apps which require enrollment for installation are not affected by this change, as users will be prompted to enroll their device if they wish to install those apps.

### Custom app categories <!--748805-->
You can now create, edit, and assign categories for apps you add to Intune. Currently, categories can only be specified in English.
See [How to add an app to Intune](/intune-azure/manage-apps/add-apps).

### Display device categories <!--814654-->
You can now view the device category as a column in the device list. You can also edit the category from the properties section of the device properties blade. See [How to add an app to Intune](/intune-azure/manage-apps/add-apps).

### Configure Windows Update for Business settings <!--776716-->

Windows as a Service is the new way of providing updates for Windows 10. Starting with Windows 10, any new Feature Updates and Quality Updates will contain the contents of all previous updates. This means that as long as you've installed the latest update, you know that your Windows 10 devices are completely up-to-date. Unlike with previous versions of Windows, you now must install the entire update instead of part of an update.

By using Windows Update for Business, you can simplify the update management experience so that you don’t need to approve individual updates for groups of devices. You can still manage risk in your environments by configuring an update rollout strategy and Windows Update will make sure that updates are installed at right time. Microsoft Intune provides the ability to configure update settings on devices and gives you the ability to defer update installation. Intune doesn’t store the updates, but only the update policy assignment. Devices access Windows Update directly for the updates.Use Intune to configure and manage **Windows 10 update rings**. An update ring contains a group of settings that configure when and how Windows 10 updates get installed. For details, see [Configure Windows Update for Business settings](/intune-azure/configure-devices/how-to-configure-windows-update-for-business).

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
