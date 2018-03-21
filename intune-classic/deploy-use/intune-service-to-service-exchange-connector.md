---
# required metadata

title: Exchange connector for Exchange Online 
description: Connect Intune to Office 365 Exchange service to support Exchange ActiveSync mobile device management (MDM).
keywords:
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 07/29/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 05fa5dc9-9bad-4557-987a-9b8ce4edebb0
ROBOTS: NOINDEX,NOFOLLOW

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: muhosabe
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Configure the Intune service to service connector for Exchange Online

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Use this information to connect Microsoft Intune and Exchange Online or the new Exchange Online Dedicated service. To determine whether your Exchange Online Dedicated environment is the **new** or **legacy** version, contact your account manager. Intune only supports one Exchange connector connection of any type per subscription.

## Service to Service Connector requirements
The **Service to Service Connector** supports only Exchange Online or Exchange Online Dedicated and has no requirements for on-premises infrastructure.

|Requirement|More information|
|---------------|--------------------|
|Exchange Online configured and running|[Exchange Online](https://technet.microsoft.com/library/jj200580.aspx) |
|Mobile device management authority| [Set the mobile device management authority to Microsoft Intune](prerequisites-for-enrollment.md#step-2-set-mdm-authority)|
|Microsoft Exchange version|Exchange Online or the new Exchange Online Dedicated service|/intune/users-permissions-add
|Active Directory synchronization|Before you can use the Intune Connector, you must [set up Active Directory synchronization](/intune/users-permissions-add) so that your local users and security groups are synchronized with your instance of Azure Active Directory.|

### Exchange cmdlet requirements

You must also create an Exchange Online user account that is used by the Intune Exchange Connector. The account must have permission to use the Intune administration console and to run the following required Windows PowerShell Exchange cmdlets:

 - Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
 - Get-MobileDeviceMailboxPolicy, Set-MobileDeviceMailboxPolicy, New-MobileDeviceMailboxPolicy, Remove-MobileDeviceMailboxPolicy
 - Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule
 - Get-MobileDeviceStatistics
 - Get-MobileDevice
 - Get-ActiveSyncDeviceClass

## Set up the Service to Service Connector

1. Open the [Microsoft Intune administration console](https://manage.microsoft.com) with a user account that has Exchange admin rights and permissions for the cmdlets [described earlier](#exchange-cmdlet-requirements). Microsoft Intune uses the email address of the currently signed-in user to set up the connection.

2.  In the workspace shortcuts pane, choose **ADMIN**>**Mobile Device Management** > **Microsoft Exchange** > **Set Up Exchange Connection**.
![Set up service to service connector page](../media/intunesa5cservicetoserviceconnector.png)

3.  On the **Set Up Exchange Connection** page, choose **Set Up Service to Service Connector**.


The Service to Service Connector automatically configures and synchronizes your Exchange Online or new Exchange Online Dedicated environment.

## Validate your Exchange connection

After you have successfully configured the Exchange Connector, go to the [Microsoft Intune administration console](https://manage.microsoft.com). Choose **Admin**> **Mobile Device Management** > **Microsoft Exchange**. Then validate that the details you provided appear under **Exchange Connection Information**.

You can also check the time and date of the last successful synchronization attempt.
