---
# required metadata

title: Determine Intune use case scenario requirements | Microsoft Docs
description: This article helps to determine Intune use case, and sub use case scenario requirements for an Microsoft Intune cloud-only implementation.
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: fd8cb5f7-19f0-4d80-8825-2bafa49624af

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffbu, cgerth
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Determine Intune use case scenario requirements

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

In this section, you will determine the requirements for each organizational group within each use case scenario. Going through this process will help you better prepare for the other Intune deployment planning areas like architecture and design, onboarding, and rollout. It can also help identify potential gaps, and challenges related to your Intune deployment project.

You might have different sets of requirements for each of your use case/sub use case scenarios and their associated organizational groups and mobile device platforms. For example, your corporate use case scenario requirements may require devices to enroll into Intune with a more restrictive set of device settings (e.g. PIN 6 characters, disabling cloud backup), as compared to your "Bring your own device" (BYOD) use case scenario, where it requires less restrictive settings (e.g. PIN 4 characters, allowing cloud backup).

You may also have organizational groups for the corporate use case scenario that have different sets of requirements (e.g. PIN settings, Wi-Fi or VPN profile, apps deployed). In addition, your requirements might be determined by the mobile device platform’s capabilities (e.g. finger print reader, email profile).

Here are a few examples of an organization’s use case requirements, showing different sets of requirements for each use case/sub use case scenario, organizational group and mobile device platform. You can also use the table below to enter your organization’s use case requirements:

| **Use cases** | **Sub use cases** | **Groups** | **Device OS platforms** | **Requirements** |
|:---:|:---:|:---:|:---:|:---:|
| Corporate | Information Worker | HR, Finance | iOS | Secure e-mail, device settings , Profiles, Apps |                                                          
| Corporate | Executives | HR, Finance | iOS | Secure e-mail, device settings, Profiles, Apps |                                                         
| Corporate | Kiosk | Retail | Android | Device settings, Profiles, Apps |
| BYOD | Information Worker | Marketing, Sales | iOS | Secure e-mail, device settings, Profiles, Apps |                                                         
| BYOD | Executives | Marketing, Sales | iOS | Secure e-mail, device settings, Profiles, Apps |

## Examples of requirements

Here are a few more examples that can be used on the "Requirements" column referred at the table above:

- **Secure e-mail**
	- Conditional access for Exchange online / on-premises
	- Outlook app protection policies
<br></br>
- **Device settings**
	- PIN setting with four, six characters
	- Restrict cloud backup
<br></br>
- **Profiles**
	- Wi-Fi
	- VPN
	- Email (Windows 10 mobile)
<br></br>
- **Apps**
	- Office 365 with app protection policies
	- Line of business (LOB) with app protection policies

## Next Section

The next section provides guidance on [how to develop an Intune rollout plan](section-4-develop-a-rollout-plan.md).
