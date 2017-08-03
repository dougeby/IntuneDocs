---
# required metadata

title: Add IMEI identifiers to Intune
titleSuffix: "Intune on Azure"
description: Learn how to add corporate identifiers (IMEI numbers) to Microsoft Intune. "
keywords:
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/05/2017
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

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

As an Intune admin, you can create and import a comma-separated value (.csv) file that lists international mobile equipment identifier (IMEI) numbers or serial numbers. Intune uses these identifiers to specify device ownership as corporate. You can declare IMEI numbers for all supported platforms. You can only declare serial number for iOS and Android devices. Each IMEI or serial number can have details specified in the list for administrative purposes.

<!-- When you upload serial numbers for company-owned iOS devices, they must be paired with a corporate enrollment profile. Devices must then be enrolled using either Apple’s device enrollment program (DEP) or Apple Configurator to have them appear as company-owned. -->

[Learn how to find an Apple device serial number](https://support.apple.com/HT204308).<br>
[Learn how to find your Android device serial number](https://support.google.com/store/answer/3333000).

## Add corporate identifiers
To create the list, create a two-column, comma-separated value (.csv) list without a header. Add the IMEI or serial numbers in the left column, and the details in the right column. Only one type of ID, IMEI or serial number, can be imported in a single .csv file. Details are limited to 128 characters and are for administrative use only. Details aren't displayed on the device. The current limit is 500 rows per .csv file.

**Upload a .csv file that has serial numbers** – Create a two-column, comma-separated value (.csv) list without a header, and limit the list to 5,000 devices or 5 MB per .csv file.

|||
|-|-|
|&lt;ID #1&gt;|&lt;Device #1 Details&gt;|
|&lt;ID #2&gt;|&lt;Device #2 Details&gt;|

This .csv file when viewed in a text editor appears as:

```
01234567890123,device details
02234567890123,device details
```

> [!IMPORTANT]
> Some Android devices have multiple IMEI numbers. Intune only reads one IMEI number per enrolled device. If you import an IMEI number but it is not the IMEI inventoried by Intune, the device is classified as a personal device instead of a company-owned device. If you import multiple IMEI numbers for a device, uninventoried numbers display **Unknown** for enrollment status.<br>
>Also note:
>Android Serial numbers are not guaranteed to be unique or present. Check with your device supplier to understand if serial number is a reliable device ID.
>Serial numbers reported by the device to Intune might not match the displayed ID in the Android Settings/About menus on the device. Verify the type of serial number reported by the device manufacturer.


**To add a .csv list of corporate identifiers**

1. In the Intune portal, choose **Device enrollment** > **Enrollment Restrictions**, choose **Corporate Device Identifiers**, and then click **Add**.

 ![Screenshot of the corporate device identifier workspace with the Add button highlighted.](./media/add-corp-id.png)

2. In the **Add Identifiers** blade, specify the identifier type: **IMEI** or **Serial**. You can specify whether previously imported numbers should **Overwrite details for existing identifiers**.

3. Click the folder icon and specify the path to the list you want to import. Navigate to the .csv file, and select **Add**. You can click **Refresh** to see new device identifiers.

Imported devices are not necessarily enrolled. Devices can have a state of either **Enrolled** or **Not contacted**. **Not contacted** means that the device has never communicated in with the Intune service.

## Delete corporate identifiers

1. In the Intune portal, choose **Device enrollment** > **Enrollment Restrictions**, choose **Corporate Device Identifiers**, and choose **Delete**.

3. In the **Delete Identifiers** blade, brows to the .csv file of device IDs to delete, and then click **Delete**.

## IMEI specifications
For detailed specifications about International Mobile Equipment Identifiers, see [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).
