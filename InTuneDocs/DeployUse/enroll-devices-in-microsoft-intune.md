---
# required metadata

title: Enroll devices | Microsoft Intune
description: Mobile device management (MDM) uses enrollment to bring devices into management and allow access to resources.
keywords:
author: NathBarn
manager: arob98
ms.date: 07/18/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8fc415f7-0053-4aa5-8d2b-03202eca4b87

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: damionw
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Enroll devices for management in Intune
Microsoft Intune mobile device management (MDM) uses enrollment to bring devices into management and allow access to resources. The way you'll enroll devices depends on the device type, ownership, and the level of management needed. "Bring your own device" (BYOD) and company-owned device (COD) scenarios require an enrollment process. Organizations using Exchange ActiveSync, either on-premises or hosted in the cloud, can enable lighter management without enrollment requirements. Windows PCs can also be managed using Intune client software.

###  Supported device platforms

Intune can manage the following device platforms:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

## Overview of device enrollment methods

The following table shows enrollment methods for corporate-owned device enrollment methods with their benefits.

**iOS Enrollment Methods**

| **Method** |	**[Wipe](#Wipe)** |	**[Affinity](#Affinity)**	|	**[Locked](#Lock)** |
|:---:|:---:|:---:|:---:|
|**[BYOD](#BYOD)** | No|	Yes |	No |
|**[DEM](#DEM)**|	No |No |No	|
|**[DEP](#DEP)**|	Yes |	Opt |	Opt|
|**[USB-SA](#USB-SA)**|	Yes |	Opt |	No|
|**[USB-Direct](#USB-Direct)**|	No |	No	| No|

**Windows and Android Enrollment Methods**

| **Method** |	**[Wipe](#Wipe)** |	**[Affinity](#Affinity)**	|	**[Locked](#Lock)** |
|:---:|:---:|:---:|:---:|
|**[BYOD](#BYOD)** | No|	Yes |	No |
|**[DEM](#DEM)**|	No |No |No	|

**Enrollment methods for corporate-owned devices**

### BYOD
“Bring Your Own Device.” Users install the Company Portal app and enroll their device. Enrolling a device with the Company Portal will work place join the device. Enrolling iOS devices with the Company Portal requires an Apple ID. BYOD does not require additional configuration for corporate-owned devises. See steps to [set up device management](get-ready-to-enroll-devices-in-microsoft-intune.md#set-up-device-management). ([Back to the table](#overview-of-device-enrollment-methods))

### DEM
Device enrollment manager. Admin creates DEM accounts to manage corporate-owned devices. Managers can then install the Company Portal and enroll many user-less devices. Learn more about [DEM](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md). ([Back to the table](#overview-of-device-enrollment-methods))

### DEP
Apple Device Enrollment Program. Admin creates and deploys policy “over the air” to corporate-owned iOS devices purchased and managed with DEP. The device is enrolled when the user runs the iOS Setup Assistant. This method supports **iOS Supervised** mode which in turn enables:
  -	Locked enrollment
  -	Conditional access
  -	Jailbreak detection
  -	Mobile application management

Learn more about [DEP](ios-device-enrollment-program-in-microsoft-intune.md). ([Back to the table](#overview-of-device-enrollment-methods))

### USB-SA
USB-connected, Setup Assistant enrollment. The admin creates an Intune policy and exports it to Apple Configurator. USB-connected, corporate-owned devices are prepared with Intune policy. The admin must enroll each device by hand. Users receive their devices and run Setup Assistant, enrolling their device. This method supports **iOS Supervised** mode which in turn enables:
  -	Conditional access
  -	Jailbreak detection
  -	Mobile application management

Learn more about [Setup Assistant enrollment with Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md). ([Back to the table](#overview-of-device-enrollment-methods))

### USB-Direct
Direct enrollment. The admin creates an Intune policy and exports it to Apple Configurator. USB-connected, corporate-owned devices are enrolled directly without requiring a factory reset. The admin must enroll each device by hand. Devices are managed as user-less devices. They are not locked or supervised and cannot support conditional access, jailbreak detection, mobile application management. Learn more about [direct enrollment with Apple Configurator](ios-direct-enrollment-in-microsoft-intune.md). ([Back to the table](#overview-of-device-enrollment-methods))

**Behavior for corporate-owned mobile devices**

### Wipe
Specifies whether enrolling the device requires that the device be factory reset, removing all data from the device and returning it to its original state.
[Retire devices](retire-devices-from-microsoft-intune-management.md) ([Back to the table](#overview-of-device-enrollment-methods))

### Affinity
Specifies whether the enrollment method supports “User Affinity” which connects a device with a specific user. “Opt” devices can be enrolled with or without user affinity. User affinity is required to support the following:
  - Mobile application management (MAM) apps
  -	Conditional access to email and company data
  -	Company Portal app

[User Affinity](enroll-corporate-owned-ios-devices-in-microsoft-intune.md#enrollment-of-company-owned-ios-devices-with-user-affinity) ([Back to the table](#overview-of-device-enrollment-methods))

### Lock
Specifies whether the device can be locked to prevent the user from removing the Intune policy, effectively removing the device from management. For iOS devices, locking the device requires that it be in Supervised mode.
([Back to the table](#overview-of-device-enrollment-methods))

## Enable device enrollment  
 Enrollment lets users access company resources on their personal devices and lets the admin ensure those devices comply with policies that protect company resources. This is the best way to enable "bring your own device" scenarios with Intune. The admin must enable enrollment in the Intune console, which might require creating a trust relationship with the device and assigning licenses to users. The device is then enrolled, usually by users entering their work or school credentials. The device then receives policy from Intune and gains access to resources.

[Get ready to enroll devices in Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)

## Enroll corporate-owned devices
Corporate-owned devices (COD) can be managed with the Intune console. iOS devices can be enrolled directly through tools provided by Apple. All device types can be enrolled by an admin or manager using the device enrollment manager. Devices with an IMEI number can also be identified and tagged as company-owned to enable COD scenarios.

[Enroll corporate-owned devices](manage-corporate-owned-devices.md)

## Mobile device management with Exchange ActiveSync and Intune
Mobile devices that aren't enrolled but that connect to Exchange ActiveSync (EAS) can be managed by Intune using EAS MDM policy. Intune uses an Exchange Connector to communicate with EAS, either on-premises and cloud-hosted.

[Mobile device management with Exchange ActiveSync and Intune](mobile-device-management-with-exchange-activesync-and-microsoft-intune.md)


## Manage Windows PCs with Intune  
You can also use Microsoft Intune to manage Windows PCs using the Intune Windows PC client software. PCs managed with the Intune client can:

 - Report software and hardware inventories
 - Install desktop applications (for example .exe and .msi files)
 - Firewall settings

Computers managed with the Intune client software cannot be selectively wiped or retired, and cannot take advantage of many Intune management features such as conditional access, VPN and Wi-Fi settings, or deployment of certificates and email configurations.

[Manage Windows PCs with Intune](manage-windows-pcs-with-microsoft-intune.md)
