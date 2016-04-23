---
# required metadata

title: Customize the Company Portal | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service:
ms.technology:
ms.assetid: eb4a9f01-f857-4563-ab6f-5d0d7dfa659d

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Customize the Company Portal
The [!INCLUDE[wit_iwportal_1](../includes/wit_iwportal_1_md.md)] is where users access company data and can do common tasks like enrolling devices, installing apps, and locating information for assistance from your IT department.

> [!TIP]
> When you customize the Company Portal, the configurations apply to both the Company Portal website and Company Portal apps.

Customizing the Company Portal helps provide a familiar and helpful experience for your end users. To do it, just log into the [Microsoft Intune administrator console](https://manage.microsoft.com) as a tenant or service administrator, choose **Admin** &gt; **Company Portal** and configure the Company Portal settings.

![alt text](./media/companyportal.png "Company portal settings in the ADMIN workspace of the Intune administration console")

## Company contact information and privacy statement
The company name is displayed as the Company Portal title. The contact information and details are displayed to users in the Contact IT screen of the Company Portal. The privacy statement is displayed when a user clicks on the privacy link.

|Field name|Max length|More information|
    |----------|------------------------|----------------|
    |Company name|40|This name is displayed as the title of the Company Portal.|
    |IT department contact name|40|This name is displayed on the **Contact IT** page.|
    |IT department phone number|20|This contact number is displayed on the **Contact IT** page.|
    |IT department email address|40|This contact address is displayed on the **Contact IT** page. You must enter a valid email address in the format **alias@domainname.com**.|
    |Additional information|120|Displayed on the **Contact IT** page.|
    |Company privacy statement URL|79|You can specify your own company privacy statement that appears when users click the privacy links from the Company Portal. You must enter a valid URL in the format **https://www.contoso.com**.|

## Support contacts
The support website is displayed to users in the Company Portal to enable them to access online support.

|Field name|Max length|More information|
    |----------|------------------------|----------------|
    |Support website URL|150|If you have a support website that you want your users to use, specify the URL here. The URL must be in the format **https://www.contoso.com**. If you don't specify a URL, nothing is displayed for the support website on the **Contact IT** page in the Company Portal.|
    |Website name|40|This name is the friendly name that is displayed for the URL to the support website. If you specify a support website URL and no friendly name, then **Go to IT website** is displayed on the **Contact IT** page in the Company Portal.|

## Company branding customization
You can customize your Company Portal with your company logo, company name, theme color and background.

|Field name|More information|
    |----------|----------------|
    |Theme color|Select a theme color to apply to the Company Portal.|
    |Include company logo|When you enable this option, you can upload your company logo to show in your Company Portal. You can upload two logos: one logo that is displayed when the Company Portal background is white, and one logo that is displayed when the Company Portal background uses your selected theme color. Each logo must be a .png or .jpg file type and have a maximum resolution of 400 x 100 pixels and be 750 KB or less in size.|
    |Choose a background for [!INCLUDE[win8_client_2](../includes/win8_client_2_md.md)] Company Portal app|This setting affects the background for the [!INCLUDE[win8_client_2](../includes/win8_client_2_md.md)] Company Portal app only.|


After you save your changes, you can use the links provided at the bottom of the **Company Portal** page of the administration console to view the Company Portal website. These links cannot be changed. When a user signs in, these links display your subscriptions in the Company Portal.

### Next steps
Congratulations! You have just completed step 7 of the *Start with a paid subscription to Microsoft Intune* guide.
>[!div class="step-by-step"]

>[&larr; **Create policies and apps**](.\start-with-a-paid-subscription-to-microsoft-intune-step-6.md)       [**Enroll devices** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)  
