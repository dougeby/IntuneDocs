---
# required metadata

title: RBAC with Microsoft Intune
description: Learn how Role-Based Access Control (RBAC) lets you control who can perform actions and make changes in Microsoft Intune.
keywords:
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/22/2019
ms.topic: conceptual
ms.prod:
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology:
ms.assetid: ca3de752-3caa-46a4-b4ed-ee9012ccae8e

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
---

# Role-based access control (RBAC) with Microsoft Intune

RBAC helps you control who can perform various Intune tasks within your organization, and who those tasks apply to. You can either use the built-in roles that cover some common Intune scenarios, or you can create your own roles. A role is defined by:

- **Role definition**: The name of a role, the resources it manages, and the permissions granted for each resource.
- **Members**: The user groups that are granted the permissions.
- **Scope (Groups)**: The user or device groups that the members can manage.
- **[Scope (Tags)](https://docs.microsoft.com/intune/scope-tags)**: Tags where the role assignment applies.
- **Assignment**: When the definition, members, and scope have been configured, the role is assigned.

![Intune RBAC example](./media/intune-rbac-1.PNG)

## Azure Active Directory roles with Intune access

| Azure Active Directory role | All Intune data | Intune audit data |
| --- | --- | --- |
| Global Administrator | Read/write | Read/write |
| Intune Service Aministrator | Read/write | Read/write |
| Conditional Access Administrator | None | None |
| Security Administrator | Read only | Read only |
| Security Operator | Read only | Read only |
| Security Reader | Read only | Read only |
| Global Reader | Read only | Read only |
| Compliance Administrator | None | Read only |
| Compliance Data Administrator | None | Read only |

**Azure Active Directory (Azure AD)** provides two Directory Roles which can be used with Intune. These roles are granted full permission to perform all activities in Intune:

- **Global Administrator:** Users with this role have access to all administrative features in Azure AD, as well as services that federate to Azure AD like Exchange Online, SharePoint Online, and Skype for Business Online. The person who signs up for the Azure AD tenant becomes a global administrator. Only global administrators can assign other Azure AD administrator roles. There can be more than one global administrator at your organization. Global admins can reset the password for any user and all other administrators.

- **Intune Service Administrator:** Users with this role have global permissions within Intune when the service is present. Additionally, other than any superseding Azure restrictions, this role provides the ability to manage users, devices, and create and manage Intune groups.

- **Conditional Access Administrator:** Users with this role only have permissions to view, create, modify, and delete conditional access policies.

	> [!IMPORTANT]
	> The Intune Service Administrator role does not provide the ability to manage Azure AD’s conditional access settings.
    >
	> To be assigned an Intune role, the user must have an Intune license.

	> [!TIP]
	> Intune also shows three Azure AD extensions: **Users**, **Groups**, and **Conditional access**, which are controlled using Azure AD RBAC. Additionally, the **User Account Administrator** only performs AAD user/group activities and does not have full permissions to perform all activities in Intune. For more information, see [RBAC with Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles).

## Roles created in the Intune classic portal

Only Intune **Service Administrators** users with "Full" permissions get migrated from the Intune classic portal to Intune in the Azure portal. You must reassign Intune **Service Administrators** users with "Read-Only" or "Helpdesk" access into the Intune roles in the Azure portal, and remove them from the classic portal.

> [!IMPORTANT]
> You might need to keep the Intune Service Administrator access in the classic portal if your admins still need access to manage PCs using Intune.

## Built-in roles

You can assign built-in roles to groups without further configuration. You can't delete or edit a built-in role.

- **Help Desk Operator**: Performs remote tasks on users and devices, and can assign applications or policies to users or devices.
- **Policy and Profile Manager**: Manages compliance policy, configuration profiles, Apple enrollment, corporate device identifiers, and security baselines.
- **Read Only Operator**: Views user, device, enrollment, configuration, and application information. Can't make changes to Intune.
- **Application Manager**: Manages mobile and managed applications, can read device information and can view device configuration profiles.
- **Intune Role Administrator**: Manages custom Intune roles and adds assignments for built-in Intune roles. It's the only Intune role that can assign permissions to Administrators.
- **School Administrator**: Manages Windows 10 devices in [Intune for Education](introduction-intune-education.md), and can take the following actions: 

    |Permission|Operation|
    |---|---|
    |Audit Data|Read|
    |DeviceConfigurations|Assign, Create, Delete, Read, Update|
    |Device Enrollment Managers|Read, Update|
    |Managed Devices|Read, Update<!--, Delete [To be added in 1803]-->|
    |Mobile apps|Assign, Create, Delete, Read, Update|
    |Reports|Read|
    |Remote Actions|Clean PC, Reboot, Remote Lock, Retire, Sync Devices, Wipe|
    |Organization|Read|

### To assign a built-in role

1. Sign into the [Azure portal](https://portal.azure.com).
2. Choose **All services** > **Intune**. Intune is located in the **Monitoring + Management** section.
3. On the **Intune** blade, choose **Roles** > **All roles**.
4. On the **Intune roles - All roles** blade, choose the built-in role you want to assign.

5. On the <*role name*> - **Overview** blade, choose **Manage** > **Assignments**.

6. On the custom role blade, choose **Assign**.

7. On the **Role Assignments** blade, enter an **Assignment name** and optional **Assignment description** for the assignment.

8. For **Members (Groups)**, choose a group that contains the user you want to give the permissions to.

9. For **Scope (Groups)**, choose a group containing the users who the member above will be allowed to manage.

10. For **Scope (Tags)**, choose tags where this role assigment will be applied.

11. When you're done, choose **OK**. The new assignment is displayed in the list of assignments.

### Intune RBAC table

- Download the [Intune RBAC table](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a) to see more details on what each role can do.

## Custom roles

You can create a custom role that includes any permissions required for a specific job function. For example, if an IT department group manages applications, policies, and configuration profiles, you can add all those permissions together in one custom role.

> [!IMPORTANT]
> To create, edit, or assign roles, your account must have one of the following permissions in Azure AD:
> - **Global Administrator**
> - **Intune Service Administrator**

### To create a custom role

1. Sign into the [Azure portal](https://portal.azure.com) with your Intune credentials.

2. Choose **All services** from the left menu, then type **Intune** in the text box filter.

3. Choose **Intune** > **Roles** > **All roles** > **Add**.

4. On the **Add Custom Role** blade, enter a name and description for the new role, then click **Permissions**.

5. On the **Permissions** blade, choose the permissions you want to use with this role. Use the [Intune RBAC table](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a) to help you decide which permissions you want to apply.

6. On the **Scope (Tags)** blade, choose tags where this custom role will be applied.

7. When you're done, choose **OK**.

7. On the **Add Custom Role** blade, click **Create**. The new role is displayed in the list on the **Intune roles - All roles** blade.

### To assign a custom role

Follow the same steps as [To assign a built-in role](https://docs.microsoft.com/intune/role-based-access-control#to-assign-a-built-in-role) and select the custom role.

## Next steps

- [Use the Intune Helpdesk operator role with the troubleshooting portal](help-desk-operators.md)



## See also

- [Assign roles using Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-users-assign-role-azure-portal)
- Learn about [Microsoft Graph API support for role-based access in Intune](https://docs.microsoft.com/graph/api/resources/intune-rbac-roledefinition?view=graph-rest-1.0)
- Get the [PowerShell SDK for the Intune Graph API](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1902.1.10)