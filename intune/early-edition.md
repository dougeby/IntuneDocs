---
# required metadata

title: Early edition
description:
keywords:
author: ErikjeMS  
ms.author: erikje
manager: dougeby
ms.date: 03/06/2018
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

# The early edition for Microsoft Intune - March 2018

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

### Enhanced jailbreak detection <!-- 846515 -->

Enhanced jailbreak detection is a new compliance setting that will improve how Intune evaluates jailbroken devices. The setting will cause the device to check-in with Intune more frequently, which will use the device’s location services and will impact battery usage.

### Ability to deploy required line-of-business (LOB) apps to All Users on Windows 10 Desktop devices <!-- 1627835 RS4 -->
Customers will be able to deploy required line-of-business Windows 10 apps to install in device contexts. This will enable these apps to be available to all users on the device. This is only applicable on Windows 10 Desktop devices. 

### Expiring line-of-business (LOB) apps for Microsoft Intune <!-- 748789 -->
In the Azure portal, Intune will alert you to line-of-business apps that are about to expire. Upon uploading a new version of the line-of-business app, Intune will remove the expiration notification from the app list.

### Company Portal enrollment improved <!-- 1874230-->
Users enrolling a device by using the Company Portal on Windows 10 build 1703 and up will be able to complete the first step of enrollment without leaving the app.

### New Management name column <!-- 1333586 -->
A new column named **Management name** will be added to the devices blade. This is an auto-generated, non-editable name assigned per device, based on the following formula: 
- Default name for all devices: <username>_<devicetype>_<enrollmenttimestamp>
- For bulk added devices: <PackageId/ProfileId>_<DeviceType>_<EnrollmentTime> 
 
This is an optional column in the devices blade. It will not be available by default and you can only access it via the column selector. The device name is not affected by this new column.

### New settings for Windows Defender Security Center notifications device configuration profile <!-- 1631906 -->

Three new settings will be added to the Windows Defender Security Center (WDSC) notifications device configuration profile.

Administrators will be able to:

- Hide the Identity pillar
- Hide the Hardware pillar and its sub-settings
- Hide the Ransomware pillar (Onedrive for Business file restoration)

When you hide these pillars from the WDSC app, end users will not be able to configure these settings, and all notifications associated with the hidden components will not be generated.

### MAM policies targeted based on management state <!-- 1665993 -->

You will be able to target MAM policies based on the management state of the device:

- **iOS devices** - you will be able to target unmanaged devices (MAM only) or Intune managed devices.
- **Android devices** - you will be able to target unmanaged devices, Intune managed devices, and Intune managed Android Enterprise Profiles (formerly Android for Work).

### Configure Gatekeeper to control macOS app download source <!-- 1690459-->

You will be able to configure Gatekeeper to protect your devices from apps by controlling where the apps can be downloaded from. You will be able to configure the following download sources: **Mac App Store**, **Mac App Store and identified developers**, or **Anywhere**. You will also be able to configure whether users can install an app using control-click to override these Gatekeeper controls.

These settings can be found under **Device configuration** -> **Create profile** -> **macOS** -> **Endpoint protection**.

### Configure the Mac application firewall <!-- 1690461 -->

You will be able to configure the Mac application firewall. You can use this to control connections on a per-application basis, rather than on a per-port basis. This makes it easier to get the benefits of firewall protection, and helps prevent undesirable apps from taking control of network ports open for legitimate apps.
 
This feature can be found under **Device configuration** -> **Create profile** -> **macOS** -> **Endpoint protection**.

Once you enable the Firewall setting, you can configure the firewall using two strategies:

- Block all incoming connections

   You can block all incoming connections for the targeted devices. If you choose to do this, incoming connections will be blocked for all apps. 

- Allow or block specific apps

   You can allow or block specific apps from receiving incoming connections. You can also enable stealth mode to prevent responses to probing requests.
 
#### More information

- Block all incoming connections

   This blocks all sharing services (such as File Sharing and Screen Sharing) from receiving incoming connections. The system services that are still allowed to receive incoming connections are:
   - configd - implements DHCP and other network configuration services
   - mDNSResponder - implements Bonjour
   - racoon -  implements IPSec

   To use sharing services, ensure **Incoming connections** is set to **Not configured** (not **Block**).

- Stealth mode

   Enable this to prevent the computer from responding to probing requests. The computer still answers incoming requests for authorized apps. Unexpected requests, such as ICMP (ping), are ignored.
 

### Updating the Help and Feedback experience on Company Portal app for Android <!--1631531 -->

