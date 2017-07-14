---
# required metadata

title: Set up the Exchange connector for on-premises EAS with Intune
titleSuffix: "Intune Azure"
description: "Intune Azure: Exchange ActiveSync MDM - Use Connector tool to enable communication between the Intune and on-premises Exchange Server"
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/08/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: a0376ea1-eb13-4f13-84da-7fd92d8cd63c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: chrisgre
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Set up the Intune on-premises Exchange Connector in Microsoft Intune Azure

On-premises Exchange Server environments can use the Intune on-premises Exchange connector to manage devices access to on-premises Exchange mailboxes based on whether or not the devices are enrolled into Intune and compliant with Intune device compliance policies. The on-premises Exchange connector is also responsible for discovering mobile devices that connect to on-premises Exchange Servers by synchronizing the existing Exchange Active Sync (EAS) record with Intune.

> [!IMPORTANT]
> Intune only supports one on-premises Exchange Connector connection of any type per subscription.

To set up a connection that enables Microsoft Intune to communicate with the on-premises Exchange Server, you need to follow the steps below:

1.  Download the Intune on-premises Exchange Connector from the Intune portal.
2.  Install and configure the Intune on-premises Exchange connector.
3.  Validate the Exchange connection.

## On-premises Exchange Connector requirements
The following table lists the requirements for the computer on which you install the On-premises Exchange Connector.

|Requirement|More information|
|---------------|--------------------|
|Operating systems|Intune supports the On-premises Exchange Connector on a computer that runs any edition of Windows Server 2008 SP2 64-bit, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2.<br /><br />The Connector is not supported on any Server Core installation.|
|Microsoft Exchange|On-premises Connectors require Microsoft Exchange 2010 SP1 or later or legacy Exchange Online Dedicated. To determine if your Exchange Online Dedicated environment is in the **new** or **legacy** configuration, contact your account manager.|
|Mobile device management authority| [Set the mobile device management authority to Intune](https://docs.microsoft.com/intune-classic/deploy-use/prerequisites-for-enrollment#step-2-mdm-authority-set).|
|Hardware|The computer on which you install the connector requires a 1.6 GHz CPU with 2 GB of RAM and 10 GB of free disk space.|users-add.md
|Active Directory synchronization|Before you can use Connector to connect Intune to your Exchange Server, you must [set up Active Directory synchronization](users-add.md) so that your local users and security groups are synchronized with your instance of Azure Active Directory.|
|Additional software|A full installation of Microsoft .NET Framework 4.5 and Windows PowerShell 2.0 must be installed on the computer that hosts the connector.|
|Network|The computer on which you install the connector must be in a domain that has a trust relationship to the domain that hosts your Exchange Server.<br /><br />The computer requires configurations to enable it to access the Intune service through firewalls and proxy servers over Ports 80 and 443. Domains that are used by Intune include manage.microsoft.com, &#42;manage.microsoft.com, and &#42;.manage.microsoft.com.|


### Exchange cmdlet requirements

You must create an Active Directory user account that is used by the Intune Exchange Connector. The account must have permission to run the following required Windows PowerShell Exchange cmdlets:


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

## Download the On-premises Exchange Connector software installation package

1. On a supported Windows Server operating system for the On-premises Exchange Connector, open the [Azure portal](http://portal.azure.com) and sign in with a user account that is an administrator in the on-premises Exchange server, and that has a license to use Exchange Server.

2. Choose **More services** from the left menu, then type **Intune** in the text box filter.

3. Choose **Intune**, the Intune Dashboard opens, choose **On-premises access**.

4. On the **On-premises access - Exchange ActiveSync connector** blade, from the **Setup** section, choose **Download the on-premises connector**.

5.  The On-premises Exchange Connector is contained in a compressed (.zip) folder that can be opened or saved. In the **File Download** dialog box, choose **Save** to store the compressed folder to a secure location.

	> [!IMPORTANT]
	> Do not rename or move the files that are in the on-premises Exchange Connector folder. Moving or renaming the folder's contents will cause the Exchange Connector installation to fail.

## Install and configure the Intune On-premises Exchange Connector
Perform the following steps to install the Intune On-premises Exchange Connector. The On-premises Exchange Connector can only be installed once per Intune subscription, and only on one computer. If you try to configure an additional On-premises Exchange Connector, the new connection will replace the original one.

1.  On a supported operating system for the On-premises Connector, extract the files in **Exchange_Connector_Setup.zip** to a secure location.

2.  After the files are extracted, open the extracted folder and double-click **Exchange_Connector_Setup.exe** to install the On-premises Exchange Connector.

    > [!IMPORTANT]
    > If the destination folder is not a secure location, you should delete the certificate file **WindowsIntune.accountcert** after you install the On-premises Connector.

3.  In the **Microsoft Intune Exchange Connector** dialog box, select either **On-premises Microsoft Exchange Server** or **Hosted Microsoft Exchange Server**.

  ![Choose your Exchange Server type](./media/intune-sa-exchange-connector-config.png)

  For an On-premises Exchange server, provide either the server name or the fully-qualified domain name of the Exchange server that hosts the **Client Access Server** role.

  For a hosted Exchange server, provide the Exchange server address. To find the hosted Exchange server URL:

    1. Open the Outlook Web App for Office 365.

    2. Choose the **?** icon at the upper left, and then select **About**.

    3. Locate the **POP External Server** value.

    4. Choose **Proxy Server** to specify proxy server settings for your hosted Exchange server.
        1. Select **Use a proxy server when synchronizing mobile device information**.

        2. Enter the **proxy server name** and the **port number** to be used to access the server.

        3. If it's necessary to provide user credentials to access the proxy server, select **Use credentials to connect to the proxy server**. Then enter the **domain\user** and the **password**.

        4. Choose **OK**.

    5. In the **User (Domain\user)** and **Password** fields, enter the credentials that are necessary to connect to your Exchange server.

    6.  Provide the necessary administrative credentials to send notifications to a user’s Exchange Server mailbox. You can configure these notifications with Conditional Access policies in Intune.

        Ensure that the Autodiscover service and Exchange Web Services are configured on the Exchange Client Access Server. For more information, see [Client Access server](https://technet.microsoft.com/library/dd298114.aspx).

    7.  In the **Password** field, provide the password for this account to enable Intune to access the Exchange Server.

    8. Choose **Connect**.

	> [!NOTE]
	> It might take a few minutes for the connection to be configured.

During configuration, the Exchange Connector stores your proxy settings to enable access to the Internet. If your proxy settings change, you will have to reconfigure the Exchange Connector to apply the updated proxy settings to the Exchange Connector.

After the Exchange Connector sets up the connection, mobile devices that are associated with users that are managed in Exchange Connector are automatically synchronized and added to the Exchange Connector. This synchronization might take some time to complete.

> [!NOTE]
> If you have installed the On-premises Exchange Connector, and if at some point you delete the Exchange connection, you must uninstall the On-premises Exchange Connector from the computer onto which it was installed.

## Validate the Exchange connection

After you have successfully configured the Exchange Connector, you can view the status of the connection and the last successful synchronization attempt. To validate the Exchange Connector connection:

- On the Intune Dashboard, choose **On-premises access**. Under **Manage**, select **Exchange on-premises access** to verify the connection status.

You can also check the time and date of the last successful synchronization attempt.

## Next steps
[Create a conditional access policy for Exchange on-premises](conditional-access-exchange-create.md)
