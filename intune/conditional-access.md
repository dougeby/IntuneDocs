---
# required metadata

title: Conditional access with Intune
titlesuffix: "Azure portal"
description: Learn how to define the conditions users and devices must meet to access company resources in Microsoft Intune."
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/23/2017
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: a1973f38-ea55-43eb-a151-505fb34a8afb

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# What's conditional access?

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

This topic describes Conditional access as it applies to Enterprise Mobility + Security (EMS), and follows that with Conditional access common scenarios when using Intune.

Enterprise Mobility + Security (EMS) Conditional Access is not a standalone product, it’s a solution that takes part on all services and products that are part of the EMS. It provides granular access control to keep your corporate data secure, while giving users an experience that allows them to do their best work from any device, and from any location.

You can define conditions that gate access to your corporate data based on location, device, user state, and application sensitivity.

> [!NOTE] 
> Conditional Access also extends its capabilities to [Office 365 services](https://blogs.technet.microsoft.com/wbaer/2017/02/17/conditional-access-policies-with-sharepoint-online-and-onedrive-for-business/).

![Conditional access architectural diagram](./media/ca-diagram-1.png)

## Conditional access with Intune

Intune adds mobile device compliance and app management policies to support the EMS Conditional Access solution.

![Intune and conditional access when using EMS](./media/intune-with-ca-1.png)

Ways to use conditional access with Intune:

-   **Device-based conditional access**

    -   Conditional access for Exchange on-premises

    -   Conditional access based on network access control

    -   Conditional access based on device risk

    -   Conditional access for Windows PCs

        -   Corporate-owned

        -   Bring your own device (BYOD)

-   **app-based conditional access**

## Next steps

[Common ways to use conditional access with Intune](conditional-access-intune-common-ways-use.md)