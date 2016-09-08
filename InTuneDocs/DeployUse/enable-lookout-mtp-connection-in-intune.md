---
# required metadata

title: Enable Lookout MTP in Intune | Microsoft Intune
description: Enable Lookout mobile threat protection in the Intune admin console.
keywords:
author: karthikaraman
manager: angrobe
ms.date: 09/08/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 2f835fd0-4e62-42f3-b7ca-ce8b7ddd40e4

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: sandera
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Enable Lookout MTP connection in the Intune admin console
This topic shows you how to enable Lookout MTP connection in Intune. You should have already configured the Intune Connector in the Lookout MTP console before doing this step.  If you have not already done so, please refer to [Setup your subscription with Lookout mobile threat protection](set-up-your-subscription-with-lookout-mtp.md) topic  to learn more.

To enable the Lookout MTP connection in Intune, in the [Microsoft Intune adminsitrator console](https://manage.microsoft.com), on the **Administration** page, choose **Third Party Service Integration**. Choose **Lookout status** and enable **Synchronization with MTP** using the toggle button.

![screenshot of the Lookout synchronization page with the enable toggle button highlighted](../media/mtp/lookout-intune-synchronization.png)

This completes the setup of the Lookout and Intune integration in the Intune administrator console.  The next few steps in implementing this solution involves deploying the Lookout for Work apps and setting up the compliance and conditional access policies.

You **must** configure the Lookout for Work app first before creating compliance policy rules and configuring conditional access. This makes sure that the app is ready and available for end-users to install the app before they can get access to email or other company resources.
## Next steps
[Configure Lookout for Work app ](configure-and-deploy-lookout-for-work-apps.md)
