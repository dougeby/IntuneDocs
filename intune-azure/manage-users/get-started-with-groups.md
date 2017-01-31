---
# required metadata

title: Get started with groups in the Intune Azure portal preview | Microsoft Docs
description: Learn what's new with groups in the Intune Azure portal preview
keywords:
author: robstackmsft
ms.author: robstack
manager: angerobe
ms.date: 01/18/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 323f384d-8a76-4adc-999b-e508d641bfa1

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: damionw
#ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Get started with groups

[!INCLUDE[azure preview](../includes/azure_preview.md)]

We've heard your feedback and have made changes to how you work with groups in Microsoft Intune.
If you are using Intune from the Azure portal, your Intune groups have been migrated to Azure Active Directory security groups.

The benefit to you is that you will now use the same groups experience across all of you Enterprise Mobility + Security, and Azure AD apps. Additionally, you'll be able to use PowerShell and Graph API to extend and customize this new functionality.

Azure AD security groups support all types of Intune deployments to both users and devices. Additionally, you can use Azure AD dynamic groups that automatically update based on the attributes you supply. For example, you could create a group of devices that run iOS 9. Whenever a new device that runs iOS 9 is enrolled, it will be automatically added to the dynamic group.

## What is not available?

Some of the Intune groups capabilities you previously might have used are not available in Azure AD:

- The **Ungrouped Users** and **Ungrouped Devices** Intune groups are no longer available.
- The option to **Exclude specific members** from a group does not exist in the Azure portal. However, you can use an Azure AD security group with advanced rules to replicate this behavior. For example, you could create an advanced rule that includes all people in your Sales department in a security group, but not those who have the word "Assistant" in their title, by using this advanced rule:
 `(user.department -eq "Sales") -and -not (user.jobTitle -contains "Assistant")`.
- The **All Exchange ActiveSync Managed Devices** group that's built-in to the Intune console was not migrated to Azure AD. However, you can still access information about EAS managed devices from the Azure portal.


## How to get started?

- Read the following Azure AD topics to learn about Azure AD security groups and how they work:
	-  [Managing access to resources with Azure Active Directory groups](https://azure.microsoft.com/en-us/documentation/articles/active-directory-manage-groups/).
	-  [Managing groups in Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-manage-groups/).
	-  [Using attributes to create advanced rules](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/).
-  Make sure that any admins who need to create groups are added to the **Intune Service Administrator** Azure AD role. Note that the Azure AD Service Admin role does not have **Manage Group** permissions.
-  If you used groups with the option **Exclude specific members**, consider whether you can redesign these groups to not need exclusions, or whether you can use advanced rules in your Azure AD query to achieve the same result.


## What happened to Intune groups?

| Groups in Intune|Group in Azure AD|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|Static user group|Static Azure AD security group|
|Dynamic user group|Static Azure AD security groups with an Azure AD security group hierarchy|
|Static device group|Static Azure AD security group|
|Dynamic device group|Dynamic Azure AD security group|
|A group with an include condition|Static Azure AD security group containing any static or dynamic members from the include condition in Intune|
|A group with an exclude condition|Not migrated|
|The built-in groups, **All Users**, **Ungrouped Users**, **All Devices**, **Ungrouped devices**, **All Computers**, **All Mobile Devices**, **All MDM managed devices**, and **All EAS managed devices**|Azure AD security groups|

In Intune, all groups have to have a parent group. Groups can only contain members from their parent group. In Azure AD, child groups can contain members that the parent group does not have.

Attributes are device properties that may be used in defining groups. This table describes how those criteria will be migrated to Azure AD security groups.

| Attribute in Intune|Attribute in Azure AD|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|Organizational Unit (OU) attribute for device groups|OU attribute for dynamic groups.|
|Domain name attribute for device groups|Domain Name attribute for dynamic groups.|
|Security group as an attribute for user groups|Groups cannot be attributes in Azure AD dynamic queries. Dynamic groups can only contain user or device specific attributes.|
|Manager attribute for user groups|Advanced Rule for *manager* attribute in dynamic groups|
|All users from the parent user group|Static group with that group as a member|
|All mobile devices from the parent device group|Static group with that group as a member|
|All mobile devices managed by Intune|Management Type attribute with ‘MDM’ as value for dynamic group|
|Nested groups within static groups |Nested groups within static groups|
|Nested groups within dynamic groups|Dynamic group with one level of nesting|

## What happens to policies and apps you previously deployed?

Policies and apps continue to be deployed to groups, just like before. However, you'll now manage these groups from the Azure portal, instead of the classic Intune console.
