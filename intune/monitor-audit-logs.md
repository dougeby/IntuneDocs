---
# required metadata

title: Audit logs for Intune actions
description: 
keywords:
author: dougeby
manager: angrobe
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 6ee841cc-5694-4ba1-8f66-1d58edec30a4

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: [ALIAS]
#ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---
Audit logs provide you with a record of activities that generate a change in Microsoft Intune. Create, Update (edit), Delete, and Assign actions, or remote tasks, generate audit events that you can review. You can review audit logs for most Intune workloads. 

## Review audit logs for Intune workloads
Review audit logs in the Monitoring group for each Intune workload.  
1. Sign into the [Azure portal](https://portal.azure.com).
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose the workload for which you want to review audit logs.
4. In the **Monitoring** group for the workload, choose **Audit logs**.

## Filter audit events
Each workload has a menu item that pre-filters the category of audit events associated with that blade. A separate filter option lets you change to different categories, and event action details within that category. You can search by UPN (for example, the user who did the action). A date range filter allows 24 hours, 7 days or 30 day options. By default, the last 30 days of audit events are displayed.

## Review audit events
Each audit log contains the following sections: 

- Activity
- Activity Status
- Intitiated by (Actor)
- Target


## Use Graph API to retrieve up to 1 year of audit events
There is a graph API also to retrieve up to 1 year’s audit events – https://graph.microsoft.com/beta/managedDevices/auditEvents

Each audit event has an Actor which contains the UPN of the user performing the activity, and the application they used to make the change.  The audit event lists the changed properties and before/after values of those properties.