We'll be updating the Help and Feedback experience on the Company Portal app for Android to align with best practices for Android apps. We'll be updating the Company Portal app for Android over the next few months to divide the **Help and Feedback** menu item to distinct **Help** and **Send Feedback** menu items. The **Help** page will feature a **Frequently Asked Questions** section and **Email Support** button to lead end users to upload logs to Microsoft and send email to company support describing the issue. **Send Feedback** will lead the user through a standard Microsoft feedback submission, which will prompt the user to choose whether, "I like something," "I don't like something," or "I have an idea."

### Custom Book categories for volume-purchase program (VPP) eBooks <!-- 1488911 -->
You will be able to create custom eBook categories and then assign VPP eBooks to those custom eBook categories. End users can then see the newly created eBook categories and books assigned to the categories.

#### Company Portal for Android visual updates <!--976944 -->

We'll be updating the Company Portal app for Android to follow Android's [Material Design](https://material.io/) guidelines. We'll publish images of the new icons to the [What's new in app UI](whats-new-app-ui.md) article when the app releases. 


<!-- 1802 start -->

### New enrollment failure trend chart and failure reasons table <!-- 1471783 -->

On the Enrollment Overview page, you will be able to view the trend of enrollment failures and the top five causes of failures. By clicking on the chart or table, you will be able to drill into details to find troubleshooting advice and remediation suggestions.

### Customize your Company Portal themes with hex codes <!--1049561 -->

You will be able to customize theme color in the Company Portal apps using hex codes. When you enter your hex code, Intune will determine the text color that provides the highest level of contrast between the text color and the background color per [WCAG 2.0 standards](http://www.w3.org/TR/WCAG20). You can preview both the text color and your company logo against the color in **Mobile apps** > **Company Portal**. 

### New Windows Defender Credential Guard settings added to endpoint protection settings <!--1102252 --> 

New [Windows Defender Credential Guard](https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard] settings will be added to **Device configuration** > **Profiles** > **Endpoint protection**. The following settings will be added: 

- Platform Security Level: specify whether Platform Security Level is enabled at the next reboot. Virtualization-based security requires Secure Boot. Virtualization-based security can optionally be enabled with the use of direct memory access (DMA) protections. DMA protections require hardware support and will only be enabled on correctly configured devices.
- Virtualization Based Security: specify whether virtualization-based security is enabled at the next reboot. 
- Windows Defender Credential Guard: turn on Credential Guard with virtualization-based security to help protect credentials at the next reboot when Platform Security Level with Secure Boot and Virtualization Based Security are both enabled. Options available include **Disabled**, **Enabled with UEFI lock**, **Enabled without lock**, and **Not configured**. 
  - The "Disabled" option turns off Credential Guard remotely if it was previously turned on with the "Enabled without lock" option.

  - The "Enabled with UEFI lock" option ensures that Credential Guard cannot be disabled with registry key or by using Group Policy. To disable Credential Guard after using this setting, you must set the Group Policy to "Disabled" and remove the security functionality from each computer, with a physically present user, in order to clear configuration persisted in UEFI. As long as the UEFI configuration persists Credential Guard is enabled.

  - The "Enabled without lock" option allows Credential Guard to be disabled remotely by using Group Policy. The devices that use this setting must be running at least Windows 10 (Version 1511).

  - The "Not Configured" option leaves the policy setting undefined. Group Policy does not write the policy setting to the registry, and so it has no impact on computers or users. If there is a current setting in the registry it will not be modified.

### Reset passwords for Android O devices <!-- 1238299 -->
You'll be able to reset the passwords for enrolled Android O devices. When you send a "Reset password" request to an Android O device, it sets a new device unlock password or a managed profile challenge to the current user. The password or challenge is sent based on whether the device has a profile owner or a device owner, and immediately takes effect.

### Local device security option settings <!-- 1251887 -->
You will be to enable security settings on Windows 10 devices using the new Local Device Security Option settings. Find these settings in the Endpoint Protection category when you create a Windows 10 device configuration policy.

### New printer settings for education profiles <!-- 1308900 -->

For education profiles, new settings will be available under the **Printers** category: **Printers**, **Default printer**, **Add new printers**. 

### iOS app provisioning configuration <!-- 1581650 -->
You will be able to assign iOS app provisioning profiles to prevent your apps from expiring by including or excluding security groups.

### New Windows Defender Exploit Guard settings <!-- 631893 -->

Six new **Attack Surface Reduction** settings and expanded **Controlled folder access: Folder protection** capabilities will be available. These settings can be found at: Device configuration\Profiles\
Create profile\Endpoint protection\Windows Defender Exploit Guard.

#### Attack Surface Reduction

|Setting name  |Setting options  |Description  |
|---------|---------|---------|
|Advanced ransomware protection|Enabled, Audit, Not configured|Use aggressive ransomware protection.|
|Flag credential stealing from the Windows local security authority subsystem|Enabled, Audit, Not configured|Flag credential stealing from the Windows local security authority subsystem (lsass.exe).|
|Process creation from PSExec and WMI commands|Block, Audit, Not configured|Block process creations originating from PSExec and WMI commands.|
|Untrusted and unsigned processes that run from USB|Block, Audit, Not configured|Block untrusted and unsigned processes that run from USB.|
|Executables that don’t meet a prevalence, age, or trusted list criteria|Block, Audit, Not configured|Block executable files from running unless they meet a prevalence, age, or trusted list criteria.|

#### Controlled folder access

|Setting name  |Setting options  |Description  |
|---------|---------|---------|
|Folder protection (already implemented)|Not configured, Enable, Audit only (already implemented)<br><br> **New**<br>Block disk modification, Audit disk modification|
Protect files and folders from unauthorized changes by unfriendly apps.<br><br>**Enable**: Prevent untrusted apps from modifying or deleting files in protected folders and from writing to disk sectors.<br><br>
**Block disk modification only**:<br>Block untrusted apps from writing to disk sectors. Untrusted apps can still modify or delete files in protected folders.|

### New Windows Defender Application Guard settings <!-- 1631890 -->

- **Enable graphics acceleration**

Administrators will be able to enable a virtual graphics processor for Windows Defender Application Guard. This setting allows the CPU to offload graphics rendering to the vGPU. This can improve performance when working with graphics intense websites or watching video within the container.

- **SaveFilestoHost**

Administrators will be able to enable files to pass from Microsoft Edge running in the container to the host file system. Turning this on will allow users to download files from Microsoft Edge in the container to the host file system.

### Including and excluding app assignment based on groups for Android Enterprise <!-- 1813081 -->
During app assignment and after selecting an assignment type, Android Enterprise (formerly known as Android for Work) will support exclude functionality.

<!-- the following are present prior to 1802 -->

### Targeting compliance policies to devices in device groups <!--1307012 -->

You will be able to target compliance policies to users in user groups. You'll be able to target compliance policies to devices in device groups.

<!-- the following are present prior to 1801 -->

### App Protection Policies  <!-- 679615 -->
Intune App Protection Policies will offer the ability to create global, default policies to quickly enable protection across all users in the entire tenant.

### Configure an iOS app PIN <!-- 1586774 -->
Soon you will be able to require a PIN for targeted iOS apps. You can configure the PIN requirement and expiration date in days through the Azure portal. When required, a user will be required to set and use a new PIN before getting access to an iOS app. Only iOS apps that have app protection enabled with the Intune App SDK will support this feature.

<!-- the following are present prior to 1711 -->

### Azure Active Directory web sites can require the Intune Managed Browser App and support Single Sign-On for the Managed Browser (Public Preview) <!-- 710595 -->   
Using Azure Active Directory (Azure AD), you will be able to restrict access to web sites on mobile devices to the Intune Managed Browser app. In the managed browser, web site data will remain secure and separate from end-user personal data. In addition, the Managed Browser will support Single Sign-On capabilities for sites protected by Azure AD. Signing in to the Managed Browser, or using the Managed Browser on a device with another app managed by Intune, allows the Managed Browser to access corporate sites protected by Azure AD without the user having to enter their credentials. This functionality applies to sites like Outlook Web Access (OWA) and SharePoint Online, as well as other corporate sites like intranet resources accessed through the Azure App Proxy.

<!-- the following are present prior to 1711 -->

### Redirecting macOS users to the new Company Portal app <!--1380728-->   
When an end user logs into the Company Portal website to enroll their macOS device, they will be directed to download the new Company Portal app for macOS to complete the process. This occurs for macOS devices using OS X El Capitan 10.11 or above. 

<!-- the following are present prior to 1709 -->

### Improved error message for when a user reaches the maximum number of devices allowed to enroll <!-- 1270370 -->
Instead of a generic error message, end users with Android devices see a friendly, actionable error message: "You have enrolled the maximum number of devices allowed by your IT admin. Please remove an enrolled device or get help from your IT admin."



## Notices

There are no active notices at this time.



### See also
See [What’s New in Microsoft Intune](whats-new.md) for details on recent developments.


