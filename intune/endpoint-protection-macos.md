---
# required metadata

title: Add endpoint protection on macOS in Microsoft Intune - Azure | Microsoft Docs
description: On macOS devices, use the gatekeeper to determine where apps can be installed, including the mac app store. Also enable or configure a firewall allow specific apps, blocks specifics apps, use stealth mode, and even block certain types of incoming connections using Microsoft Intune.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/27/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# macOS endpoint protection settings in Intune

This article shows you the endpoint protection settings that you can configure for devices running macOS. These settings include gatekeeper and firewall settings on these devices, and can be configured using a device profile in Microsoft Intune.

## Gatekeeper

- **Allow apps downloaded from these locations**: Limit apps depending on where the apps are downloaded. The intent is to protect devices from malware, and only allow apps from sources you trust. Your options to allow: 
  - **Mac App Store**
  - **Mac App Store and identified developers**
  - **Anywhere**

- **User can override Gatekeeper**: Prevents users from overriding the Gatekeeper setting, and prevents users from Control clicking to install an app. When enabled, users can Control-click any app, and install it.

## Firewall

Use the firewall to control connections per-application, rather than per-port. Using per-application settings makes it easier to get the benefits of firewall protection. It also helps prevent undesirable apps from taking control of network ports that are open for legitimate apps.

- **Use firewall to protect devices from unauthorized network access by controlling connections on a per-app basis.**
  - **Firewall**: Enable Firewall to configure how incoming connections are handled in your environment.
  - **Incoming connections**: Block all incoming connections except the connections required for basic Internet services, such as DHCP, Bonjour, and IPSec. This feature also blocks all sharing services, such as File Sharing and Screen Sharing. If you're using sharing services, then keep this setting as **Not configured**.

- **Allow or block incoming connections for specific apps**
  - **Apps allowed**: Select the apps that are explicitly allowed to receive incoming connections.
  - **Apps blocked**: Select the apps that should block incoming connections.
  - **Stealth mode**: To prevent the computer from responding to probing requests, enable stealth mode. The device continues to answer incoming requests for authorized apps. Unexpected requests, such as ICMP (ping), are ignored.
