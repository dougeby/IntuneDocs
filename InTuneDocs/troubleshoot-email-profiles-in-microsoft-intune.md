---
title: Troubleshoot email profiles in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: f5c944ea-32a6-48af-bb57-16d5f1f3c588
author: Nbigman
---
# Troubleshoot email profiles in Microsoft Intune
Listed here are some email profile issues and how to troubleshoot and resolve them..

## Unable to send images from  email account
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

