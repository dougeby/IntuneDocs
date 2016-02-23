---
title: Administrative accounts, websites, and permissions in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: 
ms.assetid: 
author: Staciebarker
---
# Administrative accounts, websites, and permissions in Microsoft Intune

Before you set up [!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)], review this topic and the information in the list below. You might also want to review [Choose how to manage devices with Microsoft Intune](introduction-to-microsoft-intune.md). After you are familiar with the capabilities of [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)], you should be ready to set up your subscription. If you start with a trial subscription, you can convert it later to a full subscription (see [How to buy Intune](https://www.microsoft.com/server-cloud/products/microsoft-intune/overview.aspx)).

- [General capabilities of Intune](what-to-know-before-setting-up-microsoft-intune.md#BKMK_general_capabilities)
- [Intune supported web browsers](supported-web-browsers.md)
- [Network infrastructure requirements for Microsoft Intune](network-infrastructure-requirements-for-microsoft-intune.md)
- [Microsoft Intune Company Portal](microsoft-intune-company-portal.md)
- [Intune integration with Microsoft cloud services and products](integration-with-cloud-services.md)
- [Intune network bandwidth use](network-bandwidth-use.md)
- [Domain names for Microsoft Intune](domain-names-for-intune.md)

You use two types of administrator accounts, user accounts with additional permissions, and two separate administration consoles to grant your admins access to the things they should manage. The following sections explain these accounts and portals.

## <a name="BKMK_AdminAccounts"></a>Intune administrator accounts and special permissions

|Account type|Permission levels|More information|
|----------------|---------------------|--------------------|
|**Tenant administrator**|Tenant administrators are assigned one administrator role, which defines the administrative scope for that user and the tasks they can manage.<br /><br />Administrator roles are common between the different Microsoft cloud services although some services might not support some roles. [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] uses the following roles:<br /><br />- **Global administrator**<br />- **Billing administrator**<br />- **Password administrator**<br />- **Service support administrator**<br />- **User management administrator**|By default, the account you use to create your [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] subscription is a tenant administrator with the global administrator role.<br />                        **As a tenant administrator, you use the [!INCLUDE[wit_icp_1](./includes/wit_icp_1_md.md)] to manage your subscription for [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)].** and assign tenant administrators from within the [!INCLUDE[wit_icp_2](./includes/wit_icp_2_md.md)].<br /><br />Use a tenant administrator with the global administration role to access the [!INCLUDE[wit_adminconsole](./includes/wit_adminconsole_md.md)] to assign your first service administrator. As a best practice, do not use a tenant administrator for day-to-day management tasks. A tenant administrator does not require a license to [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] to access the [!INCLUDE[wit_icp_2](./includes/wit_icp_2_md.md)].<br /><br />The tenant administrator is a common concept between Microsoft cloud services. When you subscribe to [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)], your service is a [tenant of Microsoft Azure AD](http://technet.microsoft.com/library/jj573650.aspx).|
|**Service administrator**|Service administrators are assigned one of the following permissions:<br /><br />**Full access**: Grants access to all areas of the [!INCLUDE[wit_adminconsole](./includes/wit_adminconsole_md.md)], with no restrictions. Can also add and manage other service administrators.<br /><br />**Read-only access**: Grants read permission to all areas of the [!INCLUDE[wit_adminconsole](./includes/wit_adminconsole_md.md)]. A read-only service admin cannot modify data, but can run reports.<br /><br />**Helpdesk - Groups Node**: Grants permissions that enable the service administrator to only perform a set of tasks commonly associated with helpdesk scenarios. For information about this permission set, see [Control what admins can see in the Microsoft Intune admin console](control-what-admins-can-see-in-the-microsoft-intune-admin-console.md).|By default, [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] does not assign a service administrator. Instead, you must use a tenant administrator with the global administrator role to assign the first service administrator for your subscription. **As a service administrator, you use the [!INCLUDE[wit_adminconsole](./includes/wit_adminconsole_md.md)] to manage day-to-day tasks for [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)]**.<br /><br />You assign service administrators from within the administrator console. A service administrator requires a license to [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] before the account can access the administration console.|
|**Device enrollment manager**|[Device enrollment managers](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) are standard user accounts that have additional permission to enroll more than five devices.|By default, each [!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)] user can enroll up to five devices.<br /><br />However, you can give a user account the device enrollment manager permission and then use that account to enroll large groups of corporate-owned devices. This is useful when the devices might be assigned to users on a temporary basis, or serve in a kiosk mode where a user to device association is not required.|

## <a name="BKMK_AdminWebsites"></a>Administrative websites for Intune
 Different administrative tasks require you to use one of the following administrative websites, which you can access using a [supported browser](supported-web-browsers.md)

- [Microsoft Intune account portal](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Microsoft Intune administrator console](https://admin.manage.microsoft.com/)

### [Microsoft Intune account portal](http://go.microsoft.com/fwlink/p/?LinkId=698854)

**As a tenant administrator, use this portal to manage your subscription**, including the following tasks when permitted by your administrator role:

- Manage user accounts for the subscription and configure directory synchronization from your on-premises Active Directory.
- Manage groups of users, called security groups.
- Assign licenses to use [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] to users.
- Configure the domain name that you use with your subscription. The domain name defines the account that users sign in with.
- Manage billing and purchase details for your subscription, including the number of licenses you have, or the amount of cloud storage space you can use.
- Find links to view the health of the [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] service.
- As a tenant administrator, you can sign in to the account portal to manage the subscription even when your account is not assigned a license to use [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)].
- Any user who has a license to [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] but is not an administrator can use this portal to reset their account password and edit their profile.
- To access the account portal, your account must have a sign-in status of **Allowed**. This status is distinct from being granted a license to the subscription. By default, all user accounts are **Allowed**.


### [Microsoft Intune administrator console](https://admin.manage.microsoft.com/)

**As a service administrator, use this portal to manage day-to-day operations** including:

- Set policies for computers and mobile devices.
- Upload and deploy software like software updates and apps.
- Manage [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] Endpoint Protection on computers.
- View device status and run reports.
- Users who don't have service administrator permissions cannot sign in to this portal, except for users who are tenant administrator with the global administrator role.
- To access the administration console, your account must have a license to use [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] and a sign-in status of **Allowed**. By default, all user accounts are set to **Allowed**.

Learn more about [adding users for your subscription](get-started-with-a-paid-subscription-to-microsoft-intune-step-3.md) and [assigning licenses for your subscription](get-started-with-a-paid-subscription-to-microsoft-intune-step-4.md).
 
 ### See also
 [What to know before you start](what-to-know-before-setting-up-microsoft-intune.md)
