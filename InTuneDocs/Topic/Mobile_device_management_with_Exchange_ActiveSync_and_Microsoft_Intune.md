---
title: Mobile device management with Exchange ActiveSync and Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: eb9618d2-dc90-48be-b921-8044b7e693ac
author: NathBarn
---
# Mobile device management with Exchange ActiveSync and Microsoft Intune
For [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] to directly manage mobile devices, users need to enroll devices into [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]. For mobile devices that users have not enrolled you can enable Exchange ActiveSync management using the Exchange connector. Exchange devices can be managed in both on premises servers and for hosted Exchange on Microsoft Office 365 in the cloud. The Exchange connector connects you with your Exchange deployment and lets you manage mobile devices through the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] console, where you have the following capabilities:

-   Deploy policies to user groups to help secure corporate data that is stored on mobile devices such as password, encryption, and attachments.

-   Define mobile device access rules by device family and device model to set which mobile devices can access Exchange ActiveSync.

-   Enroll, rename, and un-enroll devices.

-   Wipe mobile devices with the option to wipe the mobile device, such as for lost or stolen devices.

This topic contains the following sections:

-   [Configure Microsoft Intune on-premises connector for on-premises or hosted Exchange](../Topic/Mobile_device_management_with_Exchange_ActiveSync_and_Microsoft_Intune.md#bkmk_EX_OP): Use this section to configure your on-premises infrastructure with on-premises Exchange or hosted Exchange.

-   [Configure Intune service to service connector for hosted Exchange](../Topic/Mobile_device_management_with_Exchange_ActiveSync_and_Microsoft_Intune.md#bkmk_S_S)

-   [Validate your Exchange connection](../Topic/Mobile_device_management_with_Exchange_ActiveSync_and_Microsoft_Intune.md#bkmk_val_ex)

-   [Wipe for Exchange-managed Mobile Devices](../Topic/Mobile_device_management_with_Exchange_ActiveSync_and_Microsoft_Intune.md#bkmk_EXCap)

-   [Policy for Exchange-managed mobile devices](../Topic/Mobile_device_management_with_Exchange_ActiveSync_and_Microsoft_Intune.md#bkmk_pol)

-   [Exchange Access rules for mobile devices](../Topic/Mobile_device_management_with_Exchange_ActiveSync_and_Microsoft_Intune.md#bkmk_acc)

## <a name="bkmk_EX_OP"></a>Configure Microsoft Intune on-premises connector for on-premises or hosted Exchange
Use this section to configure your on-premises infrastructure with on-premises Exchange or hosted Exchange.

### Requirements
To prepare to connect [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] to your Exchange Server, you must first fulfill the following requirements. You may have already fulfilled these requirements when you set up [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].

|Requirement|More information|
|---------------|--------------------|
|Set the Mobile Device Management Authority to [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]|[Set mobile device management authority and configure Microsoft Intune](../Topic/Set_mobile_device_management_authority_and_configure_Microsoft_Intune.md)|
|Verify you have hardware requirements for the on-premises connector|[Requirements for the On-Premises Connector](../Topic/Network_infrastructure_requirements_for_Microsoft_Intune.md#BKMK_ExchanceConnectorReqs)|
|Configure a user account with permission to run the designated list of Windows PowerShell cmdlets|Powershell Cmdlets for On-Premises Exchange Connector (see below)|

### <a name="bkmk_PS_onprem"></a>Powershell Cmdlets for On-Premises Exchange Connector
You must create an Active Directory user account that is used by the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] Exchange Connector. The account must have permission to run the following required Windows PowerShell Exchange cmdlets:

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

### Download, Install and Configure the Microsoft Intune Exchange Connector
To set up a connection that enables [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] to communicate with the Exchange Server that hosts the mobile devices’ mailboxes, you must download and configure the On-Premises Connector tool from the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] administrator console.

##### To download the On-Premises Connector software installation package

1.  Open the [!INCLUDE[wit_adminconsole](../Token/wit_adminconsole_md.md)].

2.  In the workspace shortcuts pane, choose **ADMIN**.
![IntuneSA1aclickADMIN](/Image/IntuneSA1aclickADMIN.png)

3.  In the navigation pane, under **Mobile Device Management**, expand **Microsoft Exchange** and then choose **Setup Exchange Connection**.
![IntuneSA1bSetupExchangeConnection](/Image/IntuneSA1bSetupExchangeConnection.png)

4.  On the **Setup Exchange Connection** page, choose **Download On-Premises Connector**.
![IntuneSA1cOnpremConnector](/Image/IntuneSA1cOnpremConnector.png)

5.  The On-Premises Connector software is contained in a compressed (.zip) folder that can be opened or saved. In the **File Download** dialog box, choose **Save** to store the compressed folder to a secure location.

> [!IMPORTANT]
> Do not rename or move the extracted files or the On-Premises Connector software installation will not succeed.

Perform the following steps to install the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] On-Premises Connector.

> [!IMPORTANT]
> The On-Premises Connector can only be installed once per [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] subscription, and only on one computer. If you attempt to install the On-Premises Connector a second time, you will replace the initial Exchange connection.

##### To install the On-Premises Connector

1.  Extract the files in **Exchange_Connector_Setup.zip** into a secure location.

2.  After the files are extracted, double-click **Exchange_Connector_Setup.exe** to install the On-Premises Connector.

    > [!IMPORTANT]
    > If the destination folder is not a secure location, you should delete the certificate file **WindowsIntune.accountcert** after you install the On-Premises Connector.

> [!NOTE]
> You can only set up one Exchange connection per [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] account. If you try to configure an additional connection, it will replace the original connection with the new one.

##### Configure the On-Premises Exchange Connector

1.  In the **Exchange server** field, select your Exchange server environment type, either **On-premises Microsoft Exchange Server** or select **Hosted Microsoft Exchange Server** for Exchange on Microsoft Office 365.
![IntuneSA1dconfigureExchConnector](/Image/IntuneSA1dconfigureExchConnector.png)

2.  For an on-premises Exchange server, provide either the server name or fully qualified domain name of the Exchange server that hosts the Client Access server role.

3.  For a hosted Exchange server in Microsoft Office 365, provide the Exchange server address.  To find the hosted Exchange server URL:

    1.  Open the Outlook Web App for Office 365.

    2.  Choose the “?” icon at the top left, and select **About**.

    3.  Locate the **POP External Server** value.

4.  For a dedicated, hosted Exchange server, provide either the server name or the fully qualified domain name of the dedicated Exchange server that hosts the Client Access server role.

5.  Choose **Proxy Server** to specify proxy server settings for your hosted Exchange server.

    1.  Select **Use a proxy server when synchronizing mobile device information**.

    2.  Enter the **proxy server name** and the **port number** to be used to access the server.

    3.  If it is necessary to provide user credentials to access the proxy server, select Use credentials to connect to the proxy server and enter the **domain\user** and the **password**.

    4.  Choose **OK**.

6.  Provide the credentials necessary to connect to your Exchange server.

7.  Provide administrative credentials necessary to send notifications to a user’s Exchange mailbox. These notifications are configurable via Conditional Access policies using Intune. For more information on these policies see [Enable access to company resources with Microsoft Intune - deleted](../Topic/Enable_access_to_company_resources_with_Microsoft_Intune_-_deleted.md).

    Ensure that the Autodiscover service and Exchange Web Services are configured on the Exchange Client Access Server. For more information on that see [Client Access server](https://technet.microsoft.com/library/dd298114.aspx).

8.  In the **Password** field, provide the password for this account to enable [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] to access the Exchange Server.

9. Choose **Connect**.

    It may take a few minutes while the connection is set up.

    During configuration, the [!INCLUDE[wit_exch_2](../Token/wit_exch_2_md.md)] stores your proxy settings to enable access to the Internet. If your proxy settings change, you will have to reconfigure the [!INCLUDE[wit_exch_2](../Token/wit_exch_2_md.md)] in order to apply the updated proxy settings to the [!INCLUDE[wit_exch_2](../Token/wit_exch_2_md.md)].

After the [!INCLUDE[wit_exch_2](../Token/wit_exch_2_md.md)] sets up the connection, mobile devices associated with users that are managed in [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] are automatically synchronized and added to the [!INCLUDE[wit_adminconsole](../Token/wit_adminconsole_md.md)]. This synchronization may take some time to complete.

To view the status of the connection and the last successful synchronization attempt, in the [!INCLUDE[wit_adminconsole](../Token/wit_adminconsole_md.md)] choose the **ADMIN** workspace, and under **Mobile Device Management**, choose **Microsoft Exchange**.
![IntuneSA2aServiceToServiceConnectorVerification](/Image/IntuneSA2aServiceToServiceConnectorVerification.PNG)

> [!NOTE]
> If you have installed the On-Premises Connector, and if at some point you delete the Exchange connection, you must uninstall the On-Premises Connector from the computer onto which it was installed.

## <a name="bkmk_S_S"></a>Configure Intune service to service connector for hosted Exchange
Use this section to connect [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] and hosted Exchange without an on-premises infrastructure.

### Requirements
To prepare to connect [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] to your Exchange Server, make sure you have completed the following:

|Requirement|More information|
|---------------|--------------------|
|Set the Mobile Device Management Authority to [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]|[Get ready to enroll devices in Microsoft Intune](../Topic/Get_ready_to_enroll_devices_in_Microsoft_Intune.md)|
|Verify you have hardware requirements for the on-premises connector|[Requirements for the Service to Service Connector](../Topic/Network_infrastructure_requirements_for_Microsoft_Intune.md#BKMK_ServiceConnectorReqs)|
|Configure a user account with permission to run the designated list of Windows PowerShell cmdlets|PowerShell Cmdlets for Service to Service Connector (See below)|

### <a name="Bkmk_PS_STS"></a>PowerShell Cmdlets for Service to Service Connector
You must create an Exchange Online user account that is used by the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] Exchange Connector. The account must have permission to run the required Windows PowerShell Exchange cmdlets that are listed below.

-   Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings

-   Get-MobileDeviceMailboxPolicy, Set-MobileDeviceMailboxPolicy, New-MobileDeviceMailboxPolicy, Remove-MobileDeviceMailboxPolicy

-   Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule

-   Get-MobileDeviceStatistics

-   Get-MobileDevice

-   Get-ActiveSyncDeviceClass

-   Get-Recipient

-   Clear-MobileDevice, Remove-MobileDevice

### Set up the Service to Service Connector

1.  Open the [!INCLUDE[wit_adminconsole](../Token/wit_adminconsole_md.md)].

2.  In the workspace shortcuts pane, choose **ADMIN**.

3.  In the navigation pane, under **Mobile Device Management**, expand **Microsoft Exchange** and then choose **Set Up Exchange Connection**.

4.  On the **Set Up Exchange Connection** page, choose **Set Up Service to Service Connector**.
![IntuneSA5cServiceToServiceConnector](/Image/IntuneSA5cServiceToServiceConnector.PNG)

The Service to Service Connector will automatically configure and synchronize with your Hosted Exchange environment.

## <a name="bkmk_val_ex"></a>Validate your Exchange connection

-   After you have successfully configured the [!INCLUDE[wit_exch_2](../Token/wit_exch_2_md.md)], in the [!INCLUDE[wit_adminconsole](../Token/wit_adminconsole_md.md)] choose the **ADMIN** workspace, and under **Mobile Device Management**, choose **Microsoft Exchange** and validate that the details you provided appear under **Exchange Connection Information**.

-   You can also check the time and date of the last successful synchronization attempt.

## <a name="bkmk_EXCap"></a>Wipe for Exchange-managed Mobile Devices
The following table describes the retire/wipe capabilities through Exchange ActiveSync.

|Type of Wipe|Windows 8.1 and Windows RT 8.1|Windows RT|Windows Phone 8|iOS|Android|
|----------------|----------------------------------|--------------|-------------------|-------|-----------|
|Full Wipe|Removes mail account and cached mail.|Removes mail account and cached mail.|Factory Reset|Factory Reset|Factory Reset|
|Selective Wipe/Email|Removes email account|Removes email account|Not supported.|Not supported.|Not supported.|
|Selective Wipe/policies|Policy enforcement removed, but settings are not changed|Policy enforcement removed, but settings are not changed|Policy enforcement removed, but settings are not changed|Policy enforcement removed, but  settings are not changed|Policy enforcement removed, but settings are not changed|

## <a name="bkmk_pol"></a>Policy for Exchange-managed mobile devices
Policy settings can be applied through the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] console, see [Manage settings and features on your devices with Microsoft Intune policies](../Topic/Manage_settings_and_features_on_your_devices_with_Microsoft_Intune_policies.md). For a detailed list of Exchange ActiveSync policy settings and features that are supported by specific mobile devices, see [Exchange ActiveSync Client Comparison Table](http://go.microsoft.com/fwlink/?LinkId=247270).

> [!NOTE]
> Upon connecting [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] to a Microsoft Exchange environment, all users managed through [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] will have their EAS policy reset to the current default policy on the Microsoft Exchange server, unless there is a more specific policy defined within [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].

## <a name="bkmk_acc"></a>Exchange Access rules for mobile devices
Exchange access rules for mobile devices determine the level of access to Exchange that is granted to mobile devices. These setting will affect all mobile devices, even the mobile devices not enrolled in [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]. You can start off by defining a **Default Rule** which will apply to any mobile device that does not have a custom rule applied to it. The following table contains the access levels managed by Exchange ActiveSync:

|Access level|Description|
|----------------|---------------|
|**Allow all mobile devices to access Exchange, unless a custom rule states otherwise**|In the allow access state, a mobile device can synchronize through Exchange ActiveSync and connect to the Exchange server to retrieve email and manipulate calendar information, contacts, tasks, and notes. This will continue as long as the device complies with the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]**Mobile Device Security Policy** that you have configured, unless the user or the specific mobile device has been blocked by the Exchange administrator.|
|**Block all mobile devices from accessing Exchange, unless a custom rule states otherwise**|A mobile device that is blocked because of a device access setting you configured will not be allowed to connect to the Exchange server and will receive HTTP 403 Forbidden errors. The user will receive an email message from the Exchange server telling them that the mobile device was blocked from accessing their mailbox. The user will not be able to read the email message on the blocked mobile device. You can add customized text to this message to provide instructions for users whose devices are blocked through the **Set User Notification** task.|
|**Quarantine all mobile devices so I can decide later for each individual mobile device, unless a custom rule states otherwise**|When a mobile device is quarantined, the mobile device is allowed to connect to the Exchange server. However, it is given only limited access to data. The user can add content to their own Calendar, Contacts, Tasks, and Notes folders but the server will not allow the device to retrieve any content from the user's mailbox. The user will receive a single email message that tells them that the mobile device is quarantined. This message will be received by the device and will also be available in the user's mailbox. You can add customized text to this message to provide instructions for users whose devices are quarantined through the **Set User Notification** task.|
An access strategy is a combination of a **Default Rule** and **Custom Rules** that apply to all mobile devices connected to exchange. The table below lists some example access strategies.

|Access Strategy|Description|
|-------------------|---------------|
|Allow list|You can use an allow list to grant access to a list of known devices and restrict access for everything else. To do this, you must create custom rules so that the specific devices you want are allowed to access users' mailboxes. As soon as you create such a rule, you must set the default access rule to block or quarantine all other devices. To add a new device to the allow list, create a new custom rule|
|Block list|You can use a block list to grant access to all devices by default, but to block access for a set of devices that you do not want to access your organization. You create a block list by creating custom rules to block the devices that you do not want to synchronize with the organization’s mailboxes. The default rule should be set to allow access to all devices that are not explicitly blocked by the existing rules. To add a new device or set of devices to the block list, create a new custom rule.|
|Mixed allow and block|In addition to creating allow and block lists, you can quarantine new mobile devices as they are introduced into the organization while you evaluate them. For example, if you have a block list for mobile devices that are not allowed within your organization, and an allow list for mobile devices that are allowed within the organization, you can set the default rule to quarantine. All other devices will automatically be quarantined, which lets you discover new devices as they are introduced to the organization and decide whether to add them to the allow list or the block list.|
The following procedure describes how to create a custom rule.

#### Create a Default Access Rule

1.  Open the [!INCLUDE[wit_adminconsole](../Token/wit_adminconsole_md.md)].

2.  In the workspace shortcuts pane, choose the **Policy** icon and choose **Exchange Access for Mobile Devices**.

3.  In the **Default Rule** list, select the Access Rule that you wish to apply to all mobile devices not covered by a rule or personal exemption. Choose **Save**.

The following procedure describes how to create a custom rule.

#### Create a Custom Access Rule

1.  Open the [!INCLUDE[wit_adminconsole](../Token/wit_adminconsole_md.md)].

2.  In the workspace shortcuts pane, choose the **Policy** icon and choose **Exchange Access for Mobile Devices**.

3.  In the **Custom Rules** list, Choose **Add Rule** and create a custom rule. Choose **Save**.

## See Also
[Get ready to enroll devices in Microsoft Intune](../Topic/Get_ready_to_enroll_devices_in_Microsoft_Intune.md)

