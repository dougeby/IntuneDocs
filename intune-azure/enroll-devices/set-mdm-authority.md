---
# required metadata

title: Set the mobile device management authority in Microsoft Intune | Intune Azure preview | Microsoft Docs
description: Learn how to set the mobile device management authority in Intune. 
keywords:
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 11/30/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8deff871-5dff-4767-9484-647428998d82

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: dagerrit
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:
---

# Set the mobile device management authority in Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

The mobile device management authority setting determines how you manage your devices. The possible configurations are:

- **Intune Standalone** - cloud-only management, which you configure by using the Azure portal. Includes the full set of capabilities that Intune offers.

- **Intune Hybrid** - integration of the Intune cloud solution with System Center Configuration Manager. You configure Intune by using the Configuration Manager console.

- **Mobile Device Management for Office 365** - integration of Office 365 with the Intune cloud solution. You configure Intune from your Office 365 Admin Center. Includes a subset of the capabilities that are available with Intune Standalone. 

>[!IMPORTANT]
>Once you set the mobile device management authority, you cannot change it, so make your choice carefully.

**To set the mobile device management authority:**

1. In the **Enrollment** workload, choose **Overview**.

2. In the **Start managing devices** blade, choose **Set MDM Authority to Intune**. A message indicates that you have successfully set your MDM authority to Intune.