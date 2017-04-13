---
# required metadata

title: Identify Intune use case scenarios | Microsoft Docs
description: This article helps to identify Intune use case, and sub use case scenarios for a Microsoft Intune cloud-only implementation.
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 4b3c9af9-78da-44d2-8bd2-3f0f8885952d

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffbu, cgerth
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Identify Intune use case scenarios

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Mobile device management use case scenarios describe the user type or role and the ownership of their device (e.g. company or personal). User case scenarios are helpful because they let you segment your users into manageable groups. Identifying your use case scenarios is an important part of the planning process for a successful Intune deployment.

Let’s discuss a few examples to help your organization identify Intune use case scenarios, as well as organizational groups, and mobile device platforms associated with each use case.

## Use case scenarios

You can begin by referring to your organization's Intune deployment goals and objectives to help identity the main use case scenarios for your deployment. Within the scope of your Intune deployment plan, you will need to answer the following questions:

-   Are you planning to support corporate owned devices?

-   Are you planning to support personally owned devices (BYOD)?

### Sub use case scenarios

After identifying your main use case scenarios, you’ll need to determine if each use case scenario also includes sub-use cases. For example, an organization may have identified requirements to support a corporate use case scenario that includes additional sub use cases:

-   Information worker

-   Executives

-   Kiosk

Here are a few examples of use case and sub use case scenarios. You can use the table below to enter your organization’s use case, and sub use case scenarios:

| **Use cases** | **Sub use cases** |
|:---:|:---:|
| Corporate | Information worker |              
| Corporate | Executives |           
| Corporate | Kiosk |
| BYOD | Information worker |           
| BYOD | Executives |

## Identify organizational groups associated with use case scenarios

Now you need to identify the organizational groups that are associated with each use case and sub use case scenario. Here are a few examples of organizational groups associated with use case and sub use case scenarios that can be used as a template to enter your organization’s information:

| **Use cases** | **Sub use cases** | **Organizational groups** |
|:---:|:---:|:---:|
| Corporate | Information worker | HR, Finance |               
| Corporate | Executive | HR, Finance |            
| Corporate | Kiosk | Retail |
| BYOD | Information worker | Marketing, Sales |            
| BYOD | Executive | Marketing, Sales |

## Identify mobile device platforms for use case scenarios

Here you’ll identify the mobile device platforms associated with each use case scenario. For example, your corporate use case scenario may support iOS and Android Samsung KNOX device platforms, and your BYOD policy may include support for additional mobile device platforms like Android (NON-Samsung KNOX) and Windows 10 Mobile. Here’s an example of mobile device platforms that are associated with each use case scenario. You can use the table below to enter your organization’s device platforms associated with its use case scenarios:

| **Use cases** | **Sub use cases** | **Groups** | **Device platforms** |   
|:---:|:---:|:---:|:---:|
| Corporate | Information worker | HR, Finance | iOS |                                                           
| Corporate | Executives | HR, Finance | iOS |                                                           
| Corporate | Kiosk | Retail | Android |
| BYOD | Information worker | Marketing, Sales | iOS |                                                           
| BYOD | Executives | Marketing, Sales | iOS |

## Next steps

The next section provides guidance on [how to identify the Intune requirements for each use case scenario](section-3-determine-use-case-requirements.md).
