---
# required metadata

title: Troubleshoot conditional access
description: What to do when your users fail to get access to resources through Intune conditional access.
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/24/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 433fc32c-ca9c-4bad-9616-852c72faf996
ROBOTS: NOINDEX,NOFOLLOW

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: chrisgre
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Troubleshoot conditional access

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Typically, a user is trying to access email or SharePoint and receives a prompt to enroll. That prompt will lead the user to the company portal.

This topic describes what to do when your users fail to get access to resources through Intune conditional access.


## The basics for success in conditional access

In order to conditional access to work, you need the following conditions:

-	The device must be managed by Intune
-	The device must be registered with Azure Active Directory (AAD) . Under normal circumcstances this registration takes place automatically during Intune enrollment
-	The device must be compliant with your Intune compliance policies, for the device, and for the user of the device.  If there are no compliance policies, Intune enrollment is sufficient.
-	Exchange ActiveSync must be activated on the device if the user is retrieving mail through the device's native mail client rather than through Outlook.     This happens automatically for iOS, Windows Phone and Android/KNOX Standard devices.
-	Your Intune Exchange Connector should be properly configured. See [Troubleshooting the Exchange Connector in Microsoft Intune](troubleshoot-exchange-connector.md) for more information.

These conditions can be viewed for each device in the Azure Management Portal and in the device inventory report.

## Enrollment issues

 -  The device isn't enrolled, so enrollment will resolve the issue.
 -  The user enrolled the device, but the workplace join failed. The user should update the enrollment from the company portal.

## Compliance issues

 -  The device is not compliant with Intune policy. Common issues are encryption and password requirements. The user will be redirected to the company portal, where they can configure their device to be compliant.
 -  It may take some time for compliance information to be registered for a device. Wait a few minutes and try again.
 -  For iOS devices:
	 -   An existing email profile created by the user will block the deployment of an Intune admin-created profile. This is a common problem as iOS users will typically create an email profile, then enroll. The company portal will inform the user that they are not compliant due to their manually-configured email profile, and will prompt the user to remove that profile.The user should remove their email profile so that the Intune profile can be deployed. To prevent the problem instruct your users to enroll without installing an email profile and to allow Intune to deploy the profile.
	 -	 An iOS device may get stuck in a checking-compliance state, preventing the user from initiating another check-in. Restarting the company portal may fix this, and the compliance state will reflect the device state in Intune. After all of the data is collected from a device sync the compliance check is, fast, less than half a second on average.

		Typically, the reason devices stay in this state is because they are having trouble connecting to the service or the sync is taking a long time.  If the problem persists on different network configurations (cellular, Wi-Fi, VPN), through device restarts, and after verifying that the SSP is up-to-date on the device, contact Microsoft Support as described in [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md).

 - For Android devices:
 	- Certain Android devices may seem to be encrypted, but the Company Portal app recognizes these devices as not encrypted. 
	
		-	Devices that are in this state require the user to set a secure start-up passcode. The user will see a device notification from the Company Portal app asking to set a start-up passcode for the device. After tapping the device notification and confirming the existing PIN or password, choose the **Require PIN to start device** option on the **Secure start-up** screen. Then, tap the **Check Compliance** button for the device from the Company Portal app. The device should now be detected as encrypted.
	
		- 	Some device manufacturers encrypt their devices using a default PIN instead of the secret PIN set by the user. Intune recognizes encryption using the default PIN as insecure because this method of encryption can put the data on the device at risk from malicious users with physical access to the device. If this is the issue, consider using [app protection policies](/intune-classic/deploy-use/azure-portal-for-microsoft-intune-mam-policies).

## Policy issues

When you create a compliance policy and link it to an email policy, both policies have to be deployed to the same user, so be careful when planning which policies are deployed to which groups. Users that have only one policy applied are likely to find that their devices are not compliant.


## Exchange ActiveSync issues

### Compliant Android device gets quarantine notice
- An Android device that is enrolled and compliant may still get a quarantine notice when trying to access corporate resources. Before choosing the link that says **Begin**, the user should ensure that the company portal was not open when they tried to access the resources. The users should close the company portal, try again to access the resources, and then choose the **Begin** link.

### Retired device continues to have access.
- When using Exchange Online, a retired device may continue to have access for several hours after retirement. This is because Exchange caches access rights for 6 hours. Consider other means of protecting data on retired devices in this scenario.

### Device is compliant and registered with AAD but still blocked
- Sometimes, provision of the Exchange ActiveSync ID (EASID)  to AAD is delayed. A common cause of this issue is throttling, so wait a few minutes and try again.

### Device blocked

A device may be blocked from Conditional Access without receiving an activation email.

