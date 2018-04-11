---
# required metadata

title: Early edition
description:
keywords:
author: ErikjeMS  
ms.author: erikje
manager: dougeby
ms.date: 04/03/2018
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

### New Windows Defender Credential Guard settings added to endpoint protection settings <!--1102252 --><!--from 1802-->

New [Windows Defender Credential Guard](https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard) settings will be added to **Device configuration** > **Profiles** > **Endpoint protection**. The following settings will be added:

- Platform Security Level: specify whether Platform Security Level is enabled at the next reboot. Virtualization-based security requires Secure Boot. Virtualization-based security can optionally be enabled with the use of direct memory access (DMA) protections. DMA protections require hardware support and will only be enabled on correctly configured devices.
- Virtualization Based Security: specify whether virtualization-based security is enabled at the next reboot.
- Windows Defender Credential Guard: turn on Credential Guard with virtualization-based security to help protect credentials at the next reboot when Platform Security Level with Secure Boot and Virtualization Based Security are both enabled. Options available include **Disabled**, **Enabled with UEFI lock**, **Enabled without lock**, and **Not configured**.
  - The "Disabled" option turns off Credential Guard remotely if it was previously turned on with the "Enabled without lock" option.

  - The "Enabled with UEFI lock" option ensures that Credential Guard cannot be disabled with registry key or by using Group Policy. To disable Credential Guard after using this setting, you must set the Group Policy to "Disabled" and remove the security functionality from each computer, with a physically present user, in order to clear configuration persisted in UEFI. As long as the UEFI configuration persists Credential Guard is enabled.

  - The "Enabled without lock" option allows Credential Guard to be disabled remotely by using Group Policy. The devices that use this setting must be running at least Windows 10 (Version 1511).

  - The "Not Configured" option leaves the policy setting undefined. Group Policy does not write the policy setting to the registry, and so it has no impact on computers or users. If there is a current setting in the registry it will not be modified.

### Passcode support for MAM PIN on Android<!-- 1438086 -->

Intune admins will be able to set an application launch requirement to enforce a passcode instead of a numeric MAM PIN. If configured, the user will be required to set and use a passcode when prompted before getting access to MAM-enlightened applications. A passcode is defined as a numeric PIN with at least one special character or upper/lowercase alphabet. Intune supports passcode in a similar way to the existing numeric PIN... being able to set a minimum length, allowing repeat characters and sequences through the admin console. This feature requires the latest version of Company Portal on Android. This feature is already available for iOS.

###  Block camera and screen captures on Android for Work <!-- 1098977 eeready-->
Two new properties will be available to block when you configure device restrictions for Android devices: 
- Camera: Blocks access to all cameras on the device
- Screen capture: Blocks the screen capture, and also prevents the content from being shown on display devices that don't have a secure video output

Applies to Android for Work.

### Line-of-business (LOB) app support for macOS <!-- 1473977 -->
Microsoft Intune will provide the capability to install macOS LOB apps from the Azure portal. You will be able to add a macOS LOB app to Intune after it has been pre-processed by the tool available in GitHub. In the Azure portal, choose **Mobile apps** from the **Intune** blade. On the **Mobile apps** blade, choose **Apps** > **Add**. On the **Add App** blade, select **Line-of-business app**. 

### Support for user-less devices <!-- 1637553 -->
Intune will support the ability to evaluate compliance on a user-less device, such as the Microsoft Surface Hub. Compliance policy can target specific devices. So compliance (and noncompliance) can be determined for devices that don't have an associated user.

### Additions to Local Device Security Options settings <!-- 1403702 -->
You will be able to configure additional Local Device Security Options settings for Windows 10 devices. Additional settings will be available in the areas of Microsoft Network Client, Microsoft Network Server, Network access and security, and Interactive logon. Find these settings in the Endpoint Protection category when you create a Windows 10 device configuration policy.

### Require installation of policies, apps, certificate and network profiles <!-- 1553555 -->
Admins will be able to block end users from accessing the Windows 10 RS4 desktop until Intune installs policies, apps, and certificate and network profiles during the provisioning of AutoPilot devices.

### Rules for removing devices <!-- 1609459 -->
New rules will be available that let you automatically remove devices that haven't checked in for a number of days that you set. To see the new rule, go to the **Intune** pane, select **Devices**, and select **Device removal rules**.

### Prevent consumer apps and experiences on Windows 10 Enterprise RS4 Autopilot devices<!-- 1621980 -->
You will be able to prevent the installation of consumer apps and experiences on your Windows 10 Enterprise RS4 AutoPilot devices. To see this feature, go to **Intune** > **Device enrollment** > **Windows enrollment** > **Windows AutoPilot profiles** > **Create New** > **Enrollment settings**. 

### Advanced Threat Protection integrated with Intune <!-- 1629303 -->
[Advanced Threat Protection (ATP)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/dashboard-windows-defender-advanced-threat-protection) shows the risk level of Windows 10 devices. When Intune evaluates Windows 10 devices for compliance, the ATP risk score is included in this evaluation. You can use ATP with conditional access to help protect your network.

### New enrollment steps for users on devices with macOS High Sierra 10.13.2+ <!--1734567 -->
macOS high Sierra 10.13.2 introduced the concept of "User Approved" MDM enrollment. In the future, approved enrollments will allow Intune to manage some security-sensitive settings. For more information, see Apple's support documentation here: https://support.apple.com/HT208019.

