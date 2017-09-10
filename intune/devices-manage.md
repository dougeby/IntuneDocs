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

Since mobile devices took a central place in our lives, we've come to expect access to information everywhere we go. Your users use devices to access information to do their jobs in an ever-increasing array of locations, but you need to keep that information safe by ensuring the devices accessing it are secure.

This topic provides an overview of how Intune lets you manage devices while giving users access to the information they need.

Intune device management lets you connect iOS, Android, Windows, and macOS devices to Intune's cloud-based management service. Once brought into management, Intune lets you:

- Give users access to resources such as email, apps, and settings like Wi-Fi and VPN
- Protect devices with restrictions and check them for compliance
- Perform remote tasks like lock, reset, or remove company data from a device
- Monitor, troubleshoot and retire devices throughout their lifecycle

## Device management overview
Your industry requires devices to get work done, whether they're personal devices accessing email, task-based devices running a specific set work or school apps, or kiosk devices used for a single purpose. You also need to ensure the information those devices access is protected. Intune lets you decide what information users can access while putting restrictions to ensure data doesn't fall into the wrong hands.

For example, your users want to access company email and SharePoint from their personal iPhone or Android devices. Because work email frequently contains sensitive information, you need to ensure every device is locked with a PIN and is running a fairly recent operating system. Your management expects you to be able to show devices are managed. If those devices fail to meet minimum requirements, you need to block access to information until those devices are brought back into compliance. Finally, if a device is lost or its user leaves the company, you need to be able to remotely remove company data from the device.

## Device management in use

You'll get started managing devices by customizing Intune to meet your company's needs. You'll add users and groups, assign licenses, and add apps and resources to share with your users. This is a good time to set up device restrictions and conditional access policies that define a device's requirements to access company data. Intune enables modern scenarios to help protect devices and data including multi-factor authentication and Windows Hello for Business.

With Intune infrastructure in place, you can begin enrolling devices either as personal devices in a "Bring your own device" (BYOD) scenario or enrolling company-owned devices that are then distributed for use. A number of bulk-enrollment scenarios are available to simplify company-owned device enrollment.

As users begin working with devices, you can monitor devices and apps, and provide assistance such as locking or resetting lost devices. Users are empowered to reset their PIN, while a help desk portal lets you call up specific users' information to identify and resolve their issues.

When users leave the company or devices need to be retired or repurposed, Intune provides clear workflows to ensure resources and data don't leave the company.

## Implementing device management
As you think about device management, start by defining your goals. How you'll set up device management depends on your organization's needs. The following are some key considerations:

- Are there legal or privacy considerations do you need to account for in your device management strategy? [Terms and conditions](terms-and-conditions-create.md) inform users and require that they accept terms before devices can access information.
- What roles and responsibilities do you need in your IT department? [Role-based access control (RBAC)](role-based-access-control.md) lets you define administrative roles and scope.
- What resources ([email](email-settings-configure.md), [Wi-Fi](wi-fi-settings-configure.md) and [VPN](vpn-settings-configure.md) settings, [apps](app-management.md)) will you provide for your users?
- What [restrictions] do you need on devices? Can users bring  personal devices? What platforms will you support? Will you block jail-broken and rooted devices? How about features like camera access?

A [set up checklist](setup-steps.md) provides the steps to enable device management.

## Next steps
[Set up Intune](setup-steps.md)
