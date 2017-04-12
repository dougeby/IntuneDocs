---
# required metadata

title: Early edition | Microsoft Docs
description:
keywords:
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 04/05/2017
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


# The early edition for Microsoft Intune - April 2017

The **Early Edition** provides a list of features that are coming in upcoming releases of Microsoft Intune. This information is provided under NDA on an extremely limited basis and is subject to change. Some features listed here are at risk of not making the cutoff dates and may be delayed until a future release. Other features are being tested in a pilot (flighting) to ensure they're customer-ready. Please reach out to your Intune/PM buddy if you have any questions or concerns.

This page is updated periodically. Check back for additional updates.

> [!Note]
> The following changes are under development for Intune. All of these features will eventually be supported for hybrid customers' deployments (Configuration Manager with Intune). For more information about new hybrid features, check out our [hybrid What’s New page](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## New capabilities

### Improved app install status for the Windows 10 Company Portal app <!--676495-->

The Windows 10 Company Portal app will now provide app install progress bar for all modern app installs begun from the Company Portal.

### Improved status messaging in the Company Portal app for iOS <!--744866-->

New, more specific error messages will now be displayed within the Company Portal app for iOS to provide more accessible information about what is happening on devices. These error cases were previously included in a general error message titled "Company Portal Temporarily Unavailable". Additionally, if a user launches the Company Portal on iOS when they do not have an Internet connection, they will now see a persistent status bar on the homepage saying "No Internet Connection."

### MyApps available for Managed Browser <!--822308, 822303-->

Microsoft MyApps now have better support within the Managed Browser. Managed Browser users who are not targeted for management will be brought directly to the MyApps service, where they can access their admin-provisioned SaaS apps. Users who are targeted for Intune management will continue to be able to access MyApps from the built-in Managed Browser bookmark.

### New icons for the Managed Browser and the Company Portal <!--918433, 918431-->

