---
# required metadata

title: Set the mobile device management authority
titleSuffix: "Intune Azure preview"
description: "Intune Azure preview: Learn how to set the mobile device management authority in Intune. "
keywords:
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 04/20/2016
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
ms.custom: intune-azure
---

# Set the mobile device management authority

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

The mobile device management (MDM) authority setting determines how you manage your devices. As an IT admin, you must set an MDM authority before users can enroll devices for management.

Possible configurations are:

- **Intune Standalone** - cloud-only management, which you configure by using the Azure portal. Includes the full set of capabilities that Intune offers. [Set the MDM authority in the Intune console](#mdm-authority-set-to-intune).

- **Intune Hybrid** - integration of the Intune cloud solution with System Center Configuration Manager. You configure Intune by using the Configuration Manager console. [Set the MDM authority in Configuration Manager](https://docs.microsoft.com/sccm/mdm/deploy-use/configure-intune-subscription).

- **Mobile Device Management for Office 365** - integration of Office 365 with the Intune cloud solution. You configure Intune from your Office 365 Admin Center. Includes a subset of the capabilities that are available with Intune Standalone. Set the MDM authority in Office 365 Admin Center.

>[!IMPORTANT]    
After you set the MDM authority, you might be able to change it without having to contact Microsoft Support, and without having to unenroll and reenroll your existing managed devices. For details, see [What to do if you choose the wrong MDM authority setting](#what-to-do-if-you-choose-the-wrong-mdm-authority-setting) for instructions.

## Set MDM authority to Intune

1. In the Azure portal, choose **More Services** > **Monitoring + Management** > **Intune**.
  ![Screenshot of the Intune Troubleshoot workload with Select User link](media/set-mdm-auth.png)
2. On the Intune blade, choose **Device enrollment**, and then choose **Overview**.

3. On the **Start managing devices** blade, choose **Set MDM Authority to Intune**. A message indicates that you have successfully set your MDM authority to Intune.
