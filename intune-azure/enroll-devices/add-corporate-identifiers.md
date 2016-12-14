---
# required metadata

title: How to add IMEI identifiers to Intune | Intune Azure preview | Microsoft Docs
description: "Intune Azure preview: Learn how to add corporate identifiers (IMEI numbers) to Microsoft Intune. "
keywords:
author: staciebarker
ms.author: stabark
manager: angrobe
ms.date: 11/30/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: dagerrit
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:
---

# How to add IMEI identifiers to Intune Azure preview

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

You can create a list of International Mobile Equipment Identity (IMEI) numbers to identify your corporate devices. These devices may or may not be enrolled, and they have a state of either “Enrolled” or “Not contacted.” “Not contacted” means that the device never checks in with the Intune service.

To create the list, create a two-column, comma-separated value (.csv) list without a header. Add the IMEI identifier in the left column, and the details in the right column. The current maximum for the list is 500 rows.

In a text editor, the .csv list looks something like this:

01 234567 890123,device details</br>
02 234567 890123,device details

**To add a .csv list of corporate identifiers**

1. In the **Enrollment** blade, choose **Corporate Device Identifiers**.
2. If you are importing a file with new details that will overwrite the existing ones, select **Overwrite details for existing identifiers** to have the new details replace the existing details.
3. Navigate to the IMEI CSV file, and select **Add**.

**To delete a .csv list of corporate identifiers**

1. In the **Enrollment** blade, choose **Corporate Device Identifiers**.
2. Choose **Delete**.
