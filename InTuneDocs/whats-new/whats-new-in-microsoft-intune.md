---
# required metadata

title: What's new | Microsoft Docs
description: Find out what’s new in this month’s and past releases of Microsoft Intune
keywords:
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 05/03/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: priyar
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---
# What's new in Microsoft Intune - April 2017
Learn what’s new in this release of Microsoft Intune. You can also find out about upcoming changes that you should be planning for, as well as information about past releases.

> [!Note]
> All of these features will eventually be supported for hybrid customers' deployments (Configuration Manager with Intune). For more information about new hybrid features, check out our [hybrid What’s New page](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## New capabilities

### Improved sign in experience across Company Portal apps for all platforms <!--User Story 1132123-->

We are improving the sign in experience for the Intune Company Portal apps for Android, iOS, and Windows. The new user experience will automatically appear across all platforms for the Company Portal app when Azure AD makes this change. In addition, users can now sign in to the Company Portal from another device with a generated, single-use code. This is especially useful in cases when users need to sign in without credentials.

You can find screenshots of the previous sign in experience, the new sign in experience with credentials, and the new sign in experience from another device on the [What's new in app UI](whats-new-in-intune-app-ui.md) page.

### MyApps available for Managed Browser <!--822308, 822303-->

Microsoft MyApps now have better support within the Managed Browser. Managed Browser users who are not targeted for management will be brought directly to the MyApps service, where they can access their admin-provisioned SaaS apps. Users who are targeted for Intune management will continue to be able to access MyApps from the built-in Managed Browser bookmark.

### New icons for the Managed Browser and the Company Portal <!--918433, 918431, 971473-->

The Managed Browser is receiving updated icons for both the Android and iOS versions of the app. The new icon will contain the updated Intune badge to make it more consistent with other apps in Enterprise Mobility + Security (EM+S). You can see the new icon for the Managed Browser on the [what's new in Intune app UI page](whats-new-in-intune-app-ui.md).

The Company Portal is also receiving updated icons for the Android, iOS, and Windows versions of the app to improve consistency with other apps in EM+S. These icons will be gradually released across platforms from April to late May.

### Sign-in progress indicator in Android Company Portal <!--953374-->

An update to the Android Company Portal app shows a sign-in progress indicator when the user launches or resumes the app. The indicator progresses through new statuses, beginning with "Connecting...", then "Signing in...", then "Checking for security requirements..." before allowing the user to access the app. You can see the new screens for the Company Portal app for Android on the [what's new in Intune app UI page](whats-new-in-intune-app-ui.md).

### Block apps from accessing SharePoint Online <!-- 679339 -->

You can now create an app-based conditional access policy to block apps, which don't have app protection policies applied to them, from accessing [SharePoint Online](/InTune/deploy-use/mam-ca-for-sharepoint-online). In the apps-based conditional access scenario, you can specify the apps that you want to have access to SharePoint Online using the Azure portal.

### Improved app install status for the Windows 10 Company Portal app <!--676495-->

New improvements for app installs started in the Windows 10 Company Portal app include: 
-	Faster install progress reporting for MSI packages
-	Faster install progress reporting for modern apps on devices running the Windows 10 Anniversary Update and beyond
-	New progress bar for modern app installs on devices running the Windows 10 Anniversary Update and beyond

You can see the new progress bar on the [what's new in Intune app UI page](whats-new-in-intune-app-ui.md).

### Bulk Enroll Windows 10 devices <!-- 747607 -->

You can now join large numbers of devices that run the Windows 10 Creators update to Azure Active Directory and Intune with Windows Configuration Designer (WCD). To enable [bulk MDM enrollment](/intune/deploy-use/bulk-enroll-windows) for your Azure AD tenant, create a provisioning package that joins devices to your Azure AD tenant using Windows Configuration Designer, and apply the package to corporate-owned devices you'd like to bulk enroll and manage. Once the package is applied to your devices, they will Azure AD join, enroll in Intune, and be ready for your Azure AD users to log on.  Azure AD users are standard users on these devices and receive assigned policies and required apps. Self-service and Company Portal scenarios are not supported at this time.

## Notices

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


## What's new in the public preview of the Intune admin experience on Azure <!--736542-->

In early calendar year 2017 we will be migrating our full admin experience onto Azure, allowing for powerful and integrated management of core EMS workflows on a modern service platform that’s extensible using Graph APIs.

New trial tenants will start to see the public preview of the new admin experience in the Azure portal this month. While in preview state, capabilities and parity with the existing Intune console will be delivered iteratively.

The admin experience in the Azure portal will use the already announced new grouping and targeting functionality; when your existing tenant is migrated to the new grouping experience you will also be migrated to preview the new admin experience on your tenant. In the meantime, if you want to test or look at any of the new functionality until your tenant is migrated, sign up for a new Intune trial account or take a look at the [new documentation](/intune-azure/introduction/whats-new).

> [!Note]
> For the Azure portal preview, we’re rolling out the updates for this month. However, the changes may not be available right away due to how the Intune service is rolled out.  Several components of the service must be updated sequentially before the new portal features are available. Look for changes in the Azure portal preview as they roll out later this month. For the complete list of changes, see [What’s new in the Microsoft Intune preview](/intune-azure/introduction/whats-new).

### Administration roles being replaced in Azure portal

The existing mobile application management (MAM) administration roles (Contributor, Owner, and Read-Only) used in the Intune classic portal (Silverlight) are being replaced with a full set of new role-based administration controls (RBAC) in the Intune Azure portal. Once you are migrated to the Azure portal, you will need to re-assign your admins to these new administration roles. For more information about RBAC and the new roles, see [Role-based access control for Microsoft Intune](/intune-azure/access-control/role-based-access-control).


## What's coming

### Plan for change: Intune is changing the Intune Partner Portal experience <!-- 1050016 -->

We are removing the Intune Partner page from manage.microsoft.com beginning with the service update in mid-May 2017.  

If you are a partner administrator, you will no longer be able to view and take action on behalf of your customers from the Intune Partner page, but will instead need to sign in at one of two other partner portals at Microsoft.

Both the [Microsoft Partner Center](https://partnercenter.microsoft.com/) and the [Microsoft Office 365 Partner Admin Center](https://portal.office.com/) will allow you to sign into the customer accounts you manage. Moving forward as a partner, please use one of these sites to manage your customers. 


### Apple to require updates for Application Transport Security <!--748318-->

Beginning in Spring 2017, Apple has announced that they will enforce specific requirements for Application Transport Security (ATS). ATS is used to enforce stricter security on all app communications over HTTPS. This change impacts Intune customers using the iOS Company Portal apps. Review our [Intune support blog](https://aka.ms/compportalats) for more details.

### See also
* [Microsoft Intune Blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Cloud Platform roadmap](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [What's new in the Azure preview](https://docs.microsoft.com/intune-azure/introduction/whats-new)
* [What's new in the Company Portal UI](https://docs.microsoft.com/intune/whats-new/whats-new-in-company-portal-ui)
* [What's new archive](whats-new-archive.md)
