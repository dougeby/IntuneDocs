---
title: Choose between Intune and MDM for Office 365
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid:
author: robstackmsft
---

# Choose between Intune and MDM for Office 365

|Consideration|MDM for Office 365|[!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)]|
|-----------------|----------------------|---------------------------------------------------------|
|Cost|Included with many [Office 365 commercial subscriptions](http://products.office.com/business/enterprise-productivity-tools).|Requires a [paid subscription for Microsoft Intune](http://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/Purchasing.aspx) or can be purchased with the [Enterprise Mobility Suite](http://www.microsoft.com/en-us/server-cloud/products/enterprise-mobility-suite/Purchasing.aspx).|
|How you manage devices|Manage devices using the [Office 365 admin center](https://support.office.com/article/About-the-Office-365-admin-center-58537702-d421-4d02-8141-e128e3703547).|If you use [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] by itself, you manage devices using the [Intune admin console](what-to-know-before-setting-up-microsoft-intune.html).<br /><br />If you integrate Intune with System Center 2012 Configuration Manager, you use the Configuration Manager console to manage devices on-premises and in the cloud.|
|Devices you can manage|Cloud-based management for iOS, Android, and Windows Phone|Cloud-based management for iOS, Mac OS X, Android, Windows Phone, and Windows PCs|
|Key capabilities|Ensure that Office 365 corporate email and documents can be accessed only on phones and tablets that are managed by your company and that are compliant with your IT policies.<br /><br />Set and manage security policies, like device level pin lock and jailbreak detection, to help prevent unauthorized users from accessing corporate email and data on a device when it is lost or stolen.<br /><br />Remove Office 365 company data from an employee’s device while leaving their personal data in place.<br /><br />For the latest information about Office 365 MDM capabilities, see [capabilities of Built-in Mobile Device Management for Office 365](https://technet.microsoft.com/library/ms.o365.cc.devicepolicysupporteddevice.aspx).|MDM for Office 365 capabilities, plus:<br /><br />Help users securely access corporate resource with certificates, Wi-Fi, VPN, and email profiles.<br /><br />Enroll and manage collections of corporate-owned devices, simplifying policy and app deployment.<br /><br />Deploy your internal line-of-business apps and apps in stores to users.<br /><br />Enable your users to securely access corporate information using the Office mobile and line-of business apps they know, while ensuring security of data by restricting actions like *copy*, *cut*, *paste*, and *save as*, to only those apps managed by [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].<br /><br />Enable secure web browsing using the [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] Managed Browser app.<br /><br />Manage PCs from the cloud with no infrastructure required using [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], or connect [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] to [!INCLUDE[cm5short](../includes/cm5short_md.md)] to manage all of your devices including PCs, Macs, Linux and UNIX servers, and mobile devices from a single management console.|

>[!NOTE] Administrators can manage users and their mobile devices using both Intune and Office 365 concurrently on the same tenant. This lets you decided which solution is the best solution for specific users and their corresponding devices. You can then specify whether a user and his or her devices are managed with Office 365 MDM or the more feature-rich Intune management solution.
