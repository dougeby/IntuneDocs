---
title: What's new - November 2015 | Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: get-started-article
ms.assetid:
author: Lindavr
---
# What's new in Microsoft Intune

## November 2015
### App management
Intune supports mobile application management (MAM) policies that help prevent corporate data from being leaked to consumer apps or services. Historically, these policies would only be enforced on mobile apps running on devices that were also enrolled for mobile device management (MDM) into Intune.

With this month's update, Intune is expanding its MAM capabilities to new classes of devices. In addition to devices enrolled into Intune, you can now enforce MAM policies on:
* devices managed by any other device management (MDM) solution
* device that are not enrolled into any device management system, typically bring-your-own (BYO) devices

You can find more information about these new MAM capabilities in the following blog posts:
* [Enhancing managed mobile productivity](http://blogs.technet.com/b/microsoftintune/archive/2015/11/17/enhancing-managed-mobile-productivity.aspx)
* [Announcing new Microsoft Enterprise Mobility capabilities](http://blogs.technet.com/b/microsoftintune/archive/2015/11/17/enhancing-managed-mobile-productivity.aspx)

Additionally, here are some highlights and additional information about Intune's MAM features:
* Corporate data is isolated from consumer data within apps enlightened for Intune including Office Mobile apps, third-party apps that have adopted the Intune SDK, or line-of-business apps wrapped by Intune.
* Company data can be shared (**cut/copy/paste**) across company apps, while preventing the sharing of company data into personal apps. Read [How MAM policies protect app data](https://technet.microsoft.com/library/mt627825.aspx) for more details. This example scenario, [Using Microsoft Word app for work and personal tasks](https://technet.microsoft.com/library/mt627827.aspx), shows how sharing company data into personal apps is prevented.
* Key data loss prevention policies like per-App PIN, save-as controls, and managed data sharing between apps. Read [Create and deploy mobile app management policies with Microsoft Intune](https://technet.microsoft.com/library/mt627829.aspx) to see a list of all the policies.
* Word, Excel, PowerPoint, Outlook, OneNote, and OneDrive for Business all have these new capabilities and can be managed with and without device enrollment. The data loss protection capabilities are natively built into the standard Office apps in the Apple Store or the Google Play store, and do not require app wrapping or sideloading.
* To learn how to get started, see [Get started with mobile app management policies in the Azure portal](https://technet.microsoft.com/library/mt627830.aspx). To learn how to configure and deploy mobile app management policies, see [Create and deploy mobile app management policies with Microsoft Intune](https://technet.microsoft.com/library/mt627829.aspx).
* When end-users authenticate to the app with their corporate credentials, the data loss protection capabilities are automatically set up. The [End-user experience for apps associated with Microsoft Intune mobile app management policies](https://technet.microsoft.com/library/mt627827.aspx) topic has some example scenarios for accessing OneDrive on iOS and Android devices.
* Works on both iOS and Android devices.

The list of [Microsoft apps you can use with Microsoft Intune mobile application management policies](https://technet.microsoft.com/library/dn708489.aspx) has been updated to show the latest apps.

### Device management
 **Mac OS X device management**
With Intune, you can now enroll and manage Mac OS X devices. You can do the following with your Mac OS X devices:
* Enroll devices to be managed by Intune. See [Set up iOS and Mac management with Microsoft Intune](https://technet.microsoft.com/library/dn408185.aspx).
* Control device settings with a general configuration policy. See [Mac OS X configuration policy settings in Microsoft Intune](https://technet.microsoft.com/library/mt627823.aspx).
* Deploy Mac OS X settings you created with the Apple Configurator. See [Mac OS X custom policy settings in Microsoft Intune](https://technet.microsoft.com/library/mt627820.aspx).
* Collect hardware and software inventory from Mac OS X devices. See [Understand your devices with inventory in Microsoft Intune](https://technet.microsoft.com/library/jj733634.aspx).
* Run new reports that display details about the Mac OS X devices you manage. See [Understand Microsoft Intune operations by using reports](https://technet.microsoft.com/library/dn646977.aspx).

**New Edge browser settings for Windows 10 devices**
New settings have been added to the Windows 10 general configuration policy that let you manage settings and features of the Microsoft Edge browser. See [Windows 10 configuration policy settings in Microsoft Intune](https://technet.microsoft.com/library/mt404697.aspx).

**Email profiles**
A new email profiles policy has been added for Windows 10 desktop and Windows 10 mobile devices. See [Manage settings and features on your devices with Microsoft Intune policies](https://technet.microsoft.com/library/dn646984.aspx).

**New compliance policy settings**
The following new security and system policy settings have been added to the list of compliance policies:
* To make sure that Windows 8.1 or later devices that access your company resources have the latest updates installed, use the **Require automatic updates** setting. You can also specify the type of updates to be automatically installed -- either all updates marked as important to be installed, or all updates marked important or recommended. For the full list of compliance policy settings, see [Manage device compliance policies for Microsoft Intune](https://technet.microsoft.com/library/dn705843.aspx).
* The new **Require a password when the device returns from the idle state** setting combined with the existing **Minutes of inactivity before password is required** setting allows you to create a compliance setting that requires the end-user to enter a password to use a device that has been inactive for a certain time.

**New conditional access policy options**
You can apply conditional access policies to **all users** in either new or existing conditional access policies. All users licensed for Intune and Office 365 will be required to enroll their devices, and if the device platform is not supported by Intune, access is blocked for client applications using [Active Directory authentication based sign-in (modern authentication)](https://blogs.office.com/2014/11/12/office-2013-updated-authentication-enabling-multi-factor-authentication-saml-identity-providers/).

You can also specify that the conditional access policy applies to **all platforms**.  Any client application using the [Active Directory authentication based sign-in (modern authentication)](https://blogs.office.com/2014/11/12/office-2013-updated-authentication-enabling-multi-factor-authentication-saml-identity-providers/) is subject to the conditional access policy, and if the platform is not supported by Intune, it will be blocked.

### Changes and updates to Microsoft Company Portal
The following changes have been made to the company portal apps in this release:

* **Android**: A Welcome screen has been added to the Android Company Portal app to help users understand the purpose of the Company Portal app. This screen is intended to reduce downloads of the app by users whose companies are not Intune subscribers.

* **iOS**: Intune now supports the enrollment of Mac OS X devices  by using  the [Company Portal website](https://portal.manage.microsoft.com). For instructions, see [Enroll your Mac OS X device in Intune](https://technet.microsoft.com/library/mt598622.aspx).

* **Company Portal website**: Users who have enrolled their device in Intune can now reset their passcode by using the **Reset Passcode** option on the Company Portal website. Previously, only IT administrators could reset users' passcodes. The  Reset Passcode option is not supported on Windows 8.1 and Windows RT devices, and the option appears only when devices are enrolled in mobile device management (MDM) or MDM with Exchange ActiveSync. For user instructions, see [Reset your passcode](https://technet.microsoft.com/library/mt590895.aspx).

### Changes to Global Admins licensing
In October, we shared that Global Admins (also referred to as Tenant Admins) could continue to do day-to-day administration tasks without a separate Intune or Enterprise Mobility Suite (EMS) license. However, if Global Admins want to use the service, such as to enroll their own device, a corporate device, or use the Intune Company Portal, they will need an Intune or EMS license just like any other user. Below are a few additional details.
* The Intune Company Portal is where end users can:
    * enroll their device
    * view the status of their device
    * download software that a Global Admin has deployed to the organization
    * find links published by the Global Admin for how to contact their IT department

	[Learn about the Company Portal](https://technet.microsoft.com/library/dn646966.aspx#BKMK_CompanyPortal)  and about [ways to customize the Company Portal](https://technet.microsoft.com/library/dn646983.aspx#BKMK_ConfigureCompanyPortal).
* The person who signs up to purchase Intune or EMS on behalf of an organization automatically becomes the first Global Admin in their tenant. This fall, Intune started to auto-assign an Intune or EMS license to that very first Global Admin as part of the move to the [Office 365 Portal](http://portal.office.com/) and retirement of the [Intune Account Portal](http://account.manage.microsoft.com/). Any additional Global Admins added can continue to do day-to-day administration without a separate Intune or EMS license. Acting as an end user and enrolling their own (or corporate) device or downloading software from the company portal would then trigger a need for a license, just like any other user.
* The change will be phased in and will now start in January, 2016.
* For Microsoft Partners, this change should not affect your ability to administer the service on behalf of customers. For end-user tasks, a user will need to have an Intune or EMS license in order to enroll a device and access or download software from the Company Portal.

If you have any questions about this change, feel free to contact your Intune support team:
* [Microsoft Intune support channels](https://technet.microsoft.com/library/jj839713.aspx)
* [Community support](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod)

For general Microsoft Intune feedback, including filing Design Change Requests (DCRs) or bugs, please visit [Intune user voice](https://microsoftintune.uservoice.com/).

## What’s coming
Keep informed about upcoming developments for Intune with the [Cloud Platform roadmap](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&amp;dropValue=Intune).

**Protect your company data using enterprise data protection (EDP)**
When managing Windows 10 devices, Intune will be able to create and deploy configuration policies for Windows 10 enterprise data protection (EDP). EDP can help you restrict and/or alert you to company data sharing. Intune EDP policies will manage the list of apps protected by EDP, enterprise network locations, protection level, and encryption settings. To opt-in to receive preview builds of Windows, consider joining the [Windows Insider Program](https://insider.windows.com/).

**Note**: Enterprise data protection is currently being tested with a number of enterprise customers, and will become available to Windows Insiders soon.

## What's new in Intune documentation -- November 2015
**New content**
* [Mac OS X configuration policy settings in Microsoft Intune](https://technet.microsoft.com/library/mt627823.aspx): How to control device settings and features for Mac OS X devices.
* [Mac OS X custom policy settings in Microsoft Intune](https://technet.microsoft.com/library/mt627820.aspx): How to deploy Mac OS X device settings that you created using the Apple Configurator tool.
* [Configure data loss prevention app policies with Microsoft Intune](https://technet.microsoft.com/library/mt627825.aspx): Contains information about the scenarios that mobile app management policies support and  how the policy works to protect data.
* [Get started with mobile app management policies in the Azure portal](https://technet.microsoft.com/library/mt627830.aspx): What you need to get started using the Azure preview portal for mobile app management policies.
* [Create and deploy mobile app management policies with Microsoft Intune](https://technet.microsoft.com/library/mt627829.aspx): Contains a step-by-step walkthrough of how to create mobile app management policies in the Azure preview portal.
* [Monitor mobile app management policies with Microsoft Intune](https://technet.microsoft.com/library/mt627824.aspx): Information on how you can monitor your mobile app management policies using the Azure preview portal.
* [Microsoft Intune mobile app management policies and iOS Open In](https://technet.microsoft.com/library/mt627821.aspx): Information on how mobile app management policies work with iOS Open In feature.
* [End-user experience for apps associated with Microsoft Intune mobile app management policies](https://technet.microsoft.com/library/mt627827.aspx): What the end-user experience is when using apps associated with mobile app management policy.
* [Wipe managed company app data with Microsoft Intune](https://technet.microsoft.com/library/mt627826.aspx): How you can remove company app data.

**Updated content**
* [Windows 10 configuration policy settings in Microsoft Intune](https://technet.microsoft.com/library/mt404697.aspx): Added new Edge browser settings.
* [Set up iOS and Mac management with Microsoft Intune](http://technet.microsoft.com/library/dn408185.aspx): Added information about how to enroll Mac OS X devices.
* [Understand your devices with inventory in Microsoft Intune](https://technet.microsoft.com/library/jj733634.aspx): Added information about the inventory collected from Mac OS X devices. Also, updated the topic with the latest information for all device platforms.
* [Understand Microsoft Intune operations by using reports](https://technet.microsoft.com/library/dn646977.aspx): Added information about the two new reports used to display information about your managed Mac OS X devices.
* [Manage device compliance policies for Microsoft Intune](https://technet.microsoft.com/library/dn705843.aspx): Added information about the new compliance policies for requiring automatic updates and password requirement when a device returns from idle state.
* [Manage email access with Microsoft Intune](https://technet.microsoft.com/library/dn705841.aspx): Added information about the ability to apply the conditional access  policy to all platforms and all users.
* [Manage SharePoint Online access with Microsoft Intune](https://technet.microsoft.com/library/dn705844.aspx): Added information about the ability to apply conditional access policy to all platforms and all users. -->


### See also
* [Start using Microsoft Intune](start-using-microsoft-intune.md)
* [Microsoft Intune TechNet Library](http://go.microsoft.com/fwlink/?LinkID=247636)
* [Microsoft Intune Product Information](http://go.microsoft.com/fwlink/?LinkID=249135)
* [Microsoft Intune Blog](http://go.microsoft.com/fwlink/?LinkID=273882)
