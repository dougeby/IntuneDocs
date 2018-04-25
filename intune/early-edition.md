---
# required metadata

title: Early edition
description:
keywords:
author: ErikjeMS  
ms.author: erikje
manager: dougeby
ms.date: 04/24/2018
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

# The early edition for Microsoft Intune - April 2018

The **early edition** provides a list of features that are coming in upcoming releases of Microsoft Intune. This information is provided on a limited basis and is subject to change. Do not share this information outside of your company. Some features listed here are at risk of not making the cutoff dates and may be delayed until a future release. Other features are being tested in a pilot (flighting) to ensure they're customer-ready. Reach out to your Microsoft product group contact if you have any questions or concerns.

This page is updated periodically. Check back for additional updates.

> [!Note]
>The following changes are under development for Intune. For more information about new hybrid features, check out the [hybrid What’s New page](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## Intune in the Azure portal

<!-- 1804 start -->




### Additions to Local Device Security Options settings <!-- 1403702 -->
You will be able to configure additional Local Device Security Options settings for Windows 10 devices. Additional settings will be available in the areas of Microsoft Network Client, Microsoft Network Server, Network access and security, and Interactive logon. Find these settings in the Endpoint Protection category when you create a Windows 10 device configuration policy.

### Require installation of policies, apps, certificate and network profiles <!-- 1553555 -->
Admins will be able to block end users from accessing the Windows 10 RS4 desktop until Intune installs policies, apps, and certificate and network profiles during the provisioning of AutoPilot devices.

### Rules for removing devices <!-- 1609459 -->
New rules will be available that let you automatically remove devices that haven't checked in for a number of days that you set. To see the new rule, go to the **Intune** pane, select **Devices**, and select **Device removal rules**.

### Prevent consumer apps and experiences on Windows 10 Enterprise RS4 Autopilot devices<!-- 1621980 -->
You will be able to prevent the installation of consumer apps and experiences on your Windows 10 Enterprise RS4 AutoPilot devices. To see this feature, go to **Intune** > **Device enrollment** > **Windows enrollment** > **Windows AutoPilot profiles** > **Create New** > **Enrollment settings**. 

### Send diagnostic reports in Company Portal app for macOS <!-- 2216677 -->
The Company Portal app for macOS devices will be updated to improve how users report Intune-related errors. From the Company Portal app, your employees will be able to:
- Upload diagnostic reports directly to the Microsoft developer team.
- Email an incident ID to your company's IT support team.


<!-- 1803 start -->

#### Multiple Exchange Connector support <!-- 2070451 -->

You'll no longer be limited to one Microsoft Intune Exchange Connector per tenant. Intune will support multiple Exchange Connectors so that you can set up Intune conditional access with multiple on-premises Exchange organizations.

With an Intune on-premises Exchange connector, you can manage device access to your on-premises Exchange mailboxes based on whether a device is enrolled in Intune and complies with Intune device compliance policies. To set up a connector, you download the Intune on-premises Exchange connector from the Azure portal and install it on a server in your Exchange organization. On the Microsoft Intune dashboard, choose **On-premises access**, and then under **Setup**, choose **Exchange ActiveSync connector**. Download the Exchange on-premises connector and install it on a server in your Exchange organization. Now that you're no longer limited to one Exchange connector per tenant, if you have additional Exchange organizations, you can follow this same process to download and install a connector for each additional Exchange organization.

### Support coming for new Cisco AnyConnect client for iOS <!-- 1333708 -->

New VPN profiles created for Cisco AnyConnect for iOS will work with Cisco AnyConnect 4.0.7x and higher. Existing iOS Cisco AnyConnect VPN profiles will be labeled **Cisco Legacy AnyConnect** and will continue to work with Cisco AnyConnect 4.0.5x as they do today.

> [!NOTE]
> This change is only for iOS; there will continue to be only one Cisco AnyConnect option for Android, Android for Work, and macOS.

#### More information

You need to create a new iOS Cisco AnyConnect VPN profile to support the new app because the new Cisco AnyConnect app and Cisco Legacy AnyConnect app are separate apps. If you are managing the AnyConnect client in your environment, you need to deploy the new Cisco AnyConnect app as well. To complete an upgrade, you also need to delete your Cisco Legacy AnyConnect VPN profile and remove the Cisco Legacy AnyConnect app.

Network access control (NAC) integration will not work for the new AnyConnect client in the initial release. We are working with Cisco to provide NAC integration in a future Intune release.

### Ability to deploy required line-of-business (LOB) apps to All Users on Windows 10 Desktop devices <!-- 1627835 RS4 -->
Customers will be able to deploy required line-of-business Windows 10 apps to install in device contexts. This will enable these apps to be available to all users on the device. This is only applicable on Windows 10 Desktop devices.

### Company Portal enrollment improved <!-- 1874230-->
Users enrolling a device by using the Company Portal on Windows 10 build 1703 and up will be able to complete the first step of enrollment without leaving the app.

### Updating the Help and Feedback experience on Company Portal app for Android <!--1631531 -->

We'll be updating the Help and Feedback experience on the Company Portal app for Android to align with best practices for Android apps. We'll be updating the Company Portal app for Android over the next few months to divide the **Help and Feedback** menu item to distinct **Help** and **Send Feedback** menu items. The **Help** page will feature a **Frequently Asked Questions** section and **Email Support** button to lead end users to upload logs to Microsoft and send email to company support describing the issue. **Send Feedback** will lead the user through a standard Microsoft feedback submission, which will prompt the user to choose whether, "I like something," "I don't like something," or "I have an idea."


<!-- the following are present prior to 1801 -->

### App Protection Policies  <!-- 679615 -->
Intune App Protection Policies will offer the ability to create global, default policies to quickly enable protection across all users in the entire tenant.

<!-- the following are present prior to 1711 -->

### Azure Active Directory web sites can require the Intune Managed Browser App and support Single Sign-On for the Managed Browser (Public Preview) <!-- 710595 -->   
Using Azure Active Directory (Azure AD), you will be able to restrict access to web sites on mobile devices to the Intune Managed Browser app. In the managed browser, web site data will remain secure and separate from end-user personal data. In addition, the Managed Browser will support Single Sign-On capabilities for sites protected by Azure AD. Signing in to the Managed Browser, or using the Managed Browser on a device with another app managed by Intune, allows the Managed Browser to access corporate sites protected by Azure AD without the user having to enter their credentials. This functionality applies to sites like Outlook Web Access (OWA) and SharePoint Online, as well as other corporate sites like intranet resources accessed through the Azure App Proxy.




## Notices

There are no active notices at this time.


### See also
See [What’s New in Microsoft Intune](whats-new.md) for details on recent developments.


