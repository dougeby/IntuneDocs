---
# required metadata

title: Deploy Windows Information Protection (WIP) app protection policy with Intune | Microsoft Docs
description: Deploy Windows Information Protection (WIP) app protection policy with Intune from the Azure portal.
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 04/18/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f82d8aff-15d0-4b0d-b272-4a76a3e96f67

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: joglocke
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Deploy Windows Information Protection (WIP) app protection policy with Intune

> [!IMPORTANT]
> This applies for WIP with mobile application management (MAM) without enrollment scenario.

After you created your WIP app protection policy, you need to deploy it to your organization using MAM.

## To deploy your WIP policy

1.  On the **App policy** blade, choose your newly-created app protection policy, choose **User groups**, then choose **Add user group**.

	A list of user groups, made up of all the security groups in your Azure Active Directory, opens in the **Add user group** blade.

1.  Choose the group you want your policy to apply to, then click **Select** to deploy the policy.
