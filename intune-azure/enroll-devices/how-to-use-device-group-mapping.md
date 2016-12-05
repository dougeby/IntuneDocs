---
# required metadata

title: How to use device categories in Microsoft Intune | Intune Azure preview | Microsoft Docs
description: "Intune Azure preview: "
keywords:
author: robstackmsftms.author: robstack
manager: angrobe
ms.date: 10/12/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 7b668c37-40b9-4c69-8334-5d8344e78c24

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# How to use device categories in Microsoft Intune


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Use Microsoft Intune device group mapping to automatically add devices to groups based on categories that you define, in order to make it easier for you to manage those devices. 

Device categories use the following workflow:
1.	Create categories that users will choose from when they enroll their device
4.	When end users enroll their device, they must choose a category from the list of categories you configured. If a device is already enrolled, the end user will be asked to select a category the next time they access the Company Portal app.


You can create any device categories you want, for example:
•	Point of sale device
•	Demonstration device
•	Sales
•	Accounting
•	Manager

## How to configure device categories
### Step 1 - Create device categories in the Intune Azure portal
1.	In the Intune Azure Portal, choose **Enrollment**.
2.	In the **Enrollment** workload, choose **Device Categories**.
3.	On the **Device Categories** page, choose **Create** to add a new category. 
4.	In the next blade, enter a **Name** for the new category, and an optional **Description**.
5.	When you are done, click **Create**. You’ll see the category you just created in the list of categories.

You'll use the device category name when you create Azure Active Directory security groups in step 2.

### Step 2 - Create Azure Active Directory security groups
In this step, you'll create dynamic groups in the Azure portal based on the device category and device category name.
To continue, refer to the topic [Using attributes to create advanced rules](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects) in the Azure Active Directory documentation. Use the information in this topic to create a device group with an advanced rule using the **deviceCategory** attribute. For example (**device.deviceCategory -eq** "*<the device category name you got from the Intune portal>*")
After you configure device groups
When users enroll their device, they are presented with a list of the categories you configured. After they choose a category and finish enrollment, their device is added to the Active Directory security group that corresponds with the category they chose.

### How to view the categories of devices you manage
1.	In the Intune Azure Portal, open the **Devices and Groups** workload.
2.	Under **Manage**, click **MDM devices**.
3.	In the list of devices, examine the **Device category** column.

If the **Device category** column isn’t displayed, click **Columns**, choose **Device category** from the list, and then click **Apply**.

## Further information
•	You can edit a device category in the Azure Portal, but if you do this, you must manually update any Azure Active Directory Security groups that reference this category.
•	If you delete a category, any devices that were assigned to it will subsequently display the category name **Unassigned**.
