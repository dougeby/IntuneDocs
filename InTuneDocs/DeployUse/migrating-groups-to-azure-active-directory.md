---
# required metadata

title: Migrating to Azure Active Directory groups| Microsoft Intune
description: How your groups will be migrated from Intune to Azure AD
keywords:
author: nbigman
manager: angerobe
ms.date: 10/10/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 03b69afa-3548-4033-9039-191528f3fd99

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: damionw
#ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

## The new admin experience for groups
	
Based on your feedback to have one grouping and targeting experience across Enterprise Mobility & Security, we're converting Intune Groups to Azure Active Directory-based Security Groups. This will unify group management across Intune and Azure Active Directory (Azure AD). The new experience will keep you from having to duplicate groups between services, and provides extensibility using PowerShell and Graph. 

### How and when will I migrate to the new groups experience?
Current customers will be migrated over a period of time, beginning no earlier than December 2016. You will get a notice before your groups migrated. If you have any migration concerns, please contact our migration team at [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

### What new features will be available to me?
Here is the new functionality being introduced: 
 
-	 Azure AD Security Groups will be supported in Intune for all types of deployments. 
-	 Azure AD Security Groups will support grouping of devices along with users.
-	 Azure AD Security Groups will support dynamic groups with Intune device attributes. For example, you will be able to dynamically group devices based on platform, such as iOS. That way, when a new iOS device is enrolled in your organization, it will automatically be added to the iOS dynamic device group.
-	 Shared admin experiences for group management across Azure AD and Intune.
- The *Intune Service Administrator role* will be added to Azure AD to allow service admins in Intune to perform group management tasks in Azure AD.

 
### What Intune functionality won’t be available?
Though the group experience will improve, there will be some Intune functionality that will not be available after the migration.

#### Group management functionality

-	You will not be able to exclude members or groups when you create a new group. However, Azure AD dynamic groups will allow you to use attributes to create advanced rules to exclude members based on criteria. For example, you could create an advanced rule that includes all people in your Sales department in a security group, but not those who have the word "Assistant" in their title, with this advanced rule : `(user.department -eq "Sales") -and -not (user.jobTitle -contains "Assistant")`. For more information see [Using attributes to create advanced rules](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/).
-	There won’t be support for **Ungrouped Users** and **Ungrouped Devices** groups. Those groups won't be migrated.

#### Group dependent functionality

-	The Service Admin role will not have **Manage groups** permissions.
-	You won’t be able to group Exchange ActiveSync devices.  Your **All EAS Managed Devices** group will be converted from a group to a report view.
-  Pivoting with groups in reports will not be available.
-  Custom group targeting of notification rules will not be available.

### What should I do to prepare for this change?
 We have recommendations that will make this transition easier for you:
 
- Clean up any unwanted or unneeded Intune groups before migration.
- Evaluate your use of exclusion in groups, and consider how to redesign your groups so that you don't need to use exclusion, or so that you can use advanced rules to achieve the same purpose.
-  If you have admins who do not have permissions to create groups in Azure AD, ask your Azure AD administrator to add them to the **Intune Service Administrator** Azure AD role.

You can also learn more about Azure AD security groups:
-  For an overview, read [Managing access to resources with Azure Active Directory groups](https://azure.microsoft.com/en-us/documentation/articles/active-directory-manage-groups/).
-  For information about how to create and manage Azure AD groups, see [Managing groups in Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-manage-groups/).
-  For more information about advanced rules for security groups [Using attributes to create advanced rules](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/).

> [!NOTE]
You may notice that the Azure AD security group documentation does not discuss the creation of groups for devices. That functionality will be enabled in Azure AD before the Intune group migration begins.

## Migration details
Here are the details of how your Intune groups will be migrated to Azure AD security groups.

### Migration of existing groups

| Intune group becomes...|...Azure AD security group|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|Static user groups targeted by Intune policy|Static Azure AD security groups containing the same users|
|Dynamic user groups targeted by Intune policy|Static Azure AD security groups with an Azure AD security group hierarchy|
|Static device groups targeted by Intune policy|Static Azure AD security groups with devices|
|Dynamic device groups with device attributes, that are targeted by Intune policy|Dynamic Azure AD security groups with device attributes|
|A group with an include condition|A separate static Azure AD security group that will contain a group + any static/dynamic members that the include condition had allowed in Intune|
|A group with an exclude condition|...will not be migrated. Exclude conditions are not supported during the creation of static groups in Azure AD. An exclude condition can be used when creating a dynamic group in Azure AD.|
|The default groups **All Users**, **Ungrouped Users**, **All Devices**, **Ungrouped devices**, **All Computers**, **All Mobile Devices**, **All MDM managed devices**, and **All EAS managed devices**, that you use in Intune policy  |Azure AD security groups. Default groups that are not being used would have to be created by the customer when needed by using dynamic groups.|

### Changes in hierarchical views
Hierarchical view for groups in Intune 	Parent child relationship in Intune was a Superset-subset relationship, while in Azure AD that’s not the case. Child can have members that the parent didn’t have. Groups can also be cyclic in nature in Azure AD – a parent group can be a child group’s child.

### Attribute conversion during migration
Attributes are device properties that may be used in defining groups. This table describes how those criteria will be migrated to Azure AD security groups.

| Intune attribute|Azure AD attribute|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|Organizational Unit (OU) attribute for device groups|OU attribute for dynamic groups. Attribute values made available to the admin pertaining to each tenant by adding it as one of the tenant components for viewing.|
|Domain name attribute for device groups|Domain Name attribute for dynamic groups. Attribute values made available to the admin pertaining to each tenant by adding it as one of the tenant components for viewing|
|Security group as an attribute for user groups|Groups cannot be attributes in Azure AD dynamic queries. Dynamic groups can only contain user or device specific attributes.|
|Manager attribute for user groups|Advanced Rule for *manager* attribute in dynamic groups|
|All users from the parent user group|Static group with that group as a member|
|All mobile devices from the parent device group|Static group with that group as a member|
|All mobile devices managed by Microsoft Intune Direct Management|Management Type attribute with ‘MDM’ as value for dynamic group|
|All mobile devices managed by EAS|EAS devices cannot be grouped in Azure AD. Your **All EAS Managed Devices** group will be converted from a group to a report view.|
|Nested groups within static groups |Nested groups within static groups|
|Nested groups within dynamic groups|Dynamic group with one level of nesting|


## Migration of policies
While the group migration is taking place, you will continue to manage your policies in the Intune console. There will be a link in the Intune console to your Azure management console, where you will manage your groups. Your policies will continue to be deployed to the migrated Azure AD security groups that parallel your old Intune groups.

When all of Intune's functionality is migrated to the Azure management portal (around the first quarter of 2017), you will manage policies and groups there.

	 
### See also
[Managing access to resources with Azure Active Directory groups](https://azure.microsoft.com/en-us/documentation/articles/active-directory-manage-groups/)

[Managing groups in Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-manage-groups/)

[Using attributes to create advanced rules](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/)
