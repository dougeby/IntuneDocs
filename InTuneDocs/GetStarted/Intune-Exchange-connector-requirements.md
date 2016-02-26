---
title: Microsoft Intune Exchange connector requirements
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 
author: jeffgilb
---
# Exchange Connector installation requirements

## Exchange Connector installation requirements
To prepare to connect [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] to Exchange, make sure you have completed the following:

|Requirement|More information|
|---------------|--------------------|
|Set the Mobile Device Management Authority to [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)]|[Get ready to enroll devices in Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)|
|Verify you have hardware requirements for the on-premises connector (if connecting to an on-premises Exchange Server)|[Requirements for the Service to Service Connector](network-infrastructure-requirements-for-microsoft-intune.md#BKMK_ServiceConnectorReqs)|
|Configure a user account with permission to run the designated list of Windows PowerShell cmdlets|PowerShell Cmdlets for Service to Service Connector (See below)|

## Windows PowerShell Exchange cmdlet requirements

### PowerShell cmdlets for on-premises Exchange Connector
You must create an Active Directory user account that is used by the [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] Exchange Connector. The account must have permission to run the following required Windows PowerShell Exchange cmdlets:

-   Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings

-   Get-CasMailbox, Set-CasMailbox

-   Get-ActiveSyncMailboxPolicy, Set-ActiveSyncMailboxPolicy, New-ActiveSyncMailboxPolicy, Remove-ActiveSyncMailboxPolicy

-   Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule

-   Get-ActiveSyncDeviceStatistics

-   Get-ActiveSyncDevice

-   Get-ExchangeServer

-   Get-ActiveSyncDeviceClass

-   Get-Recipient

-   Clear-ActiveSyncDevice, Remove-ActiveSyncDevice

-   Set-ADServerSettings

-   Get-Command


### PowerShell Cmdlets for Service-to-Service Connector
You must create an Exchange Online user account that is used by the [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] Exchange Connector. The account must have permission to run the required Windows PowerShell Exchange cmdlets that are listed below.

-   Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings

-   Get-MobileDeviceMailboxPolicy, Set-MobileDeviceMailboxPolicy, New-MobileDeviceMailboxPolicy, Remove-MobileDeviceMailboxPolicy

-   Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule

-   Get-MobileDeviceStatistics

-   Get-MobileDevice

-   Get-ActiveSyncDeviceClass

-   Get-Recipient

-   Clear-MobileDevice, Remove-MobileDevice

### Next steps
-   [Install the Intune connector for on-premises Exchange](.\Intune-on-premises-Exchange-connector.md)
-   [Configure the Intune service to service connector for hosted Exchange](.\Intune-service-to-service-Exchange-connector.md)