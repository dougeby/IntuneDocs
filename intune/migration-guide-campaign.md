---
# required metadata

title: Start an Intune migration campaign 
description: The purpose of this article is to provide guidance on how to start a migration campaign.
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f781b029-50f2-46ee-8ff7-03b4a6719e80

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: dagerrit
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Phase 2: Migration Campaign

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

Organizations should a migration approaches which is most suitable for their needs and adjust implementation tactics based on their specific requirements. The remainder of this guide will equip you with the tools you need to achieve the goal of getting your user’s devices enrolled into Intune.

## Keys to a successful migration

These are the key lessons learned when migrating from a third-party MDM provide to Intune:

-   Communication is key to minimize end-user downtime and satisfaction.

-   Be sure to have specific and concrete migration instructions.

-   All managed devices must be un-enrolled from your existing MDM provider prior to enrolling in Intune.

-   Provide guidance from the existing MDM provider to end-users for how to un-enroll their devices.

-   Use a phased approach. Start with a small group of pilot users and incrementally add more groups of users until you reach full scale deployment.

-   Monitor the Help-desk load and enrollment success of each cycle. Leave time in the schedule to ensure success criteria can be evaluated for each group before migrating the next. Your pilot deployment should validate the following:

    -   Enrollment success and failure rates are within expectations.

    -   User productivity:

        -   Corporate resources such as VPN, Wi-Fi, email, and certificates are working.

        -   Provisioned Apps are accessible.

    -   Data security:

        -   Compliance reporting

        -   Mobile app protections enforced

-   When you are satisfied with the first phase of migrations, repeat the Migration Cycle (described below under Typical Migration cycle) for next phase.

-   Repeat phased cycles until all users are migrated to Intune.

-   Ensure Help-desk team is ready to support end-users throughout the migration campaign. Run a voluntary migration until you can estimate support call workload.

-   Don’t set deadlines for enrollment until remaining population can be handled by your Help-desk

> [!IMPORTANT] 
> Do not configure both Intune and your existing third party MDM solution to apply access controls to resources such as Exchange or SharePoint Online. Additionally, devices should only be enrolled in one solution at a time.

## Next steps

[Communication plan](migration-guide-communication-plan.md)
