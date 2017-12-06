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
Audit logs provide you with a record of activities that generate a change in Microsoft Intune. Create, Update (edit), Delete, and Assign actions or remote tasks generate audit events that you can review.   
Auditing records activity that generates a change in Intune.  Create, Update (edit), Delete, Assign actions or remote tasks all generate audit events.  They are displayed under the MONITOR group – as the menu “Audit Logs”.  You can view an audit event detail in production tenants now, but if you need a sample, let me know and I can get one for you.  

By default, the UI displays the last 30 days of audit events.  Each workload has a menu item that pre-filters out the category of audit events that are associated with that blade.  A separate filter option allows the ability to change to different categories, and event action details within that category. Search is allowed by UPN (e.g. user who did the action).  A date range filter allows 24 hours, 7 days or 30 day options.  

Each audit event has an Actor which contains the UPN of the user performing the activity, and the application they used to make the change.  The audit event lists the changed properties and before/after values of those properties.

There is a graph API also to retrieve up to 1 year’s audit events – https://graph.microsoft.com/beta/managedDevices/auditEvents

Let me know if you need a demo, or help with displaying events.
