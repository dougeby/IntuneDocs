---
# required metadata
title: What's new in Microsoft Intune - Azure | Microsoft Docs
titlesuffix:
description: Find out what's new in the Intune Azure portal
keywords:
author: ErikjeMS  
ms.author: erikje
manager: dougeby
ms.date: 08/29/2018
ms.topic: conceptual
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: dougeby
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure; get-started
---

# What's new in Microsoft Intune
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Learn what’s new each week in Microsoft Intune. You can also find out about [upcoming changes](#whats-coming), [important notices](#notices) about the service, and information about [past releases](whats-new-archive.md). Some features may roll out over several weeks and might not be available to all customers in the first week.

> [!Note]
> For information on new functionality in hybrid mobile device management (MDM), check out the [hybrid What’s New page](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).


<!-- Common categories:  
### App management
### Device configuration
### Device enrollment
### Device management
### Intune apps
### Monitor and troubleshoot
### Role-based access control

-->   

## Week of August 27, 2018

### App management

#### Packet tunnel support for iOS per-app VPN profiles for custom and Pulse Secure connection types <!-- 1520957 -->
When using iOS per-app VPN profiles, you can choose to use app-layer tunneling (app-proxy) or packet-level tunneling (packet-tunnel). These options are available with the following connection types:
- Custom VPN
- Pulse Secure
If you are not sure which value to use, consult your VPN provider's documentation.

#### Delay when iOS software updates are shown on the device <!-- 1949583 -->
In Intune > **Software Updates** > **Update policies for iOS**, you can configure the days and times when you don't want devices to install any updates. In a future update, you'll be able to delay when a software update is visibly shown on the device, from 1-90 days. 
[Configure iOS update policies in Microsoft Intune](software-updates-ios.md) lists the current settings.

#### Office 365 ProPlus version <!-- 2213968 -->
When assigning the Office 365 ProPlus apps to Windows 10 devices using Intune, you will be able to select the version of Office. In the Azure portal, select **Microsoft Intune** > **Apps** > **Add App**. Then, select **Office 365 ProPlus Suite (Windows 10)** from the **Type** dropdown list. Select **App Suite Settings** to display the associated blade. Set the **Update Channel** to a value, such as **Monthly**. Optionally, remove other version of Office (msi) from end user devices by selecting **Yes**. Select **Specific** to install a specific version of Office for the selected channel on end user devices. At this point, you can select the **Specific version** of Office to use. The available versions will change over time. Therefore, when creating a new deployment, the versions available may be newer and not have certain older versions available. Current deployments will continue to deploy the older version, but the version list will be continually updated per channel. For more information, see [Overview of update channels for Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus).

#### Support for Register DNS setting for Windows 10 VPN <!-- 2282852 -->
With this update, you can configure Windows 10 VPN profiles to dynamically register the IP addresses assigned to the VPN interface with the internal DNS, without needing to use custom profiles.
For information about the current VPN profile settings available, see [Windows 10 VPN settings](vpn-settings-windows-10.md). 

#### The macOS Company Portal installer now includes the version number in the installer file name <!--2652728-->

#### iOS automatic app updates <!-- 2729759 wnready -->
Automatic app updates work for both device and user licensed apps for iOS Version 11.0 and above.




### Device configuration

#### Windows Hello will target users and devices <!-- 1106609 -->
When you create a [Windows Hello for Business](windows-hello.md) policy, it applies to all users within the organization (tenant-wide). With this update, the policy can also be applied to specific users or specific devices using a device configuration policy (**Device Configuration** > **Profiles** > **Create profile** > **Identity Protection** > **Windows Hello for Business**).
In Intune in the Azure portal, the Windows Hello configuration and settings now exists in both **Device enrollment** and **Device configuration**. **Device enrollment** targets the entire organization (tenant-wide), and supports Windows AutoPilot (OOBE). **Device configuration** targets devices and users using a policy that's applied during check-in.
This feature applies to:  
- Windows 10 and later
- Windows Holographic for Business

#### Zscaler is an available connection for VPN profiles on iOS <!-- 1769858 eeready -->
When you create an iOS VPN device configuration profile (**Device configuration** > **Profiles** > **Create profile** > **iOS** platform > **VPN** profile type), there are several connection types, including Cisco, Citrix, and more. This update adds Zscaler as a connection type. 
[VPN settings for devices running iOS](vpn-settings-ios.md) lists the available connection types.

#### FIPS mode for Enterprise Wi-Fi profiles for Windows 10 <!-- 1879077 eeready -->
You can now enable Federal Information Processing Standards (FIPS) mode for Enterprise Wi-Fi profiles for Windows 10 in the Intune Azure portal. Be sure FIPS mode is enabled on your Wi-Fi infrastructure if you enable it in your Wi-Fi profiles.
[Wi-Fi settings for Windows 10 and later devices in Intune](wi-fi-settings-windows.md) shows you how to create a Wi-Fi profile.

#### Control S-mode on Windows 10 and later devices - public preview <!-- 1958649 -->
With this feature update, you can create a device configuration profile that switches a Windows 10 device out of S-mode, or prevent users from switching the device out of S-mode. This feature is in Intune > **Device configuration** > **Profiles** >  **Windows 10 and later** > **Edition upgrade and mode switch**.
[Introducing Windows 10 in S mode](https://www.microsoft.com/windows/s-mode) provides more information on S mode.
Applies to: the most recent [Windows Insider](https://docs.microsoft.com/en-us/windows-insider/at-work-pro/) build (while in preview).


#### Windows Defender ATP configuration package automatically added to configuration profile <!-- 2144658 -->
When using [Advanced Threat Protection and onboarding](advanced-threat-protection.md#onboard-devices-using-a-configuration-profile) devices in Intune, you previously had to download a configuration package, and add it to your configuration profile. With this update, Intune automatically gets the package from Windows Defender Security Center, and adds it to your profile.
Applies to Windows 10 and later.

#### Require users to connect during device setup <!--2311457-->
You can now set device profiles to require that the device connects to a network before proceeding past the Network page during Windows 10 setup. While this feature is in preview, a Windows Insider build 1809 or later is required to use this setting.
Applies to: the most recent [Windows Insider](https://docs.microsoft.com/en-us/windows-insider/at-work-pro/) build (while in preview).


#### Restricts apps, and block access to company resources on iOS and Android Enterprise devices <!-- 2451462 -->
In **Device compliance** > **Policies** > **Create policy** > **iOS** > **System Security**, there is a new **Restricted applications** setting. This new setting uses a compliance policy to block access to company resources if certain apps are installed on the device. The device is considered non-compliant until the restricted apps are removed from the device.
Applies to: iOS

#### Modern VPN support updates for iOS <!-- 2459928, 1819876, and 2650856 -->
This update adds support the following iOS VPN clients: 
- F5 Access (version 3.0.1 and higher)
- Citrix SSO
- Palo Alto Networks GlobalProtect version 5.0 and higher
Also in this update:
- Existing **F5 Access** connection type is renamed to **F5 Access Legacy** for iOS.
- Existing **Palo Alto Networks GlobalProtect** connection type is renamed to **Palo Alto Networks GlobalProtect (legacy)** for iOS.
Existing profiles with these connection types continue to work with their respective legacy VPN client. If you're using Cisco Legacy AnyConnect, F5 Access Legacy, Citrix VPN, or Palo Alto Networks GlobalProtect version 4.1 and earlier with iOS, you should move to the new apps. Do this as soon as possible to ensure that VPN access is available for iOS devices as they update to iOS 12.
For more information about iOS 12 and VPN profiles, see the [Microsoft Intune Support Team Blog](https://go.microsoft.com/fwlink/?linkid=2013806).

#### Export Azure classic portal compliance policies to recreate these policies in the Intune Azure portal <!-- 2469637 -->
Compliance policies created in the Azure classic portal will be deprecated. You can review and delete any existing compliance policies, however you can't update them. If you need to migrate any compliance policies to the current Intune Azure portal, you can export the policies as a comma-separated file (*.csv* file). Then, use the details in the file to recreate these policies in the Intune Azure portal.

> [!IMPORTANT]
> When the Azure classic portal retires, you will no longer be able to access or view your compliance policies. Therefore, be sure to export your policies and recreate them in the Azure portal before the Azure classic portal retires.

#### Better Mobile - New Mobile Threat Defense partner <!-- 22662717 -->
You can control mobile device access to corporate resources using conditional access based on risk assessment conducted by Better Mobile, a Mobile Threat Defense solution that integrates with Microsoft Intune.

### Device enrollment

#### Lock the Company Portal in single app mode until user sign-in <!--1067692 --> 
You now have the option to run the Company Portal in Single App mode if you authenticate a user through the Company Portal instead of Setup Assistant during DEP enrollment. This option locks the device immediately after Setup Assistant completes so that a user must sign in to access the device. This process makes sure that the device completes onboarding and is not orphaned in a state without any user tied.

#### Assign a user and friendly name to an Autopilot device <!--1346521 -->
You can now [assign a user to a single Autopilot device](enrollment-autopilot.md). Admins will also be able to give friendly names to greet the user when setting up their device with Autopilot.
Applies to: the most recent [Windows Insider](https://docs.microsoft.com/en-us/windows-insider/at-work-pro/) build (while in preview).

#### Use VPP device licenses to pre-provision the Company Portal during DEP enrollment <!-- 1608345 -->
You can now use Volume Purchase Program (VPP) device licenses to pre-provision the Company Portal during Device Enrollment Program (DEP) enrollments. To do so, when you [create or edit an enrollment profile](device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile), specify the VPP token that you want to use to install the Company Portal. Make sure that your token doesn't expire and that you have enough licenses for the Company Portal app. In cases where the token expires or runs out of licenses, Intune will push the App Store Company Portal instead (this will prompt for an Apple ID).

### Confirmation required to delete VPP token that is being used for Company Portal pre-provisioning <!-- 2237634 -->
A confirmation is now required to delete a Volume Purchase Program (VPP) token if it is being used to pre-provision the Company Portal during DEP enrollment.

#### Block Windows personal device enrollments <!-- 1849498 -->
You can [block Windows personal devices](enrollment-restrictions-set.md#set-device-type-restrictions) from enrolling with [mobile device management](windows-enroll.md) in Intune. Devices enrolled with [Intune PC agent](manage-windows-pcs-with-microsoft-intune.md) can't be blocked with this feature. This feature is rolling out over the next couple weeks so you might not see it immediately in the user interface.

#### Specify machine name patterns in an Autopilot profile <!--1849855-->
You can [specify a computer name template](enrollment-autopilot.md#create-an-autopilot-deployment-profile) to generate and set the [computer name](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) during Autopilot enrollment. Applies to: the most recent [Windows Insider](https://docs.microsoft.com/en-us/windows-insider/at-work-pro/) build (while in preview).


#### For Windows Autopilot profiles, hide the change account options on the company sign-in page and domain error page <!--1901669 -->
There are [new Windows Autopilot profile options](enrollment-autopilot.md#create-an-autopilot-deployment-profile) for admins to hide the change account options on the company sign-in and domain error pages. Hiding these options requires Company Branding to be configured in Azure Active Directory. 
Applies to: the most recent [Windows Insider](https://docs.microsoft.com/en-us/windows-insider/at-work-pro/) build (while in preview).


#### Use VPP device licenses to pre-provision the Company Portal during DEP enrollment <!-- 1608345 -->
You can now use Volume Purchase Program (VPP) device licenses to pre-provision the Company Portal during Device Enrollment Program (DEP) enrollments. To do so, when you [create or edit an enrollment profile](device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile), specify the VPP token that you want to use to install the Company Portal. Make sure that your token doesn't expire and that you have enough licenses for the Company Portal app. In cases where the token expires or runs out of licenses, Intune will push the App Store Company Portal instead (this will prompt for an Apple ID).

### Device management

#### Delete Jamf devices <!-- 2653306-->
You can delete JAMF-managed devices by going to **Devices** > choose the Jamf device > **Delete**.

#### Change terminology to "retire" and "wipe" <!-- 2175759 -->
To be consistent with the Graph API, the Intune user interface and documentation has changed the following terms:
- **Remove company data** will be changed to "retire"
- **Factory reset** will be changed to **wipe**

#### Confirmation dialog if admin tries to delete MDM Push Certificate <!-- 297909500-->
If anyone tries to delete an Apple MDM Push certificate, a confirmation dialog box displayss the number of related iOS and macOS devices. If the certificate is deleted, these devices will need to be re-enrolled.

### Additional security settings for Windows installer <!-- 2282430 -->
You can allow users to control app installs. If enabled, installations that may otherwise be stopped due to a security violation would be permitted to continue.​ You can direct the Windows installer to use elevated permissions when it installs any program on a system.​ Additionally, you can enabled Windows Information Protection (WIP) items to be indexed and the metadata about them stored in an unencrypted location. When the policy is disabled, the WIP protected items are not indexed and do not show up in the results in Cortana or file explorer. The functionality for these options are disabled by default. 

### New user experience update for the Company Portal website <!--2000968 -->
We’ve added new features, based on feedback from customers, to the Company Portal website. You'll experience a significant improvement in existing functionality and usability from your devices. Areas of the site&ndash;such as device details, feedback and support, and device overview&ndash;have received a new, modern, responsive design. You'll also see:

- Streamlined workflows across all device platforms
- Improved device identification and enrollment flows
- More helpful error messages
- Friendlier language, less tech jargon
- Ability to share direct links to apps
- Improved performance for large app catalogs
- Increased accessibility for all users  

The [Intune Company Portal website documentation](https://docs.microsoft.com/en-us/intune-user-help/using-the-intune-company-portal-website) has been updated to reflect these changes. To view an example of the app enhancements, see [UI updates for Intune end-user apps](whats-new-app-ui.md).  

### Monitor and troubleshoot

#### Enhanced jailbreak detection in compliance reporting<!-- 2198738 -->
The enhanced jailbreak detection setting states now appears in all compliance reporting in the admin console.

### Role-based access control

#### Scope tags for policies <!--1081974 eeready-->
You can [create scope tags](scope-tags.md) to limit access to Intune resources. Add a scope tag to a role assignment and then add the scope tag to a configuration profile. The role will only have access to resources with configuration profiles that have matching scope tags (or no scope tag).

## Week of August 14, 2018

### macOS support for Apple Device Enrollment Program <!-- 747651 -->
Intune now supports enrolling macOS devices into the Apple Device Enrollment Program (DEP). For more information, see [Automatically enroll macOS devices with Apple's Device Enrollment Program](device-enrollment-program-enroll-macos.md).

## Week of July 23, 2018

### App management

#### Line-of-business (LOB) app support for macOS <!-- 1895847 -->
Microsoft Intune allows macOS LOB apps to be deployed as **Required** or **Available with enrollment**. End users can get apps deployed as **Available** using the Company Portal for macOS or the [Company Portal website](https://portal.manage.microsoft.com).

#### iOS built-in app support for kiosk mode <!-- 2051098 -->
In addition to Store Apps and Managed Apps, you can now select a Built-In App (such as Safari) that runs in kiosk mode on an iOS device.

#### Edit your Office 365 Pro Plus app deployments <!-- 2150145 -->
As the Microsoft Intune admin, you have greater ability to edit your Office 365 Pro Plus app deployments. Additionally, you no longer have to delete your deployments to change any of the suite’s properties. In the Azure portal, select **Microsoft Intune** > **Client apps** > **Apps**. From the list of apps, select your Office 365 Pro Plus Suite.  


#### Updated Intune App SDK for Android is now available <!-- 2744271-->

An updated version of the Intune App SDK for Android is available to support the Android P release. If you are an app developer and use the Intune SDK for Android, you must install the updated version of the Intune app SDK to ensure that Intune functionality within your Android apps continue to work as expected on Android P devices. This version of the Intune App SDK provides a built-in plugin that performs the SDK updates. You do not need to rewrite any existing code that’s integrated. For details, see [Intune SDK for Android](https://github.com/msintuneappsdk/ms-intune-app-sdk-android). If you are using the old badging style for Intune, we recommend that you use the briefcase icon. For branding details, see [this GitHub repository](https://github.com/msintuneappsdk/intune-app-partner-badge).


### Device configuration

#### Use S/MIME to encrypt and sign a user's multiple devices  <!-- 1333642 -->
This update includes S/MIME email encryption using a new imported certificate profile (**Device configuration** > **Profiles** > **Create profile** > select the platform > **PKCS imported certificate** profile type). In Intune, you can import certificates in PFX format. Intune can then deliver those same certificates to multiple devices enrolled by a single user. This also includes:

- The native iOS email profile supports enabling S/MIME encryption using imported certificates in PFX format.
- The native mail app on Windows Phone 10 devices automatically use the S/MIME certificate.
- The private certificates can be delivered across multiple platforms. But, not all email apps support S/MIME.
- On other platforms, you may need to manually configure the mail app to enable S/MIME.  
- Email apps that support S/MIME encryption may handle retrieving certificates for S/MIME email encryption in a way that an MDM cannot support, such as reading from their publisher's certificate store.

Supported on: Windows, Windows Phone 10, macOS, iOS, Android

#### Create device compliance policy using Firewall settings on macOS devices <!-- 1497640 -->
When you create a new macOS compliance policy (**Device compliance** > **Policies** > **Create policy** > **Platform: macOS** > **System security**), there are some new **Firewall** settings available: 

- **Firewall**: Configure how incoming connections are handled in your environment.
- **Incoming connections**: **Block** all incoming connections except those required for basic internet services, such as DHCP, Bonjour, and IPSec. This setting also blocks all sharing services.
- **Stealth Mode**: **Enable** stealth mode to prevent the device from responding to probing requests. The device continues to answer incoming requests for authorized apps.

Applies to: macOS 10.12 and later

#### New Wi-Fi device configuration profile for Windows 10 and later <!-- 1879077 -->
Currently, you can import and export Wi-Fi profiles using XML files. With this update, you can create a Wi-Fi device configuration profile directly in Intune, just like some other platforms.

To create the profile, open **Device configuration** > **Profiles** > **Create Profile** > **Windows 10 and later** > **Wi-Fi**. 

Applies to Windows 10 and later.

#### Kiosk - obsolete is grayed out, and can't be changed <!-- 2149998 eeready -->
The [Kiosk feature](device-restrictions-windows-10.md#kiosk-preview---obsolete) (**Device configuration** > **Profiles** > **Create profile** > **Windows 10 and later** > **Device restrictions**) is obsolete, and replaced with [Kiosk settings for Windows 10 and later](kiosk-settings.md). With this update, the **Kiosk - Obsolete** feature is grayed out, and the user interface can't be changed or updated. 

To enable kiosk mode, see [Kiosk settings for Windows 10 and later](kiosk-settings.md).

Applies to Windows 10 and later, Windows Holographic for Business

#### APIs to use 3rd party certification authorities <!-- 2184013 -->
In this update, there is a Java API that enables third-party certificate authorities to integrate with Intune and SCEP. Then, users can add the SCEP certificate to a profile, and apply it to devices using MDM.

Currently, Intune supports [SCEP requests using Active Directory Certificate Services](certificates-scep-configure.md).

#### Toggle to show or not show the End Session button on a Kiosk browser <!-- 2455253 -->
You can now configure whether or not Kiosk browsers show the End Session button. You can see the control at **Device configuration** > **Kiosk (preview)** > **Kiosk Web Browser**. If turned on, when a user clicks the button, the app prompts for confirmation to end the session. When confirmed, the browser clears all browsing data and navigates back to the default URL.

#### Create an eSIM cellular configuration profile <!-- 2564077 -->
In **Device configuration**, you can create an eSIM cellular profile. You can import a file that contains cellular activation codes provided by your mobile operator. You can then deploy these profiles to your eSIM LTE enabled Windows 10 devices, such as the Surface Pro LTE and other eSIM capable devices.

Check to see if your [devices support eSIM profiles](https://support.microsoft.com/help/4020763/windows-10-use-esim-for-cellular-data).

Applies to Windows 10 and later. 




### Device enrollment

#### Automatically mark Android devices enrolled by using Samsung Knox Mobile Enrollment as "corporate". <!-- 2404851 -->
By default, Android devices enrolled using Samsung Knox Mobile Enrollment are now marked as **corporate** under **Device Ownership**. You don't need to manually identify corporate devices using IMEI or serial numbers prior to enrolling using Knox Mobile Enrollment.

### Device management

#### Bulk delete devices on devices blade <!-- 1793693 -->

You can now delete multiple devices at a time on the Devices blade. Choose **Devices** > **All devices** > select the devices you want to delete > **Delete**. For devices that can't be deleted, an alert will be displayed.

## Week of July 16, 2018  

### More opportunities to sync in the Company portal app for Windows  
The Company Portal app for Windows now lets you initiate a sync directly from the Windows taskbar and Start menu. This feature is especially useful if your only task is to sync devices and get access to corporate resources. To access the new feature, right-click the Company portal icon that's pinned to your taskbar or Start menu. In the menu options (also referred to as a jump list), select **Sync this device**. The Company Portal will open to the **Settings** page and initiate your sync. For a look at the new functionality see [What's new in the UI](whats-new-app-ui.md).   

### New browsing experiences in the Company portal app for Windows  

Now when browsing or searching for apps in the Company Portal app for Windows, you can toggle between the existing **Tiles** view and the newly added **Details** view. The new view lists application details such as name, publisher, publication date and installation status.  

The **Apps** page's **Installed** view lets you see details about completed and in-progress app installations. To see what the new view looks like, see [What's new in the UI](whats-new-app-ui.md).  
### Improved Company Portal app experience for device enrollment managers  
When a device enrollment manager (DEM) signs in to the Company Portal app for Windows, the app will now only list the DEM's current, running device. This improvement will reduce timeouts that previously occurred when the app tried to show all DEM-enrolled devices.  


## Week of July 9, 2018

### App management

### Block app access based on unapproved device vendors and models  <!-- 1425689 ! -->
The Intune IT admin can enforce a specified list of Android manufacturers, and/or iOS models through Intune App Protection Policies. The IT admin can provide a semicolon separated list of manufacturers for Android policies and device models for iOS policies. Intune App Protection Policies are for Android and iOS only. There are two separate actions that can be performed on this specified list:
- A block from app access on devices that are not specified.
- Or, a selective wipe of corporate data on devices that are not specified. 

The user will be unable to access the targeted application if the requirements through the policy are not met. Based on settings, the user may either be blocked, or selectively wiped of their corporate data within the app. On iOS devices, this feature requires the participation of applications (such as WXP, Outlook, Managed Browser, Yammer) to integrate the Intune APP SDK for this feature to be enforced with the targeted applications. This integration happens on a rolling basis and is dependent on the specific application teams. On Android, this feature requires the latest Company Portal. 

On end-user devices, the Intune client will take action based on a simple matching of the strings specified in the Intune blade for Application Protection Policies. This depends entirely on the value that the device reports. As such, the IT administrator is encouraged to ensure that the intended behavior is accurate. This can be accomplished by testing this setting based on a variety of device manufacturers and models targeted to a small user group. In Microsoft Intune, select **Client apps** > **App protection policies** to view and add app protection policies. For more information about app protection policies, see [What are app protection policies](app-protection-policy.md) and [Selectively wipe data using app protection policy access actions in Intune](app-protection-policies-access-actions.md).

### Access to macOS Company Portal pre-release build <!-- 1734766 -->
Using Microsoft AutoUpdate, you can sign up to receive builds early by joining the Insider program. Signing up will enable you to use the updated Company Portal before it’s available to your end users. For more information, see the [Microsoft Intune blog](https://blogs.technet.microsoft.com/intunesupport/2018/07/13/use-microsoft-autoupdate-for-early-access-to-the-macos-company-portal-app/).

## Week of July 2, 2018

### App management

#### Monitor iOS  app configuration status per device <!-- 880037 -->
As the Microsoft Intune admin, you can monitor iOS app configuration status for each managed device. From **Microsoft Intune** in the Azure portal, select **Devices** > **All devices**. From the list of managed devices, select a specific device to display a blade for the device. On the device blade, select **App configuration**.

#### Access actions for app protection policies <!-- 1483510 -->
You can configure app protection policies to explicitly wipe, block, or warn non-compliant devices. The *wipe* action removes your company’s corporate data from a device. If a wipe occurs, the device's user is notified of both the reason for the wipe and remediation steps. For some settings, like minimum OS version, you will be able to apply multiple actions, such as block and wipe. Note that these actions are triggered when the app is launched.

#### Selective wipe of organization's app data <!-- 1507030 -->
Administrators can now configure a selective wipe of the organization's data as a new action when the conditions of Application Protection Policies (APP) Access settings are not met.  This feature helps administrators automatically protect and remove sensitive organization data from applications based on pre-configured criteria.

#### Revoking an iOS app purchased through VPP <!-- 1777384 -->
As the Microsoft Intune admin, you can revoke all the licenses for a selected iOS app purchased through the volume-purchase program (VPP). You can notify users when a user licensed app is no longer assigned to them. Revoking an app license will not uninstall the related VPP app from the device. To uninstall a VPP app, you must change the assignment action to **Uninstall**. The reclaimed license count will be reflected in **Licensed Apps** node in the **App** workload of Intune. For more information related to iOS VPP apps, see [How to manage iOS apps purchased through a volume-purchase program with Microsoft Intune](vpp-apps-ios.md).

#### Updates to out-of-compliance messages in Company Portal app <!-- 1832222 -->
We revised the messages that device users see when a device is out-of-compliance. Messages  retain their original meanings but have been updated with friendlier language and less technical jargon. We also refreshed links to documentation and remediation steps to keep them up-to-date.
The following before and after text is one example of the improvements in messaging you'll see:
- **Before**: *This device hasn’t contacted the Intune service in the specified time period required by your IT admin. To resolve this issue, please open the company portal app on your device and click on the Check Compliance button.*
- **After**: *Your device has not checked in with your organization in a while. To reestablish a connection, open the Company Portal app on your device and tap Check Settings for your device.*

#### Revoke iOS VPP app license <!-- 1863797 -->
As the admin, you can reclaim an iOS VPP app license assigned to a user or device. Uninstalling an iOS VPP app will also allow you to reclaim the app license. Before uninstalling the app, the user or the device needs to be removed from the group to which the app is targeted. Removing the user or the device from the group avoids a reinstall of the app. Once these steps are complete, you can choose to assign the app license to another user or device. For more information about iOS VPP app licenses, see [Manage iOS volume-purchased apps in Microsoft Intune](vpp-apps-ios.md).

### Device configuration

#### Select device categories by using the Access Work or School settings <!-- 1058963 eenotready --> 
If you've enabled [device group mapping](https://docs.microsoft.com/en-us/intune/device-group-mapping), users on Windows 10 will now be prompted to select a device category after enrolling through the **Connect** button in **Settings** > **Accounts** > **Access work or school**. 

#### Use sAMAccountName as the account username for email profiles <!-- 1500307 -->
You can use the on-premises **sAMAccountName** as the account username for email profiles for Android, iOS, and Windows 10. You can also get the domain from the `domain` or `ntdomain` attribute in Azure Active Directory (Azure AD). Or, enter a custom static domain.

To use this feature, you must sync the `sAMAccountName` attribute from your on-premises Active Directory environment to Azure AD.

Applies to [Andoid](email-settings-android.md), [iOS](email-settings-ios.md), [Windows 10 and later](email-settings-windows-10.md)

#### See device configuration profiles in conflict <!-- 1556983 -->
In **Device Configuration**, a list of the existing profiles is shown. With this update, a new column is added that provides details on profiles that have a conflict. You can select a conflicting row to see the setting and profile that has the conflict. 

More on [manage configuration profiles](device-profile-monitor.md#view-conflicts).

#### New status for devices in device compliance <!-- 2308882 -->
In **Device compliance** > **Policies** > select a policy > **Overview**, the following new states are added:
- succeeded
- error
- conflict
- pending
- not-applicable
An image that shows the device count of a different platform is also shown. For example, if you're looking at an iOS profile, the new tile shows the count of non-iOS devices that are also assigned to this profile. See [Device compliance policies](compliance-policy-monitor.md#view-status-of-device-policies).

#### Device compliance supports 3rd party anti-virus solutions <!-- 2325484 -->
When you create a device compliance policy (**Device compliance** > **Policies** > **Create policy** > **Platform: Windows 10 and later** > **Settings** > **System Security**), there are new **[Device Security](compliance-policy-create-windows.md#windows-10-and-later-policy-settings)** options: 
- **Antivirus**: When set to **Require**, you can check compliance using antivirus solutions that are registered with Windows Security Center, such as Symantec and Windows Defender. 
- **AntiSpyware**: When set to **Require**, you can check compliance using antispyware solutions that are registered with Windows Security Center, such as Symantec and Windows Defender. 

Applies to: Windows 10 and later 

### Device enrollment

####  Devices without profiles column in the list of enrollment program tokens <!-- 1853904 -->
In the enrollment program tokens list, there is a new column showing the number of devices without a profile assigned. This helps admins assign profiles to these devices before handing them out to users. To see the new column, go to **Device enrollment** > **Apple enrollment** > **Enrollment program tokens**.

### Device management

#### Google name changes for Android for Work and Play for Work <!--842873 -->
Intune has updated "Android for Work" terminology to reflect Google branding changes. The terms "Android for Work" and "Play for Work" are no longer be used. Different terminology is used depending on the context:
- "Android enterprise" refers to the overall modern Android management stack.
- "Work profile" or "Profile Owner" refers to BYOD devices managed with work profiles.
- "Managed Google Play" refers to the Google app store.

#### Rules for removing devices <!-- 1609459 -->
New rules are available that let you automatically remove devices that haven't checked in for a number of days that you set. To see the new rule, go to the **Intune** pane, select **Devices**, and select **Device cleanup rules**.

#### Corporate-owned, single use support for Android devices <!-- 1630973 -->

Intune now supports highly-managed, locked-down, kiosk-style Android devices. This allows admins to further lock down the usage of a device to a single app or small set of apps, and prevents users from enabling other apps or performing other actions on the device. To set up Android kiosk, go to Intune > **Device enrollment** > **Android enrollment** > **Kiosk and task device enrollments**. For more information, see [Set up enrollment of Android enterprise kiosk devices](android-kiosk-enroll.md).

#### Per-row review of duplicate corporate device identifiers uploaded <!-- 2203794-->
When uploading corporate IDs, Intune now provides a list of any duplicates and gives you the option to replace or keep the existing information. The report will appear if there are duplicates after you choose **Device enrollment** > **Corporate Device Identifiers** > **Add Identifiers**. 

#### Manually add corporate device identifiers <!-- 2203803 -->
You can now manually add corporate device IDs. Choose **Device enrollment** > **Corporate Device Identifiers** > **Add**. 

## Week of June 25, 2018

### Pradeo - New Mobile Threat Defense partner <!-- 1169249 -->

You can control mobile device access to corporate resources using conditional access based on risk assessment conducted by Pradeo, a Mobile Threat Defense solution that integrates with Microsoft Intune.

## Week of June 18, 2018

### Edge mobile support for Intune app protection policies <!-- 1817882 -->

The Microsoft Edge browser for mobile devices now supports app protection policies defined in Intune.

## Week of June 11, 2018

### Use FIPS mode with the NDES Certificate connector <!-- 1333688 -->
When you install the NDES Certificate connector on a computer with Federal Information Processing Standard (FIPS) mode enabled, issuing and revoking certificates didn't work as expected. With this update, support for FIPS is included with the NDES Certificate connector. 

This update also includes:

- The NDES Certificate connector requires .NET 4.5 Framework, which is automatically included with Windows Server 2016 and Windows Server 2012 R2. Previously, .NET 3.5 Framework was the minimum required version.
- TLS 1.2 support is included with the NDES Certificate connector. So if the server with NDES Certificate connector installed supports TLS 1.2, then TLS 1.2 is used. If the server doesn't support TLS 1.2, then TLS 1.1 is used. Currently, TLS 1.1 is used for authentication between the devices and server.

For more information, see [Configure and use SCEP certificates](certificates-scep-configure.md) and [Configure and use PKCS certificates](certficates-pfx-configure.md).

## Week of June 4, 2018

### App management

#### Retrieve the associated app user model ID (AUMID) for Microsoft Store for Business apps in kiosk mode <!-- 1560077 ! -->
Intune can now retrieve the app user model ids (AUMIDs) for Microsoft Store for Business (WSfB) apps to provide improved configuration of the kiosk profile.

For more information about Microsoft Store for Business apps, see [Manage apps from Microsoft Store for Business](windows-store-for-business.md).

#### New Company Portal branding page <!-- 1916370 -->
The Company Portal branding page has a new layout, messages, and tooltips.


### Device configuration

#### Support for Palo Alto Networks GlobalProtect VPN profiles <!-- 1333680 eeready ! -->
With this update, you can choose Palo Alto Networks GlobalProtect as a VPN connection type for VPN profiles in Intune (**Device configuration** > **Profiles** > **Create profile** > **Profile type** > **VPN**). In this release, the following platforms are supported: 

- iOS
- Windows 10

#### Additions to Local Device Security Options settings <!-- 1403702 -->
You can now configure additional Local Device Security Options settings for Windows 10 devices. Additional settings are available in the areas of Microsoft Network Client, Microsoft Network Server, Network access and security, and Interactive logon. Find these settings in the Endpoint Protection category when you create a Windows 10 device configuration policy.

#### Enable kiosk mode on Windows 10 devices <!-- 1560072 ! -->
On Windows 10 devices, you can create a configuration profile and enable kiosk mode (**Device Configuration** > **Profiles** > **Create profile** > **Windows 10** > **Device Restrictions** > **Kiosk**). In this update, the **Kiosk (preview)** setting is renamed to **Kiosk (obsolete)**. **Kiosk (obsolete)** is no longer recommended for use, but will continue to function until the July update. **Kiosk (obsolete)** is replaced by the new **Kiosk** profile type (**Create profile** > **Windows 10** > **Kiosk (preview)**), which will contain the settings to configure Kiosks on Windows 10 RS4 and later.

Applies to Windows 10 and later.

#### Device profile graphical user chart is back <!-- 2160133 -->
While improving the numeric counts shown on the device profile graphical chart (**Device configuration** > **Profiles** > select an existing profile > **Overview**), the graphical user chart was temporarily removed.

With this update, the graphical user chart is back, and shown in the Azure portal.

### Device enrollment

#### Support for Windows Autopilot enrollment without user authentication <!-- 1165118 wnready -->
Intune now supports Windows Autopilot enrollment without user authentication. This is a new option in the Windows Autopilot deployment profile "Autopilot Deployment mode" set to "Self-Deploying".  The device must be running Windows 10 Insider Preview Build 17672 or later and possess a TPM 2.0 chip to successfully complete this type of enrollment. Since no user authentication is required, you should only assign this option to devices that you have physical control over.

#### New language/region setting when configuring OOBE for Autopilot <!-- 1821766 eeready -->
A new configuration setting is available to set the language and region for Autopilot profiles during the Out of Box Experience. To see the new setting, choose **Device enrollment** > **Windows enrollment** > **Deployment profiles** > **Create profile** > **Deployment mode** = **Self-deploying** > **Defaults configured**.

#### New setting for configuring device keyboard <!-- 1821768 -->
A new setting will be available to configure the keyboard for Autopilot profiles during the Out of Box Experience. To see the new setting, choose **Device enrollment** > **Windows enrollment** > **Deployment profiles** > **Create profile** > **Deployment mode** = **Self-deploying** > **Defaults configured**.

#### Autopilot profiles moving to group targeting <!-- 1877935 -->
AutoPilot deployment profiles can be assigned to Azure AD groups containing AutoPilot devices.

### Device management

#### Set compliance by device location <!-- 851881 ! -->
In some situations, you may want to restrict access to corporate resources to a specific location, defined by a network connection. You can now create a compliance policy (**Device compliance** > **Locations**) based on the IP address of the device. If the device moves outside the IP range, then the device cannot access corporate resources.

Applies to: Android devices 6.0 and higher, with the updated Company Portal app

#### Prevent consumer apps and experiences on Windows 10 Enterprise RS4 Autopilot devices<!-- 1621980 -->
You will be able to prevent the installation of consumer apps and experiences on your Windows 10 Enterprise RS4 AutoPilot devices. To see this feature, go to **Intune** > **Device configuration** > **Profiles** > **Create profile** > **Platform** = **Windows 10 or later** > **Profile type** = **Device restrictions** > **Configure** > **Windows Spotlight** > **Consumer features**. 

#### Uninstall the latest from Windows 10 software updates <!-- 1732948 eeready -->
Should you discover a breaking issue on your Windows 10 machines, you can choose to uninstall (rollback) the latest feature update or the latest quality update. Uninstalling a feature or quality update is only available for the servicing channel the device is on. Uninstalling will trigger a policy to restore the previous update on your Windows 10 machines. For feature updates specifically, you can limit the time from 2-60 days that an uninstall of the latest version can be applied. To set software update uninstall options, select **Software updates** from the **Microsoft Intune** blade within the Azure portal. Then, select **Windows 10 Update Rings** from the **Software updates** blade. You can then choose the **Uninstall** option from the **Overview** section.

#### Search all devices for IMEI and serial number <!-- 1793685 -->
You can now search for IMEI and serial numbers on the All devices blade (email, UPN, device name, and management name are still available). In Intune, choose **Devices** > **All devices** > enter your search in the search box.

#### Management name field will be editable <!-- 1875989 -->
You can now edit the management name field on a device’s **Properties** blade. To edit this field, choose **Devices** > **All devices** > choose the device > **Properties**. You can use the management name field to uniquely identify a device.

#### New All devices filter: Device category <!-- 1878520 -->
You can now filter the **All devices** list by device category. To do so, choose **Devices** > **All devices** > **Filter** > **Device category**.

#### Use TeamViewer to screen share iOS and MacOS devices <!-- 1985547 -->
Administrators can now connect to [TeamViewer](device-profile-android-teamviewer.md), and start a screen sharing session with iOS and macOS devices. iPhone, iPad, and macOS users can share their screens live with any other desktop or mobile device. 

#### Multiple Exchange Connector support <!-- 2070451 -->
You're no longer limited to one Microsoft Intune Exchange Connector per tenant. Intune now supports multiple Exchange Connectors so that you can set up Intune conditional access with multiple on-premises Exchange organizations.

With an Intune on-premises Exchange connector, you can manage device access to your on-premises Exchange mailboxes based on whether a device is enrolled in Intune and complies with Intune device compliance policies. To set up a connector, you download the Intune on-premises Exchange connector from the Azure portal and install it on a server in your Exchange organization. On the Microsoft Intune dashboard, choose **On-premises access**, and then under **Setup**, choose **Exchange ActiveSync connector**. Download the Exchange on-premises connector and install it on a server in your Exchange organization. Now that you're no longer limited to one Exchange connector per tenant, if you have additional Exchange organizations, you can follow this same process to download and install a connector for each additional Exchange organization.

#### New device hardware detail: CCID <!-- 2156657 -->
The Chip Card Interface Device (CCID) information is now included for each device. To see it, choose **Devices** > **All devices** > choose a device > **Hardware**> check under **Network details**>

#### Assign all users and all devices as scope groups <!-- 2196803 -->
You can now assign all users, all devices, and all users and all devices in scope groups. To do this, choose **Intune roles** > **All roles** > **Policy and profile manager** > **Assignments** > choose an assignment > **Scope (groups)**.

#### UDID information now included for iOS and macOS devices <!-- 2219806 wnready-->
To see the Unique Device Identifier (UDID) for iOS and macOS devices, go to **Devices** > **All devices** > choose a device > **Hardware**. UDID is only available for corporate devices (as set under **Devices** > **All devices** > choose a device > **Properties** > **Device ownership**).

### Intune apps

#### Improved troubleshooting for app installation <!-- 928990 -->
On Microsoft Intune MDM-managed devices, sometimes app installations can fail. When these app installs fail, it can be challenging to understand the failure reason or troubleshoot the issue. We're shipping a Public Preview of our App Troubleshooting features. You will notice a new node under each individual device called **Managed Apps**. This lists the apps that have been delivered via Intune MDM. Inside the node, you'll see a list of app install states. If you select an individual app, you'll see the troubleshooting view for that specific app. In the troubleshooting view, you'll see the end-to-end lifecycle of the app, such as when the app was created, modified, targeted, and delivered to a device. Additionally, if the app install was not successful, you'll be presented with the error code and a helpful message about the cause of the error. 

#### Intune app protection policies and Microsoft Edge <!-- 1818968 -->
The Microsoft Edge browser for mobile devices (iOS and Android) now supports Microsoft Intune app protection policies. Users of iOS and Android devices who sign in with their corporate Azure AD accounts in the Edge application will be protected by Intune. On iOS devices, the **Require managed browser for web content** policy will allow users to open links in Edge when it is managed.

## Week of May 14, 2018

### App management

#### Require installation of policies, apps, certificate and network profiles <!-- 1553555 -->

Admins can block end users from accessing the Windows 10 RS4 desktop until Intune installs  policies, apps, and certificate and network profiles during the provisioning of AutoPilot devices. For more info, see [Set up an enrollment status page](windows-enrollment-status.md).

#### Configuring your app protection policies <!-- 2144597 Part 2 -->

In the Azure portal, instead of going to the Intune App Protection service blade, you now just go to Intune. There is now only one location for app protection policies within Intune. Note that all of your app protection policies are on the **Mobile app** blade in Intune under **App protection policies**. This integration helps to simplify your cloud management administration. Remember, all app protection policies are already in Intune and you can modify any of your previously configured policies. Intune App Policy Protection (APP) and Conditional Access (CA) policies are now under **Conditional access**, which can be found under the **Manage** section in the **Microsoft Intune** blade or under the **Security** section in the **Azure Active Directory** blade. For more information about modifying conditional access policies, see [Conditional access in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal). For additional information, see [What are app protection policies?](app-protection-policy.md)

## Week of May 7, 2018

### App management

#### Samsung Knox mobile enrollment support <!--1112863-->

When using Intune with Samsung Knox Mobile Enrollment (KME), you can enroll large numbers of company-owned Android devices. Users on WiFi or cellular networks can enroll with just a few taps when they turn on their devices for the first time. When using the Knox Deployment App, devices can be enrolled using Bluetooth or NFC. For more information, see [Automatically enroll Android devices by using Samsung's Knox Mobile Enrollment](android-samsung-knox-mobile-enroll.md).

#### Requesting help in the Company Portal for Windows 10 <!-- 1874137 -->

The Company Portal for Windows 10 will now send app logs directly to Microsoft when the user initiates the workflow to get help with an issue. This will make it easier to troubleshoot and resolve issues that are raised to Microsoft.

## Week of April 23, 2018

### App management

#### Passcode support for MAM PIN on Android<!-- 1438086 -->

Intune admins can set an application launch requirement to enforce a passcode instead of a numeric MAM PIN. If configured, the user is required to set and use a passcode when prompted before getting access to MAM-enlightened applications. A passcode is defined as a numeric PIN with at least one special character or upper/lowercase alphabet. Intune supports passcode in a similar way to the existing numeric PIN... being able to set a minimum length, allowing repeat characters and sequences through the admin console. This feature requires the latest version of Company Portal on Android. This feature is already available for iOS.

#### Line-of-business (LOB) app support for macOS <!-- 1473977 -->
Microsoft Intune will provide the capability to install macOS LOB apps from the Azure portal. You will be able to add a macOS LOB app to Intune after it has been pre-processed by the tool available in GitHub. In the Azure portal, choose **Client apps** from the **Intune** blade. On the **Client apps** blade, choose **Apps** > **Add**. On the **Add App** blade, select **Line-of-business app**. 

#### Built-in All Users and All Devices Group for Android for Work (AFW) app assignment <!-- 1813073 -->
You can leverage the built-in **All Users** and **All Devices** groups for AFW app assignment. For more information, see [Include and exclude app assignments in Microsoft Intune](apps-inc-exl-assignments.md).

#### Intune will reinstall required apps that are uninstalled by users <!-- 1947010 -->
If an end user uninstalls a required app, Intune automatically reinstalls the app within 24 hours rather than waiting for the 7-day re-evaluation cycle.

### Device configuration

####  Device profile chart and status list show all devices in a group <!-- 1449153 eeready -->
When you configure a device profile (**Device configuration** > **Profiles**), you choose the device profile, such as iOS. You assign this profile to a group that includes iOS devices and non-iOS devices. The graphical chart count shows that the profile is applied to the iOS *and* the non-iOS devices (**Device configuration** > **Profiles** > select an existing profile > **Overview**). When you select the graphical chart in the **Overview** tab, the **Device status** lists all the devices in the group, instead of only the iOS devices. 

With this update, the graphical chart (**Device configuration** > **Profiles** > select an existing profile > **Overview**) only shows the count for the specific device profile. For example, if the configuration device profile applies to iOS devices, the chart only lists the count of the iOS devices. Selecting the graphical chart, and opening the **Device status** only lists the iOS devices.

While this update is being made, the graphical user chart is temporarily removed. 

#### Always On VPN for Windows 10 <!--1333666 -->

Currently, [Always On](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-auto-trigger-profile#always-on) can be used on Windows 10 devices by using a custom virtual private network (VPN) profile created using OMA-URI.

With this update, admins can enable Always On for Windows 10 VPN profiles directly in Intune in the Azure portal. Always On VPN profiles will automatically connect when:

- Users sign into their devices
- The network on the device changes
- The screen on the device turns back on after being turned off

#### New printer settings for education profiles <!-- 1308900 -->

For education profiles, new settings are available under the **Printers** category: **Printers**, **Default printer**, **Add new printers**.

#### Show caller ID in personal profile - Android for Work <!--1098984 -->
When using a personal profile on a device, end users may not see the caller ID details from a work contact. 

With this update, there is a new setting in **Android for Work** > **Device restrictions** > **Work profile settings**:
- Display work contact caller-id in personal profile

When enabled (not configured), the work contact caller details are displayed in the personal profile. When blocked, the work contact caller number is not displayed in the personal profile. 

Applies to: Android work profile devices on Android OS v6.0 and newer

#### New Windows Defender Credential Guard settings added to endpoint protection settings <!--1102252 --><!--from 1802 and 1804-->

With this update, [Windows Defender Credential Guard](https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard) (**Device configuration** > **Profiles** > **Endpoint protection**) includes the following settings: 

- **Windows Defender Credential Guard**: Turns on Credential Guard with virtualization-based security. Enabling this feature helps protect credentials at the next reboot when **Platform Security Level with Secure Boot** and **Virtualization Based Security** are both enabled. Options include:
  - **Disabled**: If Credential Guard was previously turned on with the **Enabled without lock**" option​, then it turns off Credential Guard remotely.

  - **Enabled with UEFI lock**: Ensures that Credential Guard cannot be disabled using a registry key or using Group Policy. To disable Credential Guard after using this setting, you must set the Group Policy to "Disabled". Then, remove the security functionality from each computer, with a physically present user. These steps clear the configuration persisted in UEFI. As long as the UEFI configuration persists, Credential Guard is enabled.​

  - **Enabled without lock**: Allows Credential Guard to be disabled remotely using Group Policy. The devices that use this setting must be running at least Windows 10 (Version 1511).

The following dependent technologies are automatically enabled when configuring Credential Guard: 

  - **Enable Virtualization-based Security (VBS)**: Turns on virtualization-based security (VBS) at next reboot. Virtualization-based security uses the Windows Hypervisor to provide support for security services, and requires Secure Boot.
  - **Secure Boot with Direct Memory Access (DMA)**: Turns on VBS with Secure Boot and direct memory access. DMA protection require hardware support, and is only enabled on properly configured devices. 

#### Use a custom subject name on SCEP certificate <!-- 2064190 -->
You can use the **OnPremisesSamAccountName** the common name in a custom subject on an SCEP certificate profile. For example, you can use `CN={OnPremisesSamAccountName})`.

####  Block camera and screen captures on Android for Work <!-- 1098977 eeready-->
Two new properties are available to block when you configure device restrictions for Android devices: 
- Camera: Blocks access to all cameras on the device
- Screen capture: Blocks the screen capture, and also prevents the content from being shown on display devices that don't have a secure video output

Applies to Android for Work.


### Device enrollment

#### New enrollment steps for users on devices with macOS High Sierra 10.13.2+ <!--1734567 -->
macOS high Sierra 10.13.2 introduced the concept of "User Approved" MDM enrollment. Approved enrollments allow Intune to manage some security-sensitive settings. For more information, see Apple's support documentation here: https://support.apple.com/HT208019.

Devices enrolled using the macOS Company Portal are considered "Not User Approved" unless the end user opens System Preferences and manually provides approval. To this end, the macOS Company Portal now directs users on macOS 10.13.2 and above to go and manually approve their enrollment at the end of the enrollment process. The Intune admin console will report on if an enrolled device is user approved.



### Device management

#### Advanced Threat Protection (ATP) and Intune are fully integrated <!-- EEready 1629303 -->

[Advanced Threat Protection (ATP)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/dashboard-windows-defender-advanced-threat-protection) shows the risk level of Windows 10 devices. In Windows Defender Security Center (ATP portal), you can create a connection to Microsoft Intune. Once created, an Intune compliance policy is used to determine an acceptable threat level. If the threat level is exceeded, an Azure Active Directory (AD) conditional access policy can then block access to different apps within your organization.

This feature allows ATP to scan files, detect threats, and report any risk on your Windows 10 devices.

See [Enable ATP with conditional access in Intune](advanced-threat-protection.md).

#### Support for user-less devices <!-- 1637553 -->
Intune supports the ability to evaluate compliance on a user-less device, such as the Microsoft Surface Hub. Compliance policy can target specific devices. So compliance (and noncompliance) can be determined for devices that don't have an associated user.

#### Delete Autopilot devices <!-- 1713650 -->
Intune admins can [delete Autopilot devices](enrollment-autopilot.md#delete-autopilot-devices).

#### Improved device deletion experience <!--1832333 -->
You're no longer be required to remove company data or factory reset a device before [deleting a device from Intune](devices-wipe.md#delete-devices-from-the-intune-portal).

To see the new experience, sign in to Intune and select **Devices** > **All devices** > the name of the device > **Delete**.

If you still want the wipe/retire confirmation, you can use the standard device lifecycle route by issuing a **Remove company data** and **Factory Reset** prior to **Delete**. 

#### Play sounds on iOS when in Lost mode <!-- 1947769 -->
When supervised iOS devices are in Mobile Device Management (MDM) [Lost mode](device-lost-mode.md), you can [play a sound](device-locate.md#activate-lost-mode-sound-alert-on-an-ios-device) (**Devices** > **All devices** > select an iOS device > **Overview** > **More**). The sound continues to play until the device is removed from Lost mode, or a user disables sound on the device. Applies to iOS devices 9.3 and newer.

#### Block or allow web results in searches made on an Intune device <!--1972804-->

Admins can now block web results from searches made on a device.

#### Improved error messaging for Apple MDM Push Certificate upload failure <!-- 2172331 -->

The error message explains that the same Apple ID must be used when renewing an existing MDM certificate.

#### Test the Company Portal for macOS on virtual machines <!-- 2216679 -->

We've published guidance to help IT admins test the Company Portal app for macOS on virtual machines in Parallels Desktop and VMware Fusion. Find out more in [enroll virtual macOS machines for testing](macos-enroll.md#enroll-virtual-macos-machines-for-testing).


### User interface

#### Improved device tiles in the Windows 10 Company Portal <!--2213364 -->

The tiles have been updated to be more accessible to low-vision users and to perform better for screen reading tools.

#### Send diagnostic reports in Company Portal app for macOS <!-- 2216677 -->
The Company Portal app for macOS devices was updated to improve how users report Intune-related errors. From the Company Portal app, your employees can:

- Upload diagnostic reports directly to the Microsoft developer team.
- Email an incident ID to your company's IT support team.

For more information see [Send errors for macOS](/intune-user-help/send-errors-macos).

#### Intune adapts to Fluent Design System in the Company Portal app for Windows 10 <!-- 1195010 WNready -->
The Intune Company Portal app for Windows 10 has been updated with the [Fluent Design System's navigation view](https://docs.microsoft.com/en-us/windows/uwp/design/basics/navigation-basics). Along the side of the app, you'll notice a static, vertical list of all top-level pages. Click any link to quickly view and switch between pages. This is the first of several updates you'll see as part of our ongoing effort to create a more adaptive, empathetic, and familiar experience in Intune. To see the updated look, go to [What's new in the app UI](whats-new-app-ui.md).

## Week of April 16, 2018

#### Use Cisco AnyConnect client for iOS <!-- EEready 1333708 -->

When you create a new VPN profile for iOS, there are now two options: **Cisco AnyConnect** and **Cisco Legacy AnyConnect**. Cisco AnyConnect profiles support 4.0.7x and newer versions. Existing iOS Cisco AnyConnect VPN profiles are labeled **Cisco Legacy AnyConnect**, and continue to work with Cisco AnyConnect 4.0.5x and older versions, as they do today.

> [!NOTE]
> This change only applies to iOS. There continues to be only one Cisco AnyConnect option for Android, Android for Work, and macOS platforms.

#### Jamf-enrolled macOS devices can now register with Intune <!-- 2370684 -->

Versions 1.3 and 1.4 of the macOS company portal did not successfully register Jamf devices with Intune. Version 1.4.2 of the macOS portal fixes this issue.


## Week of April 9, 2018  
#### Updated help experience in Company Portal app for Android <!-- 1631531 -->

We've updated the help experience in the Company Portal app for Android to align with best practices for the Android platform. Now when users encounter a problem in the app, they can tap **Menu** > **Help** and:
- Upload diagnostic logs to Microsoft.
- Send an email that describes the problem and incident ID to a company support person.  

To check out the updated help experience go to [Send logs using email](/intune-user-help/send-logs-to-your-it-admin-by-email-android) and [Send errors to Microsoft](/intune-user-help/send-logs-to-microsoft-android).


#### New enrollment failure trend chart and failure reasons table <!-- 1471783 -->

On the Enrollment Overview page, you can view the trend of enrollment failures and the top five causes of failures. By clicking on the chart or table, you can drill into details to find troubleshooting advice and remediation suggestions.

#### Update where to configure your app protection policies <!-- 2144597 -->

In the Azure portal within the Microsoft Intune service, we’re going to temporarily redirect you from the **Intune App Protection** service blade to the **Mobile app** blade. Note that all of your app protection policies are already on the **Mobile app** blade in Intune under app configuration. Instead of going to Intune App Protection, you’ll just go to Intune. In April 2018, we will stop the redirection and fully remove the **Intune App Protection** service blade, so that there's only one location for app protection policies within Intune. 

**How does this affect me?**
This change will affect both Intune standalone customers and hybrid (Intune with Configuration Manager) customers. This integration will help simplify your cloud management administration.

**What do I need to do to prepare for this change?**
Please tag **Intune** as a favorite instead of the **Intune App Protection** service blade and ensure you’re familiar with the App protection policy workflow in the **Mobile** app blade within Intune. We’ll redirect for a short period of time and then remove the **App Protection** blade. Remember, all app protection policies are already in Intune and you can modify any of your conditional access policies. For more information about modifying conditional access policies, see [Conditional access in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal). For additional information, see [What are app protection policies?](app-protection-policy.md) 


## Week of April 2, 2018

### Intune apps

#### User experience update for the Company Portal app for iOS <!--1412866 -->
We've released a major user experience update to the Company Portal app for iOS. The update features a complete visual redesign that includes a modernized look and feel. We've maintained the functionality of the app, but increased its usability and accessibility.  

You'll also see:
- Support for iPhone X.
- Faster app launch and loading responses, to save users time.
- Additional progress bars to provide users with the most up-to-date status information.
- Improvements to the way users upload logs, so if something goes wrong, it's easier to report.  

To see the updated look, go to [What's new in the app UI](whats-new-app-ui.md).

#### Protect on-premises Exchange data using Intune APP and CA <!-- 1056954 -->
You can now use Intune App Policy Protection (APP) and Conditional Access (CA) to protect access to on-premises Exchange data with Outlook Mobile. To add or modify an app protection policy within the Azure portal, select **Microsoft Intune** > **Client apps** > **App protection policies**. Before using this feature, make sure you meet the [Outlook for iOS and Android requirements](https://technet.microsoft.com/en-us/library/mt846639(v=exchg.160).aspx).

## Week of March 26, 2018

### App management

#### Alerts for expiring iOS line-of-business (LOB) apps for Microsoft Intune <!-- 748789 -->

In the Azure portal, Intune will alert you to iOS line-of-business apps that are about to expire. Upon uploading a new version of the iOS line-of-business app, Intune removes the expiration notification from the app list. This expiration notification will only be active for newly uploaded iOS line-of-business apps. A warning appears 30 days before the iOS LOB app provisioning profile expires. When it expires, the alert changes to Expired.

#### Customize your Company Portal themes with hex codes <!--1049561 -->

You can customize theme color in the Company Portal apps using hex codes. When you enter your hex code, Intune determines the text color that provides the highest level of contrast between the text color and the background color. You can preview both the text color and your company logo against the color in **Client apps** > **Company Portal**.

### Including and excluding app assignment based on groups for Android Enterprise <!-- 1813081 -->

Android Enterprise (formerly known as Android for Work) supports including and excluding groups, but does not support the pre-created **All Users** and **All Devices** built-in groups. For more information, see [Include and exclude app assignments in Microsoft Intune](apps-inc-exl-assignments.md).


### Device management

#### New security enhancements in the Intune service  <!-- 1637539 -->   

We’ve introduced a toggle in Intune on Azure that Intune standalone customers can use to treat devices without any policy assigned as **Compliant** (security feature off) or treat these devices as **Not compliant** (security feature on). This will ensure access to resources only after device compliance has been evaluated.

This feature affects you differently depending on whether you already have compliance policies assigned or not.

- If you are a new or existing account, and don't have any compliance policies assigned to your devices, then the toggle is automatically set to **Compliant**. The feature is off as a default setting in the console. There is no end-user impact.
- If you are an existing account, and you have any devices with a compliance policy assigned to them, then the toggle is automatically set to **Not compliant**. The feature is on as a default setting, as the March update rolls out.

If you use compliance policies with Conditional Access (CA), and have the feature turned on, any devices without at least one compliance policy assigned are now be blocked by CA. End-users associated with these devices, who were previously allowed access to email, lose their access unless you assign at least one compliance policy to all devices.   

Note that although the default toggle status is displayed in the UI immediately with the Intune service March updates, this toggle status is not enforced right away. Any changes you make to the toggle will not impact device compliance until we flight your account to have a working toggle. We’ll inform you via the Message center when we finish flighting your account. This could take up to a few days after your Intune service is updated for March.

**Additional Information**: [https://aka.ms/compliance_policies](https://aka.ms/compliance_policies)

#### Enhanced jailbreak detection <!-- 846515 -->

Enhanced jailbreak detection is a new compliance setting that improves how Intune evaluates jailbroken devices. The setting causes the device to check in with Intune more frequently, which uses the device’s location services and impacts battery usage.

#### Reset passwords for Android O devices <!-- 1238299 -->
You'll be able to reset the passwords for enrolled Android 8.0 devices with Work profiles. When you send a "Reset password" request to an Android 8.0 device, it sets a new device unlock password or a managed profile challenge to the current user. The password or challenge is sent and immediately takes effect.

#### Targeting compliance policies to devices in device groups <!--1307012 -->

You can target compliance policies to users in user groups. With this update, you can target compliance policies to devices in device groups. Devices targeted as part of device groups will not receive any compliance actions.

#### New Management name column <!-- 1333586 -->
 A new column named **Management name** is available on the devices blade. This is an auto-generated, non-editable name assigned per device, based on the following formula:
- Default name for all devices: <username><em><devicetype></em><enrollmenttimestamp>
- For bulk added devices: <PackageId/ProfileId><em><DeviceType></em><EnrollmentTime>

This is an optional column in the devices blade. It isn't available by default and you can only access it by using the column selector. The device name is not affected by this new column.

#### iOS devices are prompted for a PIN every 15 minutes <!--1550837 -->
After a compliance or configuration policy is applied to an iOS device, users are prompted to set a PIN every 15 minutes. Users are continually prompted until a PIN is set.

#### Schedule your automatic updates <!--1805514 -->
Intune gives you control on installing automatic updates using [Windows Update Ring settings](windows-update-for-business-configure.md). With this update, you can schedule reoccurring updates, including the week, the day, and the time.

#### Use fully distinguished name as subject for SCEP certificate <!--2221763 -->
When you create a SCEP certificate profile, you enter the Subject Name. With this update, you can use the fully distinguished name as the subject. For **Subject Name**,  select **Custom**, and then enter `CN={{OnPrem_Distinguished_Name}}`. To use the `{{OnPrem_Distinguished_Name}}` variable, be sure to sync the `onpremisesdistingishedname` user attribute using [Azure Active Directory (AD) Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) to your Azure AD.

### Device configuration

#### Enable Bluetooth contact sharing - Android for Work <!--1098983 -->
By default, Android prevents contacts in the work profile from syncing with Bluetooth devices. As a result, work profile contacts are not displayed on caller ID for Bluetooth devices.

With this update, there is a new setting in **Android for Work** > **Device restrictions** > **Work profile settings**:
- Contact sharing via Bluetooth

The Intune administrator can configure these settings to enable sharing. This is useful when pairing a device with a car-based Bluetooth device that displays caller ID for hands-free usage. When enabled, work profile contacts are displayed. When not enabled, work profile contacts won't display.

#### Configure Gatekeeper to control macOS app download source <!-- 1690459 -->

You can configure Gatekeeper to protect your devices from apps by controlling where the apps can be downloaded from. You can configure the following download sources: **Mac App Store**, **Mac App Store and identified developers**, or **Anywhere**. You can configure whether users can install an app using control-click to override these Gatekeeper controls.

These settings can be found under **Device configuration** -> **Create profile** -> **macOS** -> **Endpoint protection**.

#### Configure the Mac application firewall <!-- 1690461 -->

You can configure the Mac application firewall. You can use this to control connections on a per-application basis, rather than on a per-port basis. This makes it easier to get the benefits of firewall protection, and helps prevent undesirable apps from taking control of network ports open for legitimate apps.

This feature can be found under **Device configuration** -> **Create profile** -> **macOS** -> **Endpoint protection**.

Once you enable the Firewall setting, you can configure the firewall using two strategies:

- Block all incoming connections

   You can block all incoming connections for the targeted devices. If you choose to do this, incoming connections are blocked for all apps.

- Allow or block specific apps

   You can allow or block specific apps from receiving incoming connections. You can also enable stealth mode to prevent responses to probing requests.

####  Detailed error codes and messages <!-- 1376342 -->

In your Device Configuration, there are more detailed error codes and error messages available to see. This improved reporting shows the settings, the state of these settings, and details on troubleshooting.

##### More information

- Block all incoming connections

   This blocks all sharing services (such as File Sharing and Screen Sharing) from receiving incoming connections. The system services that are still allowed to receive incoming connections are:
  - configd - implements DHCP and other network configuration services
  - mDNSResponder - implements Bonjour
  - racoon -  implements IPSec

    To use sharing services, ensure **Incoming connections** is set to **Not configured** (not **Block**).

- Stealth mode

   Enable this to prevent the computer from responding to probing requests. The computer still answers incoming requests for authorized apps. Unexpected requests, such as ICMP (ping), are ignored.

#### Disable checks on device restart <!--1805490 -->
Intune gives you control to [manage software updates]](windows-update-for-business-configure.md). With this update, the <strong>Restart checks</strong> property is available, and enabled by default. To skip the typical checks that occur when you restart a device (such as active users, battery levels, and so on), select <strong>Skip</strong>.

#### New Windows 10 Insider Preview channels available for deployment rings <!-- 1746293 -->
You now have the option to select the following Windows 10 Insider Preview servicing channels when you create a Windows 10 deployment ring:
- Windows Insider build &#8208; Fast
- Windows Insider build &#8208; Slow
- Release Windows Insider build 

For more information about these channels, see [Manage Insider Preview Builds](https://insider.windows.com/en-us/for-business-organization-admin/).   
For more information about creating deployment channels in Intune, see [Manage software updates in Intune](windows-update-for-business-configure.md).

### Intune apps

#### Company Portal enrollment improved <!-- 1874230 eeready-->
Users enrolling a device by using the Company Portal on Windows 10 build 1703 and up are now able to complete the first step of enrollment without leaving the app.
#### HoloLens and Surface Hub now appear in device lists <!--1725868 -->
We added support for showing Intune-enrolled HoloLens and Surface Hub devices to the Company Portal app for Android.

#### Custom Book categories for volume-purchase program (VPP) eBooks <!-- 1488911 -->
You can create custom eBook categories and then assign VPP eBooks to those custom eBook categories. End users can then see the newly created eBook categories and books assigned to the categories. For more information, see [Manage volume-purchased apps and books with Microsoft Intune](vpp-apps.md).  

#### Support changes for Company Portal app for Windows send feedback option <!-- 2070166 -->
Starting April 30, 2018, the **Send Feedback** option in the Company Portal app for Windows will only work on devices running the Windows 10 Anniversary Update (1607) and later. The option to send feedback is no longer supported when using the Company Portal app for Windows with:  
- Windows 10, 1507 release  
- Windows 10, 1511 release  
- Windows Phone 8.1 

If your device is running on Windows 10 RS1 or later, download the latest version of the Windows Company Portal app from the Store. If you are running an unsupported version, please continue to send feedback through the following channels: 
- The Feedback Hub app on Windows 10
- Email WinCPfeedback@microsoft.com  

#### New Windows Defender Application Guard settings <!-- 1631890 -->

- **Enable graphics acceleration**: Administrators can enable a virtual graphics processor for Windows Defender Application Guard. This setting allows the CPU to offload graphics rendering to the vGPU. This can improve performance when working with graphics intense websites or watching video within the container.

- **SaveFilestoHost**: Administrators can enable files to pass from Microsoft Edge running in the container to the host file system. Turning this on allows users to download files from Microsoft Edge in the container to the host file system.

#### MAM protection policies targeted based on management state <!-- 1665993 -->
You can target MAM policies based on the management state of the device:
- **Android devices** - You can target unmanaged devices, Intune managed devices, and Intune managed Android Enterprise Profiles (formerly Android for Work).
- **iOS devices** - You can target unmanaged devices (MAM only) or Intune managed devices.

    > [!NOTE]
    > - iOS support for this functionality is rolling out throughout April 2018.

For more information, see [Target app protection policies based on device management state](app-protection-policies.md).

#### Improvements to the language in the Company Portal app for Windows <!-- 1683758 -->
We've improved the language in the Company Portal for Windows 10 to be more user-friendly and specific to your company. To see some sample images of what we've done, see [what's new in app UI](whats-new-app-ui.md).

#### New additions to our docs about user privacy <!-- 1440709 -->
As part of our effort to give end users more control over their data and privacy, we've published updates to our docs that explain how to view and remove data stored locally by the Company Portal apps. You can find these updates at:

- **Android**: [How to remove your Android device from Intune](/intune-user-help/unenroll-your-device-from-intune-android.md)
- **Android, if the user has declined terms of use**: [Remove your device management if you declined "Terms of Use"](/intune-user-help/unenroll-your-device-from-intune-if-you-declined-terms-of-use-android.md)
- **iOS**: [Remove your iOS device from Intune](/intune-user-help/unenroll-your-device-from-intune-ios.md)
- **Windows**: [Remove your Windows device from Intune](/intune-user-help/unenroll-your-device-from-intune-windows.md)

## Week of March 19, 2018

### Export all devices into CSV files in IE, Edge, or Chrome <!-- 2258071 -->
In **Devices** > **All devices**, you can **Export** the devices into a CSV formatted list. Internet Explorer (IE) users with >10,000 devices can successfully export their devices into multiple files. Each file has up to 10,000 devices.

Edge and Chrome users with >30,000 devices can successfully export their devices into multiple files. Each file has up to 30,000 devices.

[Manage devices](device-management.md) provides more details on what you can do with devices you manage.

## Week of March 12, 2018

### Azure Active Directory web sites can require the Intune Managed Browser app and support Single Sign-On for the Managed Browser (Public Preview) <!-- 710595 -->

Using Azure Active Directory (Azure AD), you can now restrict access to web sites on mobile devices to the Intune Managed Browser app. In the Managed Browser, web site data will remain secure and separate from end-user personal data. In addition, the Managed Browser will support Single Sign-On capabilities for sites protected by Azure AD. Signing in to the Managed Browser, or using the Managed Browser on a device with another app managed by Intune, allows the Managed Browser to access corporate sites protected by Azure AD without the user having to enter their credentials. This functionality applies to sites like Outlook Web Access (OWA) and SharePoint Online, as well as other corporate sites like intranet resources accessed through the Azure App Proxy. For additional information, see [Access controls in Azure Active Directory conditional access](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-controls).

#### Company Portal app for Android visual updates <!--976944 -->

We've updated the Company Portal app for Android to follow Android's [Material Design](https://material.io/) guidelines. You can see the images of the new icons in the [What's new in app UI](whats-new-app-ui.md) article.

### New Windows Defender Exploit Guard settings <!-- 1631893 -->

Six new <strong>Attack Surface Reduction</strong> settings and expanded <strong>Controlled folder access: Folder protection</strong> capabilities are now available. These settings can be found at: Device configuration\Profiles\
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

|              Setting name               |                                                              Setting options                                                              | Description |
|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|-------------|
| Folder protection (already implemented) | Not configured, Enable, Audit only (already implemented)<br><br> <strong>New</strong><br>Block disk modification, Audit disk modification |             |

Protect files and folders from unauthorized changes by unfriendly apps.<br><br>**Enable**: Prevent untrusted apps from modifying or deleting files in protected folders and from writing to disk sectors.<br><br>
**Block disk modification only**:<br>Block untrusted apps from writing to disk sectors. Untrusted apps can still modify or delete files in protected folders.|

## Week of February 19, 2018

### Device enrollment

#### Intune support for multiple Apple DEP / Apple School Manager accounts <!-- 747685 -->

Intune now supports enrolling devices from up to 100 different [Apple Device Enrollment Program (DEP)](device-enrollment-program-enroll-ios.md) or [Apple School Manager](apple-school-manager-set-up-ios.md) accounts. Each token uploaded can be managed separately for enrollment profiles and devices. A different enrollment profile can be automatically assigned per DEP/School Manager token uploaded. If multiple School Manager tokens are uploaded, only one can be shared with Microsoft School Data Sync at a time.

After migration, the beta Graph APIs and published scripts for managing Apple DEP or ASM over Graph will no longer work. New beta Graph APIs are in development and will be released after the migration.

#### See enrollment restrictions per user <!-- 1634444 eeready wnready -->
On the **Troubleshoot** blade, you can now see the [enrollment restrictions](enrollment-restrictions-set.md) that are in effect for each user by selecting **Enrollment restrictions** from the **Assignments** list.

### Device management
#### Windows defender health status and threat status reports <!--854704 -->

Understanding Windows Defender's health and status is key to managing Windows PCs.  With this update, Intune adds new reports and actions to the status and health of the Windows Defender agent. Using a status roll-up report in the [Device Compliance workload](compliance-policy-monitor.md), you can see devices that need any of the following:
- signature update
- Restart
- manual intervention
- full scan
- other agent states requiring intervention

A drill-in report for each status category lists the individual PCs that need attention, or those that report as **Clean**.

#### New privacy settings for device restrictions <!--1308926 -->
[Two new privacy settings](device-restrictions-windows-10.md#privacy) are now available for devices:
- **Publish user activities**: Set this to **Block** to prevent shared experiences and discovery of recently used resources in the task switcher.
- **Local activities only**: Set this to **Block** to prevent shared experiences and discovery of recently used resources in task switcher based only on local activity.

#### New settings for the Edge browser <!--1469166 -->
[Two new settings](device-restrictions-windows-10.md#edge-browser) are now available for devices with the Edge browser: **Path to favorites file** and **Changes to Favorites**.

### App management
#### Protocol exceptions for applications <!--1035509 -->

You can now create exceptions to the Intune Mobile Application Management (MAM) data transfer policy to open specific unmanaged applications. Such applications must be trusted by IT. Other than the exceptions you create, data transfer is still restricted to applications that are managed by Intune when your data transfer policy is set to **managed apps only**. You can create the restrictions by using protocols (iOS) or packages (Android).

For example, you can add the Webex package as an exception to the MAM data transfer policy. This will allow Webex links in a managed Outlook email message to open directly in the Webex application. Data transfer will still be restricted in other unmanaged applications. For more information, see [Data transfer policy exceptions for apps](app-protection-policies-exception.md).

#### Windows Information Protection (WIP) encrypted data in Windows search results <!-- 1469193 -->
A setting in the Windows Information Protection (WIP) policy now allows you to control whether WIP-encrypted data is included in Windows search results. Set this app protection policy option by selecting **Allow Windows Search Indexer to search encrypted items** in the **Advanced settings** of the Windows Information Protection policy. The app protection policy must be set to the *Windows 10* platform and the app policy **Enrollment state** must be set to **With enrollment**. For more information, see [Allow Windows Search Indexer to search encrypted items](windows-information-protection-policy-create.md#allow-windows-search-indexer-to-search-encrypted-items).

#### Configuring a self-updating mobile MSI app <!-- 1740840 -->
You can configure a known self-updating mobile MSI app to ignore the version check process. This capability is useful to avoid getting into a race condition. For instance, this type of race condition could occur when the app being auto-updated by the app developer is also being update by Intune. Both could try to enforce a version of the app on a Windows client, which could create a conflict. For these automatically updated MSI apps, you can configure the **Ignore app version** setting in the **App information** blade. When this setting is switched to **Yes**, Microsoft Intune will ignore the app version installed on the Windows client.

#### Related sets of app licenses supported in Intune <!-- 1864117 -->
Intune in the Azure portal now supports related sets of app licenses as a single app item in the UI. In addition, any Offline Licensed apps synced from Microsoft Store for Business will be consolidated into a single app entry and any deployment details from the individual packages will be migrated over to the single entry. To view related sets of app licenses in the Azure portal, select **App licenses** from the **Client apps** blade.

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

|              Setting name               |                                                              Setting options                                                              | Description |
|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|-------------|
| Folder protection (already implemented) | Not configured, Enable, Audit only (already implemented)<br><br> <strong>New</strong><br>Block disk modification, Audit disk modification |             |

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

### macOS Company Portal support for enrollments that use the Device Enrollment Manager <!-- 1352411 -->

Users can now use the Device Enrollment Manager when enrolling with the macOS Company Portal.

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



## Notices

### Plan for Change: Move to Intune on Azure for your Mobile Device Management <!—2683117-->

Since launching on Azure over a year ago, Intune has added hundreds of new customer-requested and market-leading service capabilities, and now offers far more capabilities than those offered through [hybrid]( https://aka.ms/hybrid_MDM) Mobile Device Management (MDM). Intune on Azure provides a more integrated, streamlined administrative experience for your enterprise mobility needs.

As a result, we see that most Enterprise Mobility + Security (EMS) customers choose Intune on Azure over hybrid MDM. The number of customers using hybrid MDM continues to decrease as more customers move to the cloud. Therefore, on September 1, 2019, we will retire the hybrid MDM service offering. Please plan your migration to Intune on Azure for your MDM needs. We have tools, case studies, and other resources to help with this migration.

Note: this change does not affect on-premises System Center Configuration Manager (ConfigMgr) or [co-management]( https://aka.ms/Intune_comanagement) for Windows 10 devices. If you are unsure whether you are using hybrid MDM, go to the Administration workspace of the ConfigMgr console, expand Cloud Services, and click Microsoft Intune Subscriptions. If you have a Microsoft Intune subscription setup, your tenant is configured for hybrid MDM.

#### How does this affect me?
-	Microsoft will support your hybrid MDM usage for the next year. We will continue to release major bug fixes and ensure existing functionality is supported on OS versions, such as enrollment on iOS 12. We will not invest in new features for hybrid MDM.
-	We do not expect any end user impact to this change, provided you migrate to Intune on Azure before the end of the hybrid MDM offering.
-	Licensing remains as is; Intune on Azure licenses are included with hybrid MDM.
-	We will begin to block the onboarding of new hybrid MDM customers starting in November 2018.
-	On September 1, 2019, any remaining hybrid MDM devices will no longer receive policy, apps, or security updates.

#### What do I need to do to prepare for this change?
-	Start planning your migration for MDM from the ConfigMgr console to Azure. Many customers, including Microsoft IT, have gone through this process. Read this [case study]( https://aka.ms/Intune_MSFT) sharing best practices and lessons learned from Microsoft’s own migration.  
-	Review [tools]( https://aka.ms/hybrid_tools) and [documentation]( https://aka.ms/intune_migrate) we’ve created to simplify the process of moving from hybrid MDM to Intune on Azure. Many customers, including some of our largest and smallest, have successfully used these tools and guidance to migrate.
-	Contact your partner of record or Fast Track for assistance. [FastTrack for Microsoft 365]( https://aka.ms/hybrid_fasttrack) can assist in your migration from hybrid MDM to Intune on Azure. More information on how to open this specific type of FastTrack ticket is included in the Additional Information link.

#### Additional Information
[Intune Support Blog post](https://blogs.technet.microsoft.com/intunesupport/2018/08/14/move-from-hybrid-mobile-device-management-to-intune-on-azure/)


### Plan for Change: New Intune support experience for Premier customers 
As a Microsoft Premier customer, you can currently use the Microsoft Premier Online (MPO) portal (premier.microsoft.com) and Intune on Azure (portal.azure.com) to create support requests for Intune. Starting on December 3, 2018, to continue enhancing the Premier support experience, you will be able to create support requests only in Intune on Azure.

#### How does this affect me?
After December 3, you will be not be able to create support requests in MPO.  When you try to do this, you’ll see a prompt that you will not be able to dismiss, to be redirected to Intune on Azure. Here, you can create a support request which will be routed to Intune-dedicated Microsoft Support, to diagnose and resolve your issue in a timely manner. Support requests created in the MPO portal cannot be viewed in the Azure portal, so you should stop creating support requests in MPO.  

If you use hybrid mobile device management (hybrid MDM) or use co-management, you can continue to use MPO to create support requests for ConfigMgr but use the Azure portal to create support requests for Intune. As a reminder, hybrid MDM is deprecated, and you should plan to move to Intune on Azure as soon as possible. For more information, see Move from Hybrid Mobile Device Management to Intune on Azure.

Note that only users with Global Administrator, Intune Service Administrator and Service Support Administrator roles can create support tickets in the Azure portal.

#### What can I do to prepare for this change?
- Stop using MPO and use Intune on Azure to create and manage all your Intune support requests.  
- Notify your helpdesk and update documentation if necessary.
- If you have users without Global administrator or Intune Service Administrator roles currently creating support requests in MPO, assign them the Service Support Administrator role in Azure Active Directory, so they can continue to create support tickets in the Azure portal.
- Click on Additional Information for more information and helpful links.

#### Additional Information
[https://aka.ms/IntuneSupport_MPO_to_Azure](https://aka.ms/IntuneSupport_MPO_to_Azure)

### Take action: Please update your Android device restriction or compliance policy password settings in Intune
Intune will be removing the available password type “device default” for Android 4.4 and higher devices. Due to differences in Android platforms and device defaults, that policy is often treated as optional by the device. To clear up confusion on when this setting is enforced on Android, we’ll remove this setting from the UI in an upcoming release. 
#### How does this affect me?
- If your intent is to require a password on the devices, we recommend instead of using “device default” you edit your Android platform profile(s) to clearly articulate the required password type.
- If your intent is to let your end user to decide on whether to create a password, select the “Not configured” button. 
When we remove this setting from the UI, if the setting is still set, you will be prompted to choose a value other than “Device default” on your next edit of the profile.
What do I need to do to prepare for this change?
Review the password settings in your Android and Android enterprise device restriction and compliance policies. These are listed under System security for Compliance policies and under either Device password or Work profile settings for Device restrictions. Additional information has a link to more details and screenshots for where these settings are configured.
#### Additional information
https://aka.ms/PasswordSettings 

### Plan for Change: Change Password at Next Auth added to Intune<!-- 1873216 -->
In the September service release, Intune plans to integrate Apple’s newly-released **Change Password at Next Auth** setting for devices running macOS versions 10.13 and newer. Before this setting, MDM providers can't verify that the device passcode was changed to be compliant. Intune’s configuration and compliance policies only validate that the next time a device password is changed, that it's marked as compliant. When this new Apple feature is added, your macOS users will receive a request to update their password, even if their password is compliant.

#### How does this affect me?
This impacts environments with a macOS device policy using Intune or a hybrid MDM. Now that Apple has this **Change Password at New Auth** setting, Intune can force users to update their password when a password policy is pushed. If you block company resources until the device is marked compliant, then your end users may be blocked from accessing company resources, such as email or SharePoint sites, until they reset their password. In the future, all updates to configuration and compliance password policies force targeted users to update their passwords.

#### What do I need to do to prepare for this change?
Let your helpdesk know. If you don't want to enforce this macOS device policy, we recommend you un-assign or delete your existing macOS policy. Customer research suggests most customers aren't affected by this change. Most end users update their password after receiving a request to enroll with a password, or reset their password to remain compliant.


### Plan for Change: Intune moving to support iOS 10 and later in September <!-- 2454656 -->
In September, Apple is expected to release iOS 12. Shortly after the release, we will move Intune enrollment, the Company Portal, and the managed browser to support iOS 10 and later.  

#### How does this affect me?  
Office 365 mobile apps are supported on iOS 10 and later, so you may have already upgraded your OS or devices. If so, this move will not affect you.  

However, if you have any of the devices listed below, or want to enroll any of the devices listed below, be aware that they only support iOS 9 and earlier.  To continue to access the Intune Company Portal, you must upgrade these devices, by September, to devices that support iOS 10 or later:  

* iPhone 4S  
* iPod Touch  
* iPad 2  
* iPad (3rd Generation)  
* iPad Mini (1st Generation)  

Starting in July, MDM-enrolled devices with both iOS 9 and the Company Portal will receive a prompt to upgrade their OS or device. If you use app protection policies, you can also set the “Require minimum iOS operating system (Warning only)” access setting.  

#### What do I need to do to prepare for this change?   
Check for devices or users that are affected in your organization. In Intune in the Azure portal, go to Devices > All devices, and filter by OS.  Click Columns to surface details such as OS version. Request that your users upgrade their devices to a supported OS version before September.  

### Plan for Change: Intune moving to TLS 1.2
Starting on October 31, 2018, Intune will support Transport Layer Security (TLS) protocol version 1.2 to provide best-in-class encryption, to ensure our service is more secure by default, and to align with other Microsoft services such as Microsoft Office 365. Office communicated this change in MC128929.

The Company Portal will also move to support TLS 1.2 on October 31, 2018.

#### How does this affect me?
As of October 31, 2018, Intune will no longer support TLS protocol versions 1.0 or 1.1. All client-server and browser-server combinations should use TLS version 1.2 to ensure connection without issues to Intune. Note that this change will impact end-user devices that are no longer supported by Intune but are still receiving policy through Intune, and that cannot use TLS version 1.2. This includes devices such as those running Android 4.3 and earlier. For a list of affected devices and browsers, see Additional Information below.

After October 31, 2018, if you experience an issue related to the use of an old TLS version, you will be required to update to TLS 1.2 or to a device that supports TLS 1.2 as part of the resolution.

#### What do I need to do to prepare for this change?
We recommend that you proactively remove TLS 1.0 and 1.1 dependencies in your environments and disable TLS 1.0 and 1.1 at the operating system level where possible. Begin planning your migration to TLS 1.2 today. Check the support blog post below for the list of devices that are not supported by Intune today but might still be receiving policy, and that will not be able to communicate using TLS version 1.2. You might need to notify those end users that they’ll lose access to corporate resources.

**Additional Information**: [Intune moving to TLS 1.2 for encryption](https://blogs.technet.microsoft.com/intunesupport/2018/06/05/intune-moving-to-tls-1-2-for-encryption/)


### Plan for Change: Change in support for the Microsoft Intune App SDK for Cordova plugin
Intune is ending support for the [Microsoft Intune App SDK Cordova Plugin](app-sdk-cordova.md) on May 1, 2018. We recommend that you use the Intune App Wrapping Tool instead, to prepare your Cordova based apps for manageability and availability in Intune. When this change takes effect, the Microsoft Intune APP SDK for Cordova plugin will no longer be maintained or receive updates. App developers will not be able to use this plugin. Intune plans to continue supporting apps built with Cordova. However, any apps built with the Microsoft Intune APP SDK for Cordova plugin will experience reduced functionality in Intune. After wrapping with the Intune App Wrapping Tool, apps can be deployed to end users as they normally would be. For Cordova-based Android apps that are released to the Google Play Store:
- End users will be prompted for credentials to receive Intune policy on first launch.
- Apps should be released to the app store targeted for Intune users, for example “Contoso App for Intune”.

For more information about the App Wrapping Tool, see [App Wrapping Tool for iOS](app-wrapper-prepare-ios.md) and [App Wrapping Tool for Android](app-wrapper-prepare-android.md). For any issues or questions, contact [msintuneappsdk@microsoft.com](mailto:msintuneappsdk@microsoft.com).

### Plan for Change: Use Intune on Azure now for your MDM management <!-- 1227338 -->
Over a year ago, we announced [public preview of Intune on Azure](https://cloudblogs.microsoft.com/enterprisemobility/2016/12/07/public-preview-of-intune-on-azure/) and followed up six months ago with [general availability of the new admin experience](https://cloudblogs.microsoft.com/enterprisemobility/2017/06/08/the-new-intune-and-conditional-access-admin-consoles-are-ga/) for Intune. Starting on August 31, 2018, we will turn off mobile device management (MDM) in the classic Silverlight console for those customers using Intune standalone. Instead, you can use [Intune on Azure](https://aka.ms/Intune_on_Azure) for your MDM needs. If you're still using the classic console for MDM, please stop and familiarize yourself with Intune on Azure. We do not expect any end user impact with this change. Classic PC management will remain in Silverlight. You can learn more about this change and how it affects you [here](https://aka.ms/Intune_on_Azure_mdm).

### Direct access to Apple enrollment scenarios <!--951869-->
For Intune accounts created after January 2017, Intune has enabled direct access to Apple enrollment scenarios using the Enroll Devices workload in the Azure portal. Previously, the Apple enrollment preview was only accessible from links in the Intune classic portal. Intune accounts created before January 2017 require a one-time migration before these features are available in Azure. The schedule for migration has not been announced yet, but details will be made available as soon as possible. If your existing account cannot access the Azure portal, we strongly recommend creating a trial account to test out the new experience.

## What's coming

### Local device security option settings <!-- 1251887 -->
You'll be able to enable security settings on Windows 10 devices using the new Local Device Security Option settings. Find these settings in the Endpoint Protection category when you create a Windows 10 device configuration policy.

### New user experience update for the Company Portal website <!--2000968-->

We’re introducing a new Company Portal website experience starting in August, with UI updates, streamlined workflows and accessibility improvements. This will include customer-driven enhancements like app sharing and improved overall performance to bring you a more user-friendly experience.
We’ve added some new features, based on feedback from customers like you, that will significantly improve existing functionality and usability:

* UI improvements throughout the website
* Ability to share direct links to apps
* Improved performance for large app catalogs

You don't need to take any action to prepare for this change. We’ll let you know when the updated Company Portal website becomes available for you. However, you may eventually need to update end user docs with updated screenshots. Note that you may also need to update documentation for the Company Portal app on iOS, as the website powers the **Apps** section of the iOS app. You can see a sample image for this on the [what's new in app UI](whats-new-app-ui.md) page.

### Apple to require updates for Application Transport Security <!--748318-->
Apple has announced that they will enforce specific requirements for Application Transport Security (ATS). ATS is used to enforce stricter security on all app communications over HTTPS. This change impacts Intune customers using the iOS Company Portal apps. We'll keep our [Intune support blog](https://aka.ms/compportalats) with details.



## See also
* [Microsoft Intune Blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Cloud Platform roadmap](https://www.microsoft.com/cloud-platform/roadmap)
* [What's new in the Company Portal UI](whats-new-app-ui.md)
* [What's new in previous months](whats-new-archive.md)
