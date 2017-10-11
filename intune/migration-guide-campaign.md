---
# required metadata

title: Start an Intune migration campaign
description: This article provides guidance for how to start a migration campaign.
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/12/2017
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
#ms.custom:

---

# Phase 2: Migration campaign

Choose a migration approach that is most suitable for your organization's needs and adjust implementation tactics based on your specific requirements. The remainder of this guide will equip you with the tools you need to achieve the goal of getting your users’ devices enrolled into Intune.

## Keys to a successful migration

These are the keys to migrating successfully from a third-party MDM provider to Intune:

-   Clear and helpful communication can minimize end-user downtime and dissatisfaction.

-   Be sure to have specific and concrete migration instructions.

-   All managed devices must be unenrolled from your existing MDM provider before they can be enrolled in Intune.

-   Provide guidance from your existing MDM provider to end-users for how to unenroll their devices.

-   Use a phased approach. Start with a small group of pilot users and incrementally add more groups of users until you reach full scale deployment.

-   Monitor the helpdesk load and enrollment success of each cycle. Leave time in the schedule to ensure success criteria can be evaluated for each group before migrating the next. Your pilot deployment should validate the following:

    -   Enrollment success and failure rates are within expectations.

    -   User productivity:

        -   Corporate resources such as VPN, Wi-Fi, email, and certificates are working.

        -   Provisioned apps are accessible.

    -   Data security:

        -   Compliance reporting is occurring.

        -   Mobile app protections are enforced.

When you are satisfied with the first phase of migrations, repeat the [migration cycle](migration-guide-cycle.md) for the next phase.

-   Repeat phased cycles until all users are migrated to Intune.

-   Ensure the helpdesk team is ready to support end users throughout the migration campaign. Run a voluntary migration until you can estimate support call workload.

-   Don’t set deadlines for enrollment until the remaining population can be handled by your helpdesk

> [!IMPORTANT]
> Do not configure both Intune and your existing third party MDM solution to apply access controls to resources such as Exchange or SharePoint Online. Additionally, devices should only be enrolled in one solution at a time.

## Next steps

Create your [communication plan](migration-guide-communication-plan.md).
