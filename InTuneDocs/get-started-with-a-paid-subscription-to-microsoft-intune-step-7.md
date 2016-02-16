---
title: Get started with a paid subscription to Microsoft Intune - Step 7
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: get-started-article
ms.assetid: d158503c-1276-422b-ab81-5f66c1cd7e7a
author: Staciebarker
---

# Step 7: Customize the company portal
The [!INCLUDE[wit_iwportal_1](./includes/wit_iwportal_1_md.md)] is where users access company data and can do common tasks like enrolling devices, installing apps, and locating information for assistance from your IT department.

When you customize the company portal, the configurations apply to both the company portal website and company portal apps.

## <a name="BKMK_ToCustomizeCompanyPortal"></a>Settings for customizing the company portal

1.  In the [Microsoft Intune administrator console](https://manage.microsoft.com), click **Admin** &gt; **Company Portal**.

2.  Configure one or more of the following optional items.

    |Configuration area|Field name|Maximum character length|More information|
    |----------------------|--------------|----------------------------|--------------------|
    |Company contact information and privacy statement|Company name|40|This name is displayed as the title of the company portal.|
    ||IT department contact name|40|This name is displayed on the **Contact IT** page.|
    ||IT department phone number|20|This contact number is displayed on the **Contact IT** page.|
    ||IT department email address|40|This contact address is displayed on the **Contact IT** page.<br /><br />You must enter a valid email address in the format **alias@domainname.com**.|
    ||Additional information|120|Displayed on the **Contact IT** page.|
    ||Company privacy statement URL|79|You can specify your own company privacy statement that appears when users click the privacy links from the company portal.<br /><br />You must enter a valid URL in the format **https://www.contoso.com**.|
    |Support contacts|Support website URL|150|If you have a support website that you want your users to use, specify the URL here. The URL must be in the format **https://www.contoso.com**.<br /><br />If you don't specify a URL, nothing is displayed for the support website on the **Contact IT** page in the company portal.|
    ||Website name|40|This name is the friendly name that is displayed for the URL to the support website.<br /><br />If you specify a support website URL and no friendly name, then **Go to IT website** is displayed on the **Contact IT** page in the company portal.|
    |Customization|Theme color|Not applicable|Select a theme color to apply to the company portal.|
    ||Include company logo|Not applicable|When you enable this option, you can upload your company logo to show in your company portal. You can upload two logos: one logo that is displayed when the company portal background is white, and one logo that is displayed when the company portal background uses your selected theme color.<br /><br />Each logo must be a .png or .jpg file type and have a maximum resolution of 400 x 100 pixels and be 750 KB or less in size.|
    ||Choose a background for [!INCLUDE[win8_client_2](./includes/win8_client_2_md.md)] company portal app|Not applicable|This setting affects the background for the [!INCLUDE[win8_client_2](./includes/win8_client_2_md.md)] company portal app only.|

3.  Click **Save** to save your changes.

After you save your changes, you can use the links provided at the bottom of the **Company Portal** page of the administration console to view the company portal website. These links cannot be changed. When a user signs in, these links display your subscriptions in the company portal.

**Prev** Step 6
**Next** Step 8
