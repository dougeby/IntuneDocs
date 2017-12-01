---
# required metadata

title: Early edition
description:
keywords:
author: ErikjeMS  
ms.author: erikje
manager: angrobe
ms.date: 11/29/2017
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

# The early edition for Microsoft Intune - December 2017

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

### App Protection Policies  <!-- 679615 -->
Intune App Protection Policies will offer the ability to create global, default policies to quickly enable protection across all users in the entire tenant.

### Revoking iOS Volume-Purchase Program apps  <!-- 820863 -->
For a given device that has one or more iOS Volume-Purchase Program (VPP) apps, you will be able to revoke the associated device based app license for the device. Revoking an app license will not uninstall the related VPP app from the device. To uninstall a VPP app, you must change the assignment action to **Uninstall**. For more information, see [How to manage iOS apps purchased through a volume-purchase program with Microsoft Intune](vpp-apps-ios.md).

### Revoke licenses for an iOS Volume Purchasing Program token <!-- 820870 -->
You will be able to revoke the license of all iOS Volume Purchasing Program (VPP) apps for a given VPP Token.

### Delete an iOS  Volume Purchasing Program token <!-- 820879 -->
You will be able to delete the iOS Volume Purchasing Program (VPP) token using the console. This may be necessary when you have duplicate instances of a VPP token.

### Network Access Control (NAC) device check-in reporting  <!-- 1232250 -->
Before this change, IT admins couldn't determine from the Intune side whether a NAC-managed device was communicating with their NAC solution or not. When a NAC-managed device isn't communicating with their NAC solution, the device is considered non-compliant by the NAC solution, and therefore blocked by the NAC solution itself and subsequently blocked by conditional access policies that rely on the device compliance state.

With this change, IT admins can see which NAC-managed devices have successfully communicated with their NAC solution or not. This new capability consists of two new monitoring functions located in the Device compliance workload within Intune, the statistics are shown as below:
- **Average NAC calls in the last hour**
- **Last NAC incoming request (date/time)**

### New iOS device action   <!-- 1244701 -->
You can shut down iOS 10.3 supervised devices. This action shuts down the device immediately without warning to the end user. The **Shut down (supervised only)** action can be found at the device properties when you select a device in the **Device** workload.

### Palo Alto VPN now supported <!-- 1333680 eeready -->
The **Connection type** list will include Palo Alto VPN when you configure your base VPN.

### Multiple connector support for SCEP and PFX certificate handling <!-- 1361755 eeready -->
Customers who use the on-premise NDES connector to deliver certificates to devices will be able to configure multiple connectors in a single tenant.

This new capability supports the following scenario:

- **High availability**

    Each NDES connector pulls certificate requests from Intune.  If one NDES connector goes offline, the other connector can continue to process requests.

### New automatic redeployment setting <!-- 1469168 -->
This setting allows users with administrative rights to delete all user data and settings using **CTRL + Win + R** at the device lock screen. The device will be automatically reconfigured and reenrolled into management.

This setting can be found under Windows 10 -> Device restrictions -> General -> Automatic redeployment.

### Install Office apps on macOS devices <!-- 1494311 -->
You will be able to install Office apps on macOS devices. This new app type will allow you to install Word, Excel, PowerPoint, Outlook, and OneNote. These apps also come with the Microsoft AutoUpdater (MAU), to help keep your apps secure and up-to-date.

### Surface Hub resource account supported <!-- 1566442 eeready -->
A new device action will be added so administrators can define and update the resource account associated with a Surface Hub.

The resource account is used by a Surface Hub to authenticate with Skype/Exchange so it can join a meeting. You can create a unique resource account so the Surface Hub appears in the meeting as the conference room. For example, the resource account might appear as *Conference Room B41/6233*. The resource account (known as the device account) for the Surface Hub typically needs to be configured for the conference room location and when other resource account parameters need to be changed.

When administrators want to update the resource account on a device, they must provide the current Active Directory/Azure Active Directory credentials associated with the device. If password rotation is on for the device, administrators must go to Azure Active Directory to find the password.

> [!NOTE]
> All fields get sent down in a bundle and overwrite all fields that were previously configured. Empty fields also overwrite existing fields.

The following are the settings administrators can configure:

- **Resource account**  

   - **Active Directory user**   
   Domainname\username or User Principle Name (UPN): user@domainname.com
   - **Password**


- **Optional resource account parameters** (must be set using the specified resource account)
   - **Password rotation period**   
     Ensures the account password is updated automatically by the Surface Hub every week for security reasons. To configure any parameters after this has been enabled, the account in Azure Active Directory must have the password reset first.

   - **SIP (Session Initiation Protocol) address**    
     Only used when autodiscovery fails.

   - **Email**    
     Email address of the device/resource account.

   - **Exchange server**    
     Only required when autodiscovery fails.

   - **Calendar sync**    
     Specifies whether calendar sync and other Exchange server services are enabled. For example: meeting sync.

### Intune now provides the Account Move operation  <!-- 1573558, 1579830 -->
The **Account Move** migrates a tenant from one Azure Scale Unit (ASU) to another. The **Account Move** can be used for both customer-initiated scenarios, when you call the Intune support team requesting it, and it can also be a Microsoft-driven scenario where Microsoft needs to make adjustments to the service in the back-end. During the **Account Move**, the tenant enters in read-only mode (ROM). Service operations like enrolling, renaming devices, updating compliance status will fail during the ROM period.

### New Windows Defender Security Center (WDSC) device configuration profile settings <!-- 1335507 -->
Intune adds a new section of device configuration profile settings under the Endpoint protection named **Windows Defender Security Center**. IT admins can configure which pillars of the Windows Defender Security Center app end-users can access. If an IT admin hides a pillar in the Windows Defender Security Center app, all notifications related to the hidden pillar do not display on the user's device.

