---
# required metadata

title: Add IMEI identifiers to IntunetitleSuffix: "Intune Azure preview"
description: "Intune Azure preview: Learn how to add corporate identifiers (IMEI numbers) to Microsoft Intune. "
keywords:
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/22/2017
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
ms.custom: intune-azure
---

# Add corporate identifiers

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

As an IT admin you can create and import a comma-separated value (.csv) file that lists International Mobile Equipment Identity (IMEI) numbers to identify corporate-owned devices. Each IMEI number can have details specified in the list for administrative purposes.

## Create a .csv file
To create the list, create a two-column, comma-separated value (.csv) list without a header. Add the IMEI identifier in the left column, and the details in the right column. Details are limited to 128 characters. The current limit is 500 rows per .csv file.

**Upload a .csv file that has serial numbers** – Create a two-column, comma-separated value (.csv) list without a header, and limit the list to 5,000 devices or 5 MB per .csv file.

|||
|-|-|
|&lt;IMEI #1&gt;|&lt;Device #1 Details&gt;|
|&lt;IMEI #2&gt;|&lt;Device #2 Details&gt;|

    This .csv file when viewed in a text editor appears as:

    ```
    01 234567 890123,device details
    02 234567 890123,device details
    ```

**To add a .csv list of corporate identifiers**

1. In the Azure portal, choose **More Services** > **Monitoring + Management** > **Intune**.

2. On the Intune blade, choose **Enroll devices**, and then choose **Corporate Device Identifiers**.

3. If you are importing a file with new details that will overwrite the existing ones, select **Overwrite details for existing identifiers** to have the new details replace the existing details.

4. Navigate to the IMEI CSV file, and select **Add**.

> [!IMPORTANT]
> Some Android devices have multiple IMEI numbers. Intune inventories one IMEI number per device. If you import an IMEI number but it is not the IMEI inventoried by Intune, the device will be classified as a personal device instead of a company-owned device. If you import multiple IMEI numbers for a device, uninventoried numbers will display **Unknown** for enrollment status.

Once imported, these devices might or might not be enrolled, and can have a state of either **Enrolled** or **Not contacted**. **Not contacted** means that the device has never communicated in with the Intune service.

## Delete a .csv list

1. In the Azure portal, choose **More Services** > **Monitoring + Management** > **Intune**.

2. On the Intune blade, choose **Enroll devices**, and then choose **Corporate Device Identifiers**.

3. Choose **Delete**.

For detailed specifications about International Mobile Equipment Identifiers, see [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).