The Managed Browser is receiving updated icons for both the Android and iOS versions of the app. The new icon will contain the updated Intune badge to make it more consistent with other apps in Enterprise Mobility + Security (EM+S). You can see the new icon for the Managed Browser on the [what's new in Intune app UI page](whats-new-in-intune-app-ui.md).

The Company Portal is also receiving updated icons for the Android, iOS, and Windows versions of the app to improve consistency with other apps in EM+S. These icons will be gradually released across platforms from April to late May.

### Single sign-on support from the Company Portal for iOS to Outlook for iOS <!--834012-->

Users no longer have to sign in to the Outlook app if they are signed in to the Company Portal app for iOS on the same device with the same account. When users launch the Outlook app, they will be able to select their account and automatically sign in. We are also working toward adding this functionality for other Microsoft apps.

### Sign-in progress indicator in Android Company Portal <!--953374-->

An update to the Android Company Portal app shows a sign-in progress indicator when the user launches or resumes the app. The indicator progresses through new statuses, beginning with "Connecting...", then "Signing in...", then "Checking for security requirements..." before allowing the user to access the app. You can see the new screens for the Company Portal app for Android on the [what's new in Intune app UI page](whats-new-in-intune-app-ui.md). 


## Notices

### Apple to require updates for Application Transport Security <!--748318-->

Beginning in Spring 2017, Apple has announced that they will enforce specific requirements for Application Transport Security (ATS). ATS is used to enforce stricter security on all app communications over HTTPS. This change impacts Intune customers using the iOS Company Portal apps. Review our [Intune support blog](https://aka.ms/compportalats) for more details.

### Direct access to Apple enrollment scenarios <!--951869-->

For Intune accounts created after January 2017, Intune has enabled direct access to Apple enrollment scenarios using the Enroll Devices workload in the Azure Preview portal. Previously, the Apple enrollment preview was only accessible from links in the classic Intune portal. Intune accounts created before January 2017 will require a one-time migration before these features are available in Azure. The schedule for migration has not been announced yet, but details will be made available as soon as possible. We strongly recommend creating a trial account to test out the new experience if your existing account cannot access the preview.

### What's coming for Appx in Intune on Azure <!-- 1000270 -->

As part of the migration to Intune on Azure, we are making three appx changes:

1. Adding a new appx app type in the classic Intune console that can only be deployed to MDM-enrolled devices.
2. Repurposing the existing appx app type to only be targeted to PCs managed through the Intune PC agent.
3. Converting all existing appxs into MDM appxs with the migration.

#### How does this affect me?

This will not impact any of your existing deployments to devices that are managed through the Intune PC agent. However, after migration, you will not be able to deploy those migrated appxs to any new devices that are managed through the Intune PC agent that were not previously targeted.

#### What action do I need to take

After migration, you will need to re-upload the appx again as a PC appx if you want to do new PC deployments. To learn more, see [Appx changes in Intune on Azure](https://aka.ms/appxchange) on the Intune Support team blog.  


## Public preview of the new Intune admin experience on Azure <!--736542-->

In early calendar year 2017 we will be migrating our full admin experience onto Azure, allowing for powerful and integrated management of core EMS workflows on a modern service platform that’s extensible using Graph APIs.

New trial tenants will start to see the public preview of the new admin experience in the Azure portal this month. While in preview state, capabilities and parity with the existing Intune console will be delivered iteratively.

The admin experience in the Azure portal will use the already announced new grouping and targeting functionality; when your existing tenant is migrated to the new grouping experience you will also be migrated to preview the new admin experience on your tenant. In the meantime, if you want to test or look at any of the new functionality until your tenant is migrated, sign up for a new Intune trial account or take a look at the [new documentation](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune).

### Support for managed configuration options for Android apps <!-- 621621 -->

Android apps in the Play store that support managed configuration options can be configure by Intune.  This feature lets IT view the list of configuration values supported by an app, and provides a guided, first-class UI to allow them to configure those values.

### Remote assistance for Android devices <!-- 675418 -->

Intune will use the [TeamViewer](https://www.teamviewer.com) software, purchased separately, to enable you to give remote assistance to your users who are running Android devices.

### New Android policy for complex PINs <!-- 722069 -->

You can set a required password type of Numeric complex in an Android device profile for devices that run Android 5.0 and above.  Use this setting to prevent device users from creating a PIN that contains repeating, or consecutive numbers, like 1111, or 1234.

### Additional support for Android for Work devices

- **Manage password and work profile settings** <!-- 612808 -->

  We’ve added a new Android for Work device restriction policy that lets you manage password and work profile settings on Android for Work devices you manage.

- **Allow data sharing between work and personal profiles** <!-- 1045102 -->

  We've updated the setting **Data sharing between work and personal profiles** in an Android for Work device restriction profile with new options to help you configure data sharing between work and personal profiles.

- **Restrict copy and paste between work and personal profiles** <!-- 1046094 -->

  When you manage Android for Work devices with Intune, copy and paste actions between work and personal apps are allowed. We've now added a custom device profile for Android for Work devices that lets you restrict whether copy and paste actions between work and personal apps are allowed.

### Assign LOB apps to iOS and Android devices <!-- 1057568 -->

You can assign line of business apps for iOS (.ipa files) and Android (.apk files) to users or devices.

###  New policies for iOS devices <!-- 723774, 723815, 723826, 723830, 723832 -->

- **Apps on Home screen** - You can use a device policy to control which apps users see on the Home screen of their iOS device. This policy changes the layout of the Home screen, but does not deploy any apps you specified that are not installed.

- **Connections to AirPrint devices** - You can use an Intune device policy to control which AirPrint devices (network printers) that end users of iOS device can connect to.

- **Connections to AirPlay devices** - You can use an Intune device policy to control which AirPlay devices (like Apple TV) that end users of iOS device can connect to.

- **Custom lock screen message** - You can configure a custom message that users will see on the lock screen of their iOS device, that replaces the default lock screen message.

- **Web content filter** - You can control which websites users of iOS devices can visit using one of the following two methods:

  - Add permitted, and blocked URLs using Apples built-in web content filter.
  - Allow only specified websites to be accessed by the Safari browser. Bookmarks will be created in Safari for each site you specify.


### Restrict push notifications for iOS apps <!-- 723767 -->

In an Intune device restriction profile, you can configure the following notification settings for iOS devices:

- Fully turn on or off notification for a specified app.
- Turn on or off, the notification in the notification center for a specified app.
- Specify the alert type, either **None**, **Banner**, or **Modal Alert**.
- Specify whether badges are allowed for this app.
- Specify whether notification sounds are allowed.

### Configure iOS apps to run in single app mode autonomously <!-- 737837 -->

You can use an Intune device profile to configure iOS devices to run specified apps in autonomous single app mode. When this mode is configured, and the app is run, the device is locked so that it can only run that app. An example of this is when you configure an app that lets users take a test on the device. When the app's actions are complete, or you remove this policy, the device returns to its normal state.

### Configure trusted domains for email and web browsing on iOS devices <!-- 723765 -->

From an iOS device restriction profile, you can configure the following domain settings:

- **Unmarked email domains** - Emails that the user sends or receives which don't match the domains you specify here will be marked as untrusted.

- **Managed web domains** - Documents downloaded from the URLs you specify here will be considered managed (Safari only).  

- **Safari password auto-fill domains** - Users can save passwords in Safari only from URLs matching the patterns you specify here. To use this setting, the device must be in supervised mode and not configured for multiple users. (iOS 9.3+)


### VPP apps available in iOS Company Portal <!-- 748782 -->

You can assign iOS volume-purchased (VPP) apps as **Available** installs to end users. End users will need an Apple Store account to install the app.

### Synchronize eBooks from Apple VPP Store <!-- 800878 -->

You can synchronize books you purchased from the Apple volume-purchase program store with Intune, and assign these to users.

### Multi-user management for Samsung KNOX Standard devices <!-- 971988 -->

Devices that run Samsung KNOX Standard are now supported for multi-user management by Intune. This means that end users can sign in and out of the device with their Azure Active Directory credentials, and the device is centrally managed whether it’s in use or not.  When end users sign-in, they have access to apps and additionally get any policies applied to them. When users sign out, all app data is cleared.

### Additional Windows device restriction settings <!-- 818566 -->

We've added support for additional Windows device restriction settings like additional Edge browser support, device lock screen customization, start menu customizations, Windows Spotlight search set wallpaper, and proxy setting.

### Multi-user support for Windows 10 Creators Update <!-- 822547 -->

We've added support for multi-user management for devices that run the Windows 10 Creators Update and are Azure Active Directory domain-joined. This means that when different users log onto the device with their AAD credentials, they will receive any apps and policies that were assigned to their user name.

### Fresh Start for Windows 10 PCs<!-- 1004830 -->

In this release, we’ve added a new Fresh Start device action for Windows 10 PCs.  When you issue this action, any apps that were installed on the PC are removed, and the PC is automatically updated to the latest version of Windows. This can be used to help remove pre-installed OEM apps that are often delivered with a new PC. You can configure if user data is retained when this device action is issued.

### Additional Windows 10 upgrade paths <!-- 903672 -->

You can now create an edition upgrade policy to upgrade devices to the following additional Windows 10 editions:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N

### Bulk Enroll Windows 10 devices <!-- 747607 -->

You can join large numbers of Windows 10 devices to Azure Active Directory and Intune with IT automation tools. To enable automatic MDM enrollment for your Azure AD tenant, create a provisioning package that joins the device to your Azure AD tenant using Windows Configuration Designer. Apply that package to corporate-owned devices you'd like to bulk enroll and manage.  Once the package is applied, devices connect to Azure AD, enroll in Intune, and are ready for your Azure AD users to log on.

### New MAM settings for PIN and managed storage locations <!-- 58112, 736644 -->

Two new app settings are available to help you with mobile application management (MAM) scenarios:

- **Disable app PIN when device PIN is managed** - Detects if a device PIN is present on the enrolled device, and if so, bypasses the app PIN triggered by the app protection policies. This setting will allow for a reduction in the number of times a PIN prompt is displayed to users opening a MAM-enabled application on an enrolled device. This feature is available for both Android and iOS.

- **Select which storage services corporate data can be saved to** -Allows you to specify which storage locations in which to save corporate data. Users can save to the selected storage location services, which means all other storage location services not listed will be blocked.

  List of supported storage location services:

  - OneDrive
  - Business SharePoint Online
  - Local storage


### See also
See [What’s New in Microsoft Intune](whats-new-in-microsoft-intune.md) for details on recent developments.
