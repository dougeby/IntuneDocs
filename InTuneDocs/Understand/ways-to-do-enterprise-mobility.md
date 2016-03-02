---
title: Ways to do enterprise mobility
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 2d91b8b5-bf44-4562-ab4a-6611584f9674
author: robstackmsft
---
# Ways to do enterprise mobility

Microsoft provides several options for managing your mobile devices. Depending on the type of devices you need to manage, the granularity of device and app management your business requires, and other factors such as cost, you may choose one of the mobile device management (MDM) solutions provided by Microsoft.

## MDM for Office 365

If your organization has an Office 365 subscription, you can use the inbuilt MDM capabilities to enroll devices that connect to your organization, create and manage device security policies, remotely wipe devices, and view detailed device reports. These capabilities are included in your Office 365 subscription at no extra cost.

However, MDM in Office 365 is limited to managing mobile devices such as iPhones, iPads, Android devices, and Windows phones. If you also need to manage PCs, you will need to purchase an Intune standalone subscription or use Intune with System Center Configuration Manager. Office 365 provides limited management capabilities as compared to Intune. Learn more about the differences between [MDM in Office 365 and Intune](choose-between-intune-and-mdm-for-office-365.md). <!--testing a same-journey link. just filename.md -->

>[!TIP] You need to activate Mobile Management in your Office 365 subscription before you can start managing devices. To know more about managing mobile devices in Office 365, please [visit our Office support site](https://technet.microsoft.com/library/ms.o365.cc.devicepolicysupporteddevice.aspx).

## Intune standalone

As a cloud-based MDM service, Intune provides deep device and app management capabilities for managing mobile devices (iOS devices, Android devices, Windows phones) and Windows PCs. The ability to manage Windows PCs is one of the key deciding factors between using your existing Office 365 subscription or purchasing an Intune subscription.

Additionally, Intune enables you to secure your devices and apps at a more granular level by using certificates, profiles for Wi-Fi, VPN, and email to allow secure access to specific corporate resources, deploying apps to users’ devices, and restricting certain actions on managed apps.  

Learn more about the differences between [MDM in Office 365 and Intune](choose-between-intune-and-mdm-for-office-365.html).<!--testing a same-journey link. just filename.html -->

>[!NOTE] Administrators can manage users and their mobile devices using both Intune and Office 365 concurrently on the same tenant. This lets you decided which solution is the best solution for specific users and their corresponding devices. You can then specify whether a user and his or her devices are managed with Office 365 MDM or the more feature-rich Intune management solution.

## Intune integrated with System Center Configuration Manager
Intune allows you to extend System Center Configuration Manager to manage mobile devices using the Configuration Manager console. This unified experience enables you to continue using your on-premises infrastructure to manage both mobile devices and PCs, while keeping existing policies and configurations intact.  

To help you decide between Intune standalone and Intune integrated with Configuration Manager, read the [detailed comparison of capabilities](choose-between-intune-and-hybrid.html).

>[!IMPORTANT] Once you choose Intune with System Center Configuration Manager, Configuration Manager takes over management of your mobile devices and there is no easy way to switch to Intune.

## Next steps
Read the [Introduction to Intune](introduction-to-microsoft-intune.html) if you want to learn more about Intune as a standalone solution for enterprise mobility.
