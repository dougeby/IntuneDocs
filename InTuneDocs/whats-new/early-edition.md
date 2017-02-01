---
# required metadata

title: Early edition | Microsoft Docs
description:
keywords:
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/02/2017
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

# The early edition - February 2017

The **Early Edition** provides a list of features that are coming in upcoming releases of Microsoft Intune. This information is provided under NDA on an extremely limited basis and is subject to change. Some features listed here are at risk of not making the cutoff dates and may be delayed until a future release. Other features are being tested in a pilot (flighting) to ensure they're customer-ready. Please reach out to your Intune/PM buddy if you have any questions or concerns.

This page is updated periodically. Check back for additional updates.

> [!Note]
> The following changes are under development for Intune. All of these features will eventually be supported for hybrid customers' deployments (Configuration Manager with Intune). For more information about new hybrid features, check out our [hybrid What’s New page](https://docs.microsoft.com/en-us/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## New Capabilities

### Updated enrollment process for Windows BYOD scenarios <!--713927-->


### Modernizing the Company Portal website <!--753980-->
The Company Portal website will support apps that are targeted to users who do not have managed devices. The website will align with other Microsoft products and services by using a new contrasting color scheme, dynamic illustrations, and a "hamburger menu," ![Small image of the hamburger menu that is now added at the top left corner of the Company Portal website](../media/CP_hamburger_menu.png) which will contain helpdesk contact details and information on existing managed devices. The landing page will be rearranged to emphasize apps that are available to users, with carousels for Featured and Recently Updated apps. You can find before and after images available on the [What's new in the Company Portal UI page](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui).

### View all actions on managed devices <!--677150-->
A new __Device actions__ report shows who has performed remote actions like factory reset on devices, and additionally shows the status of that action.

## Notices

### Group migration will not require any updates to groups or policies for iOS devices <!--898837-->
For every Intune device group pre-assigned by a Corporate Device Enrollment profile, a corresponding dynamic device group will be created in AAD based on the Corporate Device Enrollment profile’s name, during the migration to Azure Active Directory device groups. This will ensure the as devices enroll, they will be automatically grouped and received the same policies and apps as the original Intune group.

Once a tenant enters the migration process for grouping and targeting, Intune will automatically create a dynamic AAD group to correspond to an Intune group targeted by a Corporate Device Enrollment profile. If the Intune Admin deletes the targeted Intune group, the corresponding dynamic AAD group will not be deleted. The group's members and the dynamic query will be cleared, but the group itself will remain until the IT Admin removes it up via AAD portal.

Similarly, if the IT Admin changes which Intune group is targeted by a Corporate Device Enrollment profile, Intune will create new dynamic group reflecting the new profile assignment, but will not remove the dynamic group created for the old assignment.

### New MDM server address for Windows devices <!--893007-->
Windows and Windows Phone 8.1+ users attempting to enroll a device will fail if they enter __manage.microsoft.com__ as the MDM server address (if prompted). The MDM server address is changing from __manage.microsoft.com__ to __enrollment.manage.microsoft.com__. Notify your user to use __enrollment.manage.microsoft.com__ as the MDM server address if prompted for it while enrolling a Windows or and Windows Phone 8.1+ device.

### Bringing material design to the Company Portal app for Android <!--621622-->
Beginning in February, the Company Portal app for Android will follow material design guidelines to create a more modern look and feel. This improved user experience includes:

* __Colors__: tab headers can be colored according to your custom color palette.
* __Interface__: Featured Apps and All Apps buttons have been updated in the Apps tab. The Search button is now a floating action button.
* __Navigation__: All Apps shows a tabbed view of Featured, All and Categories for easier navigation.
* __Service__: My Devices and Contact IT tabs have improved readability.

<!--You can find before and after images on the [What's new in the Company Portal UI page](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui).-->

## Public preview of the new Intune admin experience on Azure <!--736542-->

In early calendar year 2017 we will be migrating our full admin experience onto Azure, allowing for powerful and integrated management of core EMS workflows on a modern service platform that’s extensible using Graph APIs.

New trial tenants will start to see the public preview of the new admin experience in the Azure portal this month. While in preview state, capabilities and parity with the existing Intune console will be delivered iteratively.

The admin experience in the Azure portal will use the already announced new grouping and targeting functionality; when your existing tenant is migrated to the new grouping experience you will also be migrated to preview the new admin experience on your tenant. In the meantime, if you want to test or look at any of the new functionality until your tenant is migrated, sign up for a new Intune trial account or take a look at the [new documentation](https://docs.microsoft.com/en-us/intune-azure/introduction/what-is-microsoft-intune).

If you have any questions about the timeline for your tenant’s migration, contact our migration team at [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

### February 2017

#### Custom app categories <!--748805-->
You can now create, edit, and assign categories for apps you add to Intune. Currently, categories can only be specified in English.
See [How to add an app to Intune](/intune-azure/manage-apps/add-apps).

#### Display device categories <!--814654-->
You can now view the device category as a column in the device list. You can also edit the category from the properties section of the device properties blade.

### January 2017

#### Custom app categories <!--748805-->
You can now create, edit, and assign categories for apps you add to Intune. Currently, categories can only be specified in English.

#### Assign line of business apps whether or not devices are enrolled <!--748803-->
You can now assign line of business and apps from the store to users whether or not their devices are enrolled with Intune. If the users device is not enrolled with Intune, they must go to the Company Portal website to install it, instead of the Company Portal app.

### December 2016

#### Telecom expense management integration in public preview of Azure portal<!--747605-->
We are now beginning to preview integration with third-party telecom expense management (TEM) services within the Azure portal. You can use Intune to enforce limits on domestic and roaming data usage. We are beginning these integrations with [Saaswedo](http://www.saaswedo.com). To enable this feature in your trial tenant, please [contact Microsoft support](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

### See also
See [What’s New in Microsoft Intune](whats-new-in-microsoft-intune.md) for details on recent developments.
