---
# required metadata

title: Sync Active Directory and add users to Intune | Microsoft Intune
description:  Synchronize on-premises users with Azure AD and grant administrator permissions for your Intune subscription
keywords:
author: nathbarnms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
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

# Add and synchronize users for Intune

As an administrator you can add users to Intune in a number of ways to let them enroll devices and access company resources. To add users, you can either add users directly or synchronize users from your on-premises Active Directory. Once you have added uses, you can give users additional permissions including tenant administrator, service administrator, and device enrollment manager permissions.

This topic helps you:

- [Add users to Intune](#add-users-to-intune)
- [Sync users from Active Directory](#sync-users-from-active-directory)
- [Grant additional Intune permissions](#grant-intune-permissions)

## Add users to Intune
You can manually added users to your Intune subscription via the [Office 365 portal](http://go.microsoft.com/fwlink/p/?LinkId=698854), they are not automatically assigned an Intune license. Instead, at a later time, an Intune tenant administrator must edit the user account to assign a license to the user from the Office 365 portal. For guidance, see [Add users individually or in bulk to the Office 365 portal](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).

## Sync Active Directory and add users to Intune
You can configure directory synchronization to import user accounts from your on-premises Active Directory to Microsoft Azure Active Directory (Azure AD). Having your on-premises Active Directory service connected with all of your Azure Active Directory-based services makes managing user identity much simpler. You can also configure single sign-on features to make the authentication experience for your users familiar and easy.

Making things even easier, when you use multiple services with the same [Azure AD tenant](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/), the user accounts that you have previously synchronized are available to all cloud-based services that share the same Azure AD tenant subscription.

## Synchronize on-premises users with Azure AD
The only tool that you need to synchronize your user accounts with Azure AD is the [Azure AD Connect wizard](https://www.microsoft.com/download/details.aspx?id=47594). The Azure AD Connect wizard provides a simplified and guided experience for connecting your on-premises identity infrastructure to the cloud.  Choose your topology and needs (single or multiple directories, password sync or federation), and the wizard will deploy and configure all components required to get your connection up and running. Including: sync services, Active Directory Federation Services (AD FS), and the Azure AD PowerShell module.

> [!TIP]
> Azure AD Connect encompasses functionality that was previously released as Dirsync and Azure AD Sync. Learn more about [directory integration](http://technet.microsoft.com/library/jj573653.aspx). To learn about the benefits of synchronizing user accounts from your local directory to Azure AD, see [Similarities between Active Directory and Azure AD](http://technet.microsoft.com/library/dn518177.aspx).

## Grant Intune permissions

To administer Intune, you can use:
- Two types of administrator accounts
- User accounts with additional permissions
- Two, web-based administration consoles/portals to grant your administrators access to the things they should manage.

After you've added users to your Intune subscription, we recommend that you grant a few user accounts administrative credentials. The console that you use to assign administrative credentials depends on the type of administrator you want to assign:

-   **Tenant administrator**: Use the **Microsoft Intune account portal** to assign this type of administrator to manage your subscription, including billing, cloud storage, and managing the users who can use Intune.

-   **Service administrator**: Use the **Microsoft Intune administrator console** to assign this type of administrator for day-to-day tasks including management of mobile devices or computers, deploying policy or software, and running reports.

The following sections explain these accounts and portals.

### Tenant administrator
|Permission levels|More information|
|--------------------------|-------------------------|
|Tenant administrators are assigned one administrator role, which defines the administrative scope for that user and the tasks they can manage.<br /><br />Administrator roles are common between the different Microsoft cloud services, although some services might not support some roles.<br /><br /> Microsoft Intune uses the following roles:<br /><br />- Global administrator<br />- Billing administrator<br />- Password administrator<br />- Service support administrator<br />- User management administrator|By default, the account you use to create your Microsoft Intune subscription is a tenant administrator with the global administrator role.<br /></br>  As a tenant administrator, you use the [!INCLUDE[wit_icp_1](../includes/wit_icp_1_md.md)] to manage your subscription for Intune and assign tenant administrators from  the [!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)].<br /><br />Use a tenant administrator with the global administration role to access the [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] to assign your first service administrator. As a best practice, do not use a tenant administrator for day-to-day management tasks. A tenant administrator does not require a license to Intune to access the [!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)].<br /><br />The tenant administrator is a common concept between Microsoft cloud services. When you subscribe to Intune, your service is a tenant of Microsoft Azure AD. See the Azure AD tenant section in [What is an Azure AD directory?](http://technet.microsoft.com/library/jj573650.aspx).|

[Office 365 portal](http://go.microsoft.com/fwlink/p/?LinkId=698854)

**As a tenant administrator, use this portal to manage your subscription**, including the following tasks, when permitted by your administrator role:

- Manage user accounts for the subscription, and configure directory synchronization from your on-premises Active Directory.
- Manage groups of users, called security groups.
- Assign licenses to use Intune to users.
- Configure the domain name that you use with your subscription. The domain name defines the account that users sign in with.
- Manage billing and purchase details for your subscription, including the number of licenses you have, or the amount of cloud storage space you can use.
- Find links to view the health of the Intune service.
- As a tenant administrator, you can sign in to the Office 365 portal to manage the subscription, even when your account is not assigned a license to use Intune.
- Any users who have a license to Intune, but who are not administrators, can use this portal to reset their account password and edit their profile.
- To access the Office 365 portal, your account must have a sign-in status of **Allowed**. This status is different from having a license to the subscription. By default, all user accounts are **Allowed**.

### Service administrator
|Permission levels|More information|
|--------------------------|-------------------------|
|Service administrators are assigned one of the following permissions:<br /><br />**Full access**: Grants access to all areas of the [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)], with no restrictions. Can also add and manage other service administrators.<br /><br />**Read-only access**: Grants read permission to all areas of the [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)]. A read-only service admin cannot modify data, but can run reports.<br /><br />**Helpdesk - Groups Node**: Grants permissions that enable the service administrator to perform only a set of tasks commonly associated with helpdesk scenarios. For information about this permission set, see [Customize Intune console views according to admin roles](/intune/deploy-use/control-what-admins-can-see-in-the-microsoft-intune-admin-console).|By default, Intune does not assign a service administrator. Instead, you must use a tenant administrator with the global administrator role to assign the first service administrator for your subscription. </br></br> As a service administrator, you use the [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] to manage day-to-day tasks for Intune.<br /><br />You assign service administrators from the administrator console. A service administrator requires a license to Intune before the account can access the administration console.|

[Microsoft Intune administrator console](https://manage.microsoft.com/)

**As a service administrator, use this portal to manage day-to-day operations** including:

- Set policies for computers and mobile devices.
- Upload and deploy software like software updates and apps.
- Manage Endpoint Protection on computers.
- View device status and run reports.
- Sign in to this portal. You must have either service administrator permissions or be a tenant administrator with the global administrator role to sign in to this portal.

### Device enrollment managers
|Permission levels|More information|
|--------------------------|-------------------------|
|Device enrollment managers are standard user accounts that have additional permission to enroll more than five devices.|By default, each [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] user can enroll up to five devices. However, you can give a user account the device enrollment manager permission and then use that account to enroll large groups of corporate-owned devices. This is useful when the devices might be assigned to users on a temporary basis, or might serve in a kiosk mode where a user-to-device association is not required.|

>[!div class="step-by-step"]

>[&larr; **Domain settings**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Manage Intune licenses** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-4.md)  
