---
# required metadata

title: How to use device categories in Intune
titleSuffix: "Azure portal"
description: Learn how to use device categories that users can choose when they enroll their devices in Intune."
keywords:
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/11/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 7b668c37-40b9-4c69-8334-5d8344e78c24

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: jieyang
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Map device groups

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Use Microsoft Intune device categories to automatically add devices to groups based on categories that you define, in order to make it easier for you to manage those devices.

Device categories use the following workflow:
1. Create categories that users can choose from when they enroll their device
2. When end users of iOS and Android devices enroll their device, they must choose a category from the list of categories you configured. To assign a category to a Windows device, end users must use the Company Portal website (for more information, see **After you configure device groups** in this article for more details).
3. You can then deploy policies and apps to these groups.

You can create any device categories you want, for example:
- Point of sale device
- Demonstration device
- Sales
- Accounting
- Manager

## How to configure device categories

### Step 1 - Create device categories in the Intune blade of the Azure portal
1. In the Azure portal, choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Device Enrollment**.
3. On the **Device Enrollment** blade, choose **Device Categories**.
4. On the **Device Categories** page, choose **Create** to add a new category.
5. On the next blade, enter a **Name** for the new category, and an optional **Description**.
6. When you are done, click **Create**. You can see the new category in the list of categories.

You'll use the device category name when you create Azure Active Directory security groups in step 2.

### Step 2 - Create Azure Active Directory security groups
In this step, you'll create dynamic groups in the Azure portal based on the device category and device category name.

To continue, refer to the article [Using attributes to create advanced rules](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects) in the Azure Active Directory documentation.

Use the information in this section to create a device group with an advanced rule using the **deviceCategory** attribute. For example, (**device.deviceCategory -eq** "*<the device category name you got from the Azure portal>*")

After you configure device groups, and users enroll their device, they are presented with a list of the categories you configured. After they choose a category and finish enrollment, their device is added to the Active Directory security group that corresponds with the category they chose.

### How to view the categories of devices you manage

1.	In the Azure portal, choose **More Services** > **Monitoring + Management** > **Intune**.

2. In the Intune blade of the Azure portal, choose **Devices and Groups**.

3.	Under **Manage**, click **All devices**.

4.	In the list of devices, examine the **Category** column.

If the **Category** column isn’t displayed, click **Columns**, choose **Category** from the list, and then click **Apply**.

### To change the category of a device

1. In the Azure portal, choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Devices & Groups**.
4. On the **Devices and Groups** blade, choose **Manage** > **All devices**.
5. In the list of devices, choose the device you want, then, on the device properties blade, choose **Manage** > **Properties**.
6. On the next blade, you can change the **Device category** of the selected device to any of the category names you previously configured.

## After you configure device groups

When end users of iOS and Android devices enroll their device, they must choose a category from the list of categories you configured. After they choose a category and finish enrollment, their device is added to the Intune device group, or Active Directory security group that corresponds with the category they chose.

End users on Windows should use the Company Portal website to select a category.

Regardless of platform, your end users can always go to portal.manage.microsoft.com after enrolling the device. Have the user access the Company Portal website and go to **My Devices**. They can choose an enrolled device listed on the page, then select a category.

After choosing a category, the device is automatically added to the corresponding group you created. If a device is already enrolled before you configure categories, the end user will see a notification about the device on the Company Portal website, and will be asked to select a category the next time they access the Company Portal app on iOS or Android.

## Further information
- You can edit a device category in the Azure portal, but you must manually update any Azure Active Directory Security groups that reference this category.

- If you delete a category, devices assigned to it display the category name **Unassigned**.
