---
title: Configure the Microsoft Intune Exchange connector for on-premises Exchange
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 
author: jeffgilb
---
# Configure the Intune connector for on-premises Exchange

## Requirements
To prepare to connect [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] to your Exchange Server, you must first fulfill the following requirements. You may have already fulfilled these requirements when you set up [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)].

|Requirement|More information|
|---------------|--------------------|
|Set the MDM authority to [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)]|[Set mobile device management authority and configure Microsoft Intune](set-mobile-device-management-authority-and-configure-microsoft-intune.md)|
|Verify you have hardware requirements for the on-premises connector|[Requirements for the On-Premises Connector](network-infrastructure-requirements-for-microsoft-intune.md#BKMK_ExchanceConnectorReqs)|
|Configure a user account with permission to run the designated list of Windows PowerShell cmdlets|PowerShell cmdlets for on-premises Exchange Connector (see below)|

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

## Download, install, and configure the Exchange Connector
To set up a connection that enables [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] to communicate with the Exchange Server that hosts the mobile devices’ mailboxes, you must download and configure the On-Premises Connector tool from the [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] administrator console.


![alt text](./media/ExchangeConnector.gif "Configure the Exchange Connector")

<figure class="no-border">
    <img src="./media/ExchangeConnector.gif" alt="" />
</figure>

### To download the On-Premises Connector software installation package

1.  Open the [!INCLUDE[wit_adminconsole](./includes/wit_adminconsole_md.md)].

2.  In the workspace shortcuts pane, choose **ADMIN**.
![IntuneSA1aclickADMIN](/Image/IntuneSA1aclickADMIN.png)

3.  In the navigation pane, under **Mobile Device Management**, expand **Microsoft Exchange** and then choose **Setup Exchange Connection**.
![IntuneSA1bSetupExchangeConnection](/Image/IntuneSA1bSetupExchangeConnection.png)

4.  On the **Setup Exchange Connection** page, choose **Download On-Premises Connector**.
![IntuneSA1cOnpremConnector](/Image/IntuneSA1cOnpremConnector.png)

5.  The On-Premises Connector software is contained in a compressed (.zip) folder that can be opened or saved. In the **File Download** dialog box, choose **Save** to store the compressed folder to a secure location.

> [!IMPORTANT]
> Do not rename or move the extracted files or the On-Premises Connector software installation will not succeed.

Perform the following steps to install the [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] On-Premises Connector.

> [!IMPORTANT]
> The On-Premises Connector can only be installed once per [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] subscription, and only on one computer. If you attempt to install the On-Premises Connector a second time, you will replace the initial Exchange connection.

### To install the On-Premises Connector

1.  Extract the files in **Exchange_Connector_Setup.zip** into a secure location.

2.  After the files are extracted, double-click **Exchange_Connector_Setup.exe** to install the On-Premises Connector.

    > [!IMPORTANT]
    > If the destination folder is not a secure location, you should delete the certificate file **WindowsIntune.accountcert** after you install the On-Premises Connector.

> [!NOTE]
> You can only set up one Exchange connection per [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] account. If you try to configure an additional connection, it will replace the original connection with the new one.

### Configure the On-Premises Exchange Connector

1.  In the **Exchange server** field, select your Exchange server environment type, either **On-premises Microsoft Exchange Server** or select **Hosted Microsoft Exchange Server** for Exchange on Microsoft Office 365.
![IntuneSA1dconfigureExchConnector](/Image/IntuneSA1dconfigureExchConnector.png)

2.  For an on-premises Exchange server, provide either the server name or fully qualified domain name of the Exchange server that hosts the Client Access server role.

3.  For a hosted Exchange server in Microsoft Office 365, provide the Exchange server address. To find the hosted Exchange server URL:

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

7.  Provide administrative credentials necessary to send notifications to a user’s Exchange mailbox. These notifications are configurable via Conditional Access policies using Intune. For more information on these policies see [Enable access to company resources with Microsoft Intune - deleted](enable-access-to-company-resources-with-microsoft-intune---deleted.md).

    Ensure that the Autodiscover service and Exchange Web Services are configured on the Exchange Client Access Server. For more information on that see [Client Access server](https://technet.microsoft.com/library/dd298114.aspx).

8.  In the **Password** field, provide the password for this account to enable [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] to access the Exchange Server.

9. Choose **Connect**.

    It may take a few minutes while the connection is set up.

    During configuration, the [!INCLUDE[wit_exch_2](./includes/wit_exch_2_md.md)] stores your proxy settings to enable access to the Internet. If your proxy settings change, you will have to reconfigure the [!INCLUDE[wit_exch_2](./includes/wit_exch_2_md.md)] in order to apply the updated proxy settings to the [!INCLUDE[wit_exch_2](./includes/wit_exch_2_md.md)].

After the [!INCLUDE[wit_exch_2](./includes/wit_exch_2_md.md)] sets up the connection, mobile devices associated with users that are managed in [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] are automatically synchronized and added to the [!INCLUDE[wit_adminconsole](./includes/wit_adminconsole_md.md)]. This synchronization may take some time to complete.

To view the status of the connection and the last successful synchronization attempt, in the [!INCLUDE[wit_adminconsole](./includes/wit_adminconsole_md.md)] choose the **ADMIN** workspace, and under **Mobile Device Management**, choose **Microsoft Exchange**.
![IntuneSA2aServiceToServiceConnectorVerification](/Image/IntuneSA2aServiceToServiceConnectorVerification.PNG)

> [!NOTE]
> If you have installed the On-Premises Connector, and if at some point you delete the Exchange connection, you must uninstall the On-Premises Connector from the computer onto which it was installed.

## Validate your Exchange connection

-   After you have successfully configured the [!INCLUDE[wit_exch_2](./includes/wit_exch_2_md.md)], in the [!INCLUDE[wit_adminconsole](./includes/wit_adminconsole_md.md)] choose the **ADMIN** workspace, and under **Mobile Device Management**, choose **Microsoft Exchange** and validate that the details you provided appear under **Exchange Connection Information**.

-   You can also check the time and date of the last successful synchronization attempt.