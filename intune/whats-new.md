---
# required metadata
title: What's new in Microsoft Intune
titlesuffix: "Azure portal"
description: Find out what's new in the Intune Azure portal
keywords:
author: ErikjeMS  
ms.author: erikje
manager: angrobe
ms.date: 01/02/2018
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: angrobe
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---

# What's new in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Learn what’s new each week in Microsoft Intune. You can also find out about [upcoming changes](#whats-coming), [important notices](#notices) about the service, and information about [past releases](whats-new-archive.md).

> [!Note]
> For information on new functionality in hybrid mobile device management (MDM), check out our [hybrid What’s New page](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).


<!-- Common categories:  
  ### Device enrollment
  ### Device management
  ### App management
  ### Device configuration
  ### Role-based access control
  ### Intune apps
  ### Monitor and troubleshoot

-->   


## Week of February 19, 2018
### Device enrollment
#### New option for user authentication for Apple bulk enrollment <!-- 747625 -->

New tenants will see this right away. For existing tenants, this feature is being rolled out through April. Until this roll out is complete, you might not have access to these new features.

 Intune now gives you the option to authenticate devices by using the Company Portal app for the following enrollment methods:
 
- Apple Device Enrollment Program
- Apple School Manager
- Apple Configurator Enrollment
 
When using the Company Portal option, Azure Active Directory multi-factor authentication can be enforced without blocking these enrollment methods.
 
When using the Company Portal option, Intune skips user authentication in the iOS Setup Assistant for user affinity enrollment. This means that the device is initially enrolled as a userless device, and so won't receive configurations or policies of user groups. It will only receive configurations and policies for device groups. However, Intune will automatically install the Company Portal app on the Device. The first user to launch and sign in to the Company Portal app will be associated with the device in Intune. At this point the user will receive configurations and policies of their user groups. The user association cannot be changed without re-enrollment.

#### Intune support for multiple Apple DEP / Apple School Manager accounts <!-- 747685 -->
 
Intune now supports enrolling devices from up to 100 different Apple Device Enrollment Program (DEP) or Apple School Manager accounts. Each token uploaded can be managed separately for enrollment profiles and devices. A different enrollment profile can be automatically assigned per DEP/School Manager token uploaded. If multiple School Manager tokens are uploaded, only one can be shared with Microsoft School Data Sync at a time.

After migration, the beta Graph APIs and published scripts for managing Apple DEP or ASM over Graph will no longer work. New beta Graph APIs are in development and will be released after the migration.

#### See enrollment restrictions per user <!-- 1634444 eeready wnready -->
On the **Troubleshoot** blade, you can now see the enrollment restrictions that are in effect for each user by selecting **Enrollment restrictions** from the **Assignments** list.

### Device management
#### Windows defender health status and threat status reports <!--854704 -->

Understanding Windows Defender's health and status is key to managing Windows PCs.  With this update, Intune adds new reports and actions to the status and health of the Windows Defender agent. Using a status roll up report in the Device Compliance workload, you can see devices that need any of the following:
- signature update
- Restart
- manual intervention
- full scan
- other agent states requiring intervention

A drill-in report for each status category lists the individual PCs that need attention, or those that report as **Clean**.

#### New privacy settings for device restrictions <!--1308926 -->
Two new privacy settings are now available for devices:
- **Publish user activities**: Set this to **Block** to prevent shared experiences and discovery of recently used resources in the task switcher.
- **Local activities only**: Set this to **Block** to prevent shared experiences and discovery of recently used resources in task switcher based only on local activity.

#### New settings for the Edge browser <!--1469166 -->
Two new settings are now available for devices with the Edge browser: **Path to favorites file** and **Changes to Favorites**. 

### App management
#### Protocol exceptions for applications <!--1035509 -->

You can now create exceptions to the Intune Mobile Application Management (MAM) data transfer policy to open specific unmanaged applications. Such applications must be trusted by IT. Other than the exceptions you create, data transfer is still restricted to applications that are managed by Intune when your data transfer policy is set to **managed apps only**. You can create the restrictions by using protocols (iOS) or packages (Android).
 
For example, you can add the Webex package as an exception to the MAM data transfer policy. This will allow Webex links in a managed Outlook email message to open directly in the Webex application. Data transfer will still be restricted in other unmanaged applications. For more information, see [Data transfer policy exceptions for apps](app-protection-policies-exception.md).

