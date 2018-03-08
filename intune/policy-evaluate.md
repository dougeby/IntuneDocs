---
# required metadata

title: Find out how many users are targeted by a policy
titlesuffix: Microsoft Intune
description: Find out how many users are targeted by a policy
keywords:
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/09/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 38e8a2e2-2329-11e8-b467-0ed5f89f718b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Evaluate how many users are targeted by a policy
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

You can use the **Evaluate** button to find out how many users are targeted by a device compliance or device configuration policy. This feature only calculates users, not devices.

1.	In [Intune in the Azure portal](https://aka.ms/intuneportal), choose **Device compliance** or **Device configuration**, and then choose **Policies**.
2.	Choose one of the policies, or create a new one, and then choose **Assignments**.
3.	Choose **Evaluate**. A message displays showing you how many users are targeted by this policy.

If the **Evaluate** button is grayed out, make sure that the policy has been assigned to one or more groups.

