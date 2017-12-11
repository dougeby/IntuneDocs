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

## Who can access the data?
Users with the following permissions can review audit logs:
- Global Admins
- Intune Service admins
- Users with audit/read permissions


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

- 





## Audit logs

The audit logs in Azure Active Directory provide records of system activities for compliance.  
Your first entry point to all auditing data is **Audit logs** in the **Activity** section of **Azure Active Directory**.

![Audit logs](./media/active-directory-reporting-activity-audit-logs/61.png "Audit logs")

An audit log has a default list view that shows:

- the date and time of the occurrence
- the initiator / actor (*who*) of an activity 
- the activity (*what*) 
- the target

![Audit logs](./media/active-directory-reporting-activity-audit-logs/18.png "Audit logs")

You can customize the list view by clicking **Columns** in the toolbar.

![Audit logs](./media/active-directory-reporting-activity-audit-logs/19.png "Audit logs")

This enables you to display additional fields or remove fields that are already displayed.

![Audit logs](./media/active-directory-reporting-activity-audit-logs/21.png "Audit logs")


By clicking an item in the list view, you get all available details about it.

![Audit logs](./media/active-directory-reporting-activity-audit-logs/22.png "Audit logs")


## Filtering audit logs

To narrow down the reported data to a level that works for you, you can filter the audit data using the following fields:

- Date range
- Initiated by (Actor)
- Category
- Activity resource type
- Activity

![Audit logs](./media/active-directory-reporting-activity-audit-logs/23.png "Audit logs")


The **date range** filter enables to you to define a timeframe for the returned data.  
Possible values are:

- 1 month
- 7 days
- 24 hours
- Custom

When you select a custom timeframe, you can configure a start time and an end time.

The **initiated by** filter enables you to define an actor's name or its universal principal name (UPN).

The **category** filter enables you to select one of the following filter:

- All
- Core category
- Core directory
- Self-service password management
- Self-service group management
- Account provisioning- Automated password rollover
- Invited users
- MIM service
- Identity Protection
- B2C

The **activity resource type** filter enables you to select one of the following filters:

- All 
- Group
- Directory
- User
- Application
- Policy
- Device
- Other

When you select **Group** as **activity resource type**, you get an additional filter category that enables you to also provide a **Source**:

- Azure AD
- O365


The **activity** filter is based on the category and Activity resource type selection you make. You can select a specific activity you want to see or choose all. 

You can get the list of all Audit Activities using the Graph API https://graph.windows.net/$tenantdomain/activities/auditActivityTypes?api-version=beta, where $tenantdomain = your domain name or refer to the article [audit report events](active-directory-reporting-audit-events.md).
Activity
- Activity Status
- Intitiated by (Actor): Each audit event has an Actor which contains the UPN of the user performing the activity, and the application they used to make the change.  The audit event lists the changed properties and before/after values of those properties.
- Target

## Use Graph API to retrieve up to 1 year of audit events
There is a graph API also to retrieve up to 1 year’s audit events – https://graph.microsoft.com/beta/managedDevices/auditEvents





