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

<!-- 1805 start -->

### Set compliance by device location <!-- 851881 ! -->
In some situations, you may want to restrict access to corporate resources to a specific location, defined by a network connection. You will be able to create a compliance policy (**Device compliance** > **Locations**) based on the IP address of the device. If the device moves outside the IP range, then the device cannot access corporate resources.

### Block app access based on unapproved device vendors and models  <!-- 1425689 ! -->
The Intune IT admin will be able to enforce a specified list of Android manufacturers, and/or iOS models through Intune App Protection Policies. The IT admin can provide a semicolon separated list of manufacturers for Android policies and device models for iOS policies. Intune App Protection Policies are for Android and iOS only. There will be two separate actions that can be performed on this specified list:
- A block from app access on devices that are not specified.
- Or, a selective wipe of corporate data on devices that are not specified. 

The user will be unable to access the targeted application if the requirements through the policy are not met. Based on settings, the user may either be blocked, or selectively wiped of their corporate data within the app. On iOS devices, this feature requires the participation of applications (i.e WXP, Outlook, Managed Browser, Yammer) to integrate the Intune APP SDK for the minimum version settings to be enforced for the targeted applications. This integration happens on a rolling basis and is dependent on the specific application teams. On Android, this feature requires the latest Company Portal.

On end user devices, the Intune client would take action based on a simple matching of the strings specified in the Intune blade for Application Protection Policies. This depends entirely on the value that the device reports. As such, the IT administrator is encouraged to ensure that the intended behavior is accurate. This can be accomplished by testing this setting based on a variety of device manufacturers and models targeted to a small user group.

### Enable kiosk mode on Windows 10 devices <!-- 1560072 ! -->
On Windows 10 devices, you can create a configuration profile and enable kiosk mode (**Windows 10** > **Device Restrictions** > **Kiosk**). **Kiosk (preview)** will be renamed to **Kiosk (obsolete)**. **Kiosk (obsolete)** is no longer recommended for use, and will continue to function until the July update. **Kiosk (obsolete)** will be replaced by **Kiosk**, which will contain the settings to configure Kiosks on Windows 10 RS4 and later.

Applies to Windows 10 and later.

### Access actions for app protection policies <!-- 1483510 EEready -->
You will soon be able to configure app protection policies to explicitly wipe, block, or warn non-compliant devices. The newest action *wipe* removes your company’s corporate data from a device. If a wipe occurs, the device user is notified of both the reason for the wipe and remediation steps. For some settings, like minimum OS version, you will be able to apply multiple actions, such as block and wipe.

### New inventory information for Windows devices <!-- 1333569 eeready -->

For Windows devices, the following inventory information will be available per device in the **Hardware** tab.
- TPM
- Antivirus
- Antispyware
- Firewall
- UAC
- Battery
- Domain name

For more information on how this data is retrieved by the CSP, see the DeviceGuard entires in the [DeviceStatus CSP](https://docs.microsoft.com/en-us/windows/client-management/mdm/devicestatus-csp) article.

### Intune app protection policies and Microsoft Edge <!-- 1818968 -->
The Microsoft Edge browser for mobile devices (iOS and Android) will supports Microsoft Intune app protection policies. Users who sign-in with their corporate Azure AD accounts in the Edge application will be protected by Intune, and the **Require managed browser for web content** policy will allow users to open links in Edge when it is managed.

### Intune and the Microsoft Edge browser <!-- 1818969 -->
The Microsoft Edge browser for mobile devices (iOS and Android) now supports Intune app protection policies. Users who sign-in with their corporate Azure AD accounts in the Edge browser application will be protected by Intune. 

### New language/region setting when configuring OOBE for Autopilot <!-- 1821766 -->
A new configuration setting will be available to set the language and region for Autopilot profiles during the Out of Box Experience.

### New setting for configuring device keyboard <!-- 1821768 -->
A new setting will be available to configure the keyboard for Autopilot profiles during the Out of Box Experience.

### Use TeamViewer to screen share iOS and MacOS devices <!-- 1985547 -->
Currently, you can use TeamViewer to remotely administer [Intune-managed Android and Windows devices](device-profile-android-teamviewer.md).

Administrators will be able to connect to TeamViewer, and start a screen sharing session with iOS and macOS devices. iPhone, iPad, and macOS users can share their screens live with any other desktop or mobile device. 

### New user experience update for the Company Portal website <!--2000968 -->
We’ll be adding new features, based on feedback from customers, to the Company Portal. You'll experience a significant improvement in existing functionality and usability, such as:

- UI improvements throughout the Company Portal website
- Ability to share direct links to apps
- Improved performance for large app catalogs

### Device profile graphical user chart is back <-- 2160133 -->
While improving the numeric counts shown on the device profile graphical chart (**Device configuration** > **Profiles** > select an existing profile > **Overview**), the graphical user chart was temporarily removed.

With this update, the graphical user chart is back, and shown in the Azure portal.

### Assign all users and all devices as scope groups <!-- 2196803 -->
You will be able to assign all users, all devices, and all users and all devices in scope groups.



<!-- 1804 start -->

### Additions to Local Device Security Options settings <!-- 1403702 -->
You will be able to configure additional Local Device Security Options settings for Windows 10 devices. Additional settings will be available in the areas of Microsoft Network Client, Microsoft Network Server, Network access and security, and Interactive logon. Find these settings in the Endpoint Protection category when you create a Windows 10 device configuration policy.

### Require installation of policies, apps, certificate and network profiles <!-- 1553555 -->
Admins will be able to block end users from accessing the Windows 10 RS4 desktop until Intune installs policies, apps, and certificate and network profiles during the provisioning of AutoPilot devices.

### Rules for removing devices <!-- 1609459 -->
New rules will be available that let you automatically remove devices that haven't checked in for a number of days that you set. To see the new rule, go to the **Intune** pane, select **Devices**, and select **Device removal rules**.

### Prevent consumer apps and experiences on Windows 10 Enterprise RS4 Autopilot devices<!-- 1621980 -->
You will be able to prevent the installation of consumer apps and experiences on your Windows 10 Enterprise RS4 AutoPilot devices. To see this feature, go to **Intune** > **Device enrollment** > **Windows enrollment** > **Windows AutoPilot profiles** > **Create New** > **Enrollment settings**. 


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


