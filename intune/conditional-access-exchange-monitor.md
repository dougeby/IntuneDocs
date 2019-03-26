---
# required metadata

title: Monitor Exchange conditional access in Microsoft Intune | Microsoft Intune
description: Monitor conditional access compliance for on-premises Exchange and Exchange Online through the Intune Azure portal.
keywords:
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/22/2019
ms.topic: conceptual
ms.prod:
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology:
ms.assetid: 5712682d-285b-43fd-9978-3dcfd95ec5f9

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure
ms.collection: M365-identity-device-management
---

# Monitor conditional access compliance for Exchange on-premises in Intune

Intune Admins can view reporting related to Exchange ActiveSync device records that are synchronized with Intune through the Exchange on-premises connector. The conditional access compliance reporting provides a summary of devices with different synchronization states:

- **Allow**

- **Block**

- **Quarantine**

## To monitor conditional access compliance

1. Sign in to [Intune](https://aka.ms/intuneportal), and go to **Conditional access**, then choose **Overview**.

2. Choose one of the three areas (**Allowed**, **Blocked**, or **Quarantine**) on the chart to view your conditional access compliance reporting.

   ![Image of the Conditional Access Dashboard](./media/CA-reporting-intune-1.png)

Once you choose one of three areas, you can see more details about devices being allowed, blocked, or quarantined.

You can also drill down in specific devices to see more details. For example, the device chosen on the following image is blocked. Intune gives you the option of removing corporate data from the conditional access compliance report pane.

![Image of Conditional access device detail reporting](./media/CA-reporting-intune-3.png)

At the device details pane, you can see more information:

- **Overview:** You can see device properties like: OS version, device model, ownership, serial number, device manufacturer, phone number, and last time the device checked in.

- **Properties:** You can set the device ownership (Personal or Corporate).

- **Hardware:** It provides the information you see on the Overview, and also storage details (total space and free space), system enclosure, network details, network service, and more conditional access blocking details.

- **Discovered Apps:** It shows all applications installed at your device. You can also export the list of installed apps to .CSV format.

- **Compliance:** It shows all device compliance policy details.

- **Device Configuration:** It shows all device configuration details.

- **Exchange Access:** Here you can learn more about the device state after applying conditional access policies.
