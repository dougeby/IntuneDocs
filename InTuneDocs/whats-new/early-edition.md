---
# required metadata

title: Early edition | Microsoft Docs
description:
keywords:
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 05/04/2017
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


# The early edition for Microsoft Intune - May 2017

The **Early Edition** provides a list of features that are coming in upcoming releases of Microsoft Intune. This information is provided under NDA on an extremely limited basis and is subject to change. Some features listed here are at risk of not making the cutoff dates and may be delayed until a future release. Other features are being tested in a pilot (flighting) to ensure they're customer-ready. Please reach out to your Intune/PM buddy if you have any questions or concerns.

This page is updated periodically. Check back for additional updates.

> [!Note]
> The following changes are under development for Intune. All of these features will eventually be supported for hybrid customers' deployments (Configuration Manager with Intune). For more information about new hybrid features, check out our [hybrid What’s New page](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## New capabilities

### Improved status messaging in the Company Portal app for iOS <!--744866-->

New, more specific error messages will now be displayed within the Company Portal app for iOS to provide more accessible information about what is happening on devices. These error cases were previously included in a general error message titled "Company Portal Temporarily Unavailable". Additionally, if a user launches the Company Portal on iOS when they do not have an Internet connection, they will now see a persistent status bar on the homepage saying "No Internet Connection."

### Single sign-on support from the Company Portal for iOS to Outlook for iOS <!--834012-->

Users no longer have to sign in to the Outlook app if they are signed in to the Company Portal app for iOS on the same device with the same account. When users launch the Outlook app, they will be able to select their account and automatically sign in. We are also working toward adding this functionality for other Microsoft apps.

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

This will not impact any of your existing deployments to devices that are managed through the Intune PC agent. However, after migration, you will not be able to deploy those migrated appxs to any new devices that are managed through the Intune PC agent that were not previously targeted.

After migration, you will need to re-upload the appx again as a PC appx if you want to do new PC deployments. To learn more, see [Appx changes in Intune on Azure](https://aka.ms/appxchange) on the Intune Support team blog.  


## Public preview of the new Intune admin experience on Azure <!--736542-->

In early calendar year 2017 we will be migrating our full admin experience onto Azure, allowing for powerful and integrated management of core EMS workflows on a modern service platform that’s extensible using Graph APIs.

New trial tenants will start to see the public preview of the new admin experience in the Azure portal this month. While in preview state, capabilities and parity with the existing Intune console will be delivered iteratively.

The admin experience in the Azure portal will use the already announced new grouping and targeting functionality; when your existing tenant is migrated to the new grouping experience you will also be migrated to preview the new admin experience on your tenant. In the meantime, if you want to test or look at any of the new functionality until your tenant is migrated, sign up for a new Intune trial account or take a look at the [new documentation](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune).

### Support for managed configuration options for Android apps <!-- 621621 -->

Android apps in the Play store that support managed configuration options can be configure by Intune.  This feature lets IT view the list of configuration values supported by an app, and provides a guided, first-class UI to allow them to configure those values.

### Remote assistance for Android devices <!-- 675418 -->

Intune will use the [TeamViewer](https://www.teamviewer.com) software, purchased separately, to enable you to give remote assistance to your users who are running Android devices.

###  New Web content filter policy for iOS devices <!-- 723832 -->

You can control which websites users of iOS devices can visit using one of the following two methods:

  - Add permitted, and blocked URLs using Apples built-in web content filter.
  - Allow only specified websites to be accessed by the Safari browser. Bookmarks will be created in Safari for each site you specify.

### See also
See [What’s New in Microsoft Intune](whats-new-in-microsoft-intune.md) for details on recent developments.
