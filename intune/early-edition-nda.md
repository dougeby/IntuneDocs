---
# required metadata

title: Early edition
description:
keywords:
author: ErikjeMS  
ms.author: erikje
manager: dougeby
ms.date: 11/5/2018
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
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-classic
---

# The early edition for Microsoft Intune - November 2018

> [!Note]
> NDA notification: The following changes are under development for Intune. This information is shared under NDA on a very limited basis. Do not post any of this information on social media or public websites such as Twitter, UserVoice, Reddit, and so on. 

The **early edition** provides a list of features, shared under NDA, that are coming in upcoming releases of Microsoft Intune. This information is provided on a limited basis and is subject to change. Do not tweet, post on UserVoice, or otherwise share this information outside of your company. Some features listed here are at risk of not making the cutoff dates and may be delayed until a future release. Other features are being tested in a pilot (flighting) to ensure they're customer-ready. Reach out to your Microsoft product group contact if you have any questions or concerns.

This page is updated periodically. Check back for additional updates.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## Intune in the Azure portal

<!-- 1811 start -->

### Uninstalling apps on corporate-owned supervised iOS devices <!-- 1281677 -->
You will be able to remove any app on corporate-owned supervised iOS devices. You can remove any app by targeting either user or device groups with an **Uninstall** assignment type. For personal or unsupervised iOS devices, you will continue to be able to remove only apps that were installed using Intune.

### macOS Device Enrollment Program support for Apple School Manager accounts <!--3006133-->
Intune will support using the Device Enrollment Program on macOS devices for Apple School Manager accounts.

### Set custom background in Managed Home Screen app  <!-- 3041945 -->
We'll be adding a setting that lets you customize the background appearance of the Managed Home Screen app on Android Enterprise, multi-app, kiosk mode devices.  To configure the **Custom URL background**, go to Intune in the Azure portal > Device configuration. Select a current device configuration profile or create a new one to edit its kiosk settings.

### New Microsoft Edge browser settings for Windows 10 and later <!-- 3174639 -->
A new setting will be added to help control and manage the Microsoft Edge browser on your devices. For a list of the current settings, see [Device restriction for Windows 10 (and newer)](device-restrictions-windows-10.md#microsoft-edge-browser).

### Intune app protection policies UI update <!-- 3251427 -->

Intune App protection policies allow you to configure various data protection settings for Intune protected apps, such as Microsoft Outlook and Word. We’re changing the setting and button labels to make each easier to understand. The controls will be changed from **yes**/**no** controls to primarily **block**/**allow** and **disable**/**enable** controls, while the labels will also be updated for clarity. The settings will also be reformatted, so the setting and its label are side by side in the control, providing better navigation. The default settings and number of settings will remain the same, but this change will allow the user to understand, navigate, and utilize the settings more easily to apply selected app protection policies.



<!-- 1810 start -->

### Use Microsoft-recommended settings with Security Baselines <!-- 2055484 -->
Intune integrates with other services that focus on security, including Windows Defender ATP and Office 365 ATP. Customers are asking for a common strategy and a cohesive set of end-to-end security workflows across the Microsoft 365 services. Our goal is to align strategies to build solutions that bridge security operations and common administrator tasks. 
In Intune, we aim to accomplish this goal by publishing a set of Microsoft recommended “Security baselines” (**Intune** > **Security baselines**).  An administrator will be able to create security policies directly from these baselines, and then deploy them to their users. They can also customize the best practice recommendations to meet the needs of their organization. Intune makes sure that devices stay in compliance with these baselines, and notifies administrators of users or devices that aren't in compliance.

### Scope tags for apps <!--1081941 -->
You’ll be able to create scope tags to limit access to Intune resources. Add a scope tag to a role assignment and then add the scope tag to a configuration profile. The role will only have access to resources with configuration profiles that have matching scope tags (or no scope tag).
To create a scope tag, choose **Intune roles** > **Scope (Tags)** > **Create**.
To add a scope tag to a role assignment, choose **Intune roles** > **All roles** > **Policy and Profile Manager** > **Assignments** > **Scope (Tags)**.
To add a scope tag to a configuration profile, choose **Device configuration** > **Profiles** > choose a profile > **Properties** > **Scope (Tags)**.

### Tenant Health dashboard <!-- 1124854 -->
The Tenant Status page in Intune will provide you with tenant status information in a single place. The page is divided into 4 sections:  
- **Tenant Details**: Contains information, such as your MDM Authority, the total enrolled devices in your tenant, and your license counts. This section also provides the current service release for your tenant.
- **Connector Status**: Contains information for configured connectors, such as Apple VPP, Windows Store for Business, and Certificate connectors. Based on their current state, the connectors are flagged as *Healthy*, *Warning*, or *Unhealthy*.
- **Intune Service Health**: Contains active incidents or outages for your tenant. The information in this section is retrieved directly from the Office Message Center ([https://portal.office.com](https://portal.office.com)).
- **Intune News**: Contains active messages for your tenant, which include things like notifications that your tenant has received the latest Intune features. The information in this section is retrieved directly from the Office Message Center ([https://portal.office.com](https://portal.office.com)).


### Deployed WIP policies without user enrollment <!-- 1434452 -->
Windows Information Protection (WIP) policies will be able to be deployed without requiring MDM users to enroll their Windows 10 device. This configuration allows companies to protect their corporate documents based on the WIP configuration, while allowing the user to maintain management of their own Windows devices. Once documents are protected with a WIP policy, the protected data can be selectively wiped by an Intune administrator. By selecting the user and device, and sending a wipe request, all data that was protected via the WIP policy will become unusable. From the Intune in the Azure portal, select **Mobile app** > **App selective wipe**.


<!-- 1809 start -->  

### App Protection Policy (APP) settings for web data <!-- 2662995 -->
APP policy settings for web content on both Android and iOS devices will be updated to better handle both http and https web links, as well as data transfer via iOS Universal Links and Android App Links.  

<!-- 1808 start -->

### Apple VPP token used by another MDM <!-- 1488946 -->
Intune will detect and show details if an Apple volume-purchased program (VPP) token is in use by both Intune and another MDM.

### Retired devices in the device compliance dashboard <!-- 1981119 -->
In a future update, retired devices will be removed from the device compliance dashboard. This will change your compliance numbers.


### Change in the update process for on-premises connectors <!-- 2277554 -->
Based on feedback from customers, the way updates are made to on-premises connectors will be changed. After you initially install an on-premises connector, updates will happen automatically. This change will begin with the new PFX Certificate Connector for Microsoft Intune and will subsequently roll out to other types of on-premises connectors. 

<!-- 1807 start -->

### Check for Configuration Manager compliance <!-- 2192052 -->
A future update will include a new System Center Configuration Manager compliance setting (**Device compliance** > **Policies** > **Create policy** > **Windows 10**). Configuration Manager sends signals to Intune compliance. Using the Intune setting, you can require all Configuration Manager signals to return "compliant".

For example, you require all software updates to be installed on devices. In Configuration Manager, this requirement has the “Installed” state. If any programs on the device are in unknown state, then the device will be non-compliant in Intune.

Applies to Windows 10 and later

### Alerts for expiring VPP token or Company Portal license running low <!-- 2237572 -->
If you use the Volume Purchase Program (VPP) to pre-provision the Company Portal during DEP enrollment, Intune will alert you when the VPP token is about to expire and when the licenses for the Company Portal are running low.



<!-- the following are present prior to 1711 -->

## Notices

There are no active notices at this time.

### See also
See [What’s New in Microsoft Intune](whats-new.md) for details on recent developments.



