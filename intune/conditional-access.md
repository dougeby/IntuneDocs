---
# required metadata

title: Conditional access with Microsoft Intune
titleSuffix: Microsoft Intune
description: Learn how to define the conditions users, devices, and apps must meet to access company resources in Microsoft Intune.
keywords:
author: brenduns
ms.author: brenduns
manager: dougeby    
ms.date: 03/06/2018
ms.topic: conceptual
ms.prod:
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology:
ms.assetid: a1973f38-ea55-43eb-a151-505fb34a8afb

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer:
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
---

# What's conditional access?

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Conditional access refers to ways you can control the devices and apps that are allowed to connect to your email and company resources. In this topic, learn about device-based and app-based conditional access, and find common scenarios for using conditional access with Intune.

Enterprise Mobility + Security (EMS) Conditional Access is not a standalone product, it’s a solution that takes part on all services and products that are part of the EMS. It provides granular access control to keep your corporate data secure, while giving users an experience that allows them to do their best work from any device, and from any location.

You can define conditions that gate access to your corporate data based on location, device, user state, and application sensitivity.

> [!NOTE] 
> Conditional Access also extends its capabilities to [Office 365 services](https://docs.microsoft.com/office365/enterprise/office-365-client-support-conditional-access).

![Conditional access architectural diagram](./media/ca-diagram-1.png)

## Conditional access with Intune

Conditional access is an Azure Active Directory capability that is included with an Azure Active Directory Premium license. Intune enhances this capability by adding mobile device compliance and mobile app management to the solution. 

![Intune and conditional access when using EMS](./media/intune-with-ca-1.png)

Ways to use conditional access with Intune:

-   **Device-based conditional access**

    -   Conditional access for Exchange on-premises

    -   Conditional access based on network access control

    -   Conditional access based on device risk

    -   Conditional access for Windows PCs

        -   Corporate-owned

        -   Bring your own device (BYOD)

-   **App-based conditional access**

## Next steps

[Common ways to use conditional access with Intune](conditional-access-intune-common-ways-use.md)
