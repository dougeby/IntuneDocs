---
# required metadata

title: Sync Active Directory and add users to Intune | Microsoft Intune
description:  Synchronize on-premises users with Azure AD and grant administrator permissions for your Intune subscription
keywords:
author: nathbarnms.author: nathbarn
manager: angrobe
ms.date: 08/29/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 6e9ec662-465b-4ed4-94c1-cff0fe18f126

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Sync Active Directory and add users to Intune
You can configure directory synchronization to import user accounts from your on-premises Active Directory to Microsoft Azure Active Directory (Azure AD). Having your on-premises Active Directory service connected with all of your Azure Active Directory-based services makes managing user identity much simpler. You can also configure single sign-on features to make the authentication experience for your users familiar and easy.

Making things even easier, when you use multiple services with the same [Azure AD tenant](http://technet.microsoft.com/library/jj573650.aspx#BKMK_WhatIsAnAzureADTenant), the user accounts that you have previously synchronized are available to all cloud-based services that share the same Azure AD tenant subscription.

## Synchronize on-premises users with Azure AD
The only tool that you need to synchronize your user accounts with Azure AD is the [Azure AD Connect wizard](https://www.microsoft.com/download/details.aspx?id=47594). The Azure AD Connect wizard provides a simplified and guided experience for connecting your on-premises identity infrastructure to the cloud.  Choose your topology and needs (single or multiple directories, password sync or federation), and the wizard will deploy and configure all components required to get your connection up and running. Including: sync services, Active Directory Federation Services (AD FS), and the Azure AD PowerShell module.

> [!TIP]
> Azure AD Connect encompasses functionality that was previously released as Dirsync and Azure AD Sync. Learn more about [directory integration](http://technet.microsoft.com/library/jj573653.aspx). To learn about the benefits of synchronizing user accounts from your local directory to Azure AD, see [Similarities between Active Directory and Azure AD](http://technet.microsoft.com/library/dn518177.aspx).

## Grant administrator permissions

To administer Intune, you'll use:
- Two types of administrator accounts
- User accounts with additional permissions
- Two, web-based administration consoles/portals to grant your administrators access to the things they should manage.

After you've added users to your Intune subscription, we recommend that you grant a few user accounts [administrative credentials](administrative-accounts-websites-perms.md). The console that you use to assign administrative credentials depends on the type of administrator you want to assign:

-   **Tenant administrator**: Use the **Microsoft Intune account portal** to assign this type of administrator to manage your subscription, including billing, cloud storage, and managing the users who can use Intune.

-   **Service administrator**: Use the **Microsoft Intune administrator console** to assign this type of administrator for day-to-day tasks including management of mobile devices or computers, deploying policy or software, and running reports.

The following sections explain these accounts and portals.

## Administrator accounts and user accounts with special permissions

Below are the accounts and permissions that you will use for Intune.

### Tenant administrator
|Permission levels|More information|
|--------------------------|-------------------------|
|Tenant administrators are assigned one administrator role, which defines the administrative scope for that user and the tasks they can manage.<br /><br />Administrator roles are common between the different Microsoft cloud services, although some services might not support some roles.<br /><br /> Microsoft Intune uses the following roles:<br /><br />- Global administrator<br />- Billing administrator<br />- Password administrator<br />- Service support administrator<br />- User management administrator|By default, the account you use to create your Microsoft Intune subscription is a tenant administrator with the global administrator role.<br /></br>  As a tenant administrator, you use the [!INCLUDE[wit_icp_1](../includes/wit_icp_1_md.md)] to manage your subscription for Intune and assign tenant administrators from  the [!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)].<br /><br />Use a tenant administrator with the global administration role to access the [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] to assign your first service administrator. As a best practice, do not use a tenant administrator for day-to-day management tasks. A tenant administrator does not require a license to Intune to access the [!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)].<br /><br />The tenant administrator is a common concept between Microsoft cloud services. When you subscribe to Intune, your service is a tenant of Microsoft Azure AD. See the Azure AD tenant section in [What is an Azure AD directory?](http://technet.microsoft.com/library/jj573650.aspx).|


### Service administrator
|Permission levels|More information|
|--------------------------|-------------------------|
|Service administrators are assigned one of the following permissions:<br /><br />**Full access**: Grants access to all areas of the [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)], with no restrictions. Can also add and manage other service administrators.<br /><br />**Read-only access**: Grants read permission to all areas of the [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)]. A read-only service admin cannot modify data, but can run reports.<br /><br />**Helpdesk - Groups Node**: Grants permissions that enable the service administrator to perform only a set of tasks commonly associated with helpdesk scenarios. For information about this permission set, see [Customize Intune console views according to admin roles](/intune/deploy-use/control-what-admins-can-see-in-the-microsoft-intune-admin-console).|By default, Intune does not assign a service administrator. Instead, you must use a tenant administrator with the global administrator role to assign the first service administrator for your subscription. </br></br> As a service administrator, you use the [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] to manage day-to-day tasks for Intune.<br /><br />You assign service administrators from the administrator console. A service administrator requires a license to Intune before the account can access the administration console.|



### Device enrollment managers
|Permission levels|More information|
|--------------------------|-------------------------|
|Device enrollment managers are standard user accounts that have additional permission to enroll more than five devices.|By default, each [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] user can enroll up to five devices. However, you can give a user account the device enrollment manager permission and then use that account to enroll large groups of corporate-owned devices. This is useful when the devices might be assigned to users on a temporary basis, or might serve in a kiosk mode where a user-to-device association is not required.|




>[!div class="step-by-step"]

>[&larr; **Domain settings**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Manage Intune licenses** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-4.md)  
