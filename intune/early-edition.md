---
# required metadata

title: Early edition
description:
keywords:
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 06/08/2017
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
ms.custom: intune-classic

---

# The early edition for Microsoft Intune - June 2017

The **early edition** provides a list of features that are coming in upcoming releases of Microsoft Intune. This information is provided on an extremely limited basis and is subject to change. Do not share this information outside of your company. Some features listed here are at risk of not making the cutoff dates and may be delayed until a future release. Other features are being tested in a pilot (flighting) to ensure they're customer-ready. Reach out to your Microsoft product group contact if you have any questions or concerns.

This page is updated periodically. Check back for additional updates.

> [!Note]
>The following changes are under development for Intune. For more information about new hybrid features, check out our [hybrid What’s New page](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).


## What's coming to Intune on the Azure portal

### New app configuration settings for the Intune Managed Browser <!--- 682951 --->

We will add further configurations for the Intune Managed Browser app. You will be able to use an app configuration policy to configure the default home page and bookmarks for the browser.

### Restrict Android device enrollment restriction by OS version <!-- 747620 -->

Intune will support restricting Android enrollment by operating system version number. Under **Device Type Restriction**, the IT admin will be able to set a platform configuration to restrict enrollment between a minimum and maximum operating system value. Operating system versions must be specified as Major.Minor.Build.Rev, where Minor, Build and Rev are optional.

>[!NOTE]
>This is not a security feature, as compromised devices can misrepresent their operating system version information. This is a best-effort barrier for non-malicious users.

### Android for Work support for Lookout <!-- 1087312 -->

Intune connector with Lookout will support Android for Work devices when using the Lookout for Work app. You will be able to deploy the Lookout app inside or outside the container.

### Support for offline apps from the Windows Store for Business <!--- 777044 --->

Offline apps you purchase from the Windows Store for Business will now be synchronized to the Intune portal. You will then be able to deploy these apps to device groups or user groups. Offline apps are installed by Intune, and not by the store.

### New settings for Windows 10 device restriction profile <!--- 978527,  978550, 978569, 978575, 1050031, 1058611, 1124583 --->

The following settings will be available for Windows 10 device restriction profiles:

- Windows Defender
- Cellular and connectivity
- Locked screen experience
- Privacy
- Search
- Reporting and telemetry
- Windows Spotlight
- Edge browser

### Support for shared iPads with the iOS Classroom app <!-- 1044681, 854689 -->

We will be expanding the support for managing the iOS Classroom app to include students who log in to shared iPads using their managed Apple ID.

### Office 365 ProPlus app available for Windows 10 devices <!--1121362-->

We're adding the new Office 365 ProPlus app type that makes it easy for you to assign Office 365 ProPlus apps to Windows 10 devices. Additionally, you will also be able to install Microsoft Project, and Microsoft Visio, if you own licenses for them. The apps you want will be bundled together and appear as one app in the list of apps in the Intune console.

### Tag corporate-owned devices with serial number <!-- 1215070 -->

Intune will support uploading iOS, macOS, and Android serial numbers as corporate-owned device identifiers. You will not be able to use serial numbers to block personal devices from enrolling at this time because serial numbers are not verified during enrollment. Blocking personal devices by serial number will be released in the near future.

### System Center Operations Manager management pack for Exchange connector <!-- 885457 -->

The System Center Operations Manager management pack for Exchange connector will be available to help you parse the Exchange connector logs. This will give you different ways of monitoring Intune when you need to troubleshoot issues.

### New role-based administration access for Intune admins <!-- 1099990 -->

A new conditional access admin role is being added to view, create, modify, and delete Azure AD Conditional Access policies. Previously, only global admins and security admins had this permission. You can grant Intune admins this role with its permissions so that they have access to conditional access policies.

### App-based conditional access for Microsoft Teams <!-- 1257019 -->

