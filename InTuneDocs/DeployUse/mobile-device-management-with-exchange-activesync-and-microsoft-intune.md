---
# required metadata

title: Mobile device management with Exchange ActiveSync and Microsoft Intune | Microsoft Intune
description:
keywords:
author: nathbarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 14f5cf53-6764-4e22-a18b-fa750b3acd41

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Mobile device management with Exchange ActiveSync and Microsoft Intune
For Microsoft Intune to directly manage mobile devices, users must enroll devices with Intune. For mobile devices that users haven't enrolled, you can enable Exchange ActiveSync (EAS) management using the Exchange connector. Devices can be managed with either on-premises Exchange servers and cloud-hosted Exchange on Microsoft Office 365.

## Requirements ##

This topic assumes your organization is already using Exchange, either on-premises or hosted. In addition, you must set Intune as your mobile device management authority and create an account Intune will use to run Windows PowerShell cmdlets for Exchange.

[Exchange connector requirements](intune-exchange-connector-requirements.md)

## Exchange access rules for mobile devices ##

Exchange needs a set of rules that defines what happens when mobile devices attempt to connect to EAS. These rules are managed in the Intune administration console.

[Exchange access rules for mobile devices](exchange-access-rules-for-mobile-devices.md)

## Install the Exchange connector
The Exchange connector lets you manage your Exchange deployment in the Intune console. You must first install and configure the appropriate Intune-to-Exchange connector. Choose the appropriate option based whether your Exchange server is on-premises or hosted as a service in the cloud:

-   [Install the Intune connector for on-premises Exchange](intune-on-premises-exchange-connector.md)
-   [Configure the Intune Service to Service connector for hosted Exchange](intune-service-to-service-exchange-connector.md)

## Apply policy for Exchange-managed mobile devices
Policy settings can be applied through the Intune console, see [Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md). For a list of Exchange ActiveSync policy settings and features supported by specific mobile devices, see [Exchange ActiveSync Client Comparison Table](http://go.microsoft.com/fwlink/?LinkId=247270).

> [!NOTE]
> After connecting Intune to a Microsoft Exchange environment, the EAS policy for all users managed through Intune will be reset to the current default policy on the Microsoft Exchange server, unless a more specific policy is defined within Intune.

## Wipe company data from mobile devices
Finally, you can [wipe company data from EAS-managed mobile devices](wipe-for-exchange-managed-mobile-devices.md) when they are no longer in use, or if devices are lost or stolen.
