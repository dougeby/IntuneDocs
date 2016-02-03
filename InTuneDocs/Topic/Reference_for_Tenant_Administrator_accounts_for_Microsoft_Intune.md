---
title: Reference for Tenant Administrator accounts for Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: e4eff7b9-4dcd-4959-b1d6-97dc4640dbe2
author: Staciebarker
---
# Reference for Tenant Administrator accounts for Microsoft Intune
Each tenant administrator is assigned one of the following roles:

|Role|Details|
|--------|-----------|
|**Billing administrator**|Makes purchases, manages subscriptions, manages support tickets, and monitors service health.|
|**Global administrator**|Has access to all administrative features. By default, the person who signs up to purchase a Microsoft cloud service on behalf of your organization automatically becomes the first global administrator in your tenant.<br /><br />-   Only global administrators can assign other administrator roles.<br />-   There can be more than one global administrator at your organization.|
|**Password administrator**|Resets passwords, manages service requests, and monitors service health. Password administrators can reset passwords only for users and other password administrators.|
|**Service support administrator**|Manages service requests and monitors service health.|
|**User management administrator**|Resets passwords, monitors service health, and manages user accounts, user groups, and service requests.|
Each administrator role has the following associated permissions:

|Permission|Billing administrator|Global administrator|Password administrator|Service support administrator|User management administrator|
|--------------|-------------------------|------------------------|--------------------------|---------------------------------|---------------------------------|
|View organization and user information|Yes|Yes|Yes|Yes|Yes|
|Manage support tickets|Yes|Yes|Yes|Yes|Yes|
|Reset user passwords|No|Yes|Yes|No|Yes; with limitations. This admin cannot reset passwords for billing, global, and service administrators.|
|Perform billing and purchasing operations|Yes|Yes|No|No|No|
|Create and manage user views|No|Yes|No|No|Yes|
|Create, edit, and delete users and groups, and manage user licenses|No|Yes|No|No|Yes; with limitations. This admin cannot delete a global administrator or create other administrators.|
|Manage domains|No|Yes|No|No|No|
|Manage organization information|No|Yes|No|No|No|
|Delegate administrative roles to others|No|Yes|No|No|No|
|Use directory synchronization|No|Yes|No|No|No|
To learn more about administrative accounts in [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)], read about the [different administrative accounts and permissions for separate tasks](http://technet.microsoft.com/library/dn646966.aspx). For help managing administrative users, see [Task 5: Assign administrative users](../Topic/Get_started_with_a_paid_subscription_to_Microsoft_Intune.md#BKMK_AssignAdmins) in [Get started with a paid subscription to Microsoft Intune](../Topic/Get_started_with_a_paid_subscription_to_Microsoft_Intune.md).

