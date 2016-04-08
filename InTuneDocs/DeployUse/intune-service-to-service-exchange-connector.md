---
title: Configure the Microsoft Intune Exchange connector for hosted Exchange
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid:
author: NathBarn
---
# Configure the Intune service-to-service connector for Exchange Online

Use this information to connect Microsoft Intune and Exchange Online service hosted by Office 365.

### Requirements for the Service to Service Connector
The **Service to Service Connector** supports only hosted Exchange and has no requirements for on-premises infrastructure.

However, to use this connector, the following must be true:

-   

-   The user account that you use to install the Connector must be a tenant administrator for Intune and be an administrator in the Exchange tenant with a license to use Exchange Server 2013.

|Requirement|More information|
|---------------|--------------------|
|Microsoft Exchange version|You must have an Office 365 subscription that has an Exchange Server 2013 tenant. So long as the tenant is Exchange Server 2013, the connector supports Exchange Server 2010 in that same environment.|
|Mobile device management authority| [Set the mobile device management authority to Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md#Set_MDM_Auth)|
|Active Directory Synchronization|Before you can use the Intune Connector, you must [set up Active Directory synchronization](get-started-with-a-paid-subscription-to-microsoft-intune-step-3.md) so that your local users and security groups are synchronized with your instance of Azure Active Directory.|

## Set up the Service-to-Service Connector
> [!IMPORTANT]
> Before you being installing and configuring the service-to-service connector, ensure that you meet the [Exchange connector installation requirements](./intune-exchange-connector-requirements.md).

1.  You must create an Exchange Online user account that is used by the Intune Exchange Connector. The account must have permission to run the required Windows PowerShell Exchange cmdlets that are listed below.

 - Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
 - Get-MobileDeviceMailboxPolicy, Set-MobileDeviceMailboxPolicy, New-MobileDeviceMailboxPolicy, Remove-MobileDeviceMailboxPolicy
 - Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule
 - Get-MobileDeviceStatistics
 - Get-MobileDevice
 - Get-ActiveSyncDeviceClass

2. Open the [Microsoft Intune administration console](http://manage.microsoft.com) with a user account with Exchange admin rights. Microsoft Intune uses the email address of the currently logged in user to set up the connection.

2.  In the workspace shortcuts pane, choose **ADMIN**, then go **Mobile Device Management** > **Microsoft Exchange** > **Set Up Exchange Connection**.

3.  On the **Set Up Exchange Connection** page, choose **Set Up Service to Service Connector**.

![](../media/IntuneSA5cServiceToServiceConnector.PNG)

The Service-to-Service Connector will automatically configure and synchronize with your Hosted Exchange environment.

## Validate your Exchange connection

After you have successfully configured the Exchange Connector, in the Intune admin console choose the **ADMIN** workspace and go **Mobile Device Management** > **Microsoft Exchange** and validate that the details you provided appear under **Exchange Connection Information**.

You can also check the time and date of the last successful synchronization attempt.
