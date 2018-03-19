---
# required metadata

title: How to categorize devices into groups in Intune
titleSuffix: "Microsoft Intune"
description: Learn how to categorize devices into groups for easier management.
keywords:
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
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

# Categorize devices into groups for easier management

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Use Microsoft Intune device categories to automatically add devices to groups based on categories that you define. This makes it easier for you to manage those devices.

Device categories use the following workflow:
1. Create categories that users can choose from when they enroll their device.
2. When end users of iOS and Android devices enroll a device, they must choose a category from the list of categories you configured. To assign a category to a Windows device, end users must use the Company Portal website.
3. You can then deploy policies and apps to these groups.

You can create any device categories you want. For example:
- Point of sale device
- Demonstration device
- Sales
- Accounting
- Manager

## How to configure device categories

### Step 1 - Create device categories in the Intune blade of the Azure portal
1. In [Intune in the Azure portal](https://aka.ms/intuneportal), choose **Device enrollment**.
2. On the **Device enrollment** blade, choose **Device categories**.
3. On the **Device categories** page, choose **Create** to add a new category.
4. On the **Create device category** blade, enter a **Name** for the new category, and an optional **Description**.
5. When you are done, select **Create**. You can see the new category in the list of categories.

You'll use the device category name when you create Azure Active Directory (Azure AD) security groups in step 2.

### Step 2 - Create Azure Active Directory security groups
In this step, you'll create dynamic groups in the Azure portal, based on the device category and device category name.

To continue, refer to [Using attributes to create advanced rules](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects) in the Azure AD documentation.

Use the information in this section to create a device group with an advanced rule, by using the **deviceCategory** attribute. For example: **device.deviceCategory -eq** "*the device category name you got from the Azure portal*".

After you configure device groups, and users enroll their device, they are presented with a list of the categories you configured. After they choose a category and finish enrollment, their device is added to the Active Directory security group that corresponds with the category they chose.

### View the categories of devices you manage

1.	In [Intune in the Azure portal](https://aka.ms/intuneportal), choose **Devices**.

2.	Under **Manage**, select **All devices**.

3.	In the list of devices, examine the **Device category** column.

If the **Device category** column isn’t shown, select **Columns**. Choose **Device category** from the list, and then select **Apply**.

### To change the category of a device

1. In [Intune in the Azure portal](https://aka.ms/intuneportal), choose **Devices**.
2. On the **Devices** blade, under the **Manage** section, choose **All devices**.
3. In the list of devices, choose the device you want. Then, on the device properties blade under the **Manage** section, choose **Properties**.
4. On the next blade, you can change the **Device category** of the selected device to any of the category names you previously configured.

## After you configure device groups

When end users of iOS and Android devices enroll their device, they must choose a category from the list of categories you configured. After they choose a category and finish enrollment, their device is added to the Intune device group, or the Active Directory security group that corresponds with the category they chose.

Windows users should use the Company Portal website to select a category.

Regardless of platform, your end users can always go to portal.manage.microsoft.com after enrolling the device. Have the user access the Company Portal website, and go to **My Devices**. The user can choose an enrolled device listed on the page, and then select a category.

After choosing a category, the device is automatically added to the corresponding group you created. If a device is already enrolled before you configure categories, the user sees a notification about the device on the Company Portal website. This lets the user know to select a category the next time they access the Company Portal app on iOS or Android.

## Further information
- You can edit a device category in the Azure portal, but you must manually update any Azure AD security groups that reference this category.

- If you delete a category, devices assigned to it display the category name **Unassigned**.