Devices enrolled using the macOS Company Portal will be considered "Not User Approved" unless the end user opens System Preferences and manually provides approval. To this end, the macOS Company Portal now directs users on macOS 10.13.2 and above to go and manually approve their enrollment at the end of the enrollment process. The Intune admin console will report on if an enrolled device is user approved.

### Delete Autopilot devices <!-- 1713650 -->
Intune admins will be able to delete Autopilot devices.

### Built-in All Users and All Devices Group for Android for Work (AFW) app assignment <!-- 1813073 -->
You will be able to leverage the built-in **All Users** and **All Devices** groups for AFW app assignment. For more information, see [Include and exclude app assignments in Microsoft Intune](apps-inc-exl-assignments.md).

### Improved device deletion experience <!--1832333 -->
You'll no longer be required to remove company data or factory reset a device before deleting a device from Intune.

To see the new experience, sign in to Intune and select **Devices** > **All devices** > the name of the device > **Delete**.

 If you still want the wipe/retire confirmation, you can use the standard device lifecycle route by issuing a **Remove company data** and **Factory Reset** prior to **Delete**. 

### Autopilot profiles moving to group targeting <!-- 1877935 -->
Currently, AutoPilot deployment profiles can be assigned to selected devices. Towards the end of April, here’s how you’ll assign these profiles:
- Create (Azure AD) groups containing AutoPilot devices
- Assign desired profiles to an Azure AD group. The AutoPilot profile will now be assigned to AutoPilot devices in that group.

### Play sounds on iOS when in Lost mode <!-- 1629303 -->
When supervised iOS devices are in Mobile Device Management (MDM) [Lost mode](device-lost-mode.md), you can play a sound (**Devices** > **All devices** > select an iOS device > **Overview** > **More**). The sound continues to play until the device is removed from Lost mode , or a user disables sound on the device. Applies to iOS devices 9.3 and newer.

### Use a custom subject name on SCEP certificate <!-- 2064190 -->
You'll be able to use the **OnPremisesSamAccountName** the common name in a custom subject on an SCEP certificate profile. For example, you can use `CN={OnPremisesSamAccountName})`.

### Send diagnostic reports in Company Portal app for macOS <!-- 2216677 -->
The Company Portal app for macOS devices will be updated to improve how users report Intune-related errors. From the Company Portal app, your employees will be able to:
- Upload diagnostic reports directly to the Microsoft developer team.
- Email an incident ID to your company's IT support team.

### Always On VPN for Windows 10 <!--1333666 -->

Currently, [Always On](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-auto-trigger-profile#always-on) can be used on Windows 10 devices by using a custom virtual private network (VPN) profile created using OMA-URI.

With this update, admins will be to enable Always On for Windows 10 VPN profiles directly in Intune in the Azure portal. Always On VPN profiles will automatically connect when:

- Users sign into their devices
- The network on the device changes
- The screen on the device turns back on after being turned off

### Improved error messaging for Apple MDM Push Certificate upload failure <!-- 2172331 -->

The error message will explain that the same Apple ID must be used when renewing an existing MDM certificate.

###  Device profile chart and status list show all devices in a group <!-- 1449153 eeready -->
When you configure a device profile (**Device configuration** > **Profiles**), you choose the device profile, such as iOS. You assign this profile to a group that includes iOS devices and non-iOS devices. The graphical chart count shows that the profile is applied to the iOS *and* the non-iOS devices (**Device configuration** > **Profiles** > select an existing profile > **Overview**). When you select the graphical chart in the **Overview** tab, the **Device status** lists all the devices in the group, instead of only the iOS devices. 

With this update, the graphical chart (**Device configuration** > **Profiles** > select an existing profile > **Overview**) will only show the count for the specific device profile. For example, if the configuration device profile applies to iOS devices, the chart only lists the count of the iOS devices. Selecting the graphical chart, and opening the **Device status** only lists the iOS devices.

While this update is being made, the graphical user chart is temporarily removed. 


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

<!-- 1802 start -->

### New printer settings for education profiles <!-- 1308900 -->

For education profiles, new settings will be available under the **Printers** category: **Printers**, **Default printer**, **Add new printers**.

<!-- the following are present prior to 1801 -->

### App Protection Policies  <!-- 679615 -->
Intune App Protection Policies will offer the ability to create global, default policies to quickly enable protection across all users in the entire tenant.

### Configure an iOS app PIN <!-- 1586774 -->
Soon you will be able to require a PIN for targeted iOS apps. You can configure the PIN requirement and expiration date in days through the Azure portal. When required, a user will be required to set and use a new PIN before getting access to an iOS app. Only iOS apps that have app protection enabled with the Intune App SDK will support this feature.

<!-- the following are present prior to 1711 -->

### Azure Active Directory web sites can require the Intune Managed Browser App and support Single Sign-On for the Managed Browser (Public Preview) <!-- 710595 -->   
Using Azure Active Directory (Azure AD), you will be able to restrict access to web sites on mobile devices to the Intune Managed Browser app. In the managed browser, web site data will remain secure and separate from end-user personal data. In addition, the Managed Browser will support Single Sign-On capabilities for sites protected by Azure AD. Signing in to the Managed Browser, or using the Managed Browser on a device with another app managed by Intune, allows the Managed Browser to access corporate sites protected by Azure AD without the user having to enter their credentials. This functionality applies to sites like Outlook Web Access (OWA) and SharePoint Online, as well as other corporate sites like intranet resources accessed through the Azure App Proxy.




## Notices

There are no active notices at this time.


### See also
See [What’s New in Microsoft Intune](whats-new.md) for details on recent developments.


