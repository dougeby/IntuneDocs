---
# required metadata

title: Set terms and conditions in Microsoft Intune | Intune Azure preview | Microsoft Docs
description: "Intune Azure preview: Set terms and conditions that users see in the Company Portal for Intune. "
keywords:
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 11/30/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 4a3a11a8-9c0c-4334-8c6b-6fea4d0a2efb

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: dagerrit
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:
---

# Set terms and conditions in Intune Azure preview

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

You can deploy Intune terms and conditions to user groups to explain how enrollment, access to work resources, and the Company Portal app affect devices and users. Users must accept the terms and conditions before they can use the Company Portal to enroll and access their work.

You can create and deploy multiple policies containing different terms and conditions. You can also produce versions of the same terms and conditions in different languages and then deploy these to their appropriate groups.

**To create terms and conditions**:

1. In the Azure portal, choose **More Services**, enter **Intune** in the text box, and then choose **Other** > **Intune**.

2. On the Intune blade, choose **Enroll devices**, and then choose **Terms and Conditions**.

3. Select **Create**.

4. On the **Create Terms and Conditions** blade, specify the following information:

   - **Display name**: Name to use for the terms. Users see this name in the Company Portal app.

   - **Description**: Optional details that help you identify the policy in the Azure portal.

5. Select the arrow next to Define terms of use to open the Terms and Conditions blade, and then enter the following information:

   - **Title**: The title users see in the Company Portal.

   - **Summary of Terms**: Text that explains what it means if users accept the terms.

   - **Terms and Conditions**: The legal label that users see and must either accept or reject, for example, “I agree to the terms and conditions.”

6. Select **Ok**.
