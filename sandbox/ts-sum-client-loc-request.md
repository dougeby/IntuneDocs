---
title: WSUS Location Request to the management point
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: tempfile
author: jeffgilb
---
# WSUS Location Request to the management point

## What happens when a client sends a WSUS location request
The first thing the client does is set the WSUS server that will be its update source for software update scans. That process is detailed below.

1. When the Configuration Manager client needs to process a software update scan, Scan Agent creates a scan request based on the available policy as noted in the **ScanAgent.log** log file:
```
CScanAgent::ScanByUpdates- Policy available for UpdateSourceID={C2D17964-BBDD-4339-B9F3-12D7205B39CC}
ContentVersion=38
CScanAgent::ScanByUpdates- Added Policy to final ScanRequest List UpdateSourceID={C2D17964-BBDD-4339-B9F3-12D7205B39CC}, Policy-ContentVersion=38, Required-ContentVersion=38
```
1. WScan Agent now sends a WSUS Location Request to Location Services as noted in the **ScanAgent.log** log file:
```
Inside CScanAgent::ProcessScanRequest()
CScanJobManager::Scan- entered
ScanJob({4CD06388-D509-46E4-8C00-75909EDD9EE8}): CScanJob::Initialize- entered
ScanJob({4CD06388-D509-46E4-8C00-75909EDD9EE8}): CScanJob::Scan- entered
ScanJob({4CD06388-D509-46E4-8C00-75909EDD9EE8}): CScanJob::RequestLocations- entered
asdfasdfasdfadfasdfasdfasdfad
asdfasdfasdfadfasdfasdfasdfad
```
>[!TIP]
> Each scan job is stored in WMI in the CCM_ScanJobInstance class:
>
> **Namespace**: root\CCM\ScanAgent **Class**: CCM_ScanJobInstance

3. Location Services creates a Location Request and sends it to the management point. The package ID for a WSUS location request is the Update Source Unique ID.
**LocationServices.log:**
```
LocationServices.log: CCCMWSUSLocation::GetLocationsAsyncEx
Attempting to persist WSUS location request for ContentID='{C2D17964-BBDD-4339-B9F3-12D7205B39CC}' and ContentVersion='38'
Persisted WSUS location request LocationServices
Attempting to send WSUS Location Request for ContentID='{C2D17964-BBDD-4339-B9F3-12D7205B39CC}'
WSUSLocationRequest : <WSUSLocationRequest SchemaVersion="1.00"><Content ID="{C2D17964-BBDD-4339-B9F312D7205B39CC}" Version="38"/><AssignedSite SiteCode="PS1"/><ClientLocationInfo OnInternet="0"><ADSite Name="CM12-R2PS1"/><Forest Name="CONTOSO.COM"/><Domain Name="CONTOSO.COM"/><IPAddresses><IPAddress SubnetAddress="192.168.2.0" Address="192.168.2.62"/></IPAddresses></ClientLocationInfo></WSUSLocationRequest>
Created and Sent Location Request '{C2BB9710-C548-49D0-9DF8-5F9CFC5F3862}' for package {C2D17964-BBDD-4339-B9F312D7205B39CC}
```
4. CCM Messaging sends the location request message to the management point:
**CcmMessaging.log:**
5. The management point parses this request and calls the MP_GetWSUSServerLocations stored procedure to get the WSUS locations from the database:
**MP_Location.log:**
6. After getting the results from the stored procedure, the management point sends a response to the client:
**MP_Location.log**
7. CCM Messaging receives the response and sends it back to Location Services:
**CcmMessaging.log:**
8. 8.Location Services parses the response and sends the location back to Scan Agent:
**LocationServices.log:**
9. Scan Agent now has the policy and the update source location with the appropriate content version.
**ScanAgent.log:**
10. Scan Agent notifies WUAHandler to add the update source. WUAHandler adds the update source to the registry and initiates a Group Policy refresh (if the client is in domain) to see whether Group Policy overrides the update server that we just added.
**WUAHandler.log** (*New Client showing new Update Source being added*):
11. After the updatesource is successfully added, Scan Agent raises a State Message and initiatesthe scan:
**ScanAgent.log:**

## Troubleshooting tips
Review the following log symptoms for troubleshooting tips to check for.

### ScanAgent.log shows no policy available for an Update Source and no WUAHandler.log exists or no current activity within WUAHandler.log
Check the Enable software updates on clients setting. For more information, see the following TechNet document: [About Client Settings in Configuration Manager](https://technet.microsoft.com/en-us/library/gg682067.aspx#BKMK_SoftwareUpdatesDeviceSetting).

### ScanAgent/LocationServices receive no WSUS server location
Is a Software Update Point (SUP) role installed for the site? If not, install and configure a Software Update Point and monitor SUPSetup.log for progress. See the following for more information: [Install and Configure a Software Update Point](https://technet.microsoft.com/en-us/library/gg712312.aspx#BKMK_InstallSUP).

If a SUP role is installed, is it configured and synchronizing? Check WCM.log, WSUSCtrl.log and WSyncMgr.log for errors.
select * from WSUSServerLocations
select * from Update_SyncStatus

### Client receives the WSUS location but fails to configure the WSUS registry keys
Did group policy refresh respond within the 2 minute timeout per WUAHandler.log? If so, does WUAHandler denote "Group policy settings were overwritten by a higher authority (Domain Controller)"? Check for a GPO being set within the domain.

## Next steps

>[!div class="step-by-step"]

>[My problem is solved](.\ts-sum-success.md)

>[My problem is *not* solved](.)  
