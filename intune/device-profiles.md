---
# required metadata

title: Device features and settings in Microsoft Intune - Azure | Microsoft Docs
description: Overview of the different Microsoft Intune device profiles, including features, restrictions, email, wifi, VPN, education, certificates, upgrade Windows 10, BitLocker and Windows defender, Windows Information Protection, administrative templates, and custom device configuration settings in the Azure portal. Use these profiles to manage and protect data and devices in your company.
keywords:
author: MandiOhlinger

ms.author: mandia
manager: dougeby
ms.date: 03/12/2019
ms.topic: conceptual
ms.prod:
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology:
ms.assetid:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer:
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
---

# Apply features and settings on your devices using device profiles in Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Microsoft Intune includes settings and features you can enable or disable on different devices within your organization. These settings and features are added to "configuration profiles". You can create profiles for different devices, different platforms, including iOS, Android, and Windows, and then use Intune to apply the profile to devices in your organization.

As part of your mobile device management (MDM) solution, use these configuration profiles to complete different tasks. Some profile examples include:

- On Windows 10 devices, use a profile template that blocks ActiveX controls in Internet Explorer.
- On iOS and macOS devices, allow users to use AirPrint printers in your organization.
- Allow or prevent access to bluetooth on the device.
- Create a WiFi or VPN profile that gives different devices access to your corporate network.
- Manage software updates, including when they are installed.
- Run an Android device as dedicated kiosk device that can run one app, or run many apps.

This article lists the steps to create a profile, and gives an overview of the different types of profiles you can create. Use these profiles to allow or prevent some features on the devices.

## Create the profile

