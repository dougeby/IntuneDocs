---
# required metadata

title: Troubleshoot common problems for the Intune Exchange connector
titleSuffix: Microsoft Intune
description: Troubleshoot and resolve common problems for the on-premises Microsoft Intune Exchange Connector 
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/02/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology:
ms.assetid:  
# optional metadata

#audience:
#ms.devlang:
ms.reviewer:
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure
ms.collection: M365-identity-device-management
---

# Resolve common problems for the Intune Exchange Connector
 
This article can help the Intune administrator resolve common problems for the operation of the Intune Exchange Connector.  

Before proceeding, review Troubleshoot the Intune on-premises Exchange connector for foundational information about the connector before you start troubleshooting, and common issues for the connector configuration. 

## Exchange ActiveSync device not discovered from Exchange

[Monitor the Exchange connector activity](exchange-connector-install.md#on-premises-intune-exchange-connector-high-availability-support) to see if the Exchange connector is syncing with the Exchange server. If a full sync or quick sync has completed successfully since the device joined, you can check for other possible issues, listed below. If no sync has taken place, collect the sync logs and attach them to a support request.  

- Make sure users have an Intune license, otherwise the Exchange connector won’t discover their devices.  

- If a user’s primary SMTP address is different from their UPN in Azure Active Directory (Azure AD), the Exchange Connector will not discover any devices for that user. Fix the primary SMTP address to resolve the issue.  

- If you have both Exchange 2010 and Exchange 2013 mailbox servers in your environment, we recommend pointing the Exchange connector to an Exchange 2013 Client Access Server (CAS). Otherwise, if the Exchange connector is set up to communicate with an Exchange 2010 CAS, the Exchange connector doesn't discover any Exchange 2013 users’ devices.  

- For Exchange Online Dedicated environments, you must point the Exchange connector to an Exchange 2013 CAS (not an Exchange 2010 CAS) in the dedicated environment during the initial setup, as the connector will only communicate with this CAS when executing PowerShell cmdlets.  


## Problems with the notification email message  

To support non-Knox Android devices for conditional access for on-premises mailboxes, Intune enrollment must start from the “Get Started Now” email message that’s sent by the Intune Exchange Connector. Starting enrollment from the message ensures that the device receives a unique ActiveSyncID across all platforms (Exchange, Azure AD, Intune).  

There are several reasons why a user might not receive the notification email message:  

- The notification account isn't set up correctly.
- Autodiscover fails for the notification account.
- The EWS request to send the email message fails.

Use the following to troubleshoot email notification issues.

### Review the notification account that’s used to retrieve Autodiscover settings
1. Ensure that the Autodiscover service and Exchange Web Services are configured on the Exchange Client Access services. For more information, see [Client Access services](https://docs.microsoft.com/Exchange/architecture/client-access/client-access).

   For more information, see [Autodiscover service in Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/autodiscover?view=exchserver-2019).


2. Verify that your notification account meets the following requirements:

   - The account has an active mailbox that's hosted by your Exchange on-premises server.  

   - The account UPN matches the SMTP address.

3. For autodiscover to work, your DNS server must have a DNS record for **Autodiscover.SMTPdomain.com** (for example Autodiscover.contoso.com) that points to your Exchange client access server. To check whether the record is present, do the following, while specifying your FQDN in place of *Autodiscover.SMTPdomain.com*:

   1. At a command prompt, type **NSLOOKUP**, and then press Enter.  

   2. Type **Autodiscover.SMTPdomain.com**, and then press Enter.

      The output should be similar to the following image:  
      ![Nslookup results](./media/troubleshoot-exchange-connector-common-problems/nslookup-results.png
)

   You can also test the Autodiscover service from the Internet at https://testconnectivity.microsoft.com/ or from a local domain by using the Microsoft Connectivity Analyzer Tool. For more information, see [Microsoft Connectivity Analyzer Tool](https://docs.microsoft.com/en-us/previous-versions/office/exchange-remote-connectivity/jj851141(v=exchg.80)). Download the [Microsoft Connectivity Analyzer Tool](http://go.microsoft.com/fwlink/?LinkID=313782).


### Review Autodisocvery  

If Autodiscover fails, try the following steps:
1. [Configure a valid Autodiscover DNS record](https://docs.microsoft.com/previous-versions/exchange-server/exchange-150/mt473798(v=exchg.150)). 

2. Hard code the EWS URL in the Intune Exchange Connector Configuration file, as follows:

   1. Determine the EWS URL. The default EWS URL for Exchange is **https://<mailServerFQDN>/ews/exchange.asmx**, although yours may differ. Contact the Exchange administrator to verify the correct URL for your environment.

   2. Edit the **OnPremisesExchangeConnectorServiceConfiguration.xml** file. By default, the file is located in **%ProgramData%\Microsoft\Windows Intune Exchange Connector** on the computer that's running the Exchange Connector. Open the file by using a text editor, and then change the following line to reflect the EWS URL for your environment: `<ExchangeWebServiceURL>https://<YourExchangeHOST>/EWS/Exchange.asmx</ExchangeWebServiceURL>`
    

3. Save the file, and then restart the computer or restart the Microsoft Intune Exchange Connector Service.

>[!NOTE]
> In this configuration, the Intune Exchange Connector stops using Autodiscover and instead connects directly to the EWS URL.

## Next steps  

The following article can help resolve specific errors:
- [Resolve common Errors for the Intune Exchange Connector](troubleshoot-exchange-connector-common-errors.md).

Seek assistance from support or the Intune community.
- See [Get Support](get-support.md) to use the Intune Console to help troubleshoot the issue, or to open a support case with Microsoft. 
- Post your issue in the [Microsoft Intune forums](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod).  
