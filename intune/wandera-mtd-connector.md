---
# required metadata

title: Set up Wandera Mobile Security with Intune
titleSuffix: Intune on Azure
description: How to set up the Wandera Mobile Security with Microsoft Intune to control mobile device access to your corporate resources.
keywords:
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 04/30/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology:
ms.assetid:  

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: davidra
#ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
#ms.custom:
ms.collection: M365-identity-device-management
---


# Wandera Mobile Threat Defense connector with Intune  

You can control mobile device access to corporate resources using conditional access based on risk assessment conducted by Wandera, a Mobile Threat Defense (MTD) solution that integrates with Microsoft Intune.  Risk is assessed based on telemetry collected from devices by the Wandera service, including:
- Operating systme vulnerabilities
- Malicious apps installed
- Malicoius network profiles
- Cryptojacking

You can configure *conditional access* policies that are based on Wandera's risk assessment, enabled through Intune device compliance policies. Risk assessment policy can can allow or block noncompliant devices from accessing corporate resources based on detected threats.  


## How do Intune and Wandera Mobile Mobile Threat Defense help protect your company resources?  

Wandera’s mobile app seamlessly installs using Microsoft Intune. This app captures file system, network stack, and device and application telemetry (where available), and sends it to the Wandera cloud service to assess the device's risk for mobile threats. These risk level classifications are configurable to suit your needs in the Wandera console, RADAR.

The compliance policy in Intune includes a rule for MTD based on Wandera’s risk assessment. When this rule is enabled, Intune evaluates device compliance with the policy that you enabled.

For devices that are noncompliant, access to resources like Office 365 can be blocked. Users on blocked devices receive guidance from the Wandera app to resolve the issue and regain access.

## Supported platforms  

The following platforms are supported for Wandera when enrolled in Intune:

- Android 5.0 and later  
- iOS 10.2 and later  

For more information about platform and device, see the [Wandera website](https://www.wandera.com/why-wandera/features/device-support/).

## Prerequisites  

●	Microsoft Intune subscription
●	Azure Active Directory
●	Wandera Mobile Threat Defense (formerly Wandera Secure)
For more information, see Wandera Mobile Security



 