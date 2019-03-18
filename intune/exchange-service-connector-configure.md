---
# required metadata

title: Intune Exchange connector for Exchange Online | Microsoft Intune
description: Connect Intune to Office 365 Exchange service to support Exchange ActiveSync mobile device management (MDM).
keywords:
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/18/2019
ms.topic: conceptual
ms.prod:
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology:
ms.assetid: 

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure
ms.collection: M365-identity-device-management
---

# Configure the Exchange service connector for Intune and Exchange Online
> [!IMPORTANT]  
> In MC165575, we shared that we would be removing the Exchange Online to Intune ‘Service to Service’ connector functionality in an upcoming update. With the February update to the Intune service. We are planning to remove all existing Exchange Online to Intune connectors in March 2019.
>  
>  For more information about this change, see [Reminder: Removal of existing Exchange Online to Intune connectors](whats-new#reminder-removal-of-existing-exchange-online-to-intune-connectors-)

This article shows you how to connect the Microsoft Intune service to Exchange Online or the new Exchange Online Dedicated service. To determine whether your Exchange Online Dedicated environment is the **new** or **legacy** version, contact your account manager.

With the **Service to Service Connector** you can manage both Exchange ActiveSync (EAS) and Intune managed devices from a single administrative console.  The connector is not required to enable Conditional Access for Exchange Online.

When planning a rollout of Conditional Access, it is often important to understand which users and number of user will have the new experience. The Microsoft 365 admin center provides this in the form of an Exchange Online email app usage report as part of the Activity Reports feature of that portal. These reports can be used to understand mobile email adoption in your environment before and after the deployment of Conditional Access.

## Service to Service Connector requirements
The **Service to Service Connector** supports only Exchange Online or Exchange Online Dedicated and has no requirements for an on-premises infrastructure. 


|              Requirement               |                                                                                                            More information                                                                                                            |
|----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Exchange Online configured and running |                                                                                 [Exchange Online](https://technet.microsoft.com/library/jj200580.aspx)                                                                                 |
|   Mobile device management authority   |                                                       [Set the mobile device management authority to Microsoft Intune](mdm-authority-set.md)                                                       |
|       Microsoft Exchange version       |                                                                                      Exchange Online or the new Exchange Online Dedicated service                                                                                      |
|    Active Directory synchronization    | Before you can use the Intune Connector, you must [set up Active Directory synchronization](/intune/users-add) so that your local users and security groups are synchronized with your instance of Azure Active Directory. |

### Exchange cmdlet requirements

You must also create an Exchange Online user account that is used by the Intune Exchange service connector. The account must have permission to run the following required Windows PowerShell Exchange cmdlets:

 - Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
 - Get-MobileDeviceMailboxPolicy, Set-MobileDeviceMailboxPolicy, New-MobileDeviceMailboxPolicy, Remove-MobileDeviceMailboxPolicy
 - Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule
 - Get-MobileDeviceStatistics
 - Get-MobileDevice
 - Get-ActiveSyncDeviceClass

## Set up the Service to Service Connector

1. Sign in to the [Azure portal](https://portal.azure.com) with a user account that has Exchange admin rights, permissions for the cmdlets [described earlier](#exchange-cmdlet-requirements), a valid Intune license, and the Global Administrator role. Microsoft Intune uses the email address of the currently signed-in user to set up the connection.

2. Choose **All services** from the left menu, then type **Intune** in the text box filter.

3. Choose **Intune** to open the Microsoft Intune dashboard. select **Exchange access**, and then under **Setup** select **Exchange online connector**.

4.  On the **Exchange access - Exchange online connector** page, choose **Set Up Service to Service Connector**. 

The Service to Service Connector automatically configures and synchronizes your Exchange Online or new Exchange Online Dedicated environment.

## Validate your Exchange connection

After you have successfully configured the Exchange Service to Service Connector, validate the Exchange Connector Server information on the **Exchange access - Exchange online connector** page.

You can also check the **Connection status** and the time and date of the last successful synchronization attempt.

 
