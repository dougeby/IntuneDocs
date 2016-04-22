---
# required metadata

title: Troubleshoot email profiles in Microsoft Intune | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: f5c944ea-32a6-48af-bb57-16d5f1f3c588

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Troubleshoot email profiles in Microsoft Intune
Listed here are some email profile issues and how to troubleshoot and resolve them.

If this information does not solve your problem, see [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) to find more ways to get help.


### Unable to send images from  email account
Users who have email accounts automatically configured are unable to send pictures or images from their devices.
This occurs when the option **Allow e-mail to be sent from third-party applications** is not enabled.

#### Intune solution

1.  Open the Microsoft Intune Administration Console, select **Policy** workload &gt; **Configuration Policy**.

2.  Select the email profile and click **Edit**.

3.  Select **Allow e-mail to be sent from third-party applications.**

#### Configuration Manager integrated with Intune solution

1.  Open the Configuration Manager console &gt; **Assets and Compliance**.

2.  Expand **Overview** -&gt; **Compliance Settings** -&gt; **Company Resource Access**, and select **Email Profiles**.

3.  Right-click the e-mail profile, and open **Properties**.

4.  On the **Synchronization Settings** tab, select **Allow e-mail to be sent from third-party applications**.

## Next steps
If this troubleshooting information  didn't help you, contact Microsoft Support as described in [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md).