1. In the [Azure portal](https://portal.azure.com), select **All Services** > filter on **Intune** > select **Intune**.

2. Select **Device configuration**. You have the following options:

    - **Overview**: Lists the status of your profiles, and provides additional details on the profiles you assigned to users and devices.
    - **Manage**: Create device profiles, upload custom [PowerShell scripts](intune-management-extension.md) to run within the profile, and add data plans to devices using [eSIM](esim-device-configuration.md).
    - **Monitor**: Check the status of a profile for success or failure, and also view logs on your profiles.
    - **Setup**: Add a SCEP or PFX certificate authority, or enable [Telecom Expense Management](telecom-expenses-monitor.md) in the profile.

3. Select **Profiles** > **Create Profile**. Enter the following properties:

   - **Name**: Enter a descriptive name for the profile.
   - **Description**: Enter a description for the profile. This setting is optional, but recommended.
   - **Platform**: Choose the platform of your devices. Your options:  

       - **Android**
       - **Android enterprise**
       - **iOS**
       - **macOS**
       - **Windows Phone 8.1**
       - **Windows 8.1 and later**
       - **Windows 10 and later**

   - **Profile type**: Select the type of settings you want to create. The list shown depends on the **platform** you choose:

       - [Administrative templates](administrative-templates-windows.md)
       - [Custom](custom-settings-configure.md)
       - [Delivery optimization](delivery-optimization-windows.md)
       - [Device features](device-features-configure.md)
       - [Device restrictions](device-restrictions-configure.md)
       - [Edition upgrade and mode switch](edition-upgrade-configure-windows-10.md)
       - [Education](education-settings-configure.md)
       - [Email](email-settings-configure.md)
       - [Endpoint protection](endpoint-protection-configure.md)
       - [Identity protection](identity-protection-configure.md)  
       - [Kiosk](kiosk-settings.md)
       - [PKCS certificate](certficates-pfx-configure.md)
       - [SCEP certificate](certificates-scep-configure.md)
       - [Trusted certificate](certificates-configure.md)
       - [Update policies](software-updates-ios.md)
       - [VPN](vpn-settings-configure.md)
       - [Wi-Fi](wi-fi-settings-configure.md)
       - [Windows Defender ATP](advanced-threat-protection.md)
       - [Windows Information Protection](windows-information-protection-configure.md)

     For example, if you select **iOS** for the platform, your profile type options look similar to the following:

     ![Create iOS profile in Intune](./media/create-device-profile.png)

4. Select **Settings**. The settings are organized by category. Select a category to see a list of all the settings you can configure.

5. When finished, select **OK** > **Create** to save your changes.

#### Refresh cycle times

Intune uses the following refresh cycles to check for updates to configuration profiles:

| Platform | Refresh cycle|
| --- | --- |
| iOS | Every 6 hours |
| macOS | Every 6 hours |
| Android | Every 8 hours |
| Windows 10 PCs enrolled as devices | Every 8 hours |
| Windows Phone | Every 8 hours |
| Windows 8.1 | Every 8 hours |

If the device recently enrolled, the check-in runs more frequently:

| Platform | Frequency |
| --- | --- |
| iOS | Every 15 minutes for 6 hours, and then every 6 hours |  
| Mac OS X | Every 15 minutes for 6 hours, and then every 6 hours | 
| Android | Every 3 minutes for 15 minutes, then every 15 minutes for 2 hours, and then every 8 hours | 
| Windows Phone | Every 5 minutes for 15 minutes, then every 15 minutes for 2 hours, and then every 8 hours | 
| Windows PCs enrolled as devices | Every 3 minutes for 30 minutes, and then every 8 hours | 

At any time, users can open the Company Portal app, and sync the device to immediately check for profile updates.

### 
To learn more about the different profile types, read through the next sections in this article.

## Administrative templates (Preview)

[Administrative templates](administrative-templates-windows.md) includes hundreds of settings that you can configure for Internet Explorer, OneDrive, remote desktop, Word, Excel, and other Office programs, and much more.

These templates give administrators an easy and simplified view of settings similar to group-policy, but they are 100% cloud-based. 

This feature supports:

- Windows 10 and later

## Device features

[Device features](device-features-configure.md) controls features on iOS and macOS devices, such as AirPrint, notifications, and lock screen messages.

This feature supports:

- iOS 
- macOS

## Device restrictions

[Device restrictions](device-restrictions-configure.md) controls security, hardware, data sharing, and more settings on the devices. For example, create a device restriction profile that prevents iOS device users from using the device camera. 

This feature supports:

- Android
- Android enterprise
- iOS
- macOS
- Windows 10 and later
- Windows 10 Team

## Delivery optimization

[Delivery optimization](delivery-optimization-windows.md) provides a better experience to delivery software updates. These settings are replacing the **Software Updates** > **Windows 10 update ring** settings.

Use these settings to control how software updates are downloaded to devices in your organization. For example, you can let users get their own updates, or get updates using the delivery optimization cloud services in a device profile.

This feature supports:

- Windows 10 and later

## Endpoint protection

[Endpoint protection settings for Windows 10](endpoint-protection-windows-10.md) configures BitLocker and Windows Defender settings for Windows 10 devices.

To onboard Windows Defender Advanced Threat Protection (WDATP) with Microsoft Intune, see [Configure endpoints using Mobile Device Management (MDM) tools](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/configure-endpoints-mdm-windows-defender-advanced-threat-protection).

This feature supports:

- Windows 10 and later

## Identity protection

[Identity protection](identity-protection-configure.md) controls the Windows Hello for Business experience on Windows 10 and Windows 10 Mobile devices. Configure these settings to make Windows Hello for Business available to users and devices, and to specify requirements for device PINs and gestures.  

This feature supports:  

- Windows 10 and later
- Windows Holographic for Business  

## Kiosk

[Kiosk settings](kiosk-settings.md) profile configures a device to run one app, or run many apps. You can also customize other features on your kiosk, including a start menu and a web browser.

This feature supports:

- Windows 10 and later

Kiosk settings also available as device restrictions for [Android](device-restrictions-android.md#kiosk), [Android Enterprise](device-restrictions-android-for-work.md#dedicated-device-settings), and [ios](device-restrictions-ios.md#kiosk-supervised-only).

## Email

[Email settings](email-settings-configure.md) creates, assigns, and monitors Exchange ActiveSync email settings on the devices. Email profiles help with consistency, reduce support calls, and let end-users access company email on their personal devices, without any required setup on their part. 

This feature supports: 

- Android
- iOS
- Windows Phone 8.1
- Windows 10 and later

## VPN

[VPN settings](vpn-settings-configure.md) assigns VPN profiles to users and devices in your organization, so they can easily and securely connect to the network. 

Virtual private networks (VPNs) give users secure remote access to your company network. Devices use a VPN connection profile to start a connection with your VPN server. 

This feature supports: 

- Android
- iOS
- macOS
- Windows Phone 8.1
- Windows 8.1
- Windows 10 and later

## Wi-Fi

[Wi-Fi settings](wi-fi-settings-configure.md) assigns wireless network settings to users and devices. When you assign a WiFi profile, users get access to your corporate WiFi without having to configure it themselves. 

This feature supports: 

- Android
- iOS
- macOS
- Windows 8.1 (import only)
- Windows 10 and later

## eSIM cellular - Public preview

[eSIM cellular profiles](esim-device-configuration.md) lets administrators configure cellular data plans on your managed devices for internet and data access. After getting activation codes from your mobile operator, use Intune to import these activation codes, and then assign to your eSIM capable devices.

This feature supports:
- Windows 10 Fall Creators Update and later

## Education

[Education settings - Windows 10](education-settings-configure.md) configure options for the [Windows Take a Test app](https://education.microsoft.com/gettrained/win10takeatest). When you configure these options, no other apps can run on the device until the test is complete.

[Education settings - iOS](education-settings-configure-ios-shared.md) uses the iOS Classroom app to guide learning, and control student devices in the classroom. You can configure iPad devices so many students can share a single device.

## Edition upgrade

[Windows 10 edition upgrades](edition-upgrade-configure-windows-10.md) automatically upgrades devices that run some versions of Windows 10 to a newer edition.

This feature supports: 
- Windows 10 and later

## Update policies

[iOS update policies](software-updates-ios.md) shows you how to create and assign iOS policies to install software updates on your iOS devices. You can also review the installation status.

For update policies on Windows devices, see [Delivery optimization](delivery-optimization-windows.md). 

This feature supports:
- iOS

## Certificates

[Certificates](certificates-configure.md) configures trusted, SCEP, and PKCS certificates that are assigned to devices, and used to authenticate WiFi, VPN, and email profiles.

This feature supports: 

- Android
- iOS
- Windows Phone 8.1
- Windows 8.1
- Windows 10 and later

## Windows Information Protection profile

[Windows Information Protection](windows-information-protection-configure.md) helps protect against data leakage without interfering with the employee experience. It also helps protect enterprise apps and data against accidental data leaks on enterprise-owned devices and personal devices that employees use at work. Using Windows Information Protection doesn't require changes to your environment or other apps.

This feature supports:

- Windows 10 and later

## Shared multi-user device

[Windows 10](shared-user-device-settings-windows.md) and [Windows Holographic for Business](shared-user-device-settings-windows-holographic.md) includes settings to manage devices with multiple users, also known as shared devices or shared PCs. When a user signs in to the device, you choose if the user can change the sleep options, or save files on the device. In another example, you can create a profile that deletes inactive credentials from Windows HoloLens devices to save space.

These shared multi-user device settings allow an administrator to control some of the device features, and manage these shared devices using Intune.

This feature supports:

- Windows 10 and later
- Windows Holographic for Business

## Mobility Extensions

[Mobile extensions (MX)](android-zebra-mx-overview.md) allows administrators to use and manage Zebra devices in Intune. You create StageNow profiles with your settings, and then use Intune to assign or deploy these profiles to your Zebra devices. The [StageNow logs and common issues](android-zebra-mx-logs-troubleshoot.md) is a great resource to troubleshoot profiles, and see some potential issues when using StageNow.

This feature supports:

- Android

## Custom profile

[Custom settings](custom-settings-configure.md) lets administrators assign device settings that aren't built-into Intune. For example, on Android devices, you can enter OMA-URI values. For iOS devices, you can import a configuration file you created in the Apple Configurator. 

This feature supports:

- Android
- iOS
- macOS
- Windows Phone 8.1

## Manage and troubleshoot

[Manage your profiles](device-profile-monitor.md) to check the status of devices, and the profiles assigned. Also help resolve conflicts by seeing the settings that cause a conflict, and the profiles that contains these settings. [Common issues and resolutions](device-profile-troubleshoot.md) provides a Q&A to help work with profiles, including what happens when a profile is deleted, what causes notifications to be sent to devices, and more.

## Next steps

Choose your platform, and get started.