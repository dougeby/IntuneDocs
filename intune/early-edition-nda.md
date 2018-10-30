---
# required metadata

title: Early edition
description:
keywords:
author: ErikjeMS  
ms.author: erikje
manager: dougeby
ms.date: 10/24/2018
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

# The early edition for Microsoft Intune - October 2018

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

<!-- 1810 start -->

### Use Microsoft-recommended settings with Security Baselines <!-- 2055484 -->
Intune integrates with other services that focus on security, including Windows Defender ATP and Office 365 ATP. Customers are asking for a common strategy and a cohesive set of end-to-end security workflows across the Microsoft 365 services. Our goal is to align strategies to build solutions that bridge security operations and common administrator tasks. 
In Intune, we aim to accomplish this goal by publishing a set of Microsoft recommended “Security baselines” (**Intune** > **Security baselines**).  An administrator will be able to create security policies directly from these baselines, and then deploy them to their users. They can also customize the best practice recommendations to meet the needs of their organization. Intune makes sure that devices stay in compliance with these baselines, and notifies administrators of users or devices that aren't in compliance.

### Autopilot support for hybrid Azure Active Directory joined devices <!-- 1048100 -->
You'll be able to set up hybrid Azure Active Directory joined devices by using Autopilot. Devices must be joined to your organization's network to use the hybrid Autopilot feature.

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

### Support for iOS 12 OAuth in iOS email profiles <!--2155106 -->
Intune's iOS email profiles will support iOS 12 OAuth. To see this feature, choose **Intune** > **Device Configuration** > **Profiles** > **Create profile** > **OAuth**. If this setting is turnd on, two things will happen:
1. Devices that are already targeted will be issued a new profile.
2. End users will be prompted for their credentials again.


<!-- 1809 start -->  

### App Protection Policy (APP) settings for web data <!-- 2662995 -->
APP policy settings for web content on both Android and iOS devices will be updated to better handle both http and https web links, as well as data transfer via iOS Universal Links and Android App Links.  

### Autopilot device sync frequency increasing to every 12 hours <!-- 2753673 -->
Autopilot devices will synchronize every 12 hours instead of every 24 hours.

### Intune landing page updates and node rename <!--2867309 -->
Updates to the Intune landing page will include new and changed monitoring tiles and charts for better data visualization. The **Mobile apps** node will change to **Client apps**.

### Increased end-user access using the Company portal app <!-- 772203 -->
End users will be able to access key account actions, such as password reset and their AAD profile, from the Company portal app.  

<!-- 1808 start -->

### Apple VPP token used by another MDM <!-- 1488946 -->
Intune will detect and show details if an Apple volume-purchased program (VPP) token is in use by both Intune and another MDM.

### iOS and macOS version numbers and build numbers are shown <!-- 1892471 -->
In **Device compliance** > **Device compliance**, the iOS and macOS operating system versions is shown. In a future update, the build number will also be shown for both platforms.

When security updates are released, Apple typically leaves the version number as-is, but updates the build number. By showing the build number, you can easily check if a vulnerability update is installed.

### Retired devices in the device compliance dashboard <!-- 1981119 -->
In a future update, retired devices will be removed from the device compliance dashboard. This will change your compliance numbers.


### Change in the update process for on-premises connectors <!-- 2277554 -->
Based on feedback from customers, the way updates are made to on-premises connectors will be changed. After you initially install an on-premises connector, updates will happen automatically. This change will begin with the new PFX Certificate Connector for Microsoft Intune and will subsequently roll out to other types of on-premises connectors. 

<!-- 1807 start -->

### Improved Company Portal app experience for device enrollment manager users <!-- 675800 -->
When a device enrollment manager (DEM) signs in to the Company Portal app for Windows, the app will only list the DEM's current, running device. This improvement will reduce timeouts that previously occurred when the app tried to load all DEM-enrolled devices.  

### Check for Configuration Manager compliance <!-- 2192052 -->
A future update will include a new System Center Configuration Manager compliance setting (**Device compliance** > **Policies** > **Create policy** > **Windows 10**). Configuration Manager sends signals to Intune compliance. Using the Intune setting, you can require all Configuration Manager signals to return "compliant".

For example, you require all software updates to be installed on devices. In Configuration Manager, this requirement has the “Installed” state. If any programs on the device are in unknown state, then the device will be non-compliant in Intune.

Applies to Windows 10 and later

### Alerts for expiring VPP token or Company Portal license running low <!-- 2237572 -->
If you use the Volume Purchase Program (VPP) to pre-provision the Company Portal during DEP enrollment, Intune will alert you when the VPP token is about to expire and when the licenses for the Company Portal are running low.

<!-- 1806 start -->

### 3rd-party keyboards can be blocked by APP settings on iOS <!-- 1248481 -->
On iOS devices, Intune admins will be able to block the use of 3rd-party keyboards when accessing organization data in policy protected apps. When the Application Protection Policy (APP) is set to block 3rd-party keyboards, the device user will receive a message the first time they interact with corporate data when using a 3rd-party keyboard. All options, other than the native keyboard, will be blocked and device users will not see them. Device users will only see the dialog message once. 

<!-- 1803 start -->

### Updating the Help and Feedback experience on Company Portal app for Android <!--1631531 -->

The Help and Feedback experience on the Company Portal app for Android will be updated to align with best practices for Android apps. The Company Portal app for Android will be updated over the next few months to divide the **Help and Feedback** menu item to distinct **Help** and **Send Feedback** menu items. The **Help** page will feature a **Frequently Asked Questions** section and **Email Support** button to lead end users to upload logs to Microsoft and send email to company support describing the issue. **Send Feedback** will lead the user through a standard Microsoft feedback submission, which will prompt the user to choose whether, "I like something," "I don't like something," or "I have an idea."



<!-- the following are present prior to 1711 -->

## Notices

There are no active notices at this time.

### See also
See [What’s New in Microsoft Intune](whats-new.md) for details on recent developments.