These are the pillars admins can hide from the Windows Defender Security Center device configuration profile settings:
- Virus and threat protection
- Device performance and health
- Firewall and network protections
- App and browser control
- Family options

IT admins can also customize which notifications users receive. For example, you can configure whether the users receive all notifications generated by visible pillars in the WDSC, or only critical notifications. Non-critical notifications include periodic summaries of Windows Defender Antivirus activity and notifications when scans have completed. All other notifications are considered critical. Additionally, you can also customize the notification content itself, for example, you can provide the IT contact information to embed in the notifications that appear on the users' devices.




<!-- the following are present prior to 1712 -->
### Assign Office 365 mobile apps to iOS and Android devices using built-in app type <!-- 1332318 -->
The **Built-in** app type will make it easier for you to create and assign Office 365 apps to the iOS and Android devices that you manage. These apps include 0365 apps such as Word, Excel, PowerPoint, and OneDrive. You can assign specific apps to the app type and edit the app information configuration.

### Single Sign-on support for iOS <!-- 1333645 -->  
You will be able to use Single Sign-on for iOS users. The iOS apps that are coded to look for user credentials in the Single Sign-on payload are functional with this payload configuration update. You can also use UPN and Intune Device ID to configure the Principal Name and Realm.

### Text protocol allowed from managed Apps <!-- 1414050  -->
Apps managed by the Intune App SDK will be able to send SMS messages.

### Remotely lock managed macOS device with Intune <!-- 1437691 -->
You will be able to lock a lost macOS device, and set a 6-digit recovery PIN. When locked, the **Device overview** blade displays the PIN until another device action is sent.

For more information, see [Remotely lock managed devices with Intune](device-remote-lock.md).


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

### Add "Find my iPhone" for personal devices <!--1427287-->
You will be able to view whether iOS devices have Activation Lock turned on. This feature previously could be found in the Intune in the classic portal.

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


### On-premises Exchange connector high availability support  <!-- 676614 -->   
You are able to have multiple Client Access Server (CAS) roles for on-premises Exchange connector. For example, if the main CAS fails, the Exchange connector receives a query to fall back to other CASs. This feature ensures that the service is not interrupted.

### System Center Operations Manager management pack for Exchange connector <!-- 885457 -->   
The System Center Operations Manager management pack for Exchange connector will be available to help you parse the Exchange connector logs. This management pack gives you different ways of monitoring Intune when you need to troubleshoot issues.





## Intune apps

### Helping your users help themselves with the Company Portal app for Android <!---1573324, 1573150, 1558616, 1564878--->
The Company Portal app for Android is adding instruction for end users to help them understand and, where possible, self-solve on new use cases. 

- A new message will be displayed that explains that a compliance policy for encryption has been deployed, but the [device manufacturer isn't encrypting the device](/intune-user-help/your-device-appears-encrypted-but-cp-says-otherwise-android) according to [Google's recommended guidelines](https://developer.android.com/reference/android/app/admin/DevicePolicyManager.html#setStorageEncryption(android.content.ComponentName, boolean).
- End users will be guided to the (Azure Active Directory portal)[https://account.activedirectory.windowsazure.com/r/#/profile] to remove a device if they have reached the maximum number of devices that they are allowed to add. 
- End users are given steps to follow to help them [fix activation errors on Samsung KNOX devices](https://go.microsoft.com/fwlink/?linkid=859718) or to [turn off power-saving mode](/intune-user-help/power-saving-mode-android). If neither of those solutions resolve their issue, we will provide an explanation of how to [submit logs to Microsoft](/intune-user-help/send-logs-to-microsoft-ios). 


### New 'Resolve' action available for Android devices <!---1583480--->
The Company Portal app for Android is introducing a 'Resolve' action on the _Update device settings_ page. Selecting this option will take the end user directly to the setting that is causing their device to be noncompliant. The Company Portal app for Android currently supports this action for the [device passcode](/intune-user-help/set-your-pin-or-password-android), [device encryption](/intune-user-help/encrypt-your-device-android), [USB debugging](/intune-user-help/you-need-to-turn-off-usb-debugging-android), and [Unknown Sources](/intune-user-help/you-need-to-turn-off-unknown-sources-android) settings. 




<!-- the following are present prior to 1711 -->


### Redirecting macOS users to our new Company Portal app <!--1380728-->   
When an end user logs into the Company Portal website to enroll their macOS device, they will be directed to download the new Company Portal app for macOS to complete the process. This occurs for macOS devices using OS X El Capitan 10.11 or above. 


<!-- the following are present prior to 1710 -->



### Apps that are available with or without enrollment can now be installed without being prompted for enrollment. <!-- 1334712 -->
Company apps that have been made available with or without enrollment on the Android Company Portal app can be installed without a prompt to enroll.


<!-- the following are present prior to 1709 -->

### Intune Managed Browser support for iOS and Android <!-- 1374196 -->
As of October 2017, the Intune Managed Browser app on Android app will support only devices running Android 4.4 and later. The Intune Managed Browser app on iOS will support only devices running iOS 9.0 and later. Earlier versions of Android and iOS will be able to continue using the Managed Browser, but will be unable to install new versions of the app and might not be able to access all of the app capabilities. We encourage you to update these devices to a supported operating system version.


### Improved error message for when a user reaches the maximum number of devices allowed to enroll <!-- 1270370 -->
Instead of a generic error message, end users see a friendly, actionable error message: "You have enrolled the maximum number of devices allowed by your IT admin. Please remove an enrolled device or get help from your IT admin."




## Notices

There are no active notices at this time.




### See also
See [What’s New in Microsoft Intune](whats-new.md) for details on recent developments.
