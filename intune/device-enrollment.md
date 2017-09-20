---
# required metadata

title: What is Microsoft Intune device enrollment
titlesuffix: "Azure portal"
description: Learn about enrollment for iOS, Android, and Windows devices."
keywords:
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 05/29/2017
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
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

This topic describes enrollment and lists the different ways to enroll mobile devices in Intune management.

You enroll devices in Intune so that you can manage those devices. We refer to this capability in the Intune documentation as mobile device management (MDM). When devices are enrolled in Intune, they are issued an MDM certificate, which the devices then use to communicate with the Intune service.

The way you enroll your devices depends on the device type, ownership, and the level of management you needed. "Bring your own device" (BYOD) enrollment lets users enroll their personal phones, tablets, or PCs. Corporate-owned device (COD) enrollment enables management scenarios like automatic enrollment, shared devices, or pre-authorized enrollment requirements.

If you use Exchange ActiveSync, either on-premises or hosted in the cloud, you can enable simple Intune management without enrollment (more information is coming soon). You can manage Windows PCs as mobile devices, which is the recommended method described below.


## Overview of device enrollment methods

The following table offers an overview of Intune enrollment methods with their capabilities and requirements described below.
**Legend**

- **Reset required** - Device are factory reset during enrollment.
- **User Affinity** - Associates devices with users. For more information, see [User affinity](device-enrollment-program-enroll-ios.md).
- **Locked** - Prevents users from unenrolling devices.

**iOS enrollment methods**

| **Method** |	**Reset Required** |	**User Affinity**	|	**Locked** | **Details** |
|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | No|	Yes |	No | [More information](./apple-mdm-push-certificate-get.md)|
|**[DEM](#dem)**|	No |No |No	| [More information](./device-enrollment-program-enroll-ios.md)|
|**[DEP](#dep)**|	Yes |	Optional |	Optional|[More information](./device-enrollment-program-enroll-ios.md)|
|**[USB-SA](#usb-sa)**|	Yes |	Optional |	No| [More information](./apple-configurator-setup-assistant-enroll-ios.md)|
|**[USB-Direct](#usb-direct)**|	No |	No	| No|[More information](./apple-configurator-direct-enroll-ios.md)|

**Windows enrollment methods**

| **Method** |	**Reset Required** |	**User Affinity**	|	**Locked** | **Details**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | No |	Yes |	No | [More information](windows-enroll.md)|
|**[DEM](#dem)**|	No |No |No	|[More information](device-enrollment-manager-enroll.md)|
|**Auto-enroll** | No |Yes |No | [More information](./windows-enroll.md#enable-windows-10-automatic-enrollment)|
|**Bulk enroll** |No |No |No | [More information](./windows-bulk-enroll.md) |

**Android enrollment methods**

| **Method** |	**Reset Required** |	**User Affinity**	|	**Locked** | **Details**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | No|	Yes |	No | [More information](./android-enroll.md)|
|**[DEM](#dem)**|	No |No |No	|[More information](./device-enrollment-program-enroll-ios.md)|
|**Android for Work**| No | Yes | No| [More information](./android-enroll.md#enable-enrollment-of-android-for-work-devices) |


## BYOD
"Bring your own device" users install and run the Company Portal app to enroll their devices. This program lets users access company resources like email.

## Corporate-owned devices
The following are corporate-owned devices (COD) enrollment scenarios. iOS devices can be enrolled directly through the tools that are provided by Apple. All device types can be enrolled by an admin or manager using the device enrollment manager. Devices with an IMEI number can also be identified and tagged as company-owned to enable COD scenarios.

### DEM
Device enrollment manager (DEM) is a special user account that's used to enroll and manage multiple corporate-owned devices. Managers can install the Company Portal and enroll many user-less devices. Learn more about [DEM](./device-enrollment-manager-enroll.md).

### DEP
Apple Device Enrollment Program (DEP) management lets you create and deploy policy “over the air” to iOS devices that are purchased and managed with DEP. The device is enrolled when users turn on the device for the first time and run iOS Setup Assistant. This method supports **iOS Supervised** mode, which in turn enables the following functionality:

  -	Locked enrollment
  -	Kiosk mode and other advanced configurations and restrictions

Learn more about iOS DEP enrollment:

- [Choose how to enroll iOS devices](enrollment-method-choose-ios.md)
- [Enroll iOS devices using Device Enrollment Program](device-enrollment-program-enroll-ios.md)

### USB-SA
IT admins use Apple Configurator, through USB, to prepare each corporate-owned device manually for enrollment using Setup Assistant. The IT admin creates an enrollment profile and exports it to Apple Configurator. When users receive their devices, they are then prompted to run Setup Assistant to enroll their device. This method supports **iOS Supervised** mode, which in turn enables the following features:
  -	Locked enrollment
  -	Kiosk mode and other advanced configurations and restrictions

Learn more about iOS Apple Configurator enrollment with Setup Assistant:

- [Decide how to enroll iOS devices](enrollment-method-choose-ios.md)
- [Enroll iOS devices with Configurator and Setup Assistant](apple-configurator-setup-assistant-enroll-ios.md)

### USB-Direct
For direct enrollment, the admin must enroll each device manually by creating an enrollment policy and exporting it to Apple Configurator. USB-connected, corporate-owned devices are enrolled directly and don't require a factory reset. Devices are managed as user-less devices. They are not locked or supervised and cannot support conditional access, jailbreak detection, or mobile application management.

To learn more about iOS enrollment, see:

- [Decide how to enroll iOS devices](enrollment-method-choose-ios.md)
- [Enroll iOS devices with Configurator and direct enrollment](apple-configurator-direct-enroll-ios.md)

## Mobile device management with Exchange ActiveSync and Intune
Mobile devices that aren't enrolled, but that connect to Exchange ActiveSync (EAS), can be managed by Intune using EAS MDM policy. Intune uses an Exchange Connector to communicate with EAS, either on-premises or cloud-hosted. More information is coming soon.

## Mobile device cleanup after MDM certificate expiration

The MDM certificate is renewed automatically when mobile devices are communicating with the Intune service. If mobile devices are wiped, or they fail to communicate with the Intune service for some period of time, the MDM certificate will not get renewed. The device is removed from the Azure portal 180 days after the MDM certificate expires.
