---
# required metadata

title: Mobile Threat Defense with Intune
titleSuffix: "Intune Azure preview"
description: "Protect access to company resources based on device risk"
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/09/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: ac77b590-a7ec-45a0-9516-ebf5243b6210

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Mobile Threat Defense integration with Intune


Intune Mobile Threat Defense connectors allow you to leverage your chosen Mobile Threat Defense vendor as a source of information for your compliance policies and conditional access rules. This allows IT Administrators to add a layer of protection to their corporate resources such as Exchange and Sharepoint, specifically from compromised mobile devices.

## What problem does this solve?

Companies need to protect sensitive data from emerging threats including physical, app-based, and network-based threats, as well as operating system vulnerabilities.
Historically, companies have been proactive when protecting PCs from attack, while mobile devices go un-monitored and unprotected. Mobile platforms have built-in protection such as app isolation and vetted consumer app stores, but these platforms remain vulnerable to sophisticated attacks. Today, more employees use devices for work and need access to sensitive information. Devices need to be protected from increasingly sophisticated attacks.

## How the Intune Mobile Threat Defense connectors work?

The connector protects company resources by creating a channel of communication between Intune and your chosen Mobile Threat Defense vendor. Intune Mobile Threat Defense partners offer intuitive, easy to deploy applications for mobile devices which actively scan and analyze threat information to share with Intune, for either reporting or enforcement purposes. For example, if a connected Mobile Threat Defense app reports to the Mobile Threat Defense vendor that a phone on your network is currently connected to a network which is vulnerable to Man in the Middle attacks, this information is shared with and categorized to an appropriate risk level (low/medium/high) – which can then be compared with your configured risk level allowances in Intune to determine if access to certain resources of your choice should be revoked while the device is compromised.

## Sample scenarios

When a device is considered infected by the Mobile Threat Defense solution:

![Mobile Threat Defense infected device](./media/MTD-image-1.png)

Access is granted when the device is remediated:

![Mobile Threat Defense Access granted](./media/MTD-image-2.png)

## Mobile Threat Defense partners

Learn how to protect access to company resource based on device, network, and application risk with:

- [Lookout](lookout-mobile-threat-defense-connector.md)
- [Skycure](skycure-mobile-threat-defense-connector.md)
- [Check Point SandBlast Mobile](checkpoint-sandblast-mobile-mobile-threat-defense-connector.md)