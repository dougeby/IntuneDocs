---
# required metadata

title: Troubleshoot Exchange Connector 
description: Troubleshoot issues related to the Intune Exchange connector.
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/26/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: c5cb5465-fd8e-4524-83b9-ccdf3393b6dcROBOTS: NOINDEX,NOFOLLOW

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: chrisgre
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Troubleshoot the Exchange Connector

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

This topic describes how to troubleshoot issues that may be related to the Intune Exchange Connector.

## Steps for checking the Connector configuration 

Check the configuration of the Exchange Connector and then see if the problem has been resolved.

- Be sure to specify a notification account in the initial setup of the Exchange Connector.
- The Exchange Connector Service Account must have the appropriate permissions to execute the PowerShell cmdlets used by the Exchange Connector.
- When configuring the Exchange Connector, specify a Client Access Server (CAS) that is as close as possible to the server hosting the Exchange Connector. Communication latency between the CAS and the Exchange Connector could result in device discovery delays, particularly when using O365 Dedicated.
- Be aware that there is a time lag between Exchange Connector synchronizations with the Exchange CAS. A full sync takes place once a day, and a delta (quick) sync takes place every two hours. There is a likelihood that a user with a newly-enrolled device will experience a delay in getting access.
- 
## Exchange ActiveSync device not discovered from Exchange
Check to see if the Exchange Connector is syncing with the Exchange server. To do so, locate logs for a full sync or a delta sync. See Exchange Connector Logs. If a full sync or delta sync has completed successfully since the device joined, you've eliminated this as the source of the issue. If no sync has taken place, collect the sync logs and attach them to your support request.

- If a user doesn't have an Intune license, the Exchange connector won’t discover their devices.
- If a user’s Primary SMTP address is different than their UPN in AAD, the Exchange Connector will not discover any devices for that Intune/AAD user. Fix the primary SMTP address.
- If the CAS that the Exchange Connector communicates with during a discovery cycle is an Exchange 2010 CAS and you have both Exchange 2010 and 2013 mailbox servers, the Exchange Connector will not discover any Exchange 2013 users’ devices. To resolve this, configure the Exchange Connector to point to an Exchange 2013 CAS.  Though this issue primarily concerns O365 Dedicated topologies, we still recommend pointing to an Exchange 2013 CAS in other topologies as a best practice.
- For Exchange Dedicated (O365 dedicated) environments, you must point the Exchange Connector to an Exchange 2013 (not 2010) CAS in the dedicated environment during the initial setup as it will only communicate with this CAS when executing Powershell cmdlets.


## Using Powershell to get more data on Exchange Connector issues
- To get a list of all mobile devices for a mailbox use Get-ActiveSyncDeviceStatistics -mailbox mbx
- To get a list of SMTP addresses for a mailbox use Get-Mailbox -Identity user | select emailaddresses | fl.
- To get detailed information about a device's access state use Get-CASMailbox <upn> | fl

### Next steps
If this troubleshooting information didn't help you, contact Microsoft Support as described in [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md).
