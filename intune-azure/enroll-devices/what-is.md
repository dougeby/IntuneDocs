---
# required metadata

title: What is Microsoft Intune device enrollment | Intune Azure preview | Microsoft Docs
description: "Intune Azure preview: Learn about enrollment for iOS, Android, and Windows devices."
keywords:
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# What is Microsoft Intune device enrollment

You can enroll devices, including Windows PCs, to enable mobile device management (MDM) with Microsoft Intune. This topic describes different ways to enroll mobile devices in Intune management. The way you enroll your devices depends on the device type, ownership, and the level of management that's needed. "Bring your own device" (BYOD) enrollment lets users enroll their personal phones, tablets, or PCs. Corporate-owned device (COD) enrollment enables management scenarios like remote wipe, shared devices, or user affinity for a device.

If you use Exchange ActiveSync, either on-premises or hosted in the cloud, you can enable simple Intune management without enrollment. More information is coming soon. Windows PCs can also be managed using [Intune client software](https://docs.microsoft.com/intune/deploy-use/manage-windows-pcs-with-microsoft-intune).

- **Wipe** - Indicates whether the device needs to be wiped before users can enroll the device. The term "wipe" means a factory reset of the device, which removes all data. For more information, see [Use full or selective wipe on devices](./manage-devices/use-full-or-selective-wipe-on-devices-using-microsoft-intune).
- **Affinity** - Associates devices with users. Required for mobile application management (MAM) and conditional access to company data. For more information, see [User affinity](enroll-ios-device-enrollment-program-devices.md).
- **Lock** - Prevents users from removing the device from management. iOS devices require Supervised mode for Lock. 


## Overview of device enrollment methods

The following table shows Intune enrollment methods and the supported capabilities and requirements of each method. The capabilities and requirements are described below.


**iOS enrollment methods**

| **Method** |	**Wipe required?** |	**Affinity**	|	**Lock** | **Details** |
|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | No|	Yes |	No | More information coming soon|
|**[DEM](#dem)**|	No |No |No	| [More information](enroll-devices-using-device-enrollment-manager.md)|
|**[DEP](#dep)**|	Yes |	Optional |	Optional|[More information](enroll-ios-device-enrollment-program-devices.md)|
|**[USB-SA](#usb-sa)**|	Yes |	Optional |	No| [More information](enroll-ios-devices-with-apple-configurator-using-setup-assistant.md)|
|**[USB-Direct](#usb-direct)**|	No |	No	| No|[More information](enroll-ios-devices-with-apple-configurator-using-setup-assistant.md)|



**Windows enrollment methods**

| **Method** |	**Wipe required?** |	**Affinity**	|	**Lock** | **Details**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Yes|	Yes |	No | More information coming soon|
|**[DEM](#dem)**|	No |No |No	|[More information](enroll-devices-using-device-enrollment-manager.md)|

**Android enrollment methods**

| **Method** |	**Wipe required?** |	**Affinity**	|	**Lock** | **Details**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | No|	Yes |	No | [More information coming soon|
|**[DEM](#dem)**|	No |No |No	|[More information coming soon]|


## BYOD
"Bring your own device" users install the Company Portal app and enroll their device. This enables users to connect to the company network and join the domain or Azure Active Directory. For most platforms, you have to enable BYOD enrollment for many COD scenarios.

## Corporate-owned devices
Corporate-owned devices (COD) can be managed by using the Intune console. iOS devices can be enrolled directly through the tools that are provided by Apple. All device types can be enrolled by an admin or manager using the device enrollment manager. Devices with an IMEI number can also be identified and tagged as company-owned to enable COD scenarios.

### DEM
Device enrollment manager is a special Intune account that's used to enroll and manage multiple corporate-owned devices. Managers can install the Company Portal and enroll many user-less devices. Learn more about [DEM](enroll-devices-using-device-enrollment-manager.md). ([Go back to the table](#overview-of-device-enrollment-methods))

### DEP
Apple Device Enrollment Program (DEP) management lets you create and deploy policy “over the air” to iOS devices that are purchased and managed with DEP. The device is enrolled when users turn on the device for the first time and run iOS Setup Assistant. This method supports **iOS Supervised** mode, which in turn enables:
  -	Locked enrollment
  -	Conditional access
  -	Jailbreak detection
  -	Mobile application management

Learn more about [DEP](enroll-ios-device-enrollment-program-devices.md). ([Go back to the table](#overview-of-device-enrollment-methods))

### USB-SA
USB-connected, corporate-owned devices are prepared with Intune policy. For Setup Assistant enrollment, the admin creates this Intune policy and exports it to Apple Configurator. The admin must enroll each device manually. Users receive their devices and run Setup Assistant, enrolling their device. This method supports **iOS Supervised** mode, which in turn enables:
  -	Conditional access
  -	Jailbreak detection
  -	Mobile application management

Learn more about [Setup Assistant enrollment with Apple Configurator](enroll-ios-devices-with-apple-configurator-using-setup-assistant.md). ([Go back to the table](#overview-of-device-enrollment-methods))

### USB-Direct
For direct enrollment, the admin creates an Intune policy and exports it to Apple Configurator. USB-connected, corporate-owned devices are enrolled directly and don't require a factory reset. The admin must enroll each device manually. Devices are managed as user-less devices. They are not locked or supervised and cannot support conditional access, jailbreak detection, or mobile application management. ([Go back to the table](#overview-of-device-enrollment-methods))

## Mobile device management with Exchange ActiveSync and Intune
Mobile devices that aren't enrolled but that connect to Exchange ActiveSync (EAS) can be managed by Intune using EAS MDM policy. Intune uses an Exchange Connector to communicate with EAS, either on-premises or cloud-hosted. More information is coming soon.


## Windows PC management with Intune  
You can also use Microsoft Intune to manage Windows PCs with the Intune client software. PCs that are managed with the Intune client can:

 - Report software and hardware inventories
 - Install desktop applications (for example .exe and .msi files)
 - Manage firewall settings

PCs that are managed with the Intune client software cannot be fully wiped, although selective wipe is available. PCs managed with the Intune software client cannot take advantage of many Intune management features such as conditional access, VPN and Wi-Fi settings, or deployment of certificates and email configurations. More information is coming soon.


## Supported device platforms and browsers

See [Supported devices and browsers for Intune](https://docs.microsoft.com/intune/get-started/supported-mobile-devices-and-computers)
