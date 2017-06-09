---
# required metadata

title: Add Apple Configurator serial numberstitleSuffix: "Intune on Azure"
description: Learn how to add serial numbers to corporate-owned iOS devices using the Apple Configurator."
keywords:
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: d408aa38-7d1e-40df-9067-246e53f6e26f

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: dagerrit
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Add Apple Configurator serial numbers

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Use these steps to add serial numbers to Intune when you want to [enroll corporate-owned iOS devices by using Apple Configurator with Setup Assistant](apple-configurator-setup-assistant-enroll-ios.md). You can add serial numbers one at a time, or upload a comma-separated-value (CSV) file of serial numbers. After you add serial numbers, you can assign a profile to them. The profile contains specific management settings that you want to apply to devices.

Other methods of enrolling iOS devices are described in [Choose how to enroll iOS devices in Intune](enrollment-method-choose-ios.md).

**To add Apple Configurator serial numbers to Intune**

1. Create a two-column, comma-separated value (.csv) list without a header. Add the IMEI identifier in the left column, and the details in the right column. The current maximum for the list is 500 rows. In a text editor, the .csv list looks something like this:

	F7TLWCLBX196,device details</br>
	DLXQPCWVGHMJ,device details

2. In the Azure portal, choose **More Services** > **Monitoring + Management** > **Intune**.

3.  On the Intune blade, choose **Enroll devices**, and then choose **Apple Enrollment**.

4. Under **Manage Apple Configurator Enrollment Settings**, select **Apple Configurator Serial Numbers**.

5. On the **Apple Configurator Serial Numbers** blade, select **Add**.

6. On the **Add Serial Numbers** blade, select a profile to apply to the serial numbers you're importing. If you are importing a file with new details that will overwrite the existing ones, select Overwrite details for existing identifiers to have the new details replace the existing details.

7. Navigate to the .csv file of serial numbers, and select **Add**.

## Assign a profile to specific serial numbers

Intune lets you assign profiles from two different places in the Azure portal. You can use the steps below, or you can assign profiles from the Apple Configurator Enrollment Profiles blade, which is where you create the profile (see [Enroll iOS devices with Apple Configurator by using Setup Assistant](apple-configurator-setup-assistant-enroll-ios.md). You can use the steps below to assign the profile only if you have already created the profile.

1. In the Azure portal, choose **More Services** > **Monitoring + Management** > **Intune**.

2. On the Intune blade, choose **Enroll devices**, and then choose **Apple Enrollment**.

3. On the **Apple Configurator Serial Numbers** blade, select the serial numbers you want to assign a profile to, and then select **Assign Profile**.

4. On the **Assign Profile** blade, select the profile you want to assign, and then select **Assign**.

## Delete serial numbers
You can delete serial numbers that you imported previously. You can delete serial numbers only if the device is unenrolled first. Once you remove a serial number, you can’t use Apple Configurator via Setup Assistant unless you re-add the serial number.

## View the state of a device
The device serial numbers can have one of two states:

- Enrolled - the device is enrolled, and it has connected to the Intune service
- Not Contacted - the device has never connected to the Intune service.
- Pending Reset - the device is enrolled, but a change has been made (for example, enrollment settings or the applied DEP profile have changed). If you change the DEP profile of a device, the changes are not applied until the device is unenrolled, and then re-enrolled.

**To view the state of a serial number**

On the **Apple Configurator Serial Numbers** blade, select the serial number whose state you want to see, and look under the **State** item.
