---
# required metadata

title: Choose an MDM solution | Microsoft Intune
description:
keywords:
author: jeffgilb
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 538cd810-4559-4c49-94d9-b832c8298fdd

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Choose an MDM solution that is right for you

## Intune standalone

As a cloud-based MDM service, Intune provides deep device and app management capabilities for managing mobile devices (iOS & Mac devices, Android devices, Windows phones) and Windows PCs. <!--The ability to manage Windows PCs is one of the key deciding factors between using your existing Office 365 subscription or purchasing an Intune subscription.-->

Additionally, Intune enables you to secure your devices and apps at a more granular level by using certificates, profiles for Wi-Fi, VPN, and email to allow secure access to specific corporate resources, deploying apps to users’ devices, and restricting certain actions on managed apps.  

<!-- deprecated
Learn more about the differences between [MDM in Office 365 and Intune](/intune/understand/choose-between-intune-and-mdm-for-office-365.html).

>[!NOTE] Administrators can manage users and their mobile devices using both Intune and Office 365 concurrently on the same tenant. This lets you decided which solution is the best solution for specific users and their corresponding devices. You can then specify whether a user and his or her devices are managed with Office 365 MDM or the more feature-rich Intune management solution.
-->

## Intune integrated with System Center Configuration Manager
Intune allows you to extend System Center Configuration Manager to manage mobile devices using the Configuration Manager console. This hybrid MDM experience enables you to continue using your on-premises infrastructure to manage both mobile devices and PCs, while keeping existing policies and configurations intact.  

To help you decide between Intune standalone and Intune integrated with Configuration Manager for hybrid MDM, read the [detailed comparison of capabilities](/intune/understand/choose-between-intune-and-hybrid.md).

<!-- unnecessary important here
>[!IMPORTANT] Once you choose Intune with System Center Configuration Manager, Configuration Manager takes over management of your mobile devices and there is no easy way to switch to Intune.
-->

## Next steps
Read the [Introduction to Intune](/intune/understand/introduction-to-microsoft-intune.md) if you want to learn more about Intune as a standalone solution for enterprise mobility.
