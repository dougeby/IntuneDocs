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
This topic describes the steps required to enable Lookout MTP connection in Intune. You should have already configured the Intune Connector in the Lookout MTP console.  If you have not already done so, please refer to [Setup your subscription with Lookout mobile threat protection](set-up-your-subscription-with-lookout-mtp.md) topic  to learn more.

To enable the Lookout MTP connection in Intune, go to ADMIN and choose Third Party Service Integration. Choose Lookout status and enable synchronization with MTP using the toggle button.
![screenshot of the Lookout synchronization page with the enable toggle button highlighted](../media/mtp/lookout-intune-synchronization.png)

This completes the setup of the Lookout and Intune integration in the Intune admin console.  The next few steps in implementing this solution involves configuring the Lookout for Work apps for Android and iOS, setting up the compliance policies to include the risk assessment. If you have already enabled conditional access policy, the device risk assessment will automatically be evaluated for compliance and access will be restricted accordingly. If you don’t have an existing conditional access policy you can create a new one.

You **must** configure the Lookout for Work app first before creating compliance policy rules and configuring conditional access, so when the end-users are asked to install the Lookout for work app they will be directed to the link where the app is available for install.
## Next steps
[Configure Lookout for Work app for Android and iOS](configure-and-deploy-lookout-for-work-apps.md)
