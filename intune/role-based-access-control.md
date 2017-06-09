---
# required metadata

title: RBAC with IntunetitleSuffix: "Intune Azure preview"
description: "Intune Azure preview: Learn how RBAC lets you control who can perform actions and make changes."
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/09/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: ca3de752-3caa-46a4-b4ed-ee9012ccae8e

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Role-based administration control (RBAC) with Intune

RBAC helps you control who can perform various Intune tasks within your organization, and who those tasks apply to. You can either use the built-in roles that cover some common Intune scenarios, or you can create your own roles. A role is defined by:

- **Definition** - The name of a role, and the permissions it configures.
- **Members** - The user, or group of users who will be given these permissions.
- **Scope** - The users or devices that a specified person (the member) can manage.
- **Assignment** - When the definition, members, and scope have been configured, the role is assigned.

Starting at the new Intune portal, **Azure Active Directory (Azure AD)** provides two Directory Roles which can be used with Intune. These roles are granted full permission to perform all activities in Intune:

- **Global Administrator:** Users with this role have access to all administrative features in Azure AD, as well as services that federate to Azure AD like Exchange Online, SharePoint Online, and Skype for Business Online. The person who signs up for the Azure AD tenant becomes a global administrator. Only global administrators can assign other Azure AD administrator roles. There can be more than one global administrator at your organization. Global admins can reset the password for any user and all other administrators.

- **Intune Service Administrator:** Users with this role have global permissions within Intune when the service is present. Additionally, this role provides the ability to manage users, devices, and create and manage groups.

- **User Account Administrator**: Users with this role can create and manage all aspects of users and groups. Additionally, this role includes the ability to manage support tickets and monitors service health. For example, this role does not allow deleting a global administrator, and while it does allow changing passwords for non-admins, it does not allow changing passwords for global administrators or other privileged administrators.

	> [!IMPORTANT]
	> The Intune Service Administrator role does not provide the ability to manage Azure AD’s conditional access settings.

	> [!NOTE]
	> Intune also shows three Azure AD extensions: Users, Groups and Conditional access.

## Roles created in the Intune classic console

The **Intune Service Administrators** with “Read Only” or “Helpdesk” console access are not migrated when your organization is migrated from the Intune classic console to Intune on Azure. Even though this role is not migrated, **Intune Service Administrators** can still have full permission to perform all activities in the Intune classic console.

You should re-assign your **Intune Service Administrators** from the classic console to new Intune roles and remove them from the classic portal.

> [!IMPORTANT]
> You might need to keep the Intune Service Administrator access in the classic console if your admins still need access to manage PC’s using with Intune.

## Built-in roles

The following roles are built into Intune and you can either customize these roles, or assign them to groups with no further configuration:

- **Help Desk Operator**: Performs remote tasks on users and devices and can assign applications or policies to users or devices. 
- **Policy and Profile Manager**: Manages compliance policy, configuration profiles, Apple enrollment and corporate device identifiers.
- **Read Only Operator** - Views user, device, enrollment, configuration and application information and cannot make changes to Intune.
- **Application Manager** - Manages mobile and managed applications, and can read device information.

### To assign a built-in role

1. On the **Intune roles**, choose the custom role you want to assign.

2. On the <*role name*> - **Properties** blade, choose **Manage**, then **Assignments**. On this blade, you can also edit or delete existing roles.

3. On the custom role blade, choose **Assign**.

4. On the **Role Assignments** blade, enter a **Name** and optional **Description** for the assignment, and then choose the following:
	- **Members** - Select a group that contains the user you want to give the permissions to.
	- **Scope** - Select a group containing the users who the member above will be allowed to manage.
<br></br>
5. When you are done, click **OK**. The new assignment is displayed in the list of assignments.

### Intune RBAC table

- Download the [Intune RBAC table](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a) to see more details on what each role can do.

## Custom roles

If none of the built-in roles suit your needs, you can create your own role. Additionally, you can create a custom role that includes any permissions required for a job function. For example, if an IT department group manages applications, policies and configuration profiles, you can add all those permissions together in one custom role.

