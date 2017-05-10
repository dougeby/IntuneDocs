---
# required metadata

title: What is Microsoft Intune device enrollmenttitleSuffix: "Intune Azure preview"
description: "Intune Azure preview: Learn about enrollment for iOS, Android, and Windows devices."
keywords:
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# What is device enrollment?
[!INCLUDE[azure_preview](./includes/azure_preview.md)]

This topic describes enrollment and lists the different ways to enroll mobile devices in Intune management.

You enroll devices in Intune so that you can manage those devices. We refer to this capability in the Intune documentation as mobile device management (MDM). When devices are enrolled in Intune, they are issued an MDM certificate, which the devices then use to communicate with the Intune service.

The way you enroll your devices depends on the device type, ownership, and the level of management you needed. "Bring your own device" (BYOD) enrollment lets users enroll their personal phones, tablets, or PCs. Corporate-owned device (COD) enrollment enables management scenarios like automatic enrollment, shared devices, or pre-authorized enrollment requirements.

If you use Exchange ActiveSync, either on-premises or hosted in the cloud, you can enable simple Intune management without enrollment (more information is coming soon). You can manage Windows PCs as mobile devices, which is the recommended method described below.


## Overview of device enrollment methods

The following table shows Intune enrollment methods and the supported capabilities and requirements of each method. The capabilities and requirements are described below. The following terms are used in the table:

- **Wipe** - Indicates whether the device needs to be wiped before users can enroll the device. The term "wipe" means a factory reset of the device, which removes all data. For more information, see [Use full or selective wipe on devices](devices-wipe.md).
- **Affinity** - Associates devices with users. Required for mobile application management (MAM) and conditional access to company data. For more information, see [User affinity](device-enrollment-program-enroll-ios.md).
- **Lock** - Indicates if users are prevented from unenrolling their devices from management. Users can unenroll their devices on all platforms by using their Company Portal app. They cannot use the native operating system menus to unenroll.


**iOS enrollment methods**

| **Method** |	**Wipe required?** |	**Affinity**	|	**Lock** | **Details** |
|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | No|	Yes |	No | More information coming soon|
|**[DEM](#dem)**|	No |No |No	| [More information](device-enrollment-program-enroll-ios.md)|
|**[DEP](#dep)**|	Yes |	Optional |	Optional|[More information](device-enrollment-program-enroll-ios.md)|
|**[USB-SA](#usb-sa)**|	Yes |	Optional |	No| [More information](apple-configurator-setup-assistant-enroll-ios.md)|
|**[USB-Direct](#usb-direct)**|	No |	No	| No|[More information](apple-configurator-direct-enroll-ios.md)|

**Windows enrollment methods**

| **Method** |	**Wipe required?** |	**Affinity**	|	**Lock** | **Details**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | No |	Yes |	No | [More information](#windows-enroll.md)|
|**[DEM](#dem)**|	No |No |No	|[More information](device-enrollment-manager-enroll.md)|

**Android enrollment methods**

| **Method** |	**Wipe required?** |	**Affinity**	|	**Lock** | **Details**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | No|	Yes |	No | [More information](android-enroll.md)|
|**[DEM](#dem)**|	No |No |No	|[More information](device-enrollment-program-enroll-ios.md)|
|[**Android for Work**](#android-for-work)| No | Yes | No| [More information](android-enroll.md) |


## BYOD
"Bring your own device" users install the Company Portal app and enroll their device. This enables users to connect to the company network and join the domain or Azure Active Directory. For most platforms, you have to enable BYOD enrollment for many COD scenarios. You can block enrollment of personally owned iOS and Android devices. See [Set device type restrictions](enrollment-restrictions-set.md#set-device-type-restrictions) for instructions.

## Corporate-owned devices
Corporate-owned devices (COD) can be managed by using the Azure portal. iOS devices can be enrolled directly through the tools that are provided by Apple. All device types can be enrolled by an admin or manager using the device enrollment manager. Devices with an IMEI number can also be identified and tagged as company-owned to enable COD scenarios.

### DEM
Device enrollment manager (DEM) is a special user account that's used to enroll and manage multiple corporate-owned devices. Managers can install the Company Portal and enroll many user-less devices. Learn more about [DEM](device-enrollment-manager-enroll.md). ([Go back to the table](#overview-of-device-enrollment-methods))

### DEP
Apple Device Enrollment Program (DEP) management lets you create and deploy policy “over the air” to iOS devices that are purchased and managed with DEP. The device is enrolled when users turn on the device for the first time and run iOS Setup Assistant. This method supports **iOS Supervised** mode, which in turn enables:

  -	Locked enrollment
  -	Kiosk mode and other advanced configurations and restrictions

To learn more about iOS enrollment, see:

- [Choose how to enroll iOS devices](enrollment-method-choose-ios.md)
- [Enroll iOS devices using Device Enrollment Program](device-enrollment-program-enroll-ios.md)
- [Go back to the table above](#overview-of-device-enrollment-methods)

### USB-SA
IT admins use Apple Configurator, via USB, to prepare each corporate-owned device manually for enrollment using Setup Assistant. The IT admin creates an enrollment profile and exports it to Apple Configurator. When users receive their devices, they are then prompted to run Setup Assistant to enroll their device. This method supports **iOS Supervised** mode, which in turn enables:
  -	Locked enrollment
  -	Kiosk mode and other advanced configurations and restrictions

To learn more about iOS enrollment, see:

- [Decide how to enroll iOS devices](enrollment-method-choose-ios.md)
- [Enroll iOS devices with Configurator and Setup Assistant](apple-configurator-setup-assistant-enroll-ios.md)

### USB-Direct
For direct enrollment, the admin must enroll each device manually by creating an enrollment policy and exporting it to Apple Configurator. USB-connected, corporate-owned devices are enrolled directly and don't require a factory reset. Devices are managed as user-less devices. They are not locked or supervised and cannot support conditional access, jailbreak detection, or mobile application management.

To learn more about iOS enrollment, see:

- [Decide how to enroll iOS devices](enrollment-method-choose-ios.md)
- [Enroll iOS devices with Configurator and direct enrollment](apple-configurator-direct-enroll-ios.md)

## Mobile device management with Exchange ActiveSync and Intune
Mobile devices that aren't enrolled but that connect to Exchange ActiveSync (EAS) can be managed by Intune using EAS MDM policy. Intune uses an Exchange Connector to communicate with EAS, either on-premises or cloud-hosted. More information is coming soon.

## Supported device platforms and browsers

See [Supported devices and browsers for Intune](https://docs.microsoft.com/intune-classic/get-started/supported-mobile-devices-and-computers)

## Mobile device cleanup after MDM certificate expiration

The MDM certificate is renewed automatically when mobile devices are communicating with the Intune service. If mobile devices are wiped, or they fail to communicate with the Intune service for some period of time, the MDM certificate will not get renewed. The device is removed from the Azure portal 180 days after the MDM certificate expires.
