---
# required metadata

title: Add Apple Configurator serial numbers | Intune Azure preview | Microsoft Docs
description: "Intune Azure preview: Learn how to add serial numbers to corporate-owned iOS devices using the Apple Configurator."
keywords:
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: d408aa38-7d1e-40df-9067-246e53f6e26f

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Add Apple Configurator serial numbers

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Use these steps to add serial numbers to Intune when you are enrolling corporate-owned iOS devices using Apple Configurator running on a Mac computer. This process resets the device to factory settings and prepares it to run Setup Assistant, installing the company's policies for the device’s new user. For more details about using enrolling iOS devices by using Apple Configurator, see _______________________.

## Prerequisites

- [Enroll iOS devices with Apple Configurator by using Setup Assistant](enroll-ios-devices-with-apple-configurator-using-setup-assistant.md)

**To add Apple Configurator serial numbers to Intune:**

1. Create a two-column, comma-separated value (.csv) list without a header. Add the IMEI identifier in the left column, and the details in the right column. The current maximum for the list is 500 rows. In a text editor, the .csv list looks something like this:

	01 234567 890123,device details</br>
	02 234567 890123,device details

2. In the Azure portal **Enrollment** workload, choose **Apple Enrollment**.

3. Under **Manage Apple Configurator Enrollment Settings**, select **Apple Configurator Serial Numbers**.

4. On the **Apple Configurator Serial Numbers** blade, select **Add**.

5. On the **Add Serial Numbers** blade, select a profile to apply to the serial numbers you're importing. If you are importing a file with new details that will overwrite the existing ones, select Overwrite details for existing identifiers to have the new details replace the existing details.

6. Navigate to the .csv file of serial numbers, and select **Add**.

## Assign a profile to specific serial numbers

You can assign profiles in more than one place. You can use the steps below, or you can assign profiles from the Apple Configurator Enrollment Profiles blade (see [Enroll iOS devices with Apple Configurator by using Setup Assistant](enroll-ios-devices-with-apple-configurator-using-setup-assistant.md).  

1. On the **Apple Configurator Serial Numbers** blade, select the serial numbers you want to assign a profile to, and then select **Assign Profile**.

2. On the **Assign Profile** blade, select the profile you want to assign, and then select **Assign**.

## Delete serial numbers
You can delete serial numbers that you imported previously. You can delete serial numbers only if the device is unenrolled first. Once you remove a serial number, you can’t use Apple Configurator via Setup Assistant unless you re-add the serial number.

## View the state of a device
The device serial numbers can have one of two states:

- Enrolled - the device is enrolled, and it has connected to the Intune service
- Not Contacted - the device has never connected to the Intune service.
- Pending Reset - the device is enrolled, but a change has been made (for example, enrollment settings or the applied DEP profile have changed). If you change the DEP profile of a device, the changes are not applied until the device is unenrolled, and then re-enrolled.

**To view the state of a serial number:**

On the **Apple Configurator Serial Numbers** blade, select the serial number whose state you want to see, and look under the **State** item.
