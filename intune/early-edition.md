---
# required metadata

title: Early edition
description:
keywords:
author: ErikjeMS  
ms.author: erikje
manager: dougeby
ms.date: 01/24/2018
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

# The early edition for Microsoft Intune - February 2018

The **early edition** provides a list of features that are coming in upcoming releases of Microsoft Intune. This information is provided on a limited basis and is subject to change. Do not share this information outside of your company. Some features listed here are at risk of not making the cutoff dates and may be delayed until a future release. Other features are being tested in a pilot (flighting) to ensure they're customer-ready. Reach out to your Microsoft product group contact if you have any questions or concerns.

This page is updated periodically. Check back for additional updates.

> [!Note]
>The following changes are under development for Intune. For more information about new hybrid features, check out our [hybrid What’s New page](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->

## Intune in the Azure portal


<!-- 1802 start -->


### App Protection Policies  <!-- 679615 -->
Intune App Protection Policies will offer the ability to create global, default policies to quickly enable protection across all users in the entire tenant.

### Intune support for multiple Apple DEP / Apple School Manager accounts <!-- 747685 -->

Intune will support enrolling devices from up to 100 different Apple Device Enrollment Program (DEP) or Apple School Manager accounts. Each token uploaded can be managed separately for enrollment profiles and devices. A different enrollment profile can be automatically assigned per DEP/School Manager token uploaded. If multiple School Manager tokens are uploaded, only one can be shared with Microsoft School Data Sync at a time.

After migration, the beta Graph APIs and published scripts for managing Apple DEP or ASM over Graph will no longer work. New beta Graph APIs are in development and will be released after the migration.

### Windows defender health status and threat status reports <!--854704 -->

Understanding Windows Defender's health and status is key to managing Windows PCs.  Intune will add new reports and actions to the status and health of the Windows Defender agent. Using a status roll up report in the Device Compliance workload, you'll be able to see devices that need any of the following:

- signature update
- restart
- manual intervention
- full scan
- other agent states requiring intervention

In certain cases, remote remediation actions can be taken such as triggering a signature update.  The report also indicates the number of PCs reporting as **Clean**.

A drill-in report for each status category lists the individual PCs that need attention, or those that report as **Clean**.

### Protocol exceptions for applications <!--1035509 eeready-->

You will be able to create exceptions to the Intune Mobile Application Management (MAM) data transfer policy to open specific unmanaged applications. Such applications must be trusted by IT. Other than the exceptions you create, data transfer will still be restricted to applications that are managed by Intune when your data transfer policy is set to **managed apps only**. You can create the restrictions by using protocols (iOS) or packages (Android).

For example, you can add the Webex package as an exception to the MAM data transfer policy. This will allow Webex links in a managed outlook email message to open directly in the Webex application. Data transfer will still be restricted in other unmanaged applications.

### Customize your Company Portal themes with hex codes <!--1049561 eeready-->

You will be able to customize theme color in the Company Portal apps using hex codes. When you enter your hex code, Intune will determine the text color that provides the highest level of contrast between the text color and the background color per [WCAG 2.0 standards](http://www.w3.org/TR/WCAG20). You can preview both the text color and your company logo against the color in **Mobile apps** > **Company Portal**. 

### Select device categories by using the Access Work or School settings <!-- 1058963 --> 
If you've enabled [device group mapping](https://docs.microsoft.com/en-us/intune/device-group-mapping), users on Windows 10 will be prompted to select a device category after enrolling through the **Connect** button in **Settings** > **Accounts** > **Access work or school** or during the out-of-box experience.

### New Windows Defender Credential Guard settings added to endpoint protection settings <!--1102252 --> 

New [Windows Defender Credential Guard](https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard] settings will be added to **Device configuration** > **Profiles** > **Endpoint protection**. The following settings will be added: 

- Platform Security Level: specify whether Platform Security Level is enabled at the next reboot. Virtualization-based security requires Secure Boot. Virtualization-based security can optionally be enabled with the use of direct memory access (DMA) protections. DMA protections require hardware support and will only be enabled on correctly configured devices.
- Virtualization Based Security: specify whether virtualization-based security is enabled at the next reboot. 
- Windows Defender Credential Guard: turn on Credential Guard with virtualization-based security to help protect credentials at the next reboot when Platform Security Level with Secure Boot and Virtualization Based Security are both enabled. Options available include **Disabled**, **Enabled with UEFI lock**, **Enabled without lock**, and **Not configured**. 
  - The "Disabled" option turns off Credential Guard remotely if it was previously turned on with the "Enabled without lock" option.

  - The "Enabled with UEFI lock" option ensures that Credential Guard cannot be disabled with registry key or by using Group Policy. To disable Credential Guard after using this setting, you must set the Group Policy to "Disabled" and remove the security functionality from each computer, with a physically present user, in order to clear configuration persisted in UEFI. As long as the UEFI configuration persists Credential Guard is enabled.

  - The "Enabled without lock" option allows Credential Guard to be disabled remotely by using Group Policy. The devices that use this setting must be running at least Windows 10 (Version 1511).

  - The "Not Configured" option leaves the policy setting undefined. Group Policy does not write the policy setting to the registry, and so it has no impact on computers or users. If there is a current setting in the registry it will not be modified.

### Synchronize and deploy sparsely bundled Windows Store for Business apps <!--1222672 -->
Offline apps purchased from the Windows Store for Business will be synchronized to the Intune portal. You can then deploy these apps to device groups or user groups. Offline apps are installed by Intune rather than the store.

### Reset passwords for Android O devices <!-- 1238299 -->
You'll be able to reset the passwords for enrolled Android O devices. When you send a "Reset password" request to an Android O device, it sets a new device unlock password or a managed profile challenge to the current user. The password or challenge is sent based on whether the device has a profile owner or a device owner, and immediately takes effect.

### Local device security option settings <!-- 1251887 -->
You will be to enable security settings on Windows 10 devices using the new Local Device Security Option settings. Find these settings in the Endpoint Protection category when you create a Windows 10 device configuration policy.

### New printer settings for education profiles <!-- 1308900 -->

For education profiles, new settings will be available under the **Printers** category: **Printers**, **Default printer**, **Add new printers**. 

### New privacy settings for device restrictions <!--1308926 -->

Two new privacy settings will be available for devices:

- **Publish user activities**: Set this to **Block** to prevent shared experiences and discovery of recently used resources in the task switcher.

- **Local activities only**: Set this to **Block** to prevent shared experiences and discovery of recently used resources in task switcher based only on local activity.

### macOS Company Portal support for enrollments that use the Device Enrollment Manager <!-- 1352411 -->

Users will be able to use the Device Enrollment Manager when enrolling with the macOS Company Portal.

#### New settings for the Edge browser <!--1469166 -->

Two new settings will be available for devices with the Edge browser: **Path to favorites file** and **Changes to Favorites**. 

### Windows Information Protection (WIP) encrypted data in Windows search results <!-- 1469193 -->

A new setting in the Windows Information Protection (WIP) policy will allow you to control whether WIP-encrypted data is included in Windows search results.

### Line-of-business (LOB) app support for macOS <!-- 1473977 -->
Intune will provide the capability to install macOS LOB apps. LOB apps are apps where you supply the installation file and use Intune to install the app on the device. As part of macOS LOB app support, you must use the Microsoft Intune App Wrapping Tool for macOS to pre-process macOS line-of-business (LOB) apps.

### Configure resource account settings for Surface Hubs <!-- 1475674 -->

You will be able to remotely configure resource account settings for Surface Hubs.

The resource account is used by a Surface Hub to authenticate against Skype/Exchange so it can join a meeting. 
You will want to create a unique resource account so the Surface Hub can show up in the meeting as the conference room. 
For example, a resource account such as **Conference Room B41/6233**.

> [!NOTE]
> - If you leave fields blank you will override previously configured attributes on the device.
>
> - Resource Account properties can change dynamically on the Surface Hub. For example, if password rotation is on. So, it's possible that the values 
in the Azure console will take some time to reflect the reality on the device. 
>
>   To understand what is currently configured on the Surface Hub, the Resource Account information can be included in hardware inventory 
(which already has a 7 day interval) or as read-only properties. To enhance the accuracy after the remote action has taken place, you can get the state 
of the parameters immediately after running the action to update the account/parameters on the Surface Hub.

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

### See enrollment restrictions per user <!-- 1634444 -->
On the troubleshooting blade, you will be able to see the enrollment restrictions that are in effect for each user.

### Configuring a self-updating mobile MSI app <!-- 1740840 -->
You will be able to configure a known self-updating mobile MSI app to ignore the version check process. This capability is useful to avoid getting into race condition. For instance, this could occur when the app being auto-updated by the app developer and is also being updated by Intune. Both could try to enforce a version of the app on Windows client, which could create a conflict.

### Additions to System Security settings for Windows 10 and later compliance policies <!--1704133 -->

Additions to the Windows 10 compliance settings will be available, including requiring Firewall and Windows Defender Antivirus.

### Including and excluding app assignment based on groups for Android Enterprise <!-- 1813081 -->
During app assignment and after selecting an assignment type, Android Enterprise (formerly known as Android for Work) will support exclude functionality.


### Related sets of app licenses supported in Intune <!-- 1864117 -->
Intune in the Azure portal will support related sets of app licenses as a single app item in the UI. In addition, any Offline Licensed apps synced from Microsoft Store for Business will be consolidated into a single app entry and any deployment details from the individual packages will be migrated over to the single entry. To view related sets of app licenses in the Azure portal, select **App licenses** from the **Mobile apps** blade.

<!-- the following are present prior to 1802 -->

### New option for user authentication for Apple bulk enrollment <!-- 747625 -->
Intune will give you the option to authenticate devices by using the Company Portal app for the following enrollment methods:

- Apple Device Enrollment Program
- Apple School Manager
- Apple Configurator Enrollment

When using the Company Portal option, Azure Active Directory multi-factor authentication can be enforced without blocking these enrollment methods.

When using the Company Portal option, Intune skips user authentication in the iOS Setup Assistant for user affinity enrollment. This means that the device is initially enrolled as a userless device, and so won't receive configurations or policies of user groups. It will only receive configurations and policies for device groups. However, Intune will automatically install the Company Portal app on the Device. The first user to launch and sign in to the Company Portal app will be associated with the device in Intune. At this point the user will receive configurations and policies of their user groups. The user association cannot be changed without re-enrollment.

### Intune support for multiple Apple DEP / Apple School Manager accounts <!-- 747685 -->
Intune will support enrolling devices from up to 100 different Apple Device Enrollment Program (DEP) or Apple School Manager accounts. Each token uploaded can be managed separately for enrollment profiles and devices. A different enrollment profile can be automatically assigned per DEP/School Manager token uploaded. If multiple School Manager tokens are uploaded, only one can be shared with Microsoft School Data Sync at a time.

After migration, the beta Graph APIs and published scripts for managing Apple DEP or ASM over Graph will no longer work. New beta Graph APIs are in development and will be released after the migration.

### Select device categories by using the Access Work or School settings <!-- 1058963 -->
If you've enabled [device group mapping](https://docs.microsoft.com/en-us/intune/device-group-mapping), users on Windows 10 will be prompted to select a device category after enrolling through the **Connect** button in **Settings** > **Accounts** > **Access work or school** or during the out-of-box experience.

### Targeting compliance policies to devices in device groups <!--1307012 -->

You will be able to target compliance policies to users in user groups. You'll be able to target compliance policies to devices in device groups.

### Including and excluding app assignment based on groups <!-- 1406920 -->

During app assignment and after selecting an assignment type, you'll be able to select the groups to include, as well as the groups to exclude.

### Remote "Erase" command support <!-- 1438084 -->

Admins will be able to issue an Erase command remotely.

> [!IMPORTANT]
> The erase command can’t be reversed and should be used with caution.

The erase command removes all data, including the operating system, from a device. It also removes the device from Intune management. No warning is issued to the user and the erasure occurs immediately upon issuing the command.

You will be able to configure a 6-digit recovery PIN. This PIN can be used to unlock the erased device, at which point reinstallation of the operating system will begin. After erasure has started, the PIN appears in a status bar on the device’s overview blade in Intune. The PIN will remain as long as the erasure is underway. After erasure is complete, the device disappears entirely from Intune management. Be sure to record the recovery PIN so that whoever is restoring the device can use it.

### Windows Information Protection (WIP) encrypted data in Windows search results <!-- 1469193 -->

A new setting in the Windows Information Protection (WIP) policy will allow you to control whether WIP-encrypted data is included in Windows search results.

### Website Learning Mode <!-- 1631908 -->

Intune will introduce an extension of Windows Information Protection (WIP) Learning mode. In addition to viewing information about WIP-enabled apps, you will be able to view a summary of the devices that have shared work data with websites. With this information, you can determine which websites should be added to group and user WIP policies.

### Updates to compliance emails <!--1637547 -->

When an email is sent to report a noncompliant device, details about the noncompliant device will be included. The following article will be updated to indicate this fact: [Automate actions for noncompliance](#actions-for-noncompliance).

###  Alerts for expired tokens and tokens that will soon expire <!-- 1639263 -->
The overview page will show alerts for expired tokens and tokens that will soon expire. When you click on an alert for a single token, you'll go to the token's details page.  If you click on alert with multiple tokens, you'll go to a list of all tokens with their status. Admins should renew their tokens before the expiration date.

### Remote printing over a secure network <!-- 1709994  -->
PrinterOn’s wireless mobile printing solutions will enable users to remotely print from anywhere at any time over a secure network. PrinterOn will integrate with the Intune APP SDK for both iOS and Android. You will be able to target app protection policies to this app through the Intune **App protection policies** blade in the admin console. End users will be able to download the app 'PrinterOn for Microsoft' through the Play Store or iTunes to use within their Intune ecosystem.

### Approve the Company Portal app for Android for Work <!--1797090 -->
If your organization uses Android for Work, you'll need to manually approve the Company Portal app for Android so that it will continue to receive automatic updates from the managed Google Play store.

### FaceID on iOS devices <!-- 1807377 -->
Intune app protection policies now support a setting that controls FaceID on iOS devices. This setting is for devices that supports the FaceID functionality (currently only the iPhone X). This setting is separate from the TouchID controls currently supported. Organizations have the ability to choose whether to trust FaceID as a valid PIN prompt as an alternative to the TouchID controls.

### Microsoft Graph API for Intune - General Availability  <!-- 1833289 -->
Intune APIs in Microsoft Graph will provide programmatic access to data and methods for automating administrative actions for the Intune service.  With the **General Availability** of these APIs, customers, partners and developers will be able to leverage the APIs to integrate with in-house or commercial solutions relating to or requiring the support of Intune, or other Microsoft services available through Microsoft Graph.

<!-- the following are present prior to 1801 -->

### App Protection Policies  <!-- 679615 -->
Intune App Protection Policies will offer the ability to create global, default policies to quickly enable protection across all users in the entire tenant.

### Revoking iOS Volume-Purchase Program apps  <!-- 820863 -->
For a given device that has one or more iOS Volume-Purchase Program (VPP) apps, you will be able to revoke the associated device based app license for the device. Revoking an app license will not uninstall the related VPP app from the device. To uninstall a VPP app, you must change the assignment action to **Uninstall**. For more information, see [How to manage iOS apps purchased through a volume-purchase program with Microsoft Intune](vpp-apps-ios.md).

### Revoke licenses for an iOS Volume Purchasing Program token <!-- 820870 -->
You will be able to revoke the license of all iOS Volume Purchasing Program (VPP) apps for a given VPP Token.

### New iOS device action   <!-- 1244701 -->
You can shut down iOS 10.3 supervised devices. This action shuts down the device immediately without warning to the end user. The **Shut down (supervised only)** action can be found at the device properties when you select a device in the **Device** workload.

### Intune provides the Account Move operation  <!-- 1573558, 1579830 -->
The **Account Move** migrates a tenant from one Azure Scale Unit (ASU) to another. The **Account Move** can be used for both customer-initiated scenarios, when you call the Intune support team requesting it, and it can also be a Microsoft-driven scenario where Microsoft needs to make adjustments to the service in the back-end. During the **Account Move**, the tenant enters in read-only mode (ROM). Service operations like enrolling, renaming devices, updating compliance status will fail during the ROM period.



<!-- the following are present prior to 1712 -->
### Assign Office 365 mobile apps to iOS and Android devices using built-in app type <!-- 1332318 -->
The **Built-in** app type will make it easier for you to create and assign Office 365 apps to the iOS and Android devices that you manage. These apps include 0365 apps such as Word, Excel, PowerPoint, and OneDrive. You can assign specific apps to the app type and edit the app information configuration.

### Assignment conflict resolution has changed for iOS store apps <!-- 1480316 -->
End users might experience a change in the availability of iOS store apps. Currently, an app that has been assigned to two groups with a conflict between **Required and Available** and **Not Applicable**, resolves to **Required and Available**. With the change, an app experiencing this conflict resolves to **Not Applicable**.

The change addresses the confusion when one app is assigned to multiple groups with different app intents.

If you would like to have your app available in the Information Worker Portal and the Company Portal before the November service release, you have two options:

1. Remove the **Not Applicable** assignment for your group.
2. Create a new group that does not include members with **Required and Available** intent assigned and assign that group as **Not Applicable**.

For more information, see, [How to assign apps to groups with Microsoft Intune](apps-deploy.md).

> [!Note]
> After the release you will no longer be able to view or modify Mobile Device Management (MDM) app assignments in the Intune classic console. However, you can use Azure console or the Intune Graph API to make your app assignments.

### Configure an iOS app PIN <!-- 1586774 -->
Soon you will be able to require a PIN for targeted iOS apps. You can configure the PIN requirement and expiration date in days through the Azure portal. When required, a user will be required to set and use a new PIN before getting access to an iOS app. Only iOS apps that have app protection enabled with the Intune App SDK will support this feature.

### User experience update for the Company Portal app for iOS <!--1412866-->

We will be releasing a major user experience update to the Company Portal app for iOS. The update will feature a complete visual redesign, which includes a modernized look and feel with increased usability and accessibility. All current iOS Company Portal functionality will be maintained.

We are offering a pre-release version of the updated Company Portal app for iOS through the Apple TestFlight program for you to use and to provide feedback. Sign up at https://aka.ms/intune_ios_cp_testflight for TestFlight access. 

![teaser images for new ios company portal app](./media/ios-cp-app-redesign-1801-teaser.png)

<!-- the following are present prior to 1711 -->

### Azure Active Directory web sites can require the Intune Managed Browser App and support Single Sign-On for the Managed Browser (Public Preview) <!-- 710595 -->   
Using Azure Active Directory (Azure AD), you will be able to restrict access to web sites on mobile devices to the Intune Managed Browser app. In the managed browser, web site data will remain secure and separate from end-user personal data. In addition, the Managed Browser will support Single Sign-On capabilities for sites protected by Azure AD. Signing in to the Managed Browser, or using the Managed Browser on a device with another app managed by Intune, allows the Managed Browser to access corporate sites protected by Azure AD without the user having to enter their credentials. This functionality applies to sites like Outlook Web Access (OWA) and SharePoint Online, as well as other corporate sites like intranet resources accessed through the Azure App Proxy.

<!-- the following are present prior to 1709 -->

### Intune App Protection and Citrix MDX Development Tools <!-- 709185 -->
You can manage devices and apps with a combination of Citrix XenMobile MDX and Microsoft Intune. This allows you to manage apps with Intune app protection policy while using Citrix’s mVPN technology.

You are able to find a code repository that contains the Intune App Wrapping Tool and Intune App SDK for iOS and Android, integrating with Citrix MDX mVPN technology.



<!-- the following are present prior to 1711 -->

### Redirecting macOS users to our new Company Portal app <!--1380728-->   
When an end user logs into the Company Portal website to enroll their macOS device, they will be directed to download the new Company Portal app for macOS to complete the process. This occurs for macOS devices using OS X El Capitan 10.11 or above. 


<!-- the following are present prior to 1709 -->

### Intune Managed Browser support for iOS and Android <!-- 1374196 -->
As of October 2017, the Intune Managed Browser app on Android app will support only devices running Android 4.4 and later. The Intune Managed Browser app on iOS will support only devices running iOS 9.0 and later. Earlier versions of Android and iOS will be able to continue using the Managed Browser, but will be unable to install new versions of the app and might not be able to access all of the app capabilities. We encourage you to update these devices to a supported operating system version.

### Improved error message for when a user reaches the maximum number of devices allowed to enroll <!-- 1270370 -->
Instead of a generic error message, end users with Android devices see a friendly, actionable error message: "You have enrolled the maximum number of devices allowed by your IT admin. Please remove an enrolled device or get help from your IT admin."



## Notices

There are no active notices at this time.



### See also
See [What’s New in Microsoft Intune](whats-new.md) for details on recent developments.


