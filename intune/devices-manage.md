---
# required metadata

title: What is device management in Intune
titleSuffix: "Intune on Azure"
description: Learn how to see the devices you manage with Intune, and perform remote actions on them."
keywords:
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 09/13/2017
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: cc0e66f8-4624-4406-bc85-d249af0483d6

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: [ALIAS]
#ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# What is Microsoft Intune device management?

Your users use devices to access information and do their work. You need to manage those devices to simplify how users access information while keeping that information safe. This topic provides an overview of how Intune lets you manage devices.

Device management lets you connect iOS, Android, Windows, and macOS devices to Intune's cloud-based management service. Intune device management lets you:

- Give users access to resources such as company email, apps, and settings like Wi-Fi and VPN
- Protect devices with restrictions and check them for compliance
- Perform remote tasks like lock, reset, or remove company data from a device
- Monitor, troubleshoot and retire devices throughout their lifecycle

## Device management overview
You'll get started managing devices by customizing Intune to meet your company's needs. You'll add users and groups, assign licenses, and add apps and resources to share with your users. This is a good time to set up device restrictions and conditional access policies that define device requirements to access company data.

With Intune infrastructure in place, you can begin enrolling devices either in as personal devices in a "Bring your own device" (BYOD) scenario or enrolling company-owned devices into management.

As users begin working with devices, you can monitor devices and apps, and provide assistance such as locking or resetting lost devices. Intune enables modern scenarios to help protect devices and data including multi-factor authentication and Windows Hello for Business. A troubleshooting view helps identify and resolve user issues.

When users leave the company or devices need to be retired or repurposed, Intune provides clear workflows to help ensure resources and data don't leave the company.

## Planning for device management
As you think about device management, start by defining your goals. How you'll set up device management depends on your organization's needs. The following are some key considerations:

- What legal or privacy considerations do you need to account for in your device management strategy?
  - Do you need to comply with industry or government policies or privacy laws that define the information you must manage? Intune privacy statement
  - What roles do you have or want in your IT department? Role-based access control (RBAC)
- What level of control or restrictions do you need on devices? For example:
	- Can users bring their personal devices or does your organization provide the device?
  - If your organization provides devices, are they assigned to individuals or are they shared?
	- What kinds of devices (iOS, Android, Windows, macOS) will you support?
  - Will you block jail-broken or rooted devices?
	- Do you need to block features like camera access?
	- Are there other settings like PIN complexity or device encryption you want to require?
- Finally, consider the resources you need to provide for your users and their priority. The following are examples of resources you can provide to managed devices:
	- Email profiles
	- Wi-Fi settings
	- VPN settings
	- Apps

## Device management overview
