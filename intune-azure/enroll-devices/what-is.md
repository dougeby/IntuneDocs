---
# required metadata

title: What is Microsoft Intune device enrollment | Intune Azure preview | Microsoft Docs
description: "Intune Azure preview: Learn about enrollment for iOS, Android, and Windows devices."
keywords:
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 12/30/2016
ms.topic: get-started-article
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

# What is Microsoft Intune device enrollment in Intune Azure preview
[!INCLUDE[azure_preview](../includes/azure_preview.md)]

This topic describes enrollment and lists the different ways to enroll mobile devices in Intune management.

You enroll devices, including Windows PCs, in Intune so that you can manage those devices. We refer to this capability in the Intune documentation as mobile device management (MDM). When devices are enrolled as mobile devices (not as PCs), they are issued an MDM certificate, which the devices then use to communicate with the Intune service. 

The way you enroll your devices depends on the device type, ownership, and the level of management you needed. "Bring your own device" (BYOD) enrollment lets users enroll their personal phones, tablets, or PCs. Corporate-owned device (COD) enrollment enables management scenarios like remote wipe, shared devices, or user affinity for a device.

If you use Exchange ActiveSync, either on-premises or hosted in the cloud, you can enable simple Intune management without enrollment (more information is coming soon). You can manage Windows PCs as mobile devices, which is the recommended method described below. You can also manage them as PCs by using [Intune client software](https://docs.microsoft.com/intune/deploy-use/manage-windows-pcs-with-microsoft-intune).


## Overview of device enrollment methods

The following table shows Intune enrollment methods and the supported capabilities and requirements of each method. The capabilities and requirements are described below. The following terms are used in the table:

- **Wipe** - Indicates whether the device needs to be wiped before users can enroll the device. The term "wipe" means a factory reset of the device, which removes all data. For more information, see [Use full or selective wipe on devices](/intune-azure/manage-devices/use-full-or-selective-wipe-on-devices-using-microsoft-intune).
- **Affinity** - Associates devices with users. Required for mobile application management (MAM) and conditional access to company data. For more information, see [User affinity](enroll-ios-devices-using-device-enrollment-program.md).
- **Lock** - Prevents users from removing the device from management. iOS devices require Supervised mode for Lock.


**iOS enrollment methods**

| **Method** |	**Wipe required?** |	**Affinity**	|	**Lock** | **Details** |
|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | No|	Yes |	No | More information coming soon|
|**[DEM](#dem)**|	No |No |No	| [More information](/intune-azure/enroll-devices/enroll-devices-using-device-enrollment-manager.md)|
|**[DEP](#dep)**|	Yes |	Optional |	Optional|[More information](enroll-ios-devices-using-device-enrollment-program.md)|
|**[USB-SA](#usb-sa)**|	Yes |	Optional |	No| [More information](enroll-ios-devices-with-apple-configurator-and-setup-assistant.md)|
|**[USB-Direct](#usb-direct)**|	No |	No	| No|[More information](enroll-ios-devices-with-apple-configurator-and-direct-enrollment.md)|



**Windows enrollment methods**

| **Method** |	**Wipe required?** |	**Affinity**	|	**Lock** | **Details**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Yes|	Yes |	No | More information coming soon|
|**[DEM](#dem)**|	No |No |No	|[More information](enroll-devices-using-device-enrollment-manager.md)|

**Android enrollment methods**

| **Method** |	**Wipe required?** |	**Affinity**	|	**Lock** | **Details**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | No|	Yes |	No | More information coming soon|
|**[DEM](#dem)**|	No |No |No	|[More information](/enroll-devices-using-device-enrollment-manager.md)|


## BYOD
"Bring your own device" users install the Company Portal app and enroll their device. This enables users to connect to the company network and join the domain or Azure Active Directory. For most platforms, you have to enable BYOD enrollment for many COD scenarios.

## Corporate-owned devices
Corporate-owned devices (COD) can be managed by using the Azure portal. iOS devices can be enrolled directly through the tools that are provided by Apple. All device types can be enrolled by an admin or manager using the device enrollment manager. Devices with an IMEI number can also be identified and tagged as company-owned to enable COD scenarios.

### DEM
Device enrollment manager is a special user account that's used to enroll and manage multiple corporate-owned devices. Managers can install the Company Portal and enroll many user-less devices. Learn more about [DEM](enroll-devices-using-device-enrollment-manager.md). ([Go back to the table](#overview-of-device-enrollment-methods))

### DEP
Apple Device Enrollment Program (DEP) management lets you create and deploy policy “over the air” to iOS devices that are purchased and managed with DEP. The device is enrolled when users turn on the device for the first time and run iOS Setup Assistant. This method supports **iOS Supervised** mode, which in turn enables:

  -	Locked enrollment
  -	Conditional access
  -	Jailbreak detection
  -	Mobile application management

To learn more about iOS enrollment, see:

- [Choose how to enroll iOS devices](choose-ios-enrollment-method.md)
- [Enroll iOS devices using Device Enrollment Program](enroll-ios-devices-using-device-enrollment-program.md). 
- [Go back to the table above](#overview-of-device-enrollment-methods)

### USB-SA
USB-connected, corporate-owned devices are prepared with Intune policy. For Setup Assistant enrollment, the admin creates this Intune policy and exports it to Apple Configurator. The admin must enroll each device manually. Users receive their devices and run Setup Assistant, enrolling their device. This method supports **iOS Supervised** mode, which in turn enables:
  -	Conditional access
  -	Jailbreak detection
  -	Mobile application management

To learn more about iOS enrollment, see:

- [Decide how to enroll iOS devices](choose-ios-enrollment-method.md)
- [Enroll iOS devices with Configurator and Setup Assistant](enroll-ios-devices-with-apple-configurator-and-setup-assistant.md). 

### USB-Direct
For direct enrollment, the admin creates an Intune policy and exports it to Apple Configurator. USB-connected, corporate-owned devices are enrolled directly and don't require a factory reset. The admin must enroll each device manually. Devices are managed as user-less devices. They are not locked or supervised and cannot support conditional access, jailbreak detection, or mobile application management. 

To learn more about iOS enrollment, see:

- [Decide how to enroll iOS devices](choose-ios-enrollment-method.md)
- [Enroll iOS devices with Configurator and direct enrollment](enroll-ios-devices-with-apple-configurator-and-direct-enrollment.md)

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

## Mobile device cleanup after MDM certificate expiration

The MDM certificate is renewed automatically when mobile devices are communicating with the Intune service. If mobile devices (not PCs) are wiped, or they fail to communicate with the Intune service for some period of time, the MDM certificate will not get renewed. The device is removed from the Azure portal 180 days after the MDM certificate expires.
