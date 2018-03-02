---
# required metadata

title: Device profiles in Microsoft Intune - Azure | Microsoft Docs
description: Overview of the different Microsoft Intune device profiles, including features, restrictions, email, wifi, VPN, education, certificates, upgrade Windows 10, BitLocker and Windows defender, Windows Information Protection, and custom device configuration settings in the Azure portal. Use these profile to manage and protect data and devices in your company.
keywords:
author: MandiOhlinger

ms.author: mandia
manager: dougeby
ms.date: 03/01/2018
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# What are Microsoft Intune device profiles?

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Microsoft Intune includes settings and features that you can enable or disable on different devices within your organization. These settings and features are managed using profiles. Some profile examples include: 

- A WiFi profile that gives different devices access to your corporate WiFi
- A VPN profile that gives different devices access to your VPN server within your corporate network

This topic provides an overview of the different profiles you can create for your devices. Use these profiles to allow and or prevent some features on the devices.

## Before you begin
To see the available features, open the [Azure portal](https://portal.azure.com), and open your Intune resource. 

**Device configuration** includes the following options:

- **Overview**: Lists the status of your profiles, and provides additional details on the profiles you assigned to users and devices
- **Manage**: Create device profiles, and upload custom [PowerShell scripts](intune-management-extension.md) to run within the profile
- **Monitor**: Check the status of a profile for success or failure, and also view logs on your profiles
- **Setup**: Add a certificate authority (SCEP or PFX), or enable Telecom Expense Management to the profile

## Create the profile

[Create device profiles](device-profile-create.md) provides step-by-step guidance to create a profile. 

## Device features profile

[Device features](device-features-configure.md) controls features on iOS and macOS devices, such as AirPrint, notifications, and shared device configurations.

This feature supports:  
- iOS 
- macOS

## Device restrictions profile
[Device restrictions](device-restrictions-configure.md) controls security, hardware, data sharing, and more settings on the devices. For example, create a device restriction profile that prevents iOS device users from using the device camera. 

This feature supports: 

- Android
- iOS
- macOS
- Windows 10
- Windows 10 Team

## Email profile
[Email settings](email-settings-configure.md) profile creates, assigns, and monitors Exchange ActiveSync email settings on the devices. Email profiles help ensure consistency, reduce support calls, and let end-users access company email on their personal devices, without any required setup on their part. 

This feature supports: 

- Android
- iOS
- Windows Phone 8.1
- Windows 10

## Wi-Fi profile
[Wi-Fi settings](wi-fi-settings-configure.md) assigns wireless network settings to users and devices. When you assign a WiFi profile, users get access to your corporate WiFi without having to configure it themselves. 

This feature supports: 

- Android
- iOS
- macOS
- Windows 8.1 (import only)

## VPN profile
[VPN settings](vpn-settings-configure.md) assigns VPN profiles to users and devices in your organization, so they can easily and securely connect to the network. 

Virtual private networks (VPNs) give users secure remote access to your company network. Devices use a VPN connection profile to initiate a connection with the VPN server. 

This feature supports: 

- Android
- iOS
- macOS
- Windows Phone 8.1
- Windows 8.1
- Windows 10

## Education profile
[Education settings](education-settings-configure.md) configure options for the [Windows Take a Test app](https://education.microsoft.com/gettrained/win10takeatest). When you configure these options, no other apps can run on the device until the test is complete.

## Certificates profile
[Certificates](certificates-configure.md) configures trusted, SCEP, and PKCS certificates that can be assigned to devices, and used to authenticate WiFi, VPN, and email profiles.

This feature supports: 

- Android
- iOS
- Windows Phone 8.1
- Windows 8.1
- Windows 10

## Edition upgrade profile
[Windows 10 edition upgrades](edition-upgrade-configure-windows-10.md) automatically upgrades devices that run some versions of Windows 10 to a newer edition.

This feature supports: Windows 10 only

## Endpoint protection profile
[Endpoint protection settings for Windows 10](endpoint-protection-windows-10.md) configures BitLocker and Windows Defender settings for Windows 10 devices.

This feature supports: Windows 10 only

## Windows Information Protection profile
[Windows Information Protection](windows-information-protection-configure.md) helps protect against data leakage without interfering with the employee experience. It also helps to protect enterprise apps and data against accidental data leaks on enterprise-owned devices and personal devices that employees use at work. It does this without requiring changes to your environment or other apps.

This feature supports: Windows 10 only

## Custom profile
[Custom settings](custom-settings-configure.md) includes the ability to assign device settings that are not built-into Intune. For example, on Android devices, you can enter OMA-URI values. For iOS devices, you can import a configuration file you created in the Apple Configurator. 

This feature supports: 

- Android
- iOS
- macOS
- Windows Phone 8.1