---
# required metadata

title: Early edition
description:
keywords:
author: ErikjeMS  
ms.author: erikje
manager: angrobe
ms.date: 12/21/2017
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

# The early edition for Microsoft Intune - January 2018

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

### Easier resolution of compliance issues for the Company Portal app for Windows 10 <!--676546 -->

End users with Windows devices will be able to tap the non-compliance reason in the Company Portal app. When possible, this will take them directly to the correct location in the settings app to fix the issue. 

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

### Select device categories by using the Access Work or School settings <!-- 1058963 eeready --> 
If you've enabled [device group mapping](https://docs.microsoft.com/en-us/intune/device-group-mapping), users on Windows 10 will be prompted to select a device category after enrolling through the **Connect** button in **Settings** > **Accounts** > **Access work or school** or during the out-of-box experience.

### Targeting compliance policies to devices in device groups <!--1307012 -->

You will be able to target compliance policies to users in user groups. You'll be able to target compliance policies to devices in device groups. 

### Including and excluding app assignment based on groups <!-- 1406920 -->

During app assignment and after selecting an assignment type, you'll be able to select the groups to include, as well as the groups to exclude. You'll also be able to use the pre-created groups (All Users, All Devices and All Users+Devices) as included groups.

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

#### Updates to compliance emails <!--1637547 -->

