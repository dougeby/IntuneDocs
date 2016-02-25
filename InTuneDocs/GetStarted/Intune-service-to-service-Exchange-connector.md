---
title: Configure the Microsoft Intune Exchange connector for hosted Exchange
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 
author: jeffgilb
---
# Configure the Intune service to service connector for hosted Exchange

Use this section to connect [!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)] and hosted Exchange without an on-premises infrastructure.

## Requirements
To prepare to connect [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] to your Exchange Server, make sure you have completed the following:

|Requirement|More information|
|---------------|--------------------|
|Set the Mobile Device Management Authority to [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)]|[Get ready to enroll devices in Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)|
|Verify you have hardware requirements for the on-premises connector|[Requirements for the Service to Service Connector](network-infrastructure-requirements-for-microsoft-intune.md#BKMK_ServiceConnectorReqs)|
|Configure a user account with permission to run the designated list of Windows PowerShell cmdlets|PowerShell Cmdlets for Service to Service Connector (See below)|

### PowerShell Cmdlets for Service-to-Service Connector
You must create an Exchange Online user account that is used by the [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] Exchange Connector. The account must have permission to run the required Windows PowerShell Exchange cmdlets that are listed below.

-   Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings

-   Get-MobileDeviceMailboxPolicy, Set-MobileDeviceMailboxPolicy, New-MobileDeviceMailboxPolicy, Remove-MobileDeviceMailboxPolicy

-   Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule

-   Get-MobileDeviceStatistics

-   Get-MobileDevice

-   Get-ActiveSyncDeviceClass

-   Get-Recipient

-   Clear-MobileDevice, Remove-MobileDevice

## Set up the Service-to-Service Connector

1.  Open the [!INCLUDE[wit_adminconsole](./includes/wit_adminconsole_md.md)].

2.  In the workspace shortcuts pane, choose **ADMIN**.

3.  In the navigation pane, under **Mobile Device Management**, expand **Microsoft Exchange** and then choose **Set Up Exchange Connection**.

4.  On the **Set Up Exchange Connection** page, choose **Set Up Service to Service Connector**.
![IntuneSA5cServiceToServiceConnector](/Image/IntuneSA5cServiceToServiceConnector.PNG)

The Service-to-Service Connector will automatically configure and synchronize with your Hosted Exchange environment.

## Validate your Exchange connection

-   After you have successfully configured the [!INCLUDE[wit_exch_2](./includes/wit_exch_2_md.md)], in the [!INCLUDE[wit_adminconsole](./includes/wit_adminconsole_md.md)] choose the **ADMIN** workspace, and under **Mobile Device Management**, choose **Microsoft Exchange** and validate that the details you provided appear under **Exchange Connection Information**.

-   You can also check the time and date of the last successful synchronization attempt.