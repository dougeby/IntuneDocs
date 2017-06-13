---
# required metadata

title: How a typical Intune migration cycle works 
description: The purpose of this article is to explain how an Intune migration cycle works, and give examples on how customer handle the migration cycles.
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 3688b724-9521-4210-bf4d-bcf47d8d4ca0

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: dagerrit
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Typical migration cycle

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

It’s common for an organization to start their Intune migration with a small pilot by targeting a subset of their users in the IT department. Additionally, your organization may need to discuss such factors as the group’s willingness for change, number of users, complexity, requirements, location, and business risk to assist in determining the migration time-frame.

Here’s an example of how your target groups could be scheduled:

  | **Migration targeted groups** | **Time period 1** | **Time period 2** | **Time period 3** | **Time period 4** | **...**
|:---:|:---:|:---:|:---:|:---:|:---:|
| Limited Pilot IT org (50 users) | Announce Plan | Instruct to enroll | Give deadline | Enforce conditional access |  |                                                        
| Expanded Pilot IT org (200 users) |  | Announce Plan | Instruct to enroll | Give deadline | Enforce conditional access | 
| Migration phase 1 Tech-savvy users (2000) |  |  | Announce Plan | Instruct to enroll | Give deadline | 
| Migration phase 2 Eastern US |  |  |  | Announce Plan | Instruct to enroll | 
| All Regions |  |  |  |  | Announce Plan | 

## Customer migration case study

### Adatum Corporation

- Check out [how Adatum Corporation went through the process of migration from a third-party MDM provider to Intune](https://gallery.technet.microsoft.com/Intune-migration-guide-893a95e3?redir=0).

## Monitoring migration

Microsoft Intune provides several ways that you can monitor your migration:

1.  Intune user group views

2.  Set of built-in reports, and

3.  In-console alerts.

You should track how many users have enrolled devices after each phase so that you can:

-   Evaluate the effectiveness of your communication plan.

-   Estimate the impact of enforcing conditional access.


## Post-migration

You’ll need to retire the previous MDM provider and unsubscribe from the service after migrating to Intune. Additionally, you’ll need to remove any unneeded infrastructure requirements by following the MDM provider’s instructions.