- Is there a default Exchange rule which quarantines or blocks devices? If a default rule blocks or quarantines devices, devices will not be able to receive the activation email from the Exchange Connector. This is by design.
- Is the notification account properly configured as described in Basic configuration?
- Is the device present in the Intune admin console as an Exchange ActiveSync device? If not, it's likely that device discovery is failing, probably because of an Exchange Connector sync issue. See Exchange ActiveSync device not discovered from Exchange.
- Check the Exchange Connector logs for sendemail activity and check for errors. An example of the command to search for is SendEmail from notification account to useremail.
- Before the Exchange Connector blocks the device, it sends the activation email. If the device is offline, it may not receive the activation email. Check if the device email client has email retrieval using Push instead of Poll as this could also cause the user to miss the email. Switch to Poll and see if the device receives the email.

## Non-compliant device not blocked

If you encounter a device that is not compliant but continues to have access, take the following steps.

- Review your Target and Exclusion groups. If a user isn't in the right target group or is in the exclusion group, they won’t be blocked. Only devices of users in a Target group are checked for compliance.
- Ensure the device is being discovered. Is the Exchange Connector pointing to an Exchange 2010 CAS while the user is on an Exchange 2013 server? In this case, if the default Exchange rule is Allow, even if the user is in the Target group, Intune can't be aware of the device's connection to Exchange.
- Check Device Existence/Access State in Exchange:
	- Use this PowerShell cmdlet to get a list of all mobile devices for a mailbox: "Get-ActiveSyncDeviceStatistics -mailbox mbx'. If the device isn’t listed then it isn’t accessing Exchange.
	- If the device is listed, use the Get-CASmailbox -identity:’upn’ | fl cmdlet to get detailed information about its access state, and provide that information to Microsoft Support.

## Before you open a support ticket
If these troubleshooting procedures don't resolve your issue, there is information that you may be asked to provide to Microsoft Support, such as OWA mailbox logs or Exchange Connector logs.

### Collecting OWA mailbox logs

1. Log on through OWA and choose the settings (gear) symbol next to your name in the upper right corner.
2. Choose **Options**
3. Choose **Phone** (may say **Mobile Devices**) in the  column on the left side.
4. From the top menu, choose **Mobile Devices**.
5. Choose your device from the list and then choose **Start Logging**.
6. When prompted, choose **Yes** on the pop-up dialog.
7. Perform the action that caused the issue, so that you can reproduce it.
8. Wait 1-2 minutes then go back to the phone list in OWA. Make sure your phone is selected in the list, and then from the top menu choose **Retrieve Log**.
9. You should receive an email from yourself with an attachment. When you open a support ticket, provide the contents of the email to Microsoft Support.

### Exchange Connector logs

#### General log information
To view Exchange Connector logs use the [Server Trace Viewer Tool](server trace viewer tool (https://msdn.microsoft.com/library/ms732023(v=vs.110).aspx'). This tool requires that you download the Windows Server SDK.

>[!NOTE]
>The logs are located in C:\ProgramData\Microsoft\Windows Intune Exchange Connector\Logs. The logs are contained in a series of 30 log files starting with *Connector0.log* and stopping at *Connector29.log*. Logs rollover from one to another after 10MB of data has accumulated in a log. Once the logs get to Connector29, they will start over at Connector0 again, overwriting previous log files.

#### Locating sync logs

-    Locate a full sync in the logs by searching for **full sync**. The beginning of a full sync will be marked by this text:

	'Handling command: Getting the mobile device list without a time filter (full sync) for <number> users`

    The end of the log for a full sync looks like this:

	Getting the mobile device list without a time filter (full sync) for 4 users completed successfully. Details: Inventory command result - Devices synced: 0 Commmand ID: commandIDGUID' Exchange health: 'Server health 'Name: 'PowerShellExchangeServer: <Name=mymailservername>' Status: Connected','

-	Locate a quick (delta) sync in the logs by searching for **quick sync**.

##### Exceptions in Get next command
Check the Exchange Connector logs for exceptions in **Get next command**, and provide these to Microsoft Support.

#### Verbose logging

To enable verbose logging:

1.	Open the Exchange Connector tracing configuration file. The file is located at: %ProgramData%\Microsoft\Windows Intune Exchange Connector\TracingConfiguration.xml.
2.	Locate the TraceSourceLine with the following key: OnPremisesExchangeConnectorService
3.	Change the **SourceLevel** node value from **Warning ActivityTracing** (the default) to **Verbose ActivityTracing**, as shown below.

    <TraceSourceLine>
	      <Key xsi:type="xsd:string">OnPremisesExchangeConnectorService</Key>
	      <Value xsi:type="TraceSource">
	        <SourceLevel>All</SourceLevel>
	        <Listeners>
	          <Listener>
	            <ListenerType>CircularTraceListener</ListenerType>
	            <SourceLevel>Verbose ActivityTracing</SourceLevel>
	            <FileSizeQuotaInBytes>10000000</FileSizeQuotaInBytes>
	            <FileName>Microsoft\Windows Intune Exchange Connector\Logs\Connector.svclog</FileName>
	            <FileQuota>30</FileQuota>
	          </Listener>
	        </Listeners>
	      </Value>
    </TraceSourceLine>



### Next steps
If this troubleshooting information didn't help you, contact Microsoft Support as described in [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md).
