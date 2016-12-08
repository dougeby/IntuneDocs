---
# required metadata

title: Introduction to the Microsoft Intune in the Azure portal preview | Intune Azure preview | Microsoft Docs
description: "Intune Azure preview: Get the basics about Intune, and how it can help you manage your devices."
keywords:
author: robstackmsft
ms.author: robstack
nmanager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Introduction to Microsoft Intune in the Azure portal preview


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Microsoft Intune is moving to the Azure portal and this means that the workflows and functionality you are used to will change.
The new portal offers you a preview of new and updated functionality in the Azure portal where you can manage your organization's' mobile devices, PCs, and apps. 
All Intune functionality will eventually move to Azure, but you can perform certain Intune tasks in the Azure portal today. Because this new experience is in preview, some functionality might not yet be present in the portal. Review the [What’s new in the preview](#what's-new-in-the-preview?) section for details. 

New product documentation will be released, and continually  updated during the preview. If you have suggestions you'd like to see, please leave feedback in the topic comments. We'd love to hear from you

<!--- You can view the new Intune technical preview console in Azure at [portal.azure.com]. --->

Highlights of the new experience include:

- An integrated console for all your Enterprise Mobility + Security (EMS) components
- An HTML-based console built on web standards
- Microsoft Graph API support to automate many actions
- Azure AD groups to provide compatibility across all your Azure applications

If you are looking for documentation for the existing Intune portal, see [the Intune Documentation Library](https://docs.microsoft.com/en-us/intune/)

## Before you start

To use Intune in the Azure portal, you must have an Intune admin and tenant account. You can sign up for an account [here](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20).

## What's in this library?

The documentation reflects the layout of the Intune portal to make it easier to find the information you need.

<!--- ### Plan and design
Information to help you plan and design your Intune environment.
[Read more](/intune-azure/plan-and-design/get-started) --->
### Enroll devices
How to get your devices managed by Intune.
[Read more](/intune-azure/enroll-devices/what-is)
### Manage devices
Get to know the devices you manage with inventory, and reports.
[Read more](/intune-azure/manage-devices/what-is)
### Manage users
Learn about the users of devices you manage.
[Read more](/intune-azure/manage-users/what-is)
### Manage apps
Contains information about how to publish, manage, configure, and protect apps.
[Read more](/intune-azure/manage-apps/what-is-app-management)
### Configure devices
Contains information about the profiles you can use to configure settings and features on devices you manage.
[Read more](/intune-azure/configure-devices/what-are-device-profiles) 
### Set device compliance
Define a compliance level for your devices, then report about any devices which are not compliant
[Read more](/intune-azure/set-device-compliance/what-is-device-compliance)
### Conditional access
Restrict access to Exchange services depending on conditions you specify.
[Read more](/intune-azure/conditional-access/what-is-conditional-access)


## What's new in the preview?

As the public preview progresses, and more features are added, we'll let you know about them here.

### December 2016 (initial release)

- Deploy and manage apps from a store to iOS, Android, and Windows devices
- Deploy and manage line of business (LOB) apps to iOS, Android, and Windows devices
- Deploy and manage volume-purchased apps to iOS, and Windows devices
- Deploy and manage web apps for Android, iOS, and Windows devices
- Volume-purchased apps for iOS (business and education)
- iOS managed app configuration profiles
- Configure app protection policies, and deploy line of business apps to devices that are not enrolled with Intune
- VPN profiles, per-app VPN, Wi-Fi, email, and certificate profiles
- Compliance policies
- Conditional access for Azure AD
- Conditional access for On-Premises Exchange
- Device enrollment
- Role-based access control
