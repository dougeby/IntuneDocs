---
# required metadata

title: Policies to protect Windows PCs| Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: d081f466-45dd-41d1-ab25-6d974c72a52a

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Use policies to help protect Windows PCs that run the Intune client software

Microsoft Intune offers three policies that you can use to help ensure the security of Windows PCs when they are managed by the [Intune client software](manage-windows-pcs-with-microsoft-intune.md). 

> [!TIP]
	> The capabilities offered when you manage Windows PCs using the Intune client software differ considerably than when you enroll the PC into Intune. If you want to know more about the differences between each method of managing PCs, read the following topics:
	> [Windows PC management capabilities in Microsoft Intune](../Understand/windows-pc-management-capabilities-in-microsoft-intune.md)
	> [Mobile device management capabilities in Microsoft Intune](../Understand/mobile-device-management-capabilities-in-microsoft-intune.md)

## Software updates

Intune makes it easy for you to [keep Windows PCs that you manage up-to-date](pc-software-updates.md) by informing you when important software updates from Microsoft and other companies are available. You can then approve or decline these updates. Approved updates will automatically be installed on all applicable PCs.

## Windows Firewall

The Windows Firewall helps to keep hackers, malware, and other threats from Windows PCs. Intune lets you [manage setting and features for the Windows Firewall](pc-firewall-policies.md) on all PCs that you manage.

## Endpoint Protection

As an IT admin, one of your top priorities is to [keep the Windows PCs that you manage free of malware and viruses](pc-endpoint-protection.md). Intune integrates with Endpoint Protection to provide real-time protection against malware threats, keep malware definitions up-to date, and automatically scan computers. Endpoint Protection also provides tools that help you to manage and monitor malware attacks.



### See Also
[Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)

