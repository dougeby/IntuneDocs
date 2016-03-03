---
title: Customize the company portal
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: get-started-article
ms.assetid:
author: Staciebarker
---

# 7. Customize the company portal
The [!INCLUDE[wit_iwportal_1](../includes/wit_iwportal_1_md.md)] is where users access company data and can do common tasks like enrolling devices, installing apps, and locating information for assistance from your IT department.

When you customize the company portal, the configurations apply to both the company portal website and company portal apps.

## Settings for customizing the company portal

1.  In the [Microsoft Intune administrator console](https://manage.microsoft.com), choose **Admin** &gt; **Company Portal**.

2.  Configure one or more of the following optional items.

**Configuration area**: Company contact information and privacy statement

|Field name|Maximum character length|More information|
    |----------|------------------------|----------------|
    |Company name|40|This name is displayed as the title of the company portal.|
    |IT department contact name|40|This name is displayed on the **Contact IT** page.|
    |IT department phone number|20|This contact number is displayed on the **Contact IT** page.|
    |IT department email address|40|This contact address is displayed on the **Contact IT** page. You must enter a valid email address in the format **alias@domainname.com**.|
    |Additional information|120|Displayed on the **Contact IT** page.|
    |Company privacy statement URL|79|You can specify your own company privacy statement that appears when users click the privacy links from the company portal. You must enter a valid URL in the format **https://www.contoso.com**.|

**Configuration area**: Support contacts

|Field name|Maximum character length|More information|
    |----------|------------------------|----------------|
    |Support website URL|150|If you have a support website that you want your users to use, specify the URL here. The URL must be in the format **https://www.contoso.com**. If you don't specify a URL, nothing is displayed for the support website on the **Contact IT** page in the company portal.|
    |Website name|40|This name is the friendly name that is displayed for the URL to the support website. If you specify a support website URL and no friendly name, then **Go to IT website** is displayed on the **Contact IT** page in the company portal.|

**Configuration area**: Customization

|Field name|More information|
    |----------|----------------|
    |Theme color|Select a theme color to apply to the company portal.|
    |Include company logo|When you enable this option, you can upload your company logo to show in your company portal. You can upload two logos: one logo that is displayed when the company portal background is white, and one logo that is displayed when the company portal background uses your selected theme color. Each logo must be a .png or .jpg file type and have a maximum resolution of 400 x 100 pixels and be 750 KB or less in size.|
    |Choose a background for [!INCLUDE[win8_client_2](./includes/win8_client_2_md.md)] company portal app|This setting affects the background for the [!INCLUDE[win8_client_2](./includes/win8_client_2_md.md)] company portal app only.|

3.  Choose **Save** to save your changes.

After you save your changes, you can use the links provided at the bottom of the **Company Portal** page of the administration console to view the company portal website. These links cannot be changed. When a user signs in, these links display your subscriptions in the company portal.

## Next steps
Congratulations! You have just completed step 7 of the *Get started with a paid subscription to Microsoft Intune* guide.
>[!div class="step-by-step"]
>[Next](.\get-started-with-a-paid-subscription-to-microsoft-intune-step-8.md)  **Enroll computers in Intune**
>
>[Previous](.\get-started-with-a-paid-subscription-to-microsoft-intune-step-6.md)  **Create policies and publish an app**
