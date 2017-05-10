---
# required metadata

title: How to assign apps to groups | Microsoft Docs
titleSuffix: "Intune Azure preview"
description: "Intune Azure preview: Once you've added an app to Intune, you'll want to assign it to groups of users or devices."
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/09/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: dc349e22-9e1c-42ba-9e70-fb2ef980ef7a

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---

# How to assign apps to groups with Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Once you've added an app to Intune, you'll want to get it out to users and devices. You do this by assigning it.

Apps can be assigned to devices whether or not they are managed by Intune. Use the following table to help you understand the various options for assigning apps to users and devices:

||||
|-|-|-|-|
|&nbsp;|Devices enrolled with Intune|Devices not enrolled with Intune|
|Assign to users|Yes|Yes|
|Assign to devices|Yes|No|
|Assign wrapped apps, or apps incorporating the Intune SDK (for app protection policies)|Yes|Yes|
|Assign apps as Available|Yes|Yes|
|Assign apps as Required|Yes|No|
|Uninstall apps|Yes|No|
|End users install available apps from Company Portal app|Yes|No|
|End users install available apps from web-based Company Portal|Yes|Yes|

> [!NOTE]
> Currently, you can assign iOS and Android apps (both line of business and store-purchased) to devices that are not enrolled with Intune.

## Changes to how you assign apps to groups in the Intune preview

In the Intune Azure preview, you no longer use Intune groups to assign apps; you now use Azure Active Directory (Azure AD) security groups. Because of this, you’ll need to learn about some changes to the way app assignments work, particularly when you have assigned apps to Intune child groups.
The most important thing to note is that the concept of child groups does not exist in Azure AD. However, some groups might contain the same members. In this case, the behavior between classic Intune and the Intune Azure preview is different. The following table illustrates this:

||||||
|-|-|-|-|-|
|**Intune Classic (before tenant migration)**|-|**Intune Azure (after tenant migration is complete)**|-|**More information**|
|**Parent group assignment intent**|**Child group assignment intent**|**Resulting assignment intent for common members of previous parent and child group**|**Resulting assignment intent action for members of parent group**|-|	
|Available|Required|Required and Available|Available|Required and Available means that apps assigned as required can also be seen in the Company Portal app.
|Not Applicable|Available|Not Applicable|Not Applicable|Workaround: Remove the ‘Not Applicable’ assignment intent from the Intune parent group.
|Required|Available|Required and Available|Required|-|
|Required and Available<sup>1</sup>|Available|Required and Available|Required and Available|-|	
|Required|Not Applicable|Required|Required|-|	
|Required and Available|Not Applicable|Required and Available|Required and Available|-|	
|Required|Uninstall|Required|Required|-|	
|Required and Available|Uninstall|Required and Available|Required and Available|-|
<sup>1</sup> For managed iOS store apps only, when you add these to Intune and assign them as Required, they are automatically created with both Required, and Available intents.

You can take the following actions to avoid assignment conflicts:

1.	If you previously assigned apps to related Intune parent and child groups, consider removing these assignments before your tenant migration begins.
2.	Remove child groups from parent groups, and create a new group containing the members of the old child group. You can then create a new app assignment to this group.
Notes: If the previous parent group was “All Users”, you’ll need to create a new dynamic group that does not include members of the child group.
You must make any changes to groups in the [Azure Portal](https://portal.azure.com/) for user and device groups. The [Classic Azure Portal](https://manage.windowsazure.com/) will only allow you to make changes to user groups.


## How to assign an app

1. Sign into the Azure portal.
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Mobile apps**.
1. In the **Mobile Apps** workload, choose **Manage** > **Apps**.
2. On the list of apps blade, click the app you want to assign.
3. On the <*app name*> - **Overview** blade, choose **Manage** > **Assignments**.
4. Choose **Select Groups** then, on the **Select groups** blade, choose the Azure AD groups to which you want to assign the app.
5. For each app you choose, choose an **assignment type** for the app from:
	- **Available** - Users install the app from the Company Portal app or website.
	- **Not Applicable** - The app is not installed or shown in the Company Portal.
	- **Required** - The app is installed on devices in the selected groups.
	- **Uninstall** - The app is uninstalled from devices in the selected groups.
	- **Available with or without enrollment** - Assign this app to groups of users whose devices are not enrolled with Intune. See the table above for help.
6. Once you are done, choose **Save**.

The app is now assigned to the group you chose.

See [How to monitor apps](monitor-apps.md) for information to help you monitor app assignments.
