---
# required metadata

title: Previous releases | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 45dad14a-d412-488d-bb1e-ad990ea503df

# optional metadata

ROBOTS: noindex,nofollow
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Previous Intune releases
## March 2016
### What's new as of March 29, 2016
With the exception of the update to the Windows 10 general configuration policy, all of the features releasing on March 29, 2016, are also supported for hybrid customers (Configuration Manager integrated with Intune). Hybrid support for the Windows 10 general configuration policy update is coming soon. Please note that some of these features may require the latest version of Configuration Manager.

### App management
- **MAM controls to prevent Outlook contacts sync (iOS).** A new setting is available for mobile application management without device enrollment. This setting allows you to prevent an application from syncing contacts to the native address book on iOS devices. When this setting is enabled, the app will no longer be able to save contacts to the native address book. When this setting is disabled, the app will be able to save contacts to the native address book. When you selectively wipe a device, all contacts that have already been saved to the native address book will be removed. This new setting is supported by the Outlook application on iOS devices. For more details about this and other settings, see [Create and deploy MAM policies](https://technet.microsoft.com/en-us/library/dn292747.aspx).

### Access control
- **Skype for Business Online supports conditional access.** You can set a conditional access policy for Skype for Business Online so that it can only be accessed by managed and compliant iOS and Android devices. End users who try to sign in to the Skype for Business mobile app on iOS and Android will be prompted to enroll with Intune as well as fix any non-compliance issues before sign-in can complete. For details, see [Manage access to Skype for Business Online](https://technet.microsoft.com/en-us/library/mt695297.aspx).

### Device management
- **Intune support for iOS 9.3.** On Monday March 21st, Apple announced the availability of iOS 9.3. We have been busy working to ensure that Microsoft Intune is compatible with the latest version of Apple's mobile operating system, and [we are pleased to announce that Intune supports managing iOS 9.3 devices](https://blogs.technet.microsoft.com/microsoftintune/2016/03/23/microsoft-intune-provides-support-for-ios-9-3/).

  All existing Intune features currently available for managing iOS devices will continue to work seamlessly as users upgrade their devices to iOS 9.3. In addition, iOS 9.3 is also supported today for hybrid customers (Configuration Manager integrated with Intune).

- **The Windows 10 general configuration policy now contains settings to manage Windows Defender on enrolled Windows 10 PC's.** For details, see [Windows 10 configuration policy settings in Microsoft Intune](https://technet.microsoft.com/en-us/library/mt404697.aspx).


### Company portal

- **Windows app packages available directly from the Company Portal website.** Users of Windows 8, Windows 8.1, and Windows RT PCs can now install Windows app packages (with the .appx extension) directly from the Company Portal website. Previously, you had to deploy, or users had to install the Company Portal app on their devices to install apps.

- **Users can remotely lock their device from the Company Portal website.** A new Remote Lock option has been added to the Company Portal website to enable users to remotely lock their device from the Portal if their device is lost or stolen. See the [end-user instructions](https://technet.microsoft.com/library/mt590895.aspx/?wt.mc_id=ui#BKMK_iwp_remote_lock). The following table lists the platform support for Remote Lock for Intune Standalone and Intune with Configuration Manager.

|Platform | Support details|
|---------|----------------|
|Android |Supported|
|iOS |Supported|
|Windows 10 Mobile |Supported only if the phone has a passcode set|
|Windows 10 Desktop |Not supported|
|Windows Phone 8.1 |Supported only if the phone has a passcode set|
|Windows Phone 8.0 |Not supported|
|PC (Windows 8.0 and earlier) |Not supported|
|PC (Windows 8.1) |Not supported|

### What's new as of March 10, 2016

### App management

- **Take advantage of iOS "Open-in" management for devices that are enrolled in a third-party MDM solution**
You can use your third-party mobile device management (MDM) vendor to take advantage of iOS "Open-In" management. You can set the restrictions in the configuration profile settings and deploy the app using [Manage data transfer between iOS apps](manage-data-transfer-between-ios-apps-with-microsoft-intune.md).

     This approach has two main benefits:

     1. Users are required to log in with their work account before they get access to any corporate data from Cloud Services or other apps. This ensures that mobile app management (MAM) policies are in place when the data is accessed.

     2. Managed  email profiles and other managed apps deployed through a third-parter MDM solution can share files and data with the apps that have Intune MAM policies.

- **Manage the Microsoft Outlook app with MAM policies for devices not enrolled in Intune**
You can now manage the Microsoft Outlook app on devices that are not enrolled in Intune with the Intune mobile application management policy. The updated Microsoft Outlook app with the MAM capabilities is available for both [iOS](https://itunes.apple.com/us/app/microsoft-outlook-email-calendar/id951937596?mt=8) and [Android](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook) devices. Use the instructions in the [Create and deploy mobile app management policies](https://technet.microsoft.com/library/mt627829.aspx) topic to create a MAM policy.  


- **Mobile app configuration policies give you more flexibility to specify user details for iOS apps**
You can supply user settings that an iOS app might need when it is opened. For example, you can supply a network port, or a user name. For details, see [Configure iOS apps with mobile app configuration policies in Microsoft Intune](configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune.md).


- **Deploy Adobe Reader for Microsoft Intune to Intune-managed iOS devices in your enterprise**
The Adobe Reader app for iOS can now be managed on enrolled devices with the Intune mobile application management policy.

- **Ensure deployed web clips are opened in the managed browser**
You can deploy targeted web clips that can only be opened using the managed browser on iOS and Android devices. For example, you deploy links to corporate resources through the Company Portal, and when users navigate to the links, they open directly into the managed browser where they can be protected by MAM policy. For details, see [Deploy apps ](deploy-apps.md).


- **Find, manage, and distribute Windows Store for Business apps for Windows 10 devices from the Intune administrator console**
Support for Windows Store for Business is available in Intune to help you find, manage, and distribute apps to the Windows 10 devices you’re managing. Windows Store for Business lets you manage the process of deploying and monitoring these apps from the Intune administrator console—the same console you use to manage your other apps. Specifically, Windows Store for Business manages the content and licensing  of “online licensed apps”. For details, see [Manage apps you purchased from the Windows Store for Business](manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune.md).


### Device management
- **PFX certificates distribution for iOS devices**
Intune administrators can create and deploy iOS PFX certificates for Wi-Fi, email, and VPN authentication on iOS devices. This feature is already available for Android and Windows 10 devices. For details, see [Enable access to company resources using certificate profiles ](secure-resource access-withcertificate-profiles-with-microsoft-intune.md).


- **Apply apps and policies to different device groups based on user category selection**
Intune administrators can now define custom device categories for users to select from during enrollment. For example, administrators might want their users to specify if they're enrolling a device used for the "Cash Register" or "Delivery Truck" or "Inventory Room." The category selected will cause the device to become a member of an Intune device group, which can be used for deploying different apps and policies to the enrolled device. For details, see [Categorize devices with device group mapping](categorize-devices-with-device-group-mapping-in-microsoft-intune.md).

### Changes and updates to Microsoft Company Portal
The following changes have been made to the Company Portal in this release.

**Android Company Portal app**

* When your users launch an app that is managed by mobile application management (MAM), they will see a message notifying them that the app is managed by their company. Users can now tap a “Learn More” link to get [more information](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_use_mgd_apps) here about what “managed apps” means. They can also tap “Don’t Show Again” so that the message no longer appears when they launch the app.
* New screens have been added to guide users through the enrollment process and provide more information about why users should enroll and what IT administrators can and can’t see on their enrolled devices. See the [enrollment instructions](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_enroll_devc) for details.
* Enrollment error messages are now displayed in the Company Portal app. Previously, these messages appeared in the Company Portal website. Making this change means that all error messages now appear in just one place instead of two different places.


**iOS Company Portal app**
* When your users launch an app that is managed by mobile application management (MAM), they will see a message notifying them that the app is managed by their company. Users can now tap a “Learn More” link to get [more information](https://technet.microsoft.com/library/mt598622.aspx#BKMK_ios_use_mgd_apps) here about what “managed apps” means. They can also tap “Don’t Show Again” so that the message no longer appears when they launch the app.
* New screens have been added to guide users through the enrollment process and provide more information about why users should enroll and what IT administrators can and can’t see on their enrolled devices. See the [enrollment instructions](https://technet.microsoft.com/library/mt598622.aspx#BKMK_enroll_ios_device) for details.
* Enrollment error messages are now displayed in the Company Portal app. Previously, these messages appeared in the Company Portal website. Making this change means that all error messages now appear in just one place instead of two different places.




## February 2016
### Changes and updates to Microsoft Company Portal

The following changes have been made to the Company Portal in this release.

#### Android Company Portal app
- New screens have been added to guide users through the enrollment process and provide more information about why users should enroll and what IT administrators can and can’t see on their enrolled devices. See the [enrollment instructions](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_enroll_devc) for details.
- Enrollment error messages are now displayed in the Company Portal app. Previously, these messages appeared in the Company Portal website. Making this change means that all error messages now appear in just one place instead of two different places.

#### iOS Company Portal app
 - New screens have been added to guide users through the enrollment process and provide more information about why users should enroll and what IT administrators can and can’t see on their enrolled devices. See the [enrollment instructions](https://technet.microsoft.com/library/mt598622.aspx#BKMK_enroll_ios_device) for details.

 - Enrollment error messages are now displayed in the Company Portal app. Previously, these messages appeared in the Company Portal website. Making this change means that all error messages now appear in just one place instead of two different places.


## January 2016

### Take advantage of Windows 10 features
* **Conditional access with Health Attestation Service**
Intune administrators can now view the status of Windows 10 Device Health Attestation in the Intune Admin console. Device health attestation lets the administrator ensure that client computers have trustworthy BIOS, TPM, and boot software configurations. To support device health attestation, client devices must be running Windows 10 with TPM 2 enabled. Device health attestation displays the number of devices enabled for each of the following:
	* Early-launch antimalware
	* BitLocker
	* Secure Boot
	* Code Integrity

	Read [Introduction to device compliance policies for Microsoft Intune](introduction-to-device-compliance-policies-in-microsoft-intune.md) for more details on the device health setting, collected data points, and the health attestation report. The [HAS service details](https://msdn.microsoft.com/en-us/library/dn934876.aspx) explains the service in depth.

* **Windows 10 Passport for Work Policy and certificate management**
With Intune, you can [integrate with Microsoft Passport for Work](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md), which is an alternative sign-in method for Windows 10 that uses Active Directory or an Azure Active Directory account to replace a password, smart card, or virtual smart card. Passport lets you use a user gesture to log in instead of a password. A user gesture might be a simple PIN, biometric authentication such as Windows Hello, or an external device such as a fingerprint reader.

* **VPN for specific apps**
You can select apps that automatically connect to your corporate network over VPN. Create the list of apps when you set up the VPN profile, as described in Help users connect to their work using VPN profiles with Microsoft Intune.

* **Windows 10 Full Wipe support**
You can now issue a remote full wipe of Windows 10 desktop devices enrolled in Intune through the Intune admin console. Windows 10 full wipe does a factory reset of the device.


### Apple Volume Purchase Program (VPP) update
Intune can now help you [manage apps you purchased through the Apple Volume Purchase Program (VPP) for Business](manage-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune.md). This includes synchronizing license information between Apple and Intune, and tracking how many copies of each app you have deployed.

### Use IMEI numbers to identify corporate-owned devices
You can now [import international mobile equipment identity (IMEI) numbers](specifiy-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md) for mobile device platforms that have an IMEI number to help identify corporate-owned mobile devices. Once enrolled in Intune, devices with imported IMEI numbers are tagged as Corporate, which can be used for applying policies that are different than those applied to personally owned devices.

### More apps are now compatible with Intune MAM policies
Additional apps from Microsoft partners are now compatible with Intune mobile application management (MAM) policies (for devices managed by Intune):
* Box for EMM (from Box Inc) – iOS only
* Adobe Reader (from Adobe) – Android only
* Foxit PDF Reader (from Foxit Corporation) – iOS and Android


### IE9 support ending in January
Starting in February, 2016, Internet Explorer 9 will no longer be supported as an official browser for accessing the Microsoft Intune company portal website, Intune account portal, and Intune administration console. You will need to migrate to Internet Explorer 10 or later.

## December 2015
### Changes and updates to Microsoft Company Portal
The following changes have been made to the Company Portal in this release.

**Android Company Portal app**

The following changes have been made to comply with new Google requirements. On Android 6.0 and above devices, two new messages are displayed to users:
* Allow Company Portal to make and manage phone calls?
* Allow Company Portal to access photos, media, and files on your device?

See the following tables for details about these two messages.



Message text  |Allow Company Portal to make and manage phone calls?  
---------|---------
Meaning of message     |  Enables the user's device phone number and IMEI to be sent to the Intune service and appear in the Admin console on the Hardware page.   </br></br>**NOTE: The Company Portal app never makes or manages phone calls!** The message text is controlled by Google and cannot be changed. </br></br>To see the **Hardware** page, go to **Groups** > **All mobile devices** > **Device**s. Select the user's device, and go to **View Properties** > **Hardware**.    
Where and when message appears  | The message appears when users sign in to the Company Portal app for the first time to start enrolling their device.|         
What happens if users allow access  |  The device's phone number and IMEI will appear on the Hardware page in the Admin console. |         
What happens if users deny access     | They can continue to use the Company Portal app and enroll their device, but the users's device phone number and IMEI will be blank on the Hardware page in the Admin console.       </br></br> The second time that users sign in to the Company Portal app after denying access, the message displays a **Never ask again** check box that users can select so that the message never shows again.</br></br>If users allow but then later deny access, the message appears the next time users sign in to the Company Portal app after enrollment.</br></br>If users later decide to allow access, they can go to **Settings** > **Apps** > **Company Portal** > **Permissions** > **Phone**, and then turn on the permission.
More information     |  For your users: [Sign in to the Company Portal](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_signin_cp)  </br></br>For IT Pros: The information in this table is also in [Helping your users understand Company Portal app messages](https://technet.microsoft.com/library/dn948527.aspx#BKMK_help_users_understd_msgs)   

Message text  |Allow Company Portal to access photos, media, and files on your device?  
---------|---------
Meaning of message     |  Enables the device to write data logs to the device's SD card, which enables logs to be moved by using a USB cable.   </br></br>**NOTE: The Company Portal app never accesses users' photos, media, and files!** The message text is controlled by Google and cannot be changed.     
Where and when message appears  | The message appears when users tap **Send Data** to send data logs to their IT admin.|         
What happens if users allow access  |  The logs will be copied to the SD card. |         
What happens if users deny access     | They can still send data logs, but the logs won't be copied to the device's SD card.       </br></br> The second time that users sign in to the Company Portal app after denying access, the message displays a **Never ask again** check box that users can select so that the message never shows again.</br></br>If users allow but then later deny access, the message appears the next time users try to send logs.</br></br>If users later decide to allow access, they can go to **Settings** > **Apps** > **Company Portal** > **Permissions** > **Storage**, and then turn on the permission.
More information     |  For your users: [Send diagnostic data logs to your IT admin using email](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_send_diag_logs)  </br></br>For IT Pros: The information in this table is also in [Helping your users understand Company Portal app messages](https://technet.microsoft.com/library/dn948527.aspx#BKMK_help_users_understd_msgs)   


**iOS Company Portal app**
* Users can now use Microsoft Outlook or other mail apps to send diagnostic logs to the IT administrator. Previously, only the native app could be used.
* Support has been improved for Apple's Device Enrollment Program (DEP) and corporate-enrolled devices. For details, see [You are asked to identify your device when you're trying to enroll](https://technet.microsoft.com/library/mt598622.aspx#BKMK_ios_id_your_device).
* In the user's list of enrolled devices, a green check mark now appears next to the device that the user is currently using. Before this check mark was added, users couldn't tell which enrolled device they were using.

**Windows Company Portal app**

Microsoft automatically collects anonymous data about the performance and use of the company portal to improve Microsoft products and services. End users can turn off data collection by using the Usage Data setting on their device, but administrators have no control over the data collection and cannot change the end user’s selection for this setting.



## November 2015
### App management
Intune supports mobile application management (MAM) policies that help prevent corporate data from being leaked to consumer apps or services. Historically, these policies would only be enforced on mobile apps running on devices that were also enrolled for mobile device management (MDM) into Intune.

With this month's update, Intune is expanding its MAM capabilities to new classes of devices. In addition to devices enrolled into Intune, you can now enforce MAM policies on:
* devices managed by any other device management (MDM) solution
* device that are not enrolled into any device management system, typically bring-your-own (BYO) devices

You can find more information about these new MAM capabilities in the following blog posts:
* [Enhancing managed mobile productivity](http://blogs.technet.com/b/microsoftintune/archive/2015/11/17/enhancing-managed-mobile-productivity.aspx)
* [Announcing new Microsoft Enterprise Mobility capabilities](http://blogs.technet.com/b/microsoftintune/archive/2015/11/17/enhancing-managed-mobile-productivity.aspx)

Additionally, here are some highlights and additional information about Intune's MAM features:
* Corporate data is isolated from consumer data within apps enlightened for Intune including Office Mobile apps, third-party apps that have adopted the Intune SDK, or line-of-business apps wrapped by Intune.
* Company data can be shared (**cut/copy/paste**) across company apps, while preventing the sharing of company data into personal apps. Read [How MAM policies protect app data](https://technet.microsoft.com/library/mt627825.aspx) for more details. This example scenario, [Using Microsoft Word app for work and personal tasks](https://technet.microsoft.com/library/mt627827.aspx), shows how sharing company data into personal apps is prevented.
* Key data loss prevention policies like per-App PIN, save-as controls, and managed data sharing between apps. Read [Create and deploy mobile app management policies with Microsoft Intune](https://technet.microsoft.com/library/mt627829.aspx) to see a list of all the policies.
* Word, Excel, PowerPoint, Outlook, OneNote, and OneDrive for Business all have these new capabilities and can be managed with and without device enrollment. The data loss protection capabilities are natively built into the standard Office apps in the Apple Store or the Google Play store, and do not require app wrapping or sideloading.
* To learn how to get started, see [Get started with mobile app management policies in the Azure portal](https://technet.microsoft.com/library/mt627830.aspx). To learn how to configure and deploy mobile app management policies, see [Create and deploy mobile app management policies with Microsoft Intune](https://technet.microsoft.com/library/mt627829.aspx).
* When end-users authenticate to the app with their corporate credentials, the data loss protection capabilities are automatically set up. The [End-user experience for apps associated with Microsoft Intune mobile app management policies](https://technet.microsoft.com/library/mt627827.aspx) topic has some example scenarios for accessing OneDrive on iOS and Android devices.
* Works on both iOS and Android devices.

The list of [Microsoft apps you can use with Microsoft Intune mobile application management policies](https://technet.microsoft.com/library/dn708489.aspx) has been updated to show the latest apps.

### Device management
 **Mac OS X device management**
With Intune, you can now enroll and manage Mac OS X devices. You can do the following with your Mac OS X devices:
* Enroll devices to be managed by Intune. See [Set up iOS and Mac management with Microsoft Intune](https://technet.microsoft.com/library/dn408185.aspx).
* Control device settings with a general configuration policy. See [Mac OS X configuration policy settings in Microsoft Intune](https://technet.microsoft.com/library/mt627823.aspx).
* Deploy Mac OS X settings you created with the Apple Configurator. See [Mac OS X custom policy settings in Microsoft Intune](https://technet.microsoft.com/library/mt627820.aspx).
* Collect hardware and software inventory from Mac OS X devices. See [Understand your devices with inventory in Microsoft Intune](https://technet.microsoft.com/library/jj733634.aspx).
* Run new reports that display details about the Mac OS X devices you manage. See [Understand Microsoft Intune operations by using reports](https://technet.microsoft.com/library/dn646977.aspx).

**New Edge browser settings for Windows 10 devices**
New settings have been added to the Windows 10 general configuration policy that let you manage settings and features of the Microsoft Edge browser. See [Windows 10 configuration policy settings in Microsoft Intune](https://technet.microsoft.com/library/mt404697.aspx).

**Email profiles**
A new email profiles policy has been added for Windows 10 desktop and Windows 10 mobile devices. See [Manage settings and features on your devices with Microsoft Intune policies](https://technet.microsoft.com/library/dn646984.aspx).

**New compliance policy settings**
The following new security and system policy settings have been added to the list of compliance policies:
* To make sure that Windows 8.1 or later devices that access your company resources have the latest updates installed, use the **Require automatic updates** setting. You can also specify the type of updates to be automatically installed -- either all updates marked as important to be installed, or all updates marked important or recommended. For the full list of compliance policy settings, see [Manage device compliance policies for Microsoft Intune](https://technet.microsoft.com/library/dn705843.aspx).
* The new **Require a password when the device returns from the idle state** setting combined with the existing **Minutes of inactivity before password is required** setting allows you to create a compliance setting that requires the end-user to enter a password to use a device that has been inactive for a certain time.

**New conditional access policy options**
You can apply conditional access policies to **all users** in either new or existing conditional access policies. All users licensed for Intune and Office 365 will be required to enroll their devices, and if the device platform is not supported by Intune, access is blocked for client applications using [Active Directory authentication based sign-in (modern authentication)](https://blogs.office.com/2014/11/12/office-2013-updated-authentication-enabling-multi-factor-authentication-saml-identity-providers/).

You can also specify that the conditional access policy applies to **all platforms**.  Any client application using the [Active Directory authentication based sign-in (modern authentication)](https://blogs.office.com/2014/11/12/office-2013-updated-authentication-enabling-multi-factor-authentication-saml-identity-providers/) is subject to the conditional access policy, and if the platform is not supported by Intune, it will be blocked.

### Changes and updates to Microsoft Company Portal
The following changes have been made to the company portal apps in this release:

* **Android**: A Welcome screen has been added to the Android Company Portal app to help users understand the purpose of the Company Portal app. This screen is intended to reduce downloads of the app by users whose companies are not Intune subscribers.

* **iOS**: Intune now supports the enrollment of Mac OS X devices  by using  the [Company Portal website](https://portal.manage.microsoft.com). For instructions, see [Enroll your Mac OS X device in Intune](https://technet.microsoft.com/library/mt598622.aspx).

* **Company Portal website**: Users who have enrolled their device in Intune can now reset their passcode by using the **Reset Passcode** option on the Company Portal website. Previously, only IT administrators could reset users' passcodes. The  Reset Passcode option is not supported on Windows 8.1 and Windows RT devices, and the option appears only when devices are enrolled in mobile device management (MDM) or MDM with Exchange ActiveSync. For user instructions, see [Reset your passcode](https://technet.microsoft.com/library/mt590895.aspx).

### Changes to Global Admins licensing
In October, we shared that Global Admins (also referred to as Tenant Admins) could continue to do day-to-day administration tasks without a separate Intune or Enterprise Mobility Suite (EMS) license. However, if Global Admins want to use the service, such as to enroll their own device, a corporate device, or use the Intune Company Portal, they will need an Intune or EMS license just like any other user. Below are a few additional details.
* The Intune Company Portal is where end users can:
    * enroll their device
    * view the status of their device
    * download software that a Global Admin has deployed to the organization
    * find links published by the Global Admin for how to contact their IT department

	[Learn about the Company Portal](https://technet.microsoft.com/library/dn646966.aspx#BKMK_CompanyPortal)  and about [ways to customize the Company Portal](https://technet.microsoft.com/library/dn646983.aspx#BKMK_ConfigureCompanyPortal).
* The person who signs up to purchase Intune or EMS on behalf of an organization automatically becomes the first Global Admin in their tenant. This fall, Intune started to auto-assign an Intune or EMS license to that very first Global Admin as part of the move to the [Office 365 Portal](http://portal.office.com/) and retirement of the [Intune Account Portal](http://account.manage.microsoft.com/). Any additional Global Admins added can continue to do day-to-day administration without a separate Intune or EMS license. Acting as an end user and enrolling their own (or corporate) device or downloading software from the company portal would then trigger a need for a license, just like any other user.
* The change will be phased in and will now start in January, 2016.
* For Microsoft Partners, this change should not affect your ability to administer the service on behalf of customers. For end-user tasks, a user will need to have an Intune or EMS license in order to enroll a device and access or download software from the Company Portal.

If you have any questions about this change, feel free to contact your Intune support team:
* [Microsoft Intune support channels](https://technet.microsoft.com/library/jj839713.aspx)
* [Community support](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod)

For general Microsoft Intune feedback, including filing Design Change Requests (DCRs) or bugs, please visit [Intune user voice](https://microsoftintune.uservoice.com/).


### What's new in Intune documentation -- November 2015
**New content**
* [Mac OS X configuration policy settings in Microsoft Intune](https://technet.microsoft.com/library/mt627823.aspx): How to control device settings and features for Mac OS X devices.
* [Mac OS X custom policy settings in Microsoft Intune](https://technet.microsoft.com/library/mt627820.aspx): How to deploy Mac OS X device settings that you created using the Apple Configurator tool.
* [Configure data loss prevention app policies with Microsoft Intune](https://technet.microsoft.com/library/mt627825.aspx): Contains information about the scenarios that mobile app management policies support and  how the policy works to protect data.
* [Get started with mobile app management policies in the Azure portal](https://technet.microsoft.com/library/mt627830.aspx): What you need to get started using the Azure preview portal for mobile app management policies.
* [Create and deploy mobile app management policies with Microsoft Intune](https://technet.microsoft.com/library/mt627829.aspx): Contains a step-by-step walkthrough of how to create mobile app management policies in the Azure preview portal.
* [Monitor mobile app management policies with Microsoft Intune](https://technet.microsoft.com/library/mt627824.aspx): Information on how you can monitor your mobile app management policies using the Azure preview portal.
* [Microsoft Intune mobile app management policies and iOS Open In](https://technet.microsoft.com/library/mt627821.aspx): Information on how mobile app management policies work with iOS Open In feature.
* [End-user experience for apps associated with Microsoft Intune mobile app management policies](https://technet.microsoft.com/library/mt627827.aspx): What the end-user experience is when using apps associated with mobile app management policy.
* [Wipe managed company app data with Microsoft Intune](https://technet.microsoft.com/library/mt627826.aspx): How you can remove company app data.

**Updated content**
* [Windows 10 configuration policy settings in Microsoft Intune](https://technet.microsoft.com/library/mt404697.aspx): Added new Edge browser settings.
* [Set up iOS and Mac management with Microsoft Intune](http://technet.microsoft.com/library/dn408185.aspx): Added information about how to enroll Mac OS X devices.
* [Understand your devices with inventory in Microsoft Intune](https://technet.microsoft.com/library/jj733634.aspx): Added information about the inventory collected from Mac OS X devices. Also, updated the topic with the latest information for all device platforms.
* [Understand Microsoft Intune operations by using reports](https://technet.microsoft.com/library/dn646977.aspx): Added information about the two new reports used to display information about your managed Mac OS X devices.
* [Manage device compliance policies for Microsoft Intune](https://technet.microsoft.com/library/dn705843.aspx): Added information about the new compliance policies for requiring automatic updates and password requirement when a device returns from idle state.
* [Manage email access with Microsoft Intune](https://technet.microsoft.com/library/dn705841.aspx): Added information about the ability to apply the conditional access  policy to all platforms and all users.
* [Manage SharePoint Online access with Microsoft Intune](https://technet.microsoft.com/library/dn705844.aspx): Added information about the ability to apply conditional access policy to all platforms and all users.

## October 2015

### Updates to conditional access for Exchange on-premises
**You can now allow access to Exchange Active Sync email for compliant devices enrolled in Intune when the global Exchange rule is set to block or quarantine** Until now, to allow email access on enrolled and compliant devices, you had to set the default global Exchange rule to **Allow**.

With this service update, this setting is no longer a requirement for conditional access. If your Exchange environment requires that your default global rule to be set to **Block/Quarantine**, simply check the **Default Rule Override** checkbox in the Exchange on-premises conditional access policy page. The [Manage email access with Microsoft Intune](https://technet.microsoft.com/library/dn705841.aspx) topic has more details on the rules and the resulting end user notifications.

**New one-click quarantine experience** We have simplified the quarantine email experience to allow one-click enrollment. With this service update, end users can click  a single link in the quarantine email to complete the  enrollment process within the company portal app.
### Mobile device and app management updates
**Android** All Intune management features now support Android 6.0 (Marshmallow) as described in this blog post: [Microsoft Intune Provides Day 0 Support for Android Marshmallow](http://blogs.technet.com/b/microsoftintune/archive/2015/10/09/microsoft-intune-to-provide-day-0-support-for-android-marshmallow.aspx)

**iOS** You can no longer create new app deployments to iOS devices running a version earlier than iOS 7.1. Any existing app deployments to devices running an earlier version than iOS 7.1 will continue to work and be managed by Intune.

**Windows 10** Intune now supports deploying Windows 10 Universal apps using the **Windows app package** software installer type. For details and requirements, see [Get started with app deployment in Microsoft Intune](http://technet.microsoft.com/en-US/library/dn646955.aspx).


### Changes and updates to Microsoft Company Portal apps
The following changes have been made to the company portal apps in this release:
**iOS**
New buttons have been added to the Company Portal app to make it easier for users to send diagnostic logs to their IT admins:

|Button name|Where it appears|
|------------|---------------|
|Report|Error alert messages|
|Send Diagnostic Report|About screen of the Company Portal app|


>[!div class="step-by-step"]

>[&larr; **What's new in Intune**](whats-new-in-microsoft-intune.md)    