> [!IMPORTANT]
> To create, edit, or assign roles, your account must have one of the following permissions in Azure AD:
> - **Global Administrator**
> - **Intune Service Administrator**

### To create a custom role

1. Sign into the [Azure portal](https://portal.azure.com) with your Intune credentials.

2. Choose **More services** from the left menu, then type **Intune** in the text box filter.

3. Choose **Intune**, the Intune Dashboard opens, choose **Intune roles**.

4. On the **Intune roles** blade, choose **Intune roles**, choose **Add custom**.

5. On the **Add Custom Role** blade, enter a name and description for the new role, then click **Permissions**.

3. On the **Permissions** blade, choose the permissions you want to use with this role. Use the custom role settings reference list later in this topic to help you.

4. When you are done, choose **OK**.

5. On the **Add Custom Role** blade, click **Create**. The new role is displayed in the list on the **Intune roles** blade.

### To assign a custom role

1. On the **Intune roles**, choose the custom role you want to assign.

2. On the <*role name*> - **Properties** blade, choose **Manage**, then **Assignments**. On this blade, you can also edit or delete existing roles.

3. On the custom role blade, choose **Assign**.

4. On the **Role Assignments** blade, enter a **Name** and optional **Description** for the assignment, and then choose the following:
	- **Members** - Select a group that contains the user you want to give the permissions to.
	- **Scope** - Select a group containing the users who the member above will be allowed to manage.
<br></br>
5. When you are done, click **OK**. The new assignment is displayed in the list of assignments.

## Custom role settings reference

When you create a custom role, you can configure one or more of the following settings:

### Device configurations

|||
|-|-|
|**Assign**|Assign device profiles to groups.|
|**Create**|Create device profiles.|
|**Delete**|Delete device profiles.|
|**Read**|Read device profiles and their properties.|
|**Update**|Update existing device profiles.|

### Managed apps

|||
|-|-|
|**Assign**|Assign managed apps to groups.|
|**Create**|Add new managed apps to Intune.|
|**Delete**|Delete managed apps.|
|**Read**|Read managed apps and their properties.|
|**Update**|Update existing managed apps.|
|**Wipe**|Wipe managed apps from devices.|

### Managed devices

|||
|-|-|
|**Delete**|Delete managed devices from Intune.|
|**Read**|View information about managed devices in the Intune portal.|
|**Update**|Update information about managed devices.|

### Mobile apps

|||
|-|-|
|**Assign**|Assign mobile apps to groups.|
|**Create**|Add new mobile apps to Intune.|
|**Delete**|Delete mobile apps.|
|**Read**|Read mobile apps and their properties.|
|**Update**|Update existing mobile apps.|

### Organization

|||
|-|-|
|**Read**|Read tenant settings.|
|**Update**|Update tenant settings.|

### Remote tasks

|||
|-|-|
|**Bypass Activation Lock**|Remove the activation lock from an iOS device without the user’s Apple ID and password. |
|**Disable Lost Mode**|Disable Lost Mode. Lost mode lets you specify a message and a phone number that will be displayed on the lock screen of the device.|
|**Enable Lost Mode**|Enable Lost Mode. Lost mode lets you specify a message and a phone number that will be displayed on the lock screen of the device.|
|**Locate Device**|-|
|**Reboot Now**|Causes the device to restart.|
|**Remote Lock**|Locks a device. The device owner must use their passcode to unlock it.|
|**Reset Passcode**|Generates a new passcode for the device which will be displayed on the <device name> Overview blade.|
|**Retire**|Removes only company data managed by Intune. Does not remove personal data from the device.|
|**Wipe**|Returns the device to its default settings.|

### Telecom expenses

|||
|-|-|
|**Read**|Read Telecom Expense Management (TEM) settings.|
|**Update**|Update Telecom Expense Management (TEM) settings.|

### Terms and conditions

|||
|-|-|
|**Assign**|Assign terms and conditions to groups.|
|**Create**|Create terms and conditions settings.|
|**Delete**|Delete terms and conditions settings.|
|**Read**|Read terms and conditions settings in the Intune portal.|
|**Update**|Update existing terms and conditions settings.|

## See also

- [RBAC with Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles)
- [Assign roles using Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-users-assign-role-azure-portal)