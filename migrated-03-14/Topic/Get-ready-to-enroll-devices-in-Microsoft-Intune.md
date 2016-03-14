---
title: Get ready to enroll devices in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 44fd4af0-f9b0-493a-b590-7825139d9d40
author: Lindavr
---
# Get ready to enroll devices in Microsoft Intune
[![](../Image/Nav-Icons/WIT_Tile_W_Overview.png)](https://technet.microsoft.com/library/dn646960.aspx/?WT.mc_id=IntuneOverview20150801)[![](../Image/Nav-Icons/WIT_Tile_W_GetStarted.png)](https://technet.microsoft.com/library/dn646953.aspx/?WT.mc_id=IntuneGS20150801)![](../Image/Nav-Icons/WIT_Tile_W_EnrollDevicesHighlight.png)[![](../Image/Nav-Icons/WIT_Tile_W_ManageDevices.png)](https://technet.microsoft.com/library/mt313202.aspx/?WT.mc_id=IntuneConfig20150801)[![](../Image/Nav-Icons/WIT_Tile_W_ManageApps.png)](https://technet.microsoft.com/library/dn646965.aspx/?WT.mc_id=IntuneDeploy20150801)[![](../Image/Nav-Icons/WIT_Tile_W_ProtectResources.png)](https://technet.microsoft.com/library/mt313203.aspx/?WT.mc_id=IntuneProtect20150801)[![](../Image/Nav-Icons/WIT_Tile_W_RetireData.png)](https://technet.microsoft.com/library/mt313204.aspx/?WT.mc_id=IntuneRetire20150801)[![](../Image/Nav-Icons/WIT_Tile_W_TechnicalReference.png)](https://technet.microsoft.com/library/mt282239.aspx/?WT.mc_id=IntuneTR20150801)[![](../Image/Nav-Icons/WIT_Tile_W_Troubleshooting.png)](https://technet.microsoft.com/library/mt345521.aspx)
![](../Image/Nav-Icons/WIT_Banner_EnrollDevices.png)

To let employees use company resources on mobile devices (including Android, iOS, and Windows Phone) you must enable device enrollment, the process that brings devices into management. To do this you must first set [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] as your mobile device authority and enable enrollment for the device's operating system. Computers running Windows 8.1 and Windows 10 can also be managed as mobile devices or you can manage them [using Intune client software](http://technet.microsoft.com/library/dn646959.aspx).

## Enable mobile device enrollment
To enable MDM enrollment you must set the *mobile device management authority*. The MDM authority defines the  management service with permission to manage a set of devices.  Options for MDM authority include [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], Configuration Manager with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], or Office 365 MDM solutions.  Office 365 and Intune can be used in tandem to manage mobile devices. If System Center Configuration Manager is set as the management authority, no other service can be used for mobile device management. To get started, [set your Intune as the MDM authority](https://technet.microsoft.com/library/mt346013.aspx).

You must then enable enrollment for the operating systems your organization wants to support. Certain mobile device operating systems (for example Windows and iOS) require a trust relationship between devices and [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] to allow management.

-   [Set up Android management with Microsoft Intune](../Topic/Set-up-Android-management-with-Microsoft-Intune.md)

-   [Set up iOS and Mac management with Microsoft Intune](../Topic/Set-up-iOS-and-Mac-management-with-Microsoft-Intune.md) - Including [company-owned iOS devices](https://technet.microsoft.com/library/dn408185.aspx#BKMK_DEP)

-   [Set up Windows Phone management with Microsoft Intune](../Topic/Set-up-Windows-Phone-management-with-Microsoft-Intune.md)

-   [Set up Windows device management with Microsoft Intune](../Topic/Set-up-Windows-device-management-with-Microsoft-Intune.md)

## Manage multiple devices with the device enrollment manager account
Organizations can use Intune to manage large numbers of mobile devices with a single user account. The *device enrollment manager* account is a special Intune account with permission to enroll more than five devices. See [Enroll corporate-owned devices with the Device Enrollment Manager in Microsoft Intune](../Topic/Enroll-corporate-owned-devices-with-the-Device-Enrollment-Manager-in-Microsoft-Intune.md).

## MDM with Intune and Exchange ActiveSync
For [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] to directly manage mobile devices, users need to enroll devices into [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]. For mobile devices that users have not enrolled you can enable Exchange ActiveSync management using the Exchange connector. Exchange devices can be managed in both on premises servers and for hosted Exchange on Microsoft Office 365 in the cloud. The Exchange connector connects you with your Exchange deployment and lets you manage mobile devices through the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] console. See [Mobile device management with Exchange ActiveSync and Microsoft Intune](../Topic/Mobile-device-management-with-Exchange-ActiveSync-and-Microsoft-Intune.md)

## See Also
[Documentation for Microsoft Intune](../Topic/Documentation-for-Microsoft-Intune.md)

