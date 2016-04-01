---
title: Enroll devices into Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid:
author: NathBarn
---
# Enroll devices for management in Intune
Microsoft Intune mobile device management can manage devices and provide access to resources. The way you'll manage devices depends on the device type, ownership, and the level of management needed. "Bring your own device" (BYOD) and company-owned device (COD) scenarios require an enrollment process. Organizations using Exchange ActiveSync, either on-premises or hosted in the cloud, can provide lighter management but without enrollment. Windows PCs can also be managed using Intune client software.

## Enroll devices  
 Enrollment lets users access company resources on their personal devices and lets the admin ensure devices comply with policies that protect those resources. The admin must enable enrollment in the Intune console, which might require creating a trust relationship with the device. The device is then enrolled, usually by the user entering work or school credentials. The device then receives policy from Intune and gains access to resources.

[Get ready to enroll devices in Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)

## Enroll corporate-owned devices
Corporate-owned devices (COD) can be managed with the Intune console. iOS devices can be enrolled directly through tools provided by Apple including their Device Enrollment Program or Apple Configurator. All device types can be enrolled by an admin or manager using the device enrollment manager. Devices with an IMEI number can also be identified and tagged as company-owned.
[Enroll corporate-owned devices](manage-corporate-owned-devices.md)

## Mobile device management with Exchange ActiveSync and Intune
Mobile devices that aren't enrolled but that connect to Exchange ActiveSync (EAS) can still be managed by Intune. Intune uses an Exchange Connector to communicate with EAS, either on-premises and cloud-hosted.
[Mobile device management with Exchange ActiveSync and Intune](mobile-device-management-with-exchange-activesync-and-microsoft-intune.md)


## Manage Windows PCs with Intune  
You can also use Microsoft Intune to manage Windows PCs using the Intune Windows PC client software. 

[Manage Windows PCs with Intune](manage-windows-pcs-with-microsoft-intune.md)
