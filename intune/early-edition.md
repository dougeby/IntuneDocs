---
# required metadata

title: Early edition
description:
keywords:
author: brenduns  
ms.author: brenduns
manager: angrobe
ms.date: 11/6/2017
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

# The early edition for Microsoft Intune - November 2017

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


### Assign Office 365 mobile apps to iOS and Android devices using built-in app type <!-- 1332318 -->
The **Built-in** app type will make it easier for you to create and assign Office 365 apps to the iOS and Android devices that you manage. These apps include 0365 apps such as Word, Excel, PowerPoint, and OneDrive. You can assign specific apps to the app type and edit the app information configuration.

### Single Sign-on support for iOS <!-- 1333645 -->  
You will be able to use Single Sign-on for iOS users. The iOS apps that are coded to look for user credentials in the Single Sign-on payload are functional with this payload configuration update. You can also use UPN and Intune Device ID to configure the Principal Name and Realm.

### iOS 11 app inventory API for Mobile Threat Detection <!-- 1391759 -->
Intune collects app inventory information from both personal and corporate-owned devices and makes it available for Mobile Thread Detection (MTD) providers to fetch, such as Lookout for Work. You will be able to collect app inventory from the users of iOS 11+ devices.

**App inventory**  
Inventories from both corporate-owned iOS 11+ and personally owned devices are sent to your MTD service provider. Data in the app inventory includes:

 - App ID
 - App Version
 - App Short Version
 - App Name
 - App Bundle Size
 - App Dynamic Size
 - App is validated or not
 - App is managed or not

### Audit updates <!-- 1412961 -->  
Intune auditing provides a record of change operations related to Intune.  All create, update, delete and remote task operations are captured and retained for one year.  The Azure portal provides a view of the last 30 days of audit data in each workload, and is filterable.  A corresponding Graph API allows retrieval of the auditing data stored for the last year. 

Auditing is found under the **MONITOR** group. There is an **Audit Logs** menu item for each workload.   

### Text protocol allowed from managed Apps <!-- 1414050  -->
Apps managed by the Intune App SDK will be able to send SMS messages.

### Remotely restart iOS device (supervised only) <!-- 1424595 -->
You will be able to trigger a supervised iOS 10.3+ device to restart using a device action. For more information on using the device restart action, see [Remotely restart devices with Intune](device-restart.md).

> [!Note]  
> This command requires a supervised devices and the **Device Lock** access right. The device restarts immediately. Passcode-locked iOS devices will not rejoin a Wi-Fi network after restart; after restart, they may not be able to communicate with the server.

### Remotely lock managed macOS device with Intune <!-- 1437691 -->
You will be able to lock a lost macOS device, and set a 6-digit recovery PIN. When locked, the **Device overview** blade displays the PIN until another device action is sent.

For more information, see [Remotely lock managed devices with Intune](device-remote-lock.md).

### Windows Defender Advanced Threat Protection reporting frequency settings  <!--- 1455974  --->
Windows Defender Advanced Threat Protection (WDATP) service allows admins to manage reporting frequency for managed devices. With the new **Expedite telemetry reporting frequency** option, WDATP collects data and assesses risks more frequently. The default for reporting optimizes speed and performance. Increasing the frequency of reporting can be valuable for high-risk devices. This setting can be found in the **Windows Defender ATP** profile in **Device configurations**.

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

### Support for multiple Network Device Enrollment Service (NDES) connectors <!-- 1528104 -->
NDES allows mobile devices running without domain credentials to obtain certificates based on the Simple Certificate Enrollment Protocol (SCEP). With this update, multiple NDES connectors will be supported.

### New SCEP profile details supported <!-- 1559808 -->
Administrators will be able to set additional settings when creating a SCEP profile on Windows, iOS, macOS, and Android platforms.  Administrators can set IMEI, serial number, or common name including email in the subject name format.

### Configure an iOS app PIN <!-- 1586774 -->
Soon you will be able to require a PIN for targeted iOS apps. You can configure the PIN requirement and expiration date in days through the Azure portal. When required, a user will be required to set and use a new PIN before getting access to an iOS app. Only iOS apps that have app protection enabled with the Intune App SDK will support this feature.

### Retain data during a factory reset  <!-- 1588489 -->
We are adding support for a new capability to Windows Factory reset. Now, admins can specify if device enrollment and other provisioned data are retained on a device through a factory reset. 
 
The following data is retained through a factory reset:
- User accounts associated with the device
- Machine state (domain join, AADJ)
- MDM enrollment
- OEM installed apps (store and Win32 apps)
- User profile
- User data outside of user profile
- User autologon
 
The following data is not preserved:
- User files
- User installed apps (store and Win32 apps)
- Non-default device settings 

### App install status report now a bar chart <!-- 1249446 -->  
The **App install status** report accessible for each app through the **App** list in the **Mobile apps** workload will soon be rendered as a bar chart.

### Add "Find my iPhone" for personal devices <!--1427287-->
You will be able to view whether iOS devices have Activation Lock turned on. This feature previously could be found in the Intune in the classic portal.

### Group-assigned enrollment restrictions <!-- 747598 -->
As an Intune administrator, you will be able to create custom Device Type and Device Limit enrollment restrictions for user groups.
 
The Intune Azure Portal lets you create up to 25 instances of each restriction type which can then be assigned to user groups. Group-assigned restrictions override the default restrictions.
 
All the instances of a restriction type are maintained in a strictly ordered list. This order defines a priority value for conflict resolution. A user impacted by more than one restriction instance is only restricted by the instance with the highest priority value. You can change a given instance's priority by dragging it to a different position in the list. 
 
This functionality will be released with the migration of Android for Work settings from the Android For Work enrollment menu to the Enrollment Restrictions menu. Since this migration may take several days, your account may be upgraded for other parts of the November release before you see group assignment become enabled for Enrollment Restrictions.

### Windows 10 update ring assignments are displayed <!-- 1621837 -->
When you are **Troubleshooting,** for the user you are viewing, you will be able to see any Windows 10 update rings assignments.  



<!-- the following are present prior to 1711 -->

### Azure Active Directory web sites can require the Intune Managed Browser App and support Single Sign-On for the Managed Browser (Public Preview) <!-- 710595 -->   
Using Azure Active Directory (Azure AD), you will be able to restrict access to web sites on mobile devices to the Intune Managed Browser app. In the managed browser, web site data will remain secure and separate from end-user personal data. In addition, the Managed Browser will support Single Sign-On capabilities for sites protected by Azure AD. Signing in to the Managed Browser, or using the Managed Browser on a device with another app managed by Intune, allows the Managed Browser to access corporate sites protected by Azure AD without the user having to enter their credentials. This functionality applies to sites like Outlook Web Access (OWA) and SharePoint Online, as well as other corporate sites like intranet resources accessed through the Azure App Proxy.

### Troubleshoot enrollment issues  <!--- 746324 --->  
The Troubleshoot workspace will show user enrollment issues. Details about the issue and suggested remediation steps can help admins and help desk operators troubleshoot problems. Certain enrollment issues aren't captured and some errors might not have remediation suggestions.


















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
