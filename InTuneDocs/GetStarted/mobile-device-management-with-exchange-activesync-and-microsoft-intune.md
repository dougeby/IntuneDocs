---
title: Mobile device management with Exchange ActiveSync and Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 
author: jeffgilb
---
# Mobile device management with Exchange ActiveSync and Microsoft Intune
For [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] to directly manage mobile devices, users need to enroll devices into [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]. For mobile devices that users have not enrolled you can enable Exchange ActiveSync management using the Exchange connector. Exchange devices can be managed in both on premises servers and for hosted Exchange on Microsoft Office 365 in the cloud.

# Install the Exchange connector
Before you can begin managing devices with Exchange ActiveSync and Microsoft Intune, you must first install and confugure the appropriate Intune to Exchange connector. Choose the appropriate option below depending on whether or not your Exchange server is on-premises or hosted as a service in the cloud:

-   [Install the Intune connector for on-premises Exchange](.\Intune-on-premises-Exchange-connector.md)
-   [Configure the Intune service to service connector for hosted Exchange](.\Intune-service-to-service-Exchange-connector.md)


The Exchange connector connects you with your Exchange deployment and lets you manage mobile devices through the [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] console, where you have the capabilities described in this article.

## Apply policy for Exchange-managed mobile devices
Policy settings can be applied through the [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] console, see [Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md). For a detailed list of Exchange ActiveSync policy settings and features that are supported by specific mobile devices, see [Exchange ActiveSync Client Comparison Table](http://go.microsoft.com/fwlink/?LinkId=247270).

> [!NOTE]
> Upon connecting [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] to a Microsoft Exchange environment, all users managed through [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] will have their EAS policy reset to the current default policy on the Microsoft Exchange server, unless there is a more specific policy defined within [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

## Define mobile device access rules by device family and device model to set which mobile devices can access Exchange ActiveSync.
You can [define mobile device access rules](..\Exchange-access-rules-for-mobile-devices.md) by device family and device model to set which mobile devices can access Exchange ActiveSync.

## Wipe company data from mobile devices
Finally, you can [wipe company data from mobile devices](..\Intune-service-to-service-Exchange-connector.md) when they are no longer in use, lost, or stolen.

