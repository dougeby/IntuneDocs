---
# required metadata

title: Administrative accounts, websites, and permissions in Microsoft Intune | Microsoft Intune
description: administrative accounts permissions websites
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: db3075e7-38fd-4dfe-b266-26aed10ac8ea

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Administrative accounts, websites, and permissions in Microsoft Intune

Before you set up Microsoft Intune, review this topic and other requirements listed in [What to know before you start Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md).

To administer Intune, you'll use:
- Two types of administrator accounts
- User accounts with additional permissions
- Two, web-based administration consoles/portals to grant your administrators access to the things they should manage.

The following sections explain these accounts and portals.

## Administrator accounts and user accounts with special permissions

Below are the accounts and permissions that you'll use for Intune.

### Tenant administrator
|Permission levels|More information|
|--------------------------|-------------------------|
|Tenant administrators are assigned one administrator role, which defines the administrative scope for that user and the tasks they can manage.<br /><br />Administrator roles are common between the different Microsoft cloud services, although some services might not support some roles.<br /><br /> Microsoft Intune uses the following roles:<br /><br />- Global administrator<br />- Billing administrator<br />- Password administrator<br />- Service support administrator<br />- User management administrator|By default, the account you use to create your Microsoft Intune subscription is a tenant administrator with the global administrator role.<br /></br>  As a tenant administrator, you use the [!INCLUDE[wit_icp_1](../includes/wit_icp_1_md.md)] to manage your subscription for [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] and assign tenant administrators from  the [!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)].<br /><br />Use a tenant administrator with the global administration role to access the [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] to assign your first service administrator. As a best practice, do not use a tenant administrator for day-to-day management tasks. A tenant administrator does not require a license to [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] to access the [!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)].<br /><br />The tenant administrator is a common concept between Microsoft cloud services. When you subscribe to [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], your service is a tenant of Microsoft Azure AD. See the Azure AD tenant section in [What is an Azure AD directory?](http://technet.microsoft.com/library/jj573650.aspx).|


### Service administrator
|Permission levels|More information|
|--------------------------|-------------------------|
|Service administrators are assigned one of the following permissions:<br /><br />**Full access**: Grants access to all areas of the [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)], with no restrictions. Can also add and manage other service administrators.<br /><br />**Read-only access**: Grants read permission to all areas of the [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)]. A read-only service admin cannot modify data, but can run reports.<br /><br />**Helpdesk - Groups Node**: Grants permissions that enable the service administrator to perform only a set of tasks commonly associated with helpdesk scenarios. For information about this permission set, see [Customize Intune console views according to admin roles](/intune/deploy-use/control-what-admins-can-see-in-the-microsoft-intune-admin-console).|By default, [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] does not assign a service administrator. Instead, you must use a tenant administrator with the global administrator role to assign the first service administrator for your subscription. </br></br> As a service administrator, you use the [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] to manage day-to-day tasks for [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].<br /><br />You assign service administrators from the administrator console. A service administrator requires a license to [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] before the account can access the administration console.|



### Device enrollment managers
|Permission levels|More information|
|--------------------------|-------------------------|
|Device enrollment managers are standard user accounts that have additional permission to enroll more than five devices.|By default, each [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] user can enroll up to five devices. However, you can give a user account the device enrollment manager permission and then use that account to enroll large groups of corporate-owned devices. This is useful when the devices might be assigned to users on a temporary basis, or might serve in a kiosk mode where a user-to-device association is not required.|


## Administrative websites for Intune
 Different administrative tasks require you to use one of the following administrative websites, which you can access using a [supported web browser](supported-web-browsers.md).

- [Office 365 portal](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Microsoft Intune administrator console](https://admin.manage.microsoft.com/)

### [Office 365 portal](http://go.microsoft.com/fwlink/p/?LinkId=698854)

**As a tenant administrator, use this portal to manage your subscription**, including the following tasks, when permitted by your administrator role:

- Manage user accounts for the subscription, and configure directory synchronization from your on-premises Active Directory.
- Manage groups of users, called security groups.
- Assign licenses to use [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] to users.
- Configure the domain name that you use with your subscription. The domain name defines the account that users sign in with.
- Manage billing and purchase details for your subscription, including the number of licenses you have, or the amount of cloud storage space you can use.
- Find links to view the health of the [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] service.
- As a tenant administrator, you can sign in to the Office 365 portal to manage the subscription, even when your account is not assigned a license to use [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].
- Any users who have a license to Intune, but who are not administrators, can use this portal to reset their account password and edit their profile.
- To access the Office 365 portal, your account must have a sign-in status of **Allowed**. This status is different from having a license to the subscription. By default, all user accounts are **Allowed**.


### [Microsoft Intune administrator console](https://admin.manage.microsoft.com/)

**As a service administrator, use this portal to manage day-to-day operations** including:

- Set policies for computers and mobile devices.
- Upload and deploy software like software updates and apps.
- Manage [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] Endpoint Protection on computers.
- View device status and run reports.
- Sign in to this portal. You must have either service administrator permissions or be a tenant administrator with the global administrator role to sign in to this portal.


Only users with service administrator permissions or tenant administrators with the global administrator role can sign in to this portal. To access the administration console, your account must have a license to use [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] and a sign-in status of **Allowed**.

Learn more about [adding users for your subscription](start-with-a-paid-subscription-to-microsoft-intune-step-3.md) and [assigning licenses for your subscription](start-with-a-paid-subscription-to-microsoft-intune-step-4.md).

 ### See also
 [What to know before you start Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md)