When an email is sent to report a noncompliant device, details about the noncompliant device will be included. The following article will be updated to indicate this fact: [Automate actions for noncompliance](#actions-for-noncompliance).



### Conditional Access policies for Intune is only available from the Azure portal  <!-- 1737088 1634311 --> 
We will simplify where you configure and manage conditional access. You will configure and manage your policies in the [Azure portal](https://portal.azure.com) from **Azure Active Directory** > **Conditional Access**. For your convenience, you will also be able to access this blade from Intune in the Azure portal at **Intune** > **Conditional Access**.

###  Alerts for expired tokens and tokens that will soon expire <!-- 1639263 -->

The overview page will show alerts for expired tokens and tokens that will soon expire. When you click on an alert for a single token, you'll go to the token's details page.  If you click on alert with multiple tokens, you'll go to a list of all tokens with their status. Admins should renew their tokens before the expiration date.

#### Approve the Company Portal app for Android for Work <!--1797090 -->
If your organization uses Android for Work, you'll need to manually approve the Company Portal app for Android so that it will continue to receive automatic updates from the managed Google Play store. 

### Remote printing over a secure network <!-- 1709994  -->
PrinterOn’s wireless mobile printing solutions enables users to remotely print from anywhere at any time over a secure network. PrinterOn has integrated with the Intune APP SDK for both iOS and Android. You can target app protection policies to this app through the Intune **App protection policies** blade in the admin console. End users can download the app 'PrinterOn for Microsoft' through the Play Store or iTunes to use within their Intune ecosystem.

<!-- the following are present prior to 1801 -->

### App Protection Policies  <!-- 679615 -->
Intune App Protection Policies will offer the ability to create global, default policies to quickly enable protection across all users in the entire tenant.

### Revoking iOS Volume-Purchase Program apps  <!-- 820863 -->
For a given device that has one or more iOS Volume-Purchase Program (VPP) apps, you will be able to revoke the associated device based app license for the device. Revoking an app license will not uninstall the related VPP app from the device. To uninstall a VPP app, you must change the assignment action to **Uninstall**. For more information, see [How to manage iOS apps purchased through a volume-purchase program with Microsoft Intune](vpp-apps-ios.md).

### Revoke licenses for an iOS Volume Purchasing Program token <!-- 820870 -->
You will be able to revoke the license of all iOS Volume Purchasing Program (VPP) apps for a given VPP Token.

### Network Access Control (NAC) device check-in reporting  <!-- 1232250 -->
Before this change, IT admins couldn't determine from the Intune side whether a NAC-managed device was communicating with their NAC solution or not. When a NAC-managed device isn't communicating with their NAC solution, the device is considered non-compliant by the NAC solution, and therefore blocked by the NAC solution itself and subsequently blocked by conditional access policies that rely on the device compliance state.

With this change, IT admins can see which NAC-managed devices have successfully communicated with their NAC solution or not. This new capability consists of two new monitoring functions located in the Device compliance workload within Intune, the statistics are shown as below:
- **Average NAC calls in the last hour**
- **Last NAC incoming request (date/time)**

### New iOS device action   <!-- 1244701 -->
You can shut down iOS 10.3 supervised devices. This action shuts down the device immediately without warning to the end user. The **Shut down (supervised only)** action can be found at the device properties when you select a device in the **Device** workload.


### Intune now provides the Account Move operation  <!-- 1573558, 1579830 -->
The **Account Move** migrates a tenant from one Azure Scale Unit (ASU) to another. The **Account Move** can be used for both customer-initiated scenarios, when you call the Intune support team requesting it, and it can also be a Microsoft-driven scenario where Microsoft needs to make adjustments to the service in the back-end. During the **Account Move**, the tenant enters in read-only mode (ROM). Service operations like enrolling, renaming devices, updating compliance status will fail during the ROM period.




<!-- the following are present prior to 1712 -->
### Assign Office 365 mobile apps to iOS and Android devices using built-in app type <!-- 1332318 -->
The **Built-in** app type will make it easier for you to create and assign Office 365 apps to the iOS and Android devices that you manage. These apps include 0365 apps such as Word, Excel, PowerPoint, and OneDrive. You can assign specific apps to the app type and edit the app information configuration.


### Assignment conflict resolution has changed for iOS store apps <!-- 1480316 -->
End users might experience a change in the availability of iOS store apps. Currently, an app that has been assigned to two groups with a conflict between **Required and Available** and **Not Applicable**, resolves to **Required and Available**. With the change, an app experiencing this conflict resolves to **Not Applicable**.

The change addresses the confusion when one app is assigned to multiple groups with different app intents.

If you would like to have your app available in the Information Worker Portal and the Company Portal before the November service release, you have two options:

1. Remove the **Not Applicable** assignment for your group.
2. Create a new group that does not include members with **Required and Available** intent assigned and assign that group as **Not Applicable**.

For more information, see, [How to assign apps to groups with Microsoft Intune](apps-deploy.md).

> [!Note]
> After the release you will no longer be able to view or modify Mobile Device Management (MDM) app assignments in the Intune classic console. However, you can use Azure console or the Intune Graph API to make your app assignments.

### Manage Android for Work devices independently from Android devices <!-- 1490731 -->
Intune will support managing enrollment of Android for Work devices independently from the Android platform. These settings are managed under **Device Enrollment** > **Enrollment restrictions** > **Device Type Restrictions**. (They were previously located under **Device Enrollment** > **Android for Work Enrollment** > **Android for Work Enrollment Settings**.)

By default, your Android for Work devices settings will be the same as your settings for your Android devices. However, after you change your Android for Work settings that will no longer be the case.
 
If you block personal Android for Work enrollment, only corporate Android devices can enroll as Android for Work.

When working with the new settings, consider the following:

#### If you have never previously onboarded Android for Work enrollment
The new Android for Work platform is blocked in the default Device Type Restrictions. After you onboard the feature, you can allow devices to enroll with Android for Work. To do so, change the default or create a new Device Type Restriction to supersede the default Device Type Restriction.

#### If you have onboarded Android for Work enrollment
If you’ve previously onboarded, your situation depends on the setting you chose:

| Setting | Android for Work status in default Device Type Restriction | Notes |
| --- | --- | --- |
| **Manage all devices as Android** | Blocked | All Android devices must enroll without Android for Work. |
| **Manage supported devices as Android for Work** | Allowed | All Android devices that support Android for Work must enroll with Android for Work. |
| **Manage supported devices for users only in these groups as Android for Work** | Blocked | A separate Device Type Restriction policy was created to override the default. This policy defines the groups you previously selected to allow Android for Work enrollment. Users within the selected groups will continue to be allowed to enroll their Android for Work devices. All other users are restricted from enrolling with Android for Work. |

In all cases, your intended regulation is preserved. No action is required on your part to maintain the global or per-group allowance of Android for Work in your environment.

These changes will begin rollout with the November update, but may take time to execute on your account. You will receive a confirmation notification in the Office 365 portal when these changes are effective for your account.


### Configure an iOS app PIN <!-- 1586774 -->
Soon you will be able to require a PIN for targeted iOS apps. You can configure the PIN requirement and expiration date in days through the Azure portal. When required, a user will be required to set and use a new PIN before getting access to an iOS app. Only iOS apps that have app protection enabled with the Intune App SDK will support this feature.


<!-- the following are present prior to 1711 -->

### Azure Active Directory web sites can require the Intune Managed Browser App and support Single Sign-On for the Managed Browser (Public Preview) <!-- 710595 -->   
Using Azure Active Directory (Azure AD), you will be able to restrict access to web sites on mobile devices to the Intune Managed Browser app. In the managed browser, web site data will remain secure and separate from end-user personal data. In addition, the Managed Browser will support Single Sign-On capabilities for sites protected by Azure AD. Signing in to the Managed Browser, or using the Managed Browser on a device with another app managed by Intune, allows the Managed Browser to access corporate sites protected by Azure AD without the user having to enter their credentials. This functionality applies to sites like Outlook Web Access (OWA) and SharePoint Online, as well as other corporate sites like intranet resources accessed through the Azure App Proxy.


<!-- the following are present prior to 1710 -->



### Support for Windows 10 edition upgrade policy   <!-- 903672(archived), 1119689 -->  
You will be able to create a Windows 10 edition upgrade policy that upgrades Windows 10 devices to Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education, and Windows 10 Professional Education N.
For details about Windows 10 edition upgrades, see [How to configure Windows 10 edition upgrades](edition-upgrade-configure-windows-10.md).




<!-- the following are present prior to 1709 -->



### Android for Work support for Lookout <!-- 1087312 -->   
Intune connector with Lookout will support Android for Work devices when using the Lookout for Work app. You are able to deploy the Lookout app inside or outside the container.

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
Instead of a generic error message, end users see a friendly, actionable error message: "You have enrolled the maximum number of devices allowed by your IT admin. Please remove an enrolled device or get help from your IT admin."




## Notices

There are no active notices at this time.




### See also
See [What’s New in Microsoft Intune](whats-new.md) for details on recent developments.
