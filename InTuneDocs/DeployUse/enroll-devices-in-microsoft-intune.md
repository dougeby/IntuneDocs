---
# required metadata

title: Enroll devices into Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8fc415f7-0053-4aa5-8d2b-03202eca4b87

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Enroll devices for management in Intune
Microsoft Intune mobile device management (MDM) uses enrollment to bring devices into management and allow access to resources. The way you'll enroll devices depends on the device type, ownership, and the level of management needed. "Bring your own device" (BYOD) and company-owned device (COD) scenarios require an enrollment process. Organizations using Exchange ActiveSync, either on-premises or hosted in the cloud, can enable lighter management without enrollment requirements. Windows PCs can also be managed using Intune client software.

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