The Microsoft Teams app for iOS and Android will be part of the approved apps for app-based conditional access policies for Exchange and SharePoint Online. You will be able to configure the app through the Intune App Protection blade in the Azure portal to all tenants using app-based conditional access.

## What's coming to Intune apps

### Improved notification for Samsung KNOX startup PINs <!--1087143-->

When end users need to set a start-up PIN on Samsung KNOX devices in order to become compliant with encryption, the notification displayed to end users will bring them to the exact place in the Settings app when the notification is tapped.  Previously, the notification brought the end user to the password change screen.

### Promoting the most current version of the Company Portal for Android <!--1098661-->

End users will see an in-app notification when a new recommended version of the Company Portal app for Android has been released in the app's Notifications screen. This notification will tell users that a "Company Portal update is available." Tapping the notification will open a webpage showing the list of available app stores where they can download the updated version.

### Improvements to app syncing with Windows 10 Creators Update <!-- 676505 -->

The Company Portal for Windows 10 will automatically initiate a sync for app install requests for devices with Windows 10 Creators Update (1703). This will reduce the issue of app installs stalling during the "Pending Sync" state. In addition, users will be able to manually initiate a sync from within the app.

The Company Portal for Windows 10 will also expose a refresh button to allow the user to refresh the content in the app whenever they need.

### New guided experience for Windows 10 Company Portal <!-- 1058938 -->

The Company Portal app for Windows 10 will include a guided Intune walkthrough experience for devices that have not been identified or enrolled. The new experience provides step-by-step instructions that guide the user through registering into Azure Active Directory (required for Conditional Access features) and MDM enrollment (required for device management features). The guided experience will be accessible from the Company Portal home page. Users can continue to use the app if they do not complete registration and enrollment, but will experience limited functionality.

### Improved sign in experience across Company Portal apps for all platforms <!--User Story 1132123-->

We are announcing a change that is coming in the next few months that will improve the sign in experience for the Intune Company Portal apps for Android, iOS, and Windows. The new user experience will automatically appear across all platforms for the Company Portal app when Azure AD makes this change. In addition, users can now sign in to the Company Portal from another device with a generated, single-use code. This is especially useful in cases when users need to sign in without credentials.

You can find screenshots of the previous sign in experience, the new sign in experience with credentials, and the new sign in experience from another device on the [What's new in app UI](whats-new-app-ui.md) page.


## Notices

### Apple to require updates for Application Transport Security <!--748318-->

Beginning in Spring 2017, Apple has announced that they will enforce specific requirements for Application Transport Security (ATS). ATS is used to enforce stricter security on all app communications over HTTPS. This change impacts Intune customers using the iOS Company Portal apps. Review our [Intune support blog](https://aka.ms/compportalats) for more details.

### Direct access to Apple enrollment scenarios <!--951869-->

For Intune accounts created after January 2017, Intune has enabled direct access to Apple enrollment scenarios using the Enroll Devices workload in the Azure Preview portal. Previously, the Apple enrollment preview was only accessible from links in the classic Intune portal. Intune accounts created before January 2017 will require a one-time migration before these features are available in Azure. The schedule for migration has not been announced yet, but details will be made available as soon as possible. We strongly recommend creating a trial account to test out the new experience if your existing account cannot access the preview.

### Plan for change: Intune is changing the Intune Partner Portal experience <!-- 1050016 -->

We are removing the Intune Partner page from manage.microsoft.com beginning with the service update in mid-May 2017.  

If you are a partner administrator, you will no longer be able to view and take action on behalf of your customers from the Intune Partner page, but will instead need to sign in at one of two other partner portals at Microsoft.

Both the [Microsoft Partner Center](https://partnercenter.microsoft.com/) and the [Microsoft Office 365 Partner Admin Center](https://portal.office.com/) will allow you to sign into the customer accounts you manage. Moving forward as a partner, please use one of these sites to manage your customers.

### See also
See [What’s New in Microsoft Intune](whats-new.md) for details on recent developments.
