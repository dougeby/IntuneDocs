---
# required metadata

title: Configure Windows Information Protection - IntunetitleSuffix: "Azure portal"
description: Learn about the Intune settings you can use to manage Windows Information Protection."
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 04/14/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f233672c-7d9b-4554-af1f-92c001a1a3c5

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# How to configure Windows Information Protection in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

With the increase of employee-owned devices in the enterprise, there’s also an increasing risk of accidental data leaks through apps and services, like email, social media, and the public cloud, which are outside of the enterprise’s control. For example, an employee sends the latest engineering pictures from a personal email account, copies and pastes product info into a tweet, or saves an in-progress sales report to public cloud storage.

**Windows Information Protection** helps to protect against this potential data leakage without otherwise interfering with the employee experience. It also helps to protect enterprise apps and data against accidental data leaks on enterprise-owned devices and personal devices that employees bring to work without requiring changes to your environment or other apps.

This Intune policy manages the list of apps protected by Windows Information Protection, enterprise network locations, protection level, and encryption settings.

>[!NOTE]
> To use the Windows 10 Company Portal app with Windows Information Protection, you must add the Company Portal app under the Windows Information Protection mode of **Exempt**. 

### Next steps
For more information, see [Protect your enterprise data using Windows Information Protection](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip).
