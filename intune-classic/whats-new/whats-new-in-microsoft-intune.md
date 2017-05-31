---
# required metadata

title: What's new | Microsoft Docs
description: Find out what’s new in this month’s and past releases of Microsoft Intune
keywords:
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 06/01/2017
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
# What's new in Microsoft Intune - June 2017
Learn what’s new in this release of Microsoft Intune. You can also find out about upcoming changes that you should be planning for, as well as information about past releases.

> [!Note]
> All of these features will eventually be supported for hybrid customers' deployments (Configuration Manager with Intune). For more information about new hybrid features, check out our [hybrid What’s New page](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## New capabilities

### Change your MDM authority without unenrolling managed devices

You can now change your MDM authority without having to contact Microsoft Support, and without having to unenroll and reenroll your existing managed devices. In the Configuration Manager console, you can [change your MDM authority](/sccm/mdm/deploy-use/change-mdm-authority-to-intune-standalone) from Set to Configuration Manager (hybrid) to Microsoft Intune (standalone) or vice versa. 

## What's new in the preview of Intune in the Azure portal 

Throughout the first half of 2017, we've been migrating our full admin experience onto Azure, allowing for powerful and integrated management of core EMS workflows on a modern service platform that’s extensible using Graph APIs.

New tenants have been started to see the public preview of the new admin experience in the Azure portal this month. While in preview state, capabilities and parity with the existing Intune console will be delivered iteratively.

The admin experience in the Azure portal uses the already announced new grouping and targeting functionality; when your existing tenant is migrated to the new grouping experience you will also be migrated to preview the new admin experience on your tenant. In the meantime, if you want to test or look at any of the new functionality until your tenant is migrated, sign up for a new Intune trial account or take a look at [what's new in the preview](/intune/whats-new).

## Notices

### IP addresses for Intune updated <!-- 1175274 -->

An [updated list of DNS names and IP addresses](../get-started/network-bandwidth-use.md) is available for firewall proxy settings.

### Use Azure Active Directory for conditional access <!-- 967947 -->

Conditional access is available in the Azure Active Directory section of the Azure console and provides a more powerful and flexible framework for setting policies for cloud apps like Office 365 Exchange Online and SharePoint Online.  Use the **Conditional access in Azure Active Directory** blade to configure policies instead of the classic Intune console. Existing policies in the classic Intune console will need to be re-created in the Azure console. For more information, see [Create Azure AD conditional access policies](/intune/conditional-access-exchange-create.md#create-azure-ad-conditional-access-policies-in-intune-azure-preview)

### Direct access to Apple enrollment scenarios <!--951869-->

For Intune accounts created after January 2017, Intune has enabled direct access to Apple enrollment scenarios using the Enroll Devices workload in the Azure Preview portal. Previously, the Apple enrollment preview was only accessible from links in the classic Intune portal. Intune accounts created before January 2017 will require a one-time migration before these features are available in Azure. The schedule for migration has not been announced yet, but details will be made available as soon as possible. We strongly recommend creating a trial account to test out the new experience if your existing account cannot access the preview.

### What's coming for Appx in Intune on Azure <!-- 1000270 -->

As part of the migration to Intune on Azure, we are making three appx changes:

1. Adding a new appx app type in the classic Intune console that can only be deployed to MDM-enrolled devices.
2. Repurposing the existing appx app type to only be targeted to PCs managed through the Intune PC agent.
3. Converting all existing appxs into MDM appxs with the migration.

This will not impact any of your existing deployments to devices that are managed through the Intune PC agent. However, after migration, you will not be able to deploy those migrated appxs to any new devices that are managed through the Intune PC agent that were not previously targeted.

After migration, you will need to re-upload the appx again as a PC appx if you want to do new PC deployments. To learn more, see [Appx changes in Intune on Azure](https://aka.ms/appxchange) on the Intune Support team blog.  

### Administration roles being replaced in Azure portal

The existing mobile application management (MAM) administration roles (Contributor, Owner, and Read-Only) used in the Intune classic portal (Silverlight) are being replaced with a full set of new role-based administration controls (RBAC) in the Intune Azure portal. Once you are migrated to the Azure portal, you will need to re-assign your admins to these new administration roles. For more information about RBAC and the new roles, see [Role-based access control for Microsoft Intune](/intune/role-based-access-control).

## What's coming

### Improved sign in experience across Company Portal apps for all platforms <!--User Story 1132123-->

We are announcing a change that is coming in the next few months that will improve the sign in experience for the Intune Company Portal apps for Android, iOS, and Windows. The new user experience will automatically appear across all platforms for the Company Portal app when Azure AD makes this change. In addition, users can now sign in to the Company Portal from another device with a generated, single-use code. This is especially useful in cases when users need to sign in without credentials.

You can find screenshots of the previous sign in experience, the new sign in experience with credentials, and the new sign in experience from another device on the [What's new in app UI](whats-new-in-intune-app-ui.md) page.

### Plan for change: Intune is changing the Intune Partner Portal experience <!-- 1050016 -->

We are removing the Intune Partner page from manage.microsoft.com beginning with the service update in mid-May 2017.  

If you are a partner administrator, you will no longer be able to view and take action on behalf of your customers from the Intune Partner page, but will instead need to sign in at one of two other partner portals at Microsoft.

Both the [Microsoft Partner Center](https://partnercenter.microsoft.com/) and the [Microsoft Office 365 Partner Admin Center](https://portal.office.com/) will allow you to sign into the customer accounts you manage. Moving forward as a partner, please use one of these sites to manage your customers.


### Apple to require updates for Application Transport Security <!--748318-->

Apple has announced that they will enforce specific requirements for Application Transport Security (ATS). ATS is used to enforce stricter security on all app communications over HTTPS. This change impacts Intune customers using the iOS Company Portal apps.

We have made available a version of the Company Portal app for iOS through the Apple TestFlight program that enforces the new ATS requirements. If you would like to try it so you can test your ATS compliance, email <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app">CompanyPortalBeta@microsoft.com</a> with your first name, last name, email address, and company name. Review our [Intune support blog](https://aka.ms/compportalats) for more details.

### See also
* [Microsoft Intune Blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Cloud Platform roadmap](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [What's new in the Azure preview](https://docs.microsoft.com/intune/whats-new)
* [What's new in the Company Portal UI](/intune-classic/whats-new/whats-new-in-company-portal-ui)
* [What's new archive](whats-new-archive.md)
