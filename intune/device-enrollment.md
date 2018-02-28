---
# required metadata

title: What is Microsoft Intune device enrollment
titlesuffix: "Azure portal"
description: Learn about enrollment for iOS, Android, and Windows devices.
keywords:
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/29/2017
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

Intune lets you manage your workforce’s devices and apps and how they access your company data. To use this mobile device management (MDM), the devices must first be enrolled in the Intune service. When a device is enrolled, it is issued an MDM certificate. This certificate is used to communicate with the Intune service.

As you can see in the following tables, there are several methods to enroll your workforce’s devices. Each method depends on the device's ownership (personal or corporate), device type (iOS, Windows, Android), and management requirements (resets, affinity, locking).

## iOS enrollment methods

| **Method** |	**Reset Required** |	[**User Affinity**](device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile)	|	**Locked** | **Details** |
|:---:|:---:|:---:|:---:|:---:|
| |	Devices are factory reset during enrollment. |	Associates each device with a user.| Users can’t unenroll devices.	| |
|**[BYOD](#bring-your-own-device)** | No|	Yes |	No | [More information](./apple-mdm-push-certificate-get.md)|
|**[DEM](#device-enrollment-manager)**|	No |No |No	| [More information](./device-enrollment-program-enroll-ios.md)|
|**[DEP](#apple-device-enrollment-program)**|	Yes |	Optional |	Optional|[More information](./device-enrollment-program-enroll-ios.md)|
|**[USB-SA](#usb-sa)**|	Yes |	Optional |	No| [More information](./apple-configurator-setup-assistant-enroll-ios.md)|
|**[USB-Direct](#usb-direct)**|	No |	No	| No|[More information](./apple-configurator-direct-enroll-ios.md)|

## macOS enrollment methods

| **Method** |  **Reset Required** |  **User Affinity** | **Locked** | **Details**|
|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#bring-your-own-device)** | No| Yes | No | [More information](./macos-enroll.md)|
|**[DEM](#device-enrollment-manager)**| No |No |No  | [More information](./device-enrollment-manager-enroll.md)|


## Windows enrollment methods

| **Method** |	**Reset Required** |	**User Affinity**	|	**Locked** | **Details**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#bring-your-own-device)** | No |	Yes |	No | [More information](windows-enroll.md)|
|**[DEM](#device-enrollment-manager)**|	No |No |No	|[More information](device-enrollment-manager-enroll.md)|
|**Auto-enroll** | No |Yes |No | [More information](./windows-enroll.md#enable-windows-10-automatic-enrollment)|
|**Bulk enroll** |No |No |No | [More information](./windows-bulk-enroll.md) |

## Android enrollment methods

| **Method** |	**Reset Required** |	**User Affinity**	|	**Locked** | **Details**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#bring-your-own-device)** | No|	Yes |	No | [More information](./android-enroll.md)|
|**[DEM](#device-enrollment-manager)**|	No |No |No	|[More information](./device-enrollment-manager-enroll.md)|
|**Android for Work**| No | Yes | No| [More information](./android-enroll.md#enable-enrollment-of-android-for-work-devices) |


## Bring your own device
Bring your own devices (BYOD) include personal phones, tables, and PCs. Users install and run the Company Portal app to enroll BYODs. This program lets users access company resources like email.

## Corporate-owned device
Corporate-owned devices (COD) include phones, tablets, and PCs owned by the organization and distributed to the workforce. COD enrollment supports scenarios like automatic enrollment, shared devices, or pre-authorized enrollment requirements. A common way to enroll CODs is for an administrator or manager to use the device enrollment manager (DEM). iOS devices can be enrolled directly through the Device Enrollment Program (DEP) tools that are provided by Apple. Devices with an IMEI number can also be identified and tagged as company-owned.

### Device enrollment manager
Device enrollment manager (DEM) is a special user account that's used to enroll and manage multiple corporate-owned devices. Managers can install the Company Portal and enroll many user-less devices. Learn more about [DEM](./device-enrollment-manager-enroll.md).

### Apple Device Enrollment Program
Apple Device Enrollment Program (DEP) management lets you create and deploy policy “over the air” to iOS devices that are purchased and managed with DEP. The device is enrolled when users turn on the device for the first time and run iOS Setup Assistant. This method supports iOS supervised mode, which enables a device to be configured with specific functionality.

Learn more about iOS DEP enrollment:

- [Choose how to enroll iOS devices](ios-enroll.md)
- [Enroll iOS devices using Device Enrollment Program](https://docs.microsoft.com/intune/device-restrictions-ios#device-enrollment-program)

### USB-SA
IT admins use Apple Configurator, through USB, to prepare each corporate-owned device manually for enrollment using Setup Assistant. The IT admin creates an enrollment profile and exports it to Apple Configurator. When users receive their devices, they are then prompted to run Setup Assistant to enroll their device. This method supports **iOS supervised** mode, which in turn enables the following features:
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

The MDM certificate is renewed automatically when mobile devices are communicating with the Intune service. If mobile devices are wiped, or they fail to communicate with the Intune service for some period of time, the MDM certificate is not renewed. The device is removed from the Azure portal 180 days after the MDM certificate expires.
