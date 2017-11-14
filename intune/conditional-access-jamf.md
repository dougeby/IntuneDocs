---
# required metadata

title: Integrate Jamf Pro with Intune conditional access
titlesuffix: "Azure portal"
description: "Use conditional access to help secure Jamf-managed devices."
keywords:
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/14/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 4b6dcbcc-4661-4463-9a36-698d673502c6

# optional metadata

#ROBOTS: NOINDEX, NOFOLLOW
#audience:
#ms.devlang:
ms.reviewer: elocholi
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---

# Integrate Jamf Pro with Intune conditional access

[!INCLUDE][azure_portal](./includes/azure_portal.md)]

[!INCLUDE][macos-preview-1708](/intune-user-help/includes/macos-preview-1708.md]

If your organization uses [Jamf Pro](https://www.jamf.com) to manage Mac, iOS, and tvOS devices, you can use Microsoft Intune and Azure Active Directory to apply [conditional access](conditional-access.md) policies. This ensures that your end users are compliant with your organizations policy for accessing confidential information.

## Prerequisites

You need the following to configure conditional access with Jamf Pro:

- Access to the Intune Private Preview for macOS conditional access
- Jamf Pro 10.1.0 or later
- [Company Portal app for macOS](https://aka.ms/macoscompanyportal)
- macOS devices with OS X 10.11 Yosemite or later

## Connecting Jamf Pro to Intune