#### Windows Information Protection (WIP) encrypted data in Windows search results <!-- 1469193 -->
A setting in the Windows Information Protection (WIP) policy now allows you to control whether WIP-encrypted data is included in Windows search results. Set this app protection policy option by selecting **Allow Windows Search Indexer to search encrypted items** in the **Advanced settings** of the Windows Information Protection policy. The app protection policy must be set to the *Windows 10* platform and the app policy **Enrollment state** must be set to **With enrollment**. For more information, see [Allow Windows Search Indexer to search encrypted items](windows-information-protection-policy-create.md#allow-windows-search-indexer-to-search-encrypted-items).

#### Configuring a self-updating mobile MSI app <!-- 1740840 -->
You can configure a known self-updating mobile MSI app to ignore the version check process. This capability is useful to avoid getting into a race condition. For instance, this type of race condition could occur when the app being auto-updated by the app developer is also being update by Intune. Both could try to enforce a version of the app on a Windows client, which could create a conflict. For these automatically updated MSI apps, you can configure the **Ignore app version** setting in the **App information** blade. When this setting is switched to **Yes**, Microsoft Intune will ignore the app version installed on the Windows client. 

#### Related sets of app licenses supported in Intune <!-- 1864117 -->
Intune in the Azure portal now supports related sets of app licenses as a single app item in the UI. In addition, any Offline Licensed apps synced from Microsoft Store for Business will be consolidated into a single app entry and any deployment details from the individual packages will be migrated over to the single entry. To view related sets of app licenses in the Azure portal, select **App licenses** from the **Mobile apps** blade.

### Device configuration
#### Windows Information Protection (WIP) file extensions for automatic encryption <!-- 1463582 -->
A setting in the Windows Information Protection (WIP) policy now lets you specify which file extensions are automatically encrypted when copying from a Server Message Block (SMB) share within the corporate boundary, as defined in the WIP policy.

#### Configure resource account settings for Surface Hubs

You can now remotely configure resource account settings for Surface Hubs.

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

#### New Windows Defender Exploit Guard settings <!-- 631893 -->

Six new **Attack Surface Reduction** settings and expanded **Controlled folder access: Folder protection** capabilities are now available. These settings can be found at: Device configuration\Profiles\
Create profile\Endpoint protection\Windows Defender Exploit Guard.

##### Attack Surface Reduction


|Setting name  |Setting options  |Description  |
|---------|---------|---------|
|Execution of password-protected executable content from email|Block, Audit, Not configured|Prevent password-protected executable files downloaded over email from running.|
|Advanced ransomware protection|Enabled, Audit, Not configured|Use aggressive ransomware protection.|
|Flag credential stealing from the Windows local security authority subsystem|Enabled, Audit, Not configured|Flag credential stealing from the Windows local security authority subsystem (lsass.exe).|
|Process creation from PSExec and WMI commands|Block, Audit, Not configured|Block process creations originating from PSExec and WMI commands.|
|Untrusted and unsigned processes that run from USB|Block, Audit, Not configured|Block untrusted and unsigned processes that run from USB.|
|Executables that don’t meet a prevalence, age, or trusted list criteria|Block, Audit, Not configured|Block executable files from running unless they meet a prevalence, age, or trusted list criteria.|

##### Controlled folder access

|Setting name  |Setting options  |Description  |
|---------|---------|---------|
|Folder protection (already implemented)|Not configured, Enable, Audit only (already implemented)<br><br> **New**<br>Block disk modification, Audit disk modification|
Protect files and folders from unauthorized changes by unfriendly apps.<br><br>**Enable**: Prevent untrusted apps from modifying or deleting files in protected folders and from writing to disk sectors.<br><br>
**Block disk modification only**:<br>Block untrusted apps from writing to disk sectors. Untrusted apps can still modify or delete files in protected folders.|

#### Additions to System Security settings for Windows 10 and later compliance policies <!--1704133-->

Additions to the Windows 10 compliance settings are now available, including requiring Firewall and Windows Defender Antivirus. 


### Role-based access control
### Intune apps
#### Support for offline apps from the Microsoft Store for Business <!--1222672-->
Offline apps that you purchased from the Microsoft Store for Business are now synchronized to the Azure portal. You can deploy these apps to device groups or user groups. Offline apps are installed by Intune, not by the store.

#### Prevent end users from manually adding or removing accounts in the work profile <!-- 1728700 -->

When you deploy the Gmail app into an Android for Work profile, you can now prevent end users from manually adding or removing accounts in the work profile by using the **Add and remove accounts** setting in the Android for Work Device restrictions profile.

## Week of February 5, 2018

### Device enrollment

#### New option for user authentication for Apple bulk enrollment <!-- 747625 eeready -->

> [!NOTE]
> New tenants see this right away. For existing tenants, this feature is being rolled out through April. Until this roll out is complete, you might not have access to these new features.

Intune now gives you the option to authenticate devices by using the Company Portal app for the following enrollment methods:

- Apple Device Enrollment Program
- Apple School Manager
- Apple Configurator Enrollment

When using the Company Portal option, Azure Active Directory multi-factor authentication can be enforced without blocking these enrollment methods.

When using the Company Portal option, Intune skips user authentication in the iOS Setup Assistant for user affinity enrollment. This means that the device is initially enrolled as a userless device, and so doesn't receive configurations or policies of user groups. It only receives configurations and policies for device groups. However, Intune will automatically install the Company Portal app on the Device. The first user to launch and sign in to the Company Portal app will be associated with the device in Intune. At this point, the user will receive configurations and policies of their user groups. The user association cannot be changed without re-enrollment.

#### Intune support for multiple Apple DEP / Apple School Manager accounts <!-- 747685 eeready -->

Intune now supports enrolling devices from up to 100 different Apple Device Enrollment Program (DEP) or Apple School Manager accounts. Each token uploaded can be managed separately for enrollment profiles and devices. A different enrollment profile can be automatically assigned per DEP/School Manager token uploaded. If multiple School Manager tokens are uploaded, only one can be shared with Microsoft School Data Sync at a time.

After migration, the beta Graph APIs and published scripts for managing Apple DEP or ASM over Graph will no longer work. New beta Graph APIs are in development and will be released after the migration.

### Remote printing over a secure network <!-- 1709994  -->
PrinterOn’s wireless mobile printing solutions will enable users to remotely print from anywhere at any time over a secure network. PrinterOn will integrate with the Intune APP SDK for both iOS and Android. You will be able to target app protection policies to this app through the Intune **App protection policies** blade in the admin console. End users will be able to download the app 'PrinterOn for Microsoft' through the Play Store or iTunes to use within their Intune ecosystem.

## Week of January 29, 2018

### Device enrollment

#### Alerts for expired tokens and tokens that will soon expire <!-- 1639263 -->
The overview page now shows alerts for expired tokens and tokens that will soon expire. When you click on an alert for a single token, you'll go to the token's details page.  If you click on alert with multiple tokens, you'll go to a list of all tokens with their status. Admins should renew their tokens before the expiration date.

### Device management

#### Remote "Erase" command support for macOS devices <!-- 1438084 -->

Admins can issue an Erase command remotely for macOS devices.

> [!IMPORTANT]
> The erase command can’t be reversed and should be used with caution.

The erase command removes all data, including the operating system, from a device. It also removes the device from Intune management. No warning is issued to the user and the erasure occurs immediately upon issuing the command.

You must configure a 6-digit recovery PIN. This PIN can be used to unlock the erased device, at which point reinstallation of the operating system will begin. After erasure has started, the PIN appears in a status bar on the device’s overview blade in Intune. The PIN will remain as long as the erasure is underway. After erasure is complete, the device disappears entirely from Intune management. Be sure to record the recovery PIN so that whoever is restoring the device can use it.

#### Revoke licenses for an iOS Volume Purchasing Program token <!-- 820870 --> 
You can revoke the license of all iOS Volume Purchasing Program (VPP) apps for a given VPP Token.

### App management

#### Revoking iOS Volume-Purchase Program apps  <!-- 820863 -->
For a given device that has one or more iOS Volume-Purchase Program (VPP) apps, you can revoke the associated device-based app license for the device. Revoking an app license will not uninstall the related VPP app from the device. To uninstall a VPP app, you must change the assignment action to **Uninstall**. For more information, see [How to manage iOS apps purchased through a volume-purchase program with Microsoft Intune](vpp-apps-ios.md).

#### Assign Office 365 mobile apps to iOS and Android devices using built-in app type <!-- 1332318 -->
The **Built-in** app type makes it easier for you to create and assign Office 365 apps to the iOS and Android devices that you manage. These apps include 0365 apps such as Word, Excel, PowerPoint, and OneDrive. You can assign specific apps to the app type and edit the app information configuration.

#### Including and excluding app assignment based on groups <!-- 1406920 -->

During app assignment and after selecting an assignment type, you can select the groups to include, as well as the groups to exclude.

#### Website Learning Mode <!-- 1631908 -->

Intune now has an extension of Windows Information Protection (WIP) Learning mode. In addition to viewing information about WIP-enabled apps, you can view a summary of the devices that have shared work data with websites. With this information, you can determine which websites should be added to group and user WIP policies.

#### Approve the Company Portal app for Android for Work <!--1797090 -->
If your organization uses Android for Work, you'll need to manually approve the Company Portal app for Android so that it will continue to receive automatic updates from the managed Google Play store.

#### FaceID on iOS devices <!-- 1807377 -->
Intune app protection policies now support a setting that controls FaceID on iOS devices. This setting is for devices that supports the FaceID functionality (currently only the iPhone X). This setting is separate from the TouchID controls currently supported. Organizations have the ability to choose whether to trust FaceID as a valid PIN prompt as an alternative to the TouchID controls.

### Device configuration

#### You can assign an application configuration policy to groups by including and excluding assignments  <!-- 1480316 --> 

You can assign an application configuration policy to a group of users and devices by using a combination of including and excluding assignments. Assignments can be chosen as either a custom selection of groups or as a virtual group. A virtual group can include **All users**, **All Device**, or **All Users + All Devices**.

#### Support for Windows 10 edition upgrade policy   <!-- 903672(archived), 1119689 -->  
You can create a Windows 10 edition upgrade policy that upgrades Windows 10 devices to Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education, and Windows 10 Professional Education N.
For details about Windows 10 edition upgrades, see [How to configure Windows 10 edition upgrades](edition-upgrade-configure-windows-10.md).

#### Conditional Access policies for Intune is only available from the Azure portal  <!-- 1737088 1634311 -->

Starting with this release, you must configure and manage your Conditional Access policies in the [Azure portal](https://portal.azure.com) from **Azure Active Directory** > **Conditional Access**. For your convenience, you can also access this blade from Intune in the Azure portal at **Intune** > **Conditional Access**.

#### Updates to compliance emails <!--1637547 -->

When an email is sent to report a noncompliant device, details about the noncompliant device are included. 


## Week of January 22, 2018

### Intune apps

#### New functionality for the "Resolve" action for Android devices <!--1583480-->

The Company Portal app for Android is expanding the "Resolve" action for **Update device settings** to resolve [device encryption issues](/intune-user-help/encrypt-your-device-android).

#### Remote lock available in Company Portal app for Windows 10 <!--676506-->
End users can now remotely lock their devices from the Company Portal app for Windows 10. This will not be displayed for the local device they're actively using.

#### Easier resolution of compliance issues for the Company Portal app for Windows 10 <!--676546-->
End users with Windows devices will be able to tap the noncompliance reason in the Company Portal app. When possible, this will take them directly to the correct location in the settings app to fix the issue.

## Week of December 11, 2017

### Device configuration

#### New automatic redeployment setting <!-- 1469168 -->
The **Automatic redeployment** setting allows users with administrative rights to delete all user data and settings using **CTRL + Win + R** at the device lock screen. The device is automatically reconfigured and reenrolled into management. This setting can be found under Windows 10 > Device restrictions > General > Automatic redeployment. For details, see [Intune device restriction settings for Windows 10](device-restrictions-windows-10.md#general).

#### Support for additional source editions in the Windows 10 edition upgrade policy  <!-- 903672,  1119689 -->
You can now use the Windows 10 edition upgrade policy to upgrade from additional Windows 10 editions (Windows 10 Pro, Windows 10 Pro for Education, Windows 10 Cloud, etc.). Prior to this release, the supported edition upgrade paths were more limited. For details, see [How to configure Windows 10 edition upgrades](edition-upgrade-configure-windows-10.md).

#### New Windows Defender Security Center (WDSC) device configuration profile settings <!-- 1335507 -->

Intune adds a new section of device configuration profile settings under the Endpoint protection named **Windows Defender Security Center**. IT admins can configure which pillars of the Windows Defender Security Center app end-users can access. If an IT admin hides a pillar in the Windows Defender Security Center app, all notifications related to the hidden pillar do not display on the user's device.

These are the pillars admins can hide from the Windows Defender Security Center device configuration profile settings:
- Virus and threat protection
- Device performance and health
- Firewall and network protections
- App and browser control
- Family options

IT admins can also customize which notifications users receive. For example, you can configure whether the users receive all notifications generated by visible pillars in the WDSC, or only critical notifications. Non-critical notifications include periodic summaries of Windows Defender Antivirus activity and notifications when scans have completed. All other notifications are considered critical. Additionally, you can also customize the notification content itself, for example, you can provide the IT contact information to embed in the notifications that appear on the users' devices.

#### Multiple connector support for SCEP and PFX certificate handling <!-- 1361755 -->

Customers who use the on-premise NDES connector to deliver certificates to devices can now configure multiple connectors in a single tenant.

This new capability supports the following scenario:

- **High availability**

Each NDES connector pulls certificate requests from Intune.  If one NDES connector goes offline, the other connector can continue to process requests.

#### Customer subject name can use AAD_DEVICE_ID variable  <!-- 1468599 -->

When you create a SCEP certificate profile in Intune, you can now use the AAD_DEVICE_ID variable when you build the custom subject name.   When the certificate is requested using this SCEP profile, the variable is replaced with the AAD device ID of the device making the certificate request.


### Device management

#### Manage Jamf-enrolled macOS devices with Intune's device compliance engine <!-- 1592747 -->
You can now use Jamf to send macOS device state information to Intune, which will then evaluate it for compliance with policies defined in the Intune console. Based on the device compliance state as well as other conditions (such as location, user risk, etc.), conditional access will enforce compliance for macOS devices accessing cloud and on-premises applications connected with Azure AD, including Office 365. Find out more about [setting up Jamf integration](conditional-access-integrate-jamf.md) and [enforcing compliance for Jamf-managed devices](conditional-access-assign-jamf.md).

#### New iOS device action   <!-- 1424701 -->

You can now shut down iOS 10.3 supervised devices. This action shuts down the device immediately without warning to the end user. The **Shut down (supervised only)** action can be found at the device properties when you select a device in the **Device** workload.

#### Disallow date/time changes to Samsung Knox devices <!-- 1468103 -->

We've added a new feature that allows you to block date and time changes on Samsung Knox devices. You can find this in **Device configuration profiles** > **Device restrictions (Android)** > **General**.

#### Surface Hub resource account supported <!-- 1566442  -->

A new device action has been added so administrators can define and update the resource account associated with a Surface Hub.

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

#### Install Office apps on macOS devices <!-- 1494311 -->
You will now be able to install Office apps on macOS devices. This new app type will allow you to install Word, Excel, PowerPoint, Outlook, and OneNote. These apps also come with the Microsoft AutoUpdate (MAU), to help keep your apps secure and up-to-date.

### App management

#### Delete an iOS  Volume Purchasing Program token <!-- 820879 -->
You can delete the iOS Volume Purchasing Program (VPP) token using the console. This may be necessary when you have duplicate instances of a VPP token.

### Intune apps

#### End user messaging for accounts <!--1573558 for 1712-->

Users of the Company Portal website, will be blocked from taking actions that require write access to your tenant. They will see appropriate error messaging explaining that their account is under maintenance. Similar changes are coming to the Company Portal apps for Android, iOS, macOS, and Windows soon. You can see this error in the [what's new in app UI](whats-new-app-ui.md).



### Role-based access control

#### A new entity collection named Current User is limited to currently active user data <!-- 1667026 -->

The **Users** entity collection contains all the Azure Active Directory (Azure AD) users with assigned licenses in your enterprise. For example, a user may be added to Intune and then removed during the course of the last month. While this user is not present at the time of the report, the user and state are present in the data. You could create a report that would show the duration of the user's historic presence in your data.

In contrast, the new **Current User** entity collection only contains users who have not been removed. The **Current User** entity collection only contains currently active users. For information about the **current user** entity collection, see [Reference for current user entity](reports-ref-current-user.md).


### Updated Graph APIs <!-- 1736360 -->

In this release, we've updated a few of the Graph API's for Intune that are in beta. Please check out the monthly [Graph API changelog](https://developer.microsoft.com/graph/docs/concepts/changelog) for more information.

## Week of December 4, 2017

### Monitor and troubleshoot

#### Intune supports Windows Information Protection (WIP) denied apps <!-- 1479103 -->
You can specify denied apps in Intune. If an app is denied, it is blocked from accessing corporate information, effectively the opposite of the allowed apps list. For more information, see [Recommended deny list for Windows Information Protection](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp?f=255&MSPPError=-2147217396#recommended-deny-list-for-windows-information-protection).


## Week of November 27, 2017

### Device enrollment

#### Troubleshoot enrollment issues  <!-- 746324 -->

The **Troubleshoot** workspace now shows user enrollment issues. Details about the issue and suggested remediation steps can
help administrators and help desk operators troubleshoot problems. Certain enrollment issues aren't captured and some errors
might not have remediation suggestions.

#### Group-assigned enrollment restrictions <!-- 747598 -->

As an Intune administrator, you can now [create custom Device Type and Device Limit enrollment restrictions for user groups](enrollment-restrictions-set.md).

The Intune Azure portal lets you create up to 25 instances of each restriction type, which can then be assigned to user groups. Group-assigned restrictions override the default restrictions.

All the instances of a restriction type are maintained in a strictly ordered list. This order defines a priority value for conflict resolution. A user impacted by more than one restriction instance is only restricted by the instance with the highest priority value. You can change a given instance's priority by dragging it to a different position in the list.

This functionality will be released with the migration of Android for Work settings from the Android For Work enrollment menu to the Enrollment Restrictions menu. Since this migration may take several days, your account may be upgraded for other parts of the November release before you see group assignment become enabled for Enrollment Restrictions.

#### Support for multiple Network Device Enrollment Service (NDES) connectors <!-- 1528104 -->

NDES allows mobile devices running without domain credentials to obtain certificates based on the Simple Certificate Enrollment Protocol (SCEP).
With this update, multiple NDES connectors are supported.

#### Manage Android for Work devices independently from Android devices <!-- 1490731 EEready-->

**Note**: The following changes will start rolling out with the November update, but may take time to execute on your account. You will receive a confirmation notification in the Office 365 portal when these changes are effective for your account. After the roll-out, you’ll have additional manageability options. There will be no change to the end user experience during the rollout.

Intune supports managing enrollment of Android for Work devices independently from the Android platform. These settings are managed under **Device Enrollment** > **Enrollment restrictions** > **Device Type Restrictions**. (They were previously located under **Device Enrollment** > **Android for Work Enrollment** > **Android for Work Enrollment Settings**.)

By default, your Android for Work devices settings are the same as your settings for your Android devices. However, after you change your Android for Work settings that will no longer be the case.

If you block personal Android for Work enrollment, only corporate Android devices can enroll as Android for Work.

When working with the new settings, consider the following points:

##### If you have never previously onboarded Android for Work enrollment

The new Android for Work platform is blocked in the default Device Type Restrictions. After you onboard the feature, you can allow devices to enroll with Android for Work. To do so, change the default or create a new Device Type Restriction to supersede the default Device Type Restriction.

##### If you have onboarded Android for Work enrollment

If you’ve previously onboarded, your situation depends on the setting you chose:

| Setting | Android for Work status in default Device Type Restriction | Notes |
| --- | --- | --- |
| **Manage all devices as Android** | Blocked | All Android devices must enroll without Android for Work. |
| **Manage supported devices as Android for Work** | Allowed | All Android devices that support Android for Work must enroll with Android for Work. |
| **Manage supported devices for users only in these groups as Android for Work** | Blocked | A separate Device Type Restriction policy was created to override the default. This policy defines the groups you previously selected to allow Android for Work enrollment. Users within the selected groups will continue to be allowed to enroll their Android for Work devices. All other users are restricted from enrolling with Android for Work. |

In all cases, your intended regulation is preserved. No action is required on your part to maintain the global or per-group allowance of Android for Work in your environment.

### App management

#### App install report updated to include Install Pending status <!-- 1249446 -->  

The **App install status** report, accessible for each app through the **App** list in the **Mobile apps** workload, now contains an **Install Pending** count for Users and Devices.

#### iOS 11 app inventory API for Mobile Threat Detection <!-- 1391759 -->

Intune collects app inventory information from both personal and corporate-owned devices and makes it available for Mobile Thread Detection (MTD) providers to fetch, such as Lookout for Work. You can collect an app inventory from the users of iOS 11+ devices.

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


### Device management

#### Migrate hybrid MDM users and devices to Intune standalone <!-- 1463747 wnready -->
New processes and tools are now available for moving users and their devices from hybrid MDM to Intune in the Azure portal, allowing you to do the following tasks:
- Copy policies and profiles from the Configuration Manager console to Intune in the Azure portal
- Move a subset of users to Intune in the Azure portal, while keeping the rest in hybrid MDM
- Migrate devices to Intune in the Azure portal without needing to re-enroll them

For details, see [Migrate hybrid MDM users and devices to Intune standalone](https://docs.microsoft.com/sccm/mdm/deploy-use/migrate-hybridmdm-to-intunesa).

#### On-premises Exchange connector high availability support  <!-- 676614 -->
After the Exchange connector creates a connection to Exchange using the specified CAS, the connector now has the ability to discovery other CASs. If the primary CAS becomes unavailable, the connector will fail over to another CAS, if available, until the primary CAS becomes available. For details, see [On-premises Exchange connector high availability support](exchange-connector-install.md#on-premises-exchange-connector-high-availability-support).

#### Remotely restart iOS device (supervised only) <!-- 1424595 -->

You can now trigger a supervised iOS 10.3+ device to restart using a device action. For more information on using the device restart action, see [Remotely restart devices with Intune](device-restart.md).

> [!Note]
> This command requires a supervised devices and the **Device Lock** access right. The device restarts immediately. Passcode-locked iOS devices will not rejoin a Wi-Fi network after restart; after restart, they may not be able to communicate with the server.

#### Single Sign-on support for iOS <!-- 1333645 -->  

You can use Single Sign-on for iOS users. The iOS apps that are coded to look for user credentials in the Single Sign-on payload are functional with this payload configuration update. You can also use UPN and Intune Device ID to configure the Principal Name and Realm. For details, see [Configure Intune for iOS device single sign-on](sso-ios.md).

#### Add "Find my iPhone" for personal devices <!--1427287-->
You can now view whether iOS devices have Activation Lock turned on. This feature previously could be found in the Intune in the classic portal.


#### Remotely lock managed macOS device with Intune <!-- 1437691 -->

You can lock a lost macOS device, and set a 6-digit recovery PIN. When locked, the **Device overview** blade displays the PIN until another device action is sent.

For more information, see [Remotely lock managed devices with Intune](device-remote-lock.md).

#### New SCEP profile details supported <!-- 1559808 -->

Administrators are now able to set additional settings when creating a SCEP profile on Windows, iOS, macOS, and Android platforms.  Administrators can set IMEI, serial number, or common name including email in the subject name format.

<!-- #### Update to what device details your company may see -1616825
The Company Portal app for Android can now use geofencing to protect access to company resources. It uses network details such as IP address, default gateway address, and Domain Name System (DNS) to determine whether to allow access to protected company resources. -->

#### Retain data during a factory reset  <!--1588489 -->
When resetting Windows 10 version 1709 and later to factory settings, a new capability is available. Admins can specify if device enrollment and other provisioned data are retained on a device through a factory reset.

The following data is retained through a factory reset:
- User accounts associated with the device
- Machine state (domain join, Azure Active Directory-joined)
- MDM enrollment
- OEM installed apps (store and Win32 apps)
- User profile
- User data outside of user profile
- User autologon

The following data is not retained:
- User files
- User installed apps (store and Win32 apps)
- Non-default device settings

### Monitor and troubleshoot
#### Window 10 update ring assignments are displayed <!-- 1621837 -->
When you are **Troubleshooting,** for the user you are viewing, you are able to see any Windows 10 update rings assignments.  

#### Windows Defender Advanced Threat Protection reporting frequency settings  <!-- 1455974  -->
Windows Defender Advanced Threat Protection (WDATP) service allows admins to manage reporting frequency for managed devices. With the new **Expedite telemetry reporting frequency** option, WDATP collects data and assesses risks more frequently. The default for reporting optimizes speed and performance. Increasing the frequency of reporting can be valuable for high-risk devices. This setting can be found in the **Windows Defender ATP** profile in **Device configurations**.

#### Audit updates <!-- 1412961 -->  
Intune auditing provides a record of change operations related to Intune.  All create, update, delete, and remote task operations are captured and retained for one year.  The Azure portal provides a view of the last 30 days of audit data in each workload, and is filterable.  A corresponding Graph API allows retrieval of the auditing data stored for the last year.

Auditing is found under the **MONITOR** group. There is an **Audit Logs** menu item for each workload.




## Week of November 20, 2017

### App management

#### Google Play Protect support on Android <!-- 908720 -->

With the release of Android Oreo, Google introduces a suite of security features called Google Play Protect that allow users and
organizations to run secure apps and secure Android images. Intune now supports Google Play Protect features, including SafetyNet
remote attestation. Admins can set compliance policy requirements that require Google Play Protect to be configured and healthy.
The **SafetyNet device attestation** setting requires the device to connect with a Google service to verify that the device is
healthy and is not compromised. Admins can also set a configuration profile setting for Android for Work to require that
installed apps are verified by Google Play services. If a device is not compliant with Google Play Protect requirements, conditional access might block users from accessing corporate resources.

- Learn [How to create a device compliance policy to enable Google Play Protect](https://docs.microsoft.com/intune/compliance-policy-create-google-play-protect).

#### Text protocol allowed from managed Apps <!-- 1414050  -->

Apps managed by the Intune App SDK are able to send SMS messages.

## Week of November 13, 2017

### Intune Apps
#### Company Portal app for macOS is available <!--1541700-->
The Intune Company Portal on macOS has an updated experience, which has been optimized to cleanly display all the information and compliance notifications your users need for all the devices they have enrolled. And, once the Intune Company Portal has been deployed to a device, Microsoft AutoUpdate for macOS will provide updates to it. You can download the new Intune Company Portal for macOS by logging into the Intune Company Portal website from a macOS device.

#### Microsoft Planner is now part of the mobile app management (MAM) list of approved apps  <!-- 1248473 -->
The Microsoft Planner app for iOS and Android is now part of the approved apps for mobile app management (MAM). The app can be configured through the Intune App Protection blade in the Azure portal to all tenants.
- Learn more the [MAM list of approved apps](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

#### Per-App VPN requirement update frequency on iOS devices   <!-- 1547061 -->  
Administrators may now remove Per-App VPN requirements for apps on iOS devices; affected devices will after their next Intune check-in, which generally occurs within 15 minutes.  

### Monitor and troubleshoot
#### Support for System Center Operations Manager management pack for Exchange connector <!-- 885457 -->
The System Center Operations Manager (SCOM) management pack for Exchange connector is now available to help you parse the Exchange connector logs. This feature gives you different ways of monitoring the service when you need to troubleshoot issues.

## Week of November 6, 2017

### Device enrollment
#### Co-management for Windows 10 devices  <!-- 1243445 -->
Co-management is a solution that provides a bridge from traditional to modern management, and it provides you with a path to make the transition using a phased approach. At its foundation, co-management is a solution where Windows 10 devices are concurrently managed by Configuration Manager and Microsoft Intune, as well as joined to Active Directory (AD) and Azure Active Directory (Azure AD).  This configuration provides you with a path to modernize over time, at the pace that’s right for your organization if you can’t move all at once.  

#### Restrict Windows Enrollment by OS version <!-- 245498 -->
As an Intune administrator, you can now specify a minimum and maximum version of Windows 10 for device enrollments. You can set these restrictions in the **Platform Configurations** blade.

Intune will continue to support enrolling Windows 8.1 PCs and phones. However, only Windows 10 versions can be set with minimum and maximum limits. To permit enrollment of 8.1 devices, leave the minimum limit empty.

#### Alerts for Windows AutoPilot unassigned devices  <!-- 1631236 -->
A new alert is available for Windows AutoPilot unassigned devices on the **Microsoft Intune** > **Device enrollment** > **Overview** page. This alert shows how many devices from the AutoPilot program do not have AutoPilot deployment profiles assigned. Use the information in the alert to create profiles and assign them to the unassigned devices. When you click the alert, you see a full list of Windows AutoPilot devices and detailed information about them. For more information, see [Enroll Windows devices using Windows AutoPilot deployment program](https://docs.microsoft.com/intune/enrollment-autopilot).

### Device management

#### Refresh button for Devices list    <!-- 1333581 -->
Because the Device list does not refresh automatically, you can use the new Refresh button to update the devices that display in the list.

#### Support for Symantec Cloud Certification Authority (CA)  <!-- 1333638 -->    
Intune now supports Symantec Cloud CA, which allows the Intune Certificate Connector to issue PKCS certificates from the Symantec Cloud CA to Intune managed devices. If you're already using the Intune Certificate Connector with Microsoft Certification Authority (CA), you can use the existing Intune Certificate Connector setup to add the Symantec CA support.

#### New items added to device inventory   <!--1404455 -->
The following new items are now available to the [inventory taken by enrolled devices](device-inventory.md):

- Wi-Fi MAC address
- Total storage space
- Total free space
- MEID
- Subscriber carrier


### App management
#### Set access for apps by minimum Android security patch on the device<!-- 1278463 -->   
An administrator is able to define the minimum Android security patch that must be installed on the device in order to gain access to a managed application under a managed account.

> [!Note]  
> This feature only restricts security patches released by Google on Android 6.0+ devices.

#### App-conditional launch support <!-- 1193313 -->
IT admins can now set a requirement through the Azure admin portal to enforce a passcode instead a numeric PIN through the mobile app management (MAM) when the application launch. If configured, the user is required to set and use a passcode when prompted before getting access to MAM-enlightened applications. A passcode is defined as a numeric PIN with at least one special character or upper/lowercase alphabet. This release of Intune will enable this feature **on iOS only**. Intune supports passcode in a similar way to numeric PIN, it sets a minimum length, allowing repeat characters and sequences. This feature requires the participation of applications (that is, WXP, Outlook, Managed Browser, Yammer) to integrate the Intune App SDK with the code for this feature in place for the passcode settings to be enforced in the targeted applications.

#### App Version number for line-of-business in device install status report <!-- 1233999 -->
With this release, the Device install status report displays the app version number for the line-of-business apps for iOS and Android. You may use this information to troubleshoot your apps, or find devices that are running outdated app versions.


### Device configuration
#### Admins can now configure the Firewall settings on a device using a device configuration profile <!-- 951708 -->   
Admins can turn on firewall for devices, and also configure various protocols for domain, private, and public networks.  These firewall settings can be found in the "Endpoint protection" profile.

#### Windows Defender Application Guard helps protect devices from untrusted websites, as defined by your organization <!-- 958257 -->   
Admins can define sites as "trusted" or "corporate" using a Windows Information Protection workflow or the new "Network boundary" profile under device configurations. If they are viewed with Microsoft Edge, any sites that aren't listed in on a 64-bit Windows 10 device’s trusted network boundary open instead in a browser within a Hyper-V virtual computer.

Application Guard can be found in the device configuration profiles, in the "Endpoint protection" profile. From there, admins can configure interaction between the virtualized browser and the host machine, nontrusted sites and trusted sites, and storing data generated in the virtualized browser. To use Application Guard on a device, a network boundary first must be configured. It's important to define only one network boundary for a device.  

#### Windows Defender Application Control on Windows 10 Enterprise provides mode to trust only authorized apps <!-- 1031096 -->    
With thousands of new malicious files created every day, using antivirus signature-based detection to fight against malware might no longer provide an adequate defense against new attacks. Using Windows Defender Application Control on Windows 10 Enterprise, you can change device configuration from a mode where apps are trusted unless blocked by an antivirus or other security solution, to a mode where the operating system trusts only apps authorized by your enterprise. You assign trust to apps in Windows Defender Application Control.

Using Intune, you can configure the application control policies either in "audit only" mode or enforce mode. Apps aren't blocked when running in “audit only” mode. “Audit only” mode logs all events in local client logs. You can also configure whether only Windows components and Microsoft Store apps are allowed to run or whether additional apps with good reputations as defined by the Intelligent Security Graph are allowed to run.

#### Window Defender Exploit Guard is a new set of intrusion prevention capabilities for Windows 10 <!-- 1063615 -->   
Window Defender Exploit Guard includes custom rules to reduce the exploitability of applications, prevents macro and script threats, automatically blocks network connections to low reputation IP addresses, and can secure data from ransomware and unknown threats. Windows Defender Exploit Guard consists of the following components:

- **Attack Surface Reduction (ASR)** provides rules that allow you to prevent macro, script, and email threats.
- **Controlled Folder access** automatically blocks access to content to protected folders.
- **Network Filter** blocks outbound connection from any app to low rep IP/domain
- **Exploit Protection** provides memory, control flow, and policy restrictions that can be used to protect an application from exploits.


#### Manage PowerShell scripts in Intune for Windows 10 devices <!-- 790537 -->

The Intune management extension lets you upload PowerShell scripts in Intune to run on Windows 10 devices. The extension supplements Windows 10 mobile device management (MDM) capabilities and makes it easier for you to move to modern management. For details, see [Manage PowerShell scripts in Intune for Windows 10 devices](intune-management-extension.md).

#### New device restriction settings for Windows 10      <!-- 1308850 -->
-    Messaging (mobile only) - disable testing or MMS messages
-    Password - settings to enable FIPS and the use of Windows Hello devices secondary devices for authentication 
-    Display - settings to turn on or off GDI Scaling for legacy apps

#### Windows 10 kiosk mode device restrictions <!-- 1308872 -->   
You can restrict Windows 10 device users to kiosk mode, which limits users to a set of predefined apps.  To do so, create a Windows 10 device restriction profile and set the Kiosk settings.

Kiosk mode supports two modes: **single app** (allows a user to run just one app) or **multi app** (permits access to a set of apps).  You define the user account and device name, which determines the supported apps).  When the user is logged in, they're limited to the defined apps.  To learn more, see [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp). 

Kiosk mode requires:

- Intune must be the MDM authority.
- The apps must already be installed on the target device.
- The device must be [properly provisioned](https://docs.microsoft.com/windows/configuration/set-up-a-kiosk-for-windows-10-for-desktop-editions).

#### New device configuration profile for creating network boundaries <!-- 1311967 -->   
A new device configuration profile called **Network boundary** can be found with your other device configuration profiles. Use this profile to define online resources that you want to be considered corporate and trusted. You must define a network boundary for a device *before* features such as Windows Defender Application Guard and Windows Information Protection can be used on the device. It’s important to define only one network boundary for each device.

You can define enterprise cloud resources, IP address ranges, and internal proxy servers that you want to be considered trusted. Once defined, the network boundary can be consumed by other features such as Windows Defender Application Guard and Windows Information Protection.

####  Two additional settings for Windows Defender Antivirus <!-- 1338409 -->  
**File blocking level**

| | |
|---|---|
| Not Configured | **Not Configured** uses the default Windows Defender Antivirus blocking level and provides strong detection without increasing the risk of detecting legitimate files. |
| High | **High** applies a strong level of detection.
| High +  | **High +** provides the High level with additional protection measures that might impact client performance.
| Zero tolerance  | **Zero tolerance** blocks all unknown executables. |

While unlikely, setting to **High** may cause some legitimate files to be detected.
We recommend you set File blocking level to the default, **Not configured**.

**Time out extension for file scanning by the cloud**  

| | |
|--|--|
| Number of seconds (0-50) | Specify the maximum amount of time that Windows Defender Antivirus should block a file while waiting for a result from the cloud. The default amount is 10 seconds: any additional time specified here (up to 50 seconds) is added to those 10 seconds. In most cases, the scan takes much less time than the maximum. Extending the time allows the cloud to thoroughly investigate suspicious files. We recommend that you enable this setting and specify at least 20 additional seconds. |

#### Citrix VPN added for Windows 10 devices <!-- 1512457 -->  
You can configure Citrix VPN for their Windows 10 devices. You can choose the Citrix VPN in the *Select a connection type* list in the **Base VPN** blade when configuring a VPN for Windows 10 and later.

> [!Note]
> Citrix configuration existed for iOS and Android.

#### Wi-Fi connections support pre-shared keys on iOS <!-- 1550823 -->
Customers can configure Wi-Fi profiles to use pre-shared keys (PSK) for WPA/WPA2 Personal connections on iOS devices. These profiles are pushed to user's device when the device is enrolled into Intune.

When the profile has been pushed to the device, the next step depends on the profile configuration.  If set to connect automatically, it does so when the network is next needed.  When the profile is connects manually, the user must activate the connection manually.  

### Intune apps

#### Access to managed app logs for iOS <!-- 1469920 -->
End users with the managed Browser installed can now view the management status of all Microsoft published apps and send logs for troubleshooting their managed iOS apps.

Learn how to enable the troubleshooting mode in the Managed Browser on an iOS device, see [How to access to managed app logs using the Managed Browser on iOS](app-configuration-managed-browser.md#how-to-access-to-managed-app-logs-using-the-managed-browser-on-ios).

#### Improvements to device setup workflow in the Company Portal for iOS in version 2.9.0 <!-- 1417174 -->

The device setup workflow has been improved in the Company Portal app for iOS. The language is more user-friendly and we've combined screens where possible. The language is more specific to your company by using your company name throughout the setup text. You can see this updated workflow on the [what's new in app UI page](whats-new-app-ui.md).

### Monitor and troubleshoot

#### User entity contains latest user data in Data Warehouse data model <!-- 1544273 -->
The first version of the Intune Data Warehouse data model only contained recent, historical Intune data. Report makers could not capture the current state of a user. In this update, the **User entity** is populated with the latest user data.


## Notices

### Plan for Change: Update where you Configure your App Protection Policies

Starting in March of 2018, we’re going to temporarily redirect you from the Intune App Protection service blade in the Azure portal to the Mobile app blade within Intune in the Azure portal. Note that all of your App protection policies are already on the Mobile app blade in Intune under app configuration. Instead of going to Intune App Protection, you’ll just go to Intune. In April, we will stop the redirection and fully remove the Intune App Protection service blade, again it is duplicating what is now built into Intune. 

#### How does this affect me?
This change will affect both Intune standalone customers and hybrid (Intune with Configuration Manager) customers. This integration will help simplify your cloud management administration. Now, you’ll just have one blade to go to in Azure – the Intune blade – to manage groups, policies, apps, and any mobile device management.

#### What do I need to do to prepare for this change?
Please tag Intune as a favorite instead of the Intune App Protection service blade and ensure you’re familiar with the App protection policy workflow in the Mobile app blade within Intune. We’ll redirect for a short period of time and then remove the App Protection blade. Remember, all App Protection policies are already over in Intune and you can modify any of your conditional access policies by following the documentation here: [https://aka.ms/azuread_ca](https://aka.ms/azuread_ca).

**Additional Information**: [https://aka.ms/intuneapppolicy](https://aka.ms/intuneapppolicy)

### Updated: New security enhancements in the Intune service  <!-- 1637539 -->   

We’re rolling out security enhancements in the Intune service. As a part of this change, with the March update to the Intune service, you will have a toggle in the Intune on Azure console to turn this security feature on or off. When the feature is on, devices with no compliance policy assigned to them will be marked as ‘not compliant’.

**Hybrid customers**: We will not be introducing this change for hybrid customers at this time. You do not need to take any action. However, we highly encourage you to ensure that your devices have at least one compliance policy assigned to them.

#### How does this affect me?

When we start rolling this change out in the March update, this feature will affect you differently depending on whether you already have compliance policies assigned or not.

- If you are a new or existing tenant and do not have any compliance policies assigned to your devices, the toggle will be automatically set to **compliant**. The feature will be off as a default setting in the console. There will be no end user impact.
- If you are an existing tenant and you have any devices with a compliance policy assigned to them, the toggle will automatically be set to ‘not compliant’. The feature will be on as a default setting, when the March update rolls out. 

If you use compliance policies with Conditional Access (CA), and have the feature turned on, any devices without at least one compliance policy assigned to them will now be blocked by CA. End users associated with these devices, who were previously allowed access to email, will lose their access unless you assign at least one compliance policy to all devices.   
 
#### What do I need to do to prepare for this change?  

If you use Conditional Access, we recommend you have this feature turned on and leave the toggle set to **Not compliant**. To avoid loss of email access for your end users, please ensure that all your devices have at least one compliance policy assigned to them. Here are some changes we’re making to help you do this:   

- We’ve introduced a report called **Devices without compliance policy** in the Intune portal, which you can use to identify all the devices in your environment that do not have a compliance policy assigned. 
- There is an **All Users** option to make it easy to assign a compliance policy to all users.

If you choose to leave the toggle turned off, no further action is required on your part.

**Additional Information**: [https://aka.ms/compliance_policies](https://aka.ms/compliance_policies)

### Plan for Change: Change in support for the Microsoft Intune App SDK for Cordova plugin
Intune is ending support for the [Microsoft Intune App SDK Cordova Plugin](app-sdk-cordova.md) on May 1, 2018. We recommend that you use the Intune App Wrapping Tool instead, to prepare your Cordova based apps for manageability and availability in Intune. When this change takes effect, the Microsoft Intune APP SDK for Cordova plugin will no longer be maintained or receive updates. App developers will not be able to use this plugin. Intune plans to continue supporting apps built with Cordova. However, any apps built with the Microsoft Intune APP SDK for Cordova plugin will experience reduced functionality in Intune. After wrapping with the Intune App Wrapping Tool, apps can be deployed to end users as they normally would be. For Cordova-based Android apps that are released to the Google Play Store:
- End users will be prompted for credentials to receive Intune policy on first launch.
- Apps should be released to the app store targeted for Intune users, for example “Contoso App for Intune”. 

For more information about the App Wrapping Tool, see [App Wrapping Tool for iOS](app-wrapper-prepare-ios.md) and [App Wrapping Tool for Android](app-wrapper-prepare-android.md). For any issues or questions, contact [msintuneappsdk@microsoft.com](mailto:msintuneappsdk@microsoft.com). 

### Plan for Change: Use Intune on Azure now for your MDM management <!-- 1227338 -->
Over a year ago, we announced [public preview of Intune on Azure](https://cloudblogs.microsoft.com/enterprisemobility/2016/12/07/public-preview-of-intune-on-azure/) and followed up six months ago with [general availability of the new admin experience](https://cloudblogs.microsoft.com/enterprisemobility/2017/06/08/the-new-intune-and-conditional-access-admin-consoles-are-ga/) for Intune. Starting on April 2, 2018, we will turn off mobile device management (MDM) in the classic Silverlight console for those customers using Intune standalone. Instead, you can use [Intune on Azure](https://aka.ms/Intune_on_Azure) for your MDM needs. If you're still using the classic console for MDM, please stop and familiarize yourself with Intune on Azure. We do not expect any end user impact with this change. Classic PC management will remain in Silverlight. You can learn more about this change and how it affects you [here](https://aka.ms/Intune_on_Azure_mdm).


### Plan for Change: Easy Assist End-of-Life <!-- 1556480 -->
Intune uses the Microsoft Easy Assist for PC management remote assistance. One thing you may not know is that Microsoft Easy Assist is a component of Office Live Meeting, a service that is being deprecated December 31, 2017. Therefore, Intune’s Easy Assist offering will also reach end of life on December 31, 2017.

### Manage Android for Work devices independently from Android devices <!-- 1490731 EEready-->    
**Note**: The following changes will start rolling out with the November update, but may take time to execute on your account. You will receive a confirmation notification in the Office 365 portal when these changes are effective for your account. After the roll out, you’ll have additional manageability options. There will be no change to the end user experience during the rollout.

Intune supports managing enrollment of Android for Work devices independently from the Android platform. These settings are managed under **Device Enrollment** > **Enrollment restrictions** > **Device Type Restrictions**. (They were previously located under **Device Enrollment** > **Android for Work Enrollment** > **Android for Work Enrollment Settings**.)

By default, your Android for Work devices settings will be the same as your settings for your Android devices. However, after you change your Android for Work settings that will no longer be the case.

If you block personal Android for Work enrollment, only corporate Android devices can enroll as Android for Work.

When working with the new settings, consider the following points:

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

### Deprecating support for OS X Mavericks 10.10 and previous versions of macOS <!--1489263, plan for change for 1802-->
Deprecation of enrollment for devices with OS X Yosemite 10.10 and previous versions of macOS will begin in February 2018. Intune fully supports OS X El Capitan 10.11 and newer.

### New path for managed devices in Graph API <!-- 1586728 -->
The path used to access managed devices in the beta version of the Graph API is changing. 

| | |
|--|--|
| Current path |  https://graph.microsoft.com/beta/managedDevices |
| New path | https://graph.microsoft.com/beta/deviceManagement/managedDevices |

Both paths will work through the month of October. After the October service release, only the new path will work.  If you are using the Graph API to access managed devices, update and verify your scripts and applications with the new path. For additional changes, check the monthly [Graph API changelog](https://developer.microsoft.com/graph/docs/concepts/changelog).


### Direct access to Apple enrollment scenarios <!--951869-->
For Intune accounts created after January 2017, Intune has enabled direct access to Apple enrollment scenarios using the Enroll Devices workload in the Azure portal. Previously, the Apple enrollment preview was only accessible from links in the Intune classic portal. Intune accounts created before January 2017 require a one-time migration before these features are available in Azure. The schedule for migration has not been announced yet, but details will be made available as soon as possible. If your existing account cannot access the Azure portal, we strongly recommend creating a trial account to test out the new experience.

### Administration roles being replaced in Azure portal
The existing mobile application management (MAM) administration roles (Contributor, Owner, and Read-Only) used in the Intune classic portal (Silverlight) are being replaced with a full set of new role-based administration controls (RBAC) in the Intune Azure portal. Once you are migrated to the Azure portal, you will need to reassign your admins to these new administration roles. For more information about RBAC and the new roles, see [Role-based access control for Microsoft Intune](/intune/role-based-access-control).

## What's coming

### User experience update for the Company Portal app for iOS <!--1412866-->

We will be releasing a major user experience update to the Company Portal app for iOS. The update will feature a complete visual redesign, which includes a modernized look and feel with increased usability and accessibility. All current iOS Company Portal functionality will be maintained.

We are offering a pre-release version of the updated Company Portal app for iOS through the Apple TestFlight program for you to use and to provide feedback. Sign up at https://aka.ms/intune_ios_cp_testflight for TestFlight access.

### Conditional Access policies for Intune will only be available from the Azure portal  <!-- 1737088 -->
We are simplifying where you configure and manage conditional access. Currently, you can manage conditional access from the Intune App Protection (MAM) blade, and through the classic Azure AD experience in the [Windows Azure portal](https://manage.windowsazure.com). Starting in January, you will only be able to configure and manage your policies in the [Azure portal](https://portal.azure.com) from **Azure Active Directory** > **Conditional Access**. For your convenience, you can also access this blade from Intune in the Azure portal at **Intune** > **Conditional Access**.

### Manage Jamf-enrolled macOS devices with Intune's device compliance engine <!--1592747-->
Beginning in early 2018, Jamf will send macOS device state information to Intune, which will then evaluate it for compliance with policies defined in the Intune console. Based on the device compliance state as well as other conditions (such as location, user risk, etc.), conditional access will enforce compliance for macOS devices accessing cloud and on-premises applications connected with Azure AD, including Office 365.

### Changes in support for the Intune iOS Company Portal app  <!-- 1164474  -->
Coming soon, there will be a new version of the Microsoft Intune Company Portal app for iOS that will support only devices running iOS 9.0 or later. The version of the Company Portal that supports iOS 8 will still be available for a short period of time. However, if you also use MAM-enabled iOS apps we support iOS 9.0 and later, so you'll want to ensure your end users update to the latest OS. 

#### How does this affect me?
We are letting you know this in advance, even though we don't have specific dates, so you have time to plan. Ensure your users are updated to iOS 9+ and when the Company Portal app releases, request that your end users update their Company Portal app.

#### What do I need to do to prepare for this change?
Encourage your users to update to iOS 9.0 or later to take full advantage of new Intune features.  Encourage users to install the new
version of the Company Portal and take advantage of the new features it will offer.

Go to the Intune in the Azure portal and view Devices > All Devices and filter by iOS version to see any current devices with operating systems earlier than iOS 9.


### Apple to require updates for Application Transport Security <!--748318-->
Apple has announced that they will enforce specific requirements for Application Transport Security (ATS). ATS is used to enforce stricter security on all app communications over HTTPS. This change impacts Intune customers using the iOS Company Portal apps.

We have made available a version of the Company Portal app for iOS through the Apple TestFlight program that enforces the new ATS requirements. If you would like to try it so you can test your ATS compliance, email <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app">CompanyPortalBeta@microsoft.com</a> with your first name, last name, email address, and company name. Review our [Intune support blog](https://aka.ms/compportalats) for more details.

## See also
* [Microsoft Intune Blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Cloud Platform roadmap](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [What's new in the Company Portal UI](whats-new-app-ui.md)
* [What's new in previous months](whats-new-archive.md)
