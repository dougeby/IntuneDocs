---
title: MD Maintain Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 61d342c8-172a-4db8-8cf6-1e886845e516
---
# MD Maintain Microsoft Intune
As a cloud service hosted by Microsoft, the [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] service is maintained automatically with little maintenance required by you. However, you should be familiar with the following maintenance tasks that might be required to maintain your service:

-   [Common maintenance tasks](../Topic/Maintain-Microsoft-Intune.md#BKMK_Maintenance)

-   [Change your contact preferences](../Topic/Maintain-Microsoft-Intune.md#BKMK_ManagePreferences)

-   [Manage partner relationships](../Topic/Maintain-Microsoft-Intune.md#BKMK_ManagePartners)

-   [Decommission your subscription](../Topic/Maintain-Microsoft-Intune.md#BKMK_DecommissionIntune)

## <a name="BKMK_Maintenance"></a>Common maintenance tasks

|Task|Details|
|--------|-----------|
|**Update the [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] service**|[!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] is a cloud service, and Microsoft manages service updates for you. Each time you connect to an administrative web portal, you connect to the most current version available.<br /><br />Typically, service updates do not cause a visible change. However, important updates are detailed in the **Notice** board, which is displayed when you connect to the [!INCLUDE[wit_adminconsole](../Token/wit_adminconsole_md.md)] after a service update. You can also view notices on the **Notice** page of the **Alerts** workspace of the [!INCLUDE[wit_adminconsole](../Token/wit_adminconsole_md.md)].<br /><br />When there are updates to the client software, you might be prompted to download and deploy the updated client.<br /><br />See [Microsoft Intune Service Updates](http://technet.microsoft.com/library/dn292747.aspx).|
|**Back up and recover [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] data in the cloud**|As part of the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] service, the infrastructure and data that is managed for you includes configurations you make for your instance of, data and status from the devices you manage, data you upload to the cloud storage, such as software you deploy and license information, and user accounts that you add to your instance of Microsoft Azure AD.<br /><br />Data you upload for use with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] is maintained in the cloud but does not replace the need to maintain an on-premises backup for the source of that information.<br /><br />For information about how Microsoft manages your data, download the [Microsoft Intune Privacy and Data Protection Overview](http://download.microsoft.com/download/C/C/8/CC8065C4-829F-4635-B731-1D39287444C0/Windows_Intune_Privacy_and_Data_Protection_Overview.pdf) white paper.|
|**Reinstall the On-Premises Exchange Connector**|There are no options to back up or restore this connector. When you install or reinstall this connector, the new instance replaces any previously configured connector.|
|**Reinstall the Service to Service Connector**|The configuration of this connector is maintained in your cloud storage and does not require backup or restoration. When you configure this connector, the new instance replaces any previously configured connector.|
|**Back up individual devices and computers**|[!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] does not manage the backup or recovery for data, settings, or applications on mobile devices or computers that you manage with the service.|

## <a name="BKMK_ManagePreferences"></a>Change your contact preferences
Administrators for [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] have the option to receive product-related communications from Microsoft:

**To manage the communications you receive**:

1.  In the [Microsoft Intune account portal](http://go.microsoft.com/fwlink/?LinkId=698854), click **Message Center**.

2.  Edit the **Contact preferences** section to provide your contact details and to select the communications you want to receive.

3.  Click **Save**.

You will continue to receive email messages related to your billing and service accounts even if you choose not to receive additional product information.

## <a name="BKMK_ManagePartners"></a>Manage partner relationships
If you do not currently work with a partner, you can find one on the [Microsoft Pinpoint](http://go.microsoft.com/fwlink/?linkid=235605) website. Partner availability depends on the services you use and the country or region where you will use those services.

**Manage a Partner for your subscription**

Partners are advisors who can provide sales, support, and technical expertise to help you set up and maintain your subscription. You can add, change, or remove a Microsoft partner from your subscription at any time.

Before you add or change a partner for your subscription, you must have the partner’s Microsoft Partner ID.

**To manage a partner for a subscription**:

1.  In the [Microsoft Intune account portal](http://go.microsoft.com/fwlink/?LinkId=698854), click **Manage**.

2.  Click [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)].

3.  On the **Subscription details** page, in the right pane under **Partner information**, click:

    -   **Add** if you are adding a partner to your subscription.

    -   **Edit** if you are changing or removing a partner.

4.  Update the information for **Microsoft partner ID**:

    1.  To add or change a partner, enter the Partner ID of the partner you want to work with.

    2.  To remove a partner, clear the Partner ID

5.  Click **OK** to save the change.

**Manage a delegated administrator**

When you subscribe to [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], you are given administrator permissions and can assign administrator permissions to other users in your company. However, when you want someone else to administer the service, you can delegate this role to a Microsoft partner. When you authorize a partner to take on this role, the partner is referred to as a *delegated administrator*.

**Add a delegated administrator**: This process must be initiated by your Microsoft partner.

1.  The partner sends you an email message asking you if you want to give them permissions to act as a delegated administrator.

2.  Read the partner's terms in the email message.

3.  To authorize the agreement, click the link provided in the message, which will take you to an authorization page.

**View your delegated administrators**:

1.  In the [Microsoft Intune account portal](http://go.microsoft.com/fwlink/?LinkId=698854), under **Support**, click **Overview**.

2.  On the **Support overview** page, under **Delegated administrators**, click **Manage your delegated administrators**.

**Remove a delegated administrator**:

When you remove a delegated administrator, you remove the partner’s permissions to access and modify your service. You can remove the delegated partner at any time.

1.  In the [Microsoft Intune account portal](http://go.microsoft.com/fwlink/?LinkId=698854), under **Support**, click **Overview**.

2.  On the **Support overview** page, under **Delegated administrators**, click **Manage your delegated administrators**.

3.  On the **Delegated administrators** page, select the partner that you want to remove and click **Remove delegated administrator**.

## <a name="BKMK_DecommissionIntune"></a>Decommission your subscription
Use the following information to remove data from devices and your infrastructure when you plan to no longer use [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)].

|Task|Details|
|--------|-----------|
|**Cancel your subscription**|To cancel your subscription, you must [Contact Assisted Phone Support for Microsoft Intune](http://technet.microsoft.com/library/jj839713.aspx).<br /><br />To help protect your privacy, we ask you to provide the following information regarding your account: the work or school account you use to sign in to the cloud service, the first and last name of the primary contact for your organization, the name of your organization as it shows on your account, and the complete street address of your organization.<br /><br />Before you cancel your subscription:<br /><br />**Remove domains from your cloud service**: If you added your own domain names for your organization to use with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], you need to [Remove a domain](http://msdn.microsoft.com/library/azure/jj151817.aspx#bkmk_remove).<br /><br />**Save your data**: The data associated with your online service is deleted 90 days after you cancel your subscription.<br /><br />After your subscription is canceled, if you change your mind, you can reinstate your subscription within 90 days by contacting Support by phone.|
|**Remove data from devices and computers**|When you plan to no longer use the service to manage a device, you might want to uninstall the applications you manage with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], remove the [!INCLUDE[wit_iwportal_1](../Token/wit_iwportal_1_md.md)] app, and uninstall the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] client software from computers.<br /><br />Typically, applications and configurations that are introduced by [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] remain in place after you stop using [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]. Therefore, plan to use the built-in options to wipe devices to remove sensitive information, and plan to uninstall applications before ending active management. The process to uninstall applications is app-specific.<br /><br />Be aware that settings previously enforced or set by remain in place on the device. When the settings are no longer enforced, they can be changed by the owner of the device.<br /><br />For information about retiring devices from [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], see the following topics:<br /><br />**Mobile devices**: See [Help protect your data with remote wipe, remote lock, or passcode reset using Microsoft Intune](../Topic/Help-protect-your-data-with-remote-wipe,-remote-lock,-or-passcode-reset-using-Microsoft-Intune.md).<br /><br />**Computers**: See the "To retire a computer" section in [Common Windows PC management tasks with the Microsoft Intune computer client](../Topic/Common-Windows-PC-management-tasks-with-the-Microsoft-Intune-computer-client.md).|
|**Remove infrastructure**|[!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]has no common infrastructure or software that you uninstall from your servers. However, the following are examples of optional tools you might use with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] that you can uninstall when no longer used in your environment:<br /><br />On-Premises Exchange Connector<br /><br />Tools for Active Directory synchronization, including Directory Sync tool, Microsoft Active Directory Federation Services 2.0 (AD FS), AD FS 2.0 Proxy, and TThird-party Identity Provider.<br /><br />Before uninstalling a tool or solution, ensure it is no longer in use. For example, you might use a solution such as the Active Directory Sync Tool to synchronize your local users with Azure AD. If you continue to subscribe to other cloud services like Office 365, you might need to retain the tool for use by that service.|
|**Remove data from the cloud**|When you choose to no longer subscribe to [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], you can use the [!INCLUDE[wit_icp_2](../Token/wit_icp_2_md.md)] and [!INCLUDE[wit_adminconsole](../Token/wit_adminconsole_md.md)] to actively remove information and data you store in the cloud. This data can include your user and device information, software you uploaded to deploy to devices, and custom configurations such as groups and reports.<br /><br />If you do not remove your data from the cloud before your subscription ends, it enters a 90-day grace period during which you can continue to access and manage your data in [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]. However, during this grace period, you cannot manage devices by using the service.<br /><br />After the grace period expires, Microsoft deletes all instances of your data automatically, and that information is no longer available. For more information, see “Data disposition” in the [Microsoft Intune Privacy and Data Protection Overview](http://download.microsoft.com/download/C/C/8/CC8065C4-829F-4635-B731-1D39287444C0/Windows_Intune_Privacy_and_Data_Protection_Overview.pdf) white paper.|

## See Also
[Technical reference for Microsoft Intune](../Topic/Technical-reference-for-Microsoft-Intune.md)

