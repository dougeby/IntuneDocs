---
# required metadata

title: Determine Intune rollout targeted groups and timeframes | Microsoft Docs
description: This article helps to determine rollout targeted groups and timeframes for a Microsoft Intune cloud-only implementation.
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 3a63f78f-a7e7-4f44-9288-16b28d5d58ca

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffbu, cgerth
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Develop an Intune rollout plan

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

This section will help you to determine the organizational groups that will be targeted for your Intune rollout, as well as the rollout timeframe for each group, and the enrollment approaches that will be used.

## Determine Intune rollout targeted groups and timeframes

It's important to first identify the groups that will be targeted with your Intune rollout. The targeted groups were previously discussed in the identify Intune use case scenarios section of this guide.

Secondly, you’ll need to determine the timeframe that each group will be targeted for the Intune rollout. This normally requires a discussion within the Intune deployment team and with targeted groups, to help determine the most appropriate rollout timeframe for each group.

For example, the Intune deployment team may discuss such factors as the group’s willingness for change, number of users and devices, types of device platforms, requirements, geographic location and business risk to determine the rollout timeframe.

Organizations commonly choose to start the Intune rollout with an initial pilot, targeting a small group of users in the IT department. The pilot could then be expanded to include a broader set of IT users and participation from other organizational groups. After a successful pilot, organizations are ready to start a full production rollout, targeting the rest of the organization’s groups, some examples of different rollout groups and phases are provided below:

-   **Pilot:** The first phase to rollout should be pilot users. The pilot users should understand they are the first users in a new solution and are willing to provide feedback to help improve configuration, documentation, notifications, and ease the way for all other users in later rollout phases. These users should not be Executives or VIPs.

-   **Departments:** Each department can be a rollout phase. In this scenario, you will target an entire department at once. In this type of rollout, each phase most likely will be using the mobile device in the same way and accessing the same applications. The users most likely will also have the same types of policies.

-   **Geography:** This type of deployment consists of deploying to all users in a specific geography whether it’s the same continent, country, region, or same company’s building. This type of phased deployment allows the ability to focus on specific location of users. This could allow more [white glove](#user-assisted-enrollment) approach as the number of locations deploying Intune at the same time is reduced. Because there are chances of different departments or use cases being at the same location, different use cases might be deployed at the same time.

-   **Platform:** This type of deployment consists of deploying similar platforms at the same time. An example might be all iOS devices the first month, followed by Android, followed by Windows. This type of phased deployment helps simplify helpdesk support. The helpdesk support would only have to support a single platform at a time.

Here’s an example of an Intune rollout plan that includes targeted groups and timelines:

| **Rollout phase** | **July** | **August** | **September** | **October** |
|:---:|:---:|:---:|:---:|:---:|
| Limited Pilot | IT (50 users) |  |  |  |                                                         
| Expanded Pilot | IT (200 users), IT Executives (10 users) |  |  |  |                                                         
| Production rollout phase 1 |  | Sales and Marketing (2000 users) |  |  |
| Production rollout phase 2 |  |  | Retail (1000 users) |  |
| Production rollout phase 3 |  |  |  | HR (50 users), Finance (40 users), Executives (30 users) |

## Determine the Intune enrollment approach

Now that you have determined the targeted groups and timeframes for your Intune rollout, the next step is to choose the most appropriate Intune enrollment approach for each group. There are different enrollment approaches that organizations can use for their Intune rollout. A couple common enrollment approaches include user self-service, user assisted-enrollment, and IT tech fair.

### User self-service

With this approach, the user is responsible for enrolling their own device, usually following enrollment instructions provided by their IT organization. This approach is most commonly used in organizations and is more scalable than user assisted enrollment.

### User assisted-enrollment

This is known as "white glove" approach, which an IT team member would assist the user through the enrollment process, in person or via Skype. This approach is commonly used with executive staff and other groups that may need more assistance during the enrollment process.

### IT tech fair

Another option for Intune user enrollment is to have an IT technical fair. At this event, the IT group would setup an Intune enrollment assistance booth where users could receive information on Intune enrollment, ask questions and get assistance with the enrollment process. Leveraging this option can be beneficial for both IT group and the user, especially during early phases of Intune rollout.

Here’s an example of an Intune rollout plan with targeted groups, timelines and enrollment approaches:

| **Rollout phase** | **July** | **August** | **September** | **October** |
|:---:|:---:|:---:|:---:|:---:|
| Limited Pilot |  |  |  |  |                                                         
| Self-service | IT |  |  |  |
| Expanded Pilot |  |  |  |  |                                                         
| Self-service | IT |  |  |  |
| White glove | IT Executives |  |  |  |
| Production rollout phase 1 |  | Sales, Marketing |  |  |
| Self-service |  | Sales and Marketing |  |  |
| Production rollout phase 2 |  |  | Retail |  |
| Self-service |  |  |  |  |
| Production rollout phase 3 |  |  | Retail |  |
| Self-service |  |  |  | HR, Finance |
| White glove |  |  |  | Executives |

## Next Section

The next section provides guidance on [developing an Intune rollout communication plan](section-5-develop-a-rollout-communication-plan.md).
