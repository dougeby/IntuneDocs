---
# required metadata

title: Role-based access control (RBAC) for Microsoft Intune | Intune Azure preview | Microsoft Docs
description: "Intune Azure preview: Learn how RBAC lets you control who can perform actions and make changes."
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/18/2016
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

# Role-based access control (RBAC) for Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

In simple terms, Intune **roles** (or RBAC) help you control who can perform various Intune actions, and who those actions apply to. You can either use the built-in roles that cover some common Intune scenarios, or you can create your own roles.

A role is defined by:

- **Definition** - The name of a role, and the permissions it configures.
- **Members** - The user, or group of users who will be given these permissions.
- **Scope** - The users or devices that a specified person (the member) can manage.
- **Assignment** - When the definition, members, and scope have been configured, the role is assigned.

## Built-in roles

The following roles are built into Intune and you can either customize these roles, or assign them to groups with no further configuration.

- **Intune Administrator** - Has full permissions for all Intune operations.
- **Application Manager** - Manage and deploy applications and profiles.
- **Configuration Policy Manager** - Manage and deploy configuration settings and profiles.
- **Helpdesk Operator** - Perform remote tasks and view user and device	information.
- **Read Only Operator** - View information in the Intune portal without the ability to make changes.


## Custom roles

If none of the built-in roles suit your needs, you can create your own role by choosing settings that span many of the capabilities of Intune. You can see a list of the available settings later in this topic.

### Example

You hire a new IT admin who will be in charge of deploying and managing apps to users in your London office. The users are in an Azure AD group named **London**. You want to ensure the IT admin cannot deploy apps to users in any other office. You take the following actions:

- Assign the built-in **Application Manager** role with the following properties:
	- **Members** - Select a group that contains the IT admin who will be deploying apps
	- **Scope** - Select the **London** Azure AD group.

	>[!IMPORTANT]
	>To create, edit, or assign roles, your account must have one of the following permissions in Azure AD:
	>- **Global AAD Admin**
	>- **Intune Service Admin**

### How to create a custom role

1. Sign into the Azure portal.
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Access control**.
![Access control workload](./media/axxess-control.png)
1. On the **Roles** blade of the **Access control** workload, choose **Add custom**.
2. On the **Add Custom Role** blade, enter a name and description for the new role, and then click **Permissions**.
3. On the **Permissions** blade, choose the permissions you want to use with this role. Use the custom role settings reference list later in this topic to help you.
4. When you are done, click **OK**.
5. On the **Add Custom Role** blade, click **Create**.

The new role is displayed in the list on the **Roles** blade.

## How to assign a role

1. On the **Roles** blade of the **Access control** workload, choose the built-in, or custom role you want to assign.
2. On the <*role name*> - **Properties** blade, choose **Manage** > **Assignments**.
	>[!TIP]
	>On this blade, you can also edit or delete existing roles.
3. On the next blade, choose **Assign**.
4. On the **Role Assignments** blade, enter a **Name** and optional **Description** for the assignment, and then choose the following:
	- **Members** - Select a group that contains the user you want to give the permissions to.
	- **Scope** - Select a group containing the users who the member above will be allowed to manage.
5. When you are done, click **OK**.

The new assignment is displayed in the list of assignments.

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