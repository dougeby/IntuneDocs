---
title: Mobile device management with Exchange ActiveSync and Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid:
author: nathbarn
---
# Mobile device management with Exchange ActiveSync and Microsoft Intune
For Microsoft Intune to directly manage mobile devices, users must enroll devices with Intune. For mobile devices that users haven't enrolled, you can enable Exchange ActiveSync (EAS) management using the Exchange connector. Devices can be managed with either on-premises Exchange servers and cloud-hosted Exchange on Microsoft Office 365.

**Prerequisites**
 - Exchange configured and running, on-premises or hosted
 - [Intune as your mobile device authority](get-ready-to-enroll-devices-in-microsoft-intune.md#BKMK_Set_MDM_Authority)
 - [Exchange access rules defined](exchange-access-rules-for-mobile-devices.md)
 - [Active Directory user account with permission to run Exchange cmdlets](Intune-Exchange-connector-requirements.md)
 - Users assigned for Exchange ActiveSync management

## Install the Exchange connector
The Exchange connector lets you manage your Exchange deployment in the Intune console. You must first install and configure the appropriate Intune-to-Exchange connector. Choose the appropriate option based whether your Exchange server is on-premises or hosted as a service in the cloud:

-   [Install the Intune connector for on-premises Exchange](.\intune-on-premises-exchange-connector.md)
-   [Configure the Intune Service to Service connector for hosted Exchange](.\intune-service-to-service-exchange-connector.md)


## Apply policy for Exchange-managed mobile devices
Policy settings can be applied through the Intune console, see [Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md). For a list of Exchange ActiveSync policy settings and features supported by specific mobile devices, see [Exchange ActiveSync Client Comparison Table](http://go.microsoft.com/fwlink/?LinkId=247270).

> [!NOTE]
> After connecting Intune to a Microsoft Exchange environment, the EAS policy for all users managed through Intune will be reset to the current default policy on the Microsoft Exchange server, unless a more specific policy is defined within Intune.

## Define mobile device access rules by device family and device model to set which mobile devices can access Exchange ActiveSync.
You can [define mobile device access rules](..\exchange-access-rules-for-mobile-devices.md) by device family and device model to set which mobile devices can access Exchange ActiveSync.

## Wipe company data from mobile devices
Finally, you can [wipe company data from mobile devices](..\intune-service-to-service-exchange-connector.md) when they are no longer in use, lost, or stolen.
