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
You can also use Microsoft Intune to manage Windows PCs using the Intune Windows PC client software.

|Windows PC management (Desktop) capabilities | Mobile Device Management (Mobile) capabilities|
|---------|-----------|
|**Manage software updates**: You can keep PCs up-to-date, and manage when updates are applied. [https://technet.microsoft.com/library/dn646968.aspx](https://technet.microsoft.com/library/dn646968.aspx) | **Certificate, email, VPN and WiFi profiles**: You can deploy certificate profiles to mobile devices, and also deploy e-mail, VPN and WiFi profiles. See Enable access to company resources with Microsoft Intune - deleted.|
|**Windows Firewall Policy**: This helps to ensure that no PC used by your company has a inactive or improperly-configured Windows Firewall. https://technet.microsoft.com/en-us/library/mt346040.aspx |**Conditional access**: Use Intune conditional access policies to control access to on-premises Microsoft Exchange or Exchange Online email from devices. See Manage access to email and SharePoint with Microsoft Intune.|
|**Anti-malware protection**: Intune provides additional control over the built-in Defender client which helps protect your PCs from malware. https://technet.microsoft.com/en-us/library/dn646970.aspx |**Device settings**: Configure mobile device security and functional settings for enrolled Windows 10 devices. Examples include Require a password, limit the number of failed attempts, limit the minutes before the screen locks, set password expiration, and prevent previously-used passwords. For details, see Windows 10 configuration policy settings in Microsoft Intune.|
|**Hardware and Software Inventory**: Intune provides detailed information about the hardware and software of managed computers. |**Selectively wipe or retire devices**: You can wipe corporate data off of missing or stolen devices. https://technet.microsoft.com/en-us/library/jj676679.aspx |
| |**Custom Settings**: Deploy OMA-URI settings that can be used to control device features such as whether the app store can be used, and what modern apps can be launched. This is useful when the setting you need is not available in a configuration policy. |
|**Deploy "Modern Apps", as well as desktop applications** (exe and msi file format installations)  |**Deploy "Modern Apps" only**, but not desktop applications in .exe and .msi format.|

[Manage Windows PCs with Intune](manage-windows-pcs-with-microsoft-intune.md)
