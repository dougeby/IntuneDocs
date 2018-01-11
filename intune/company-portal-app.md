---
# required metadata

title: How to configure the Company Portal apptitleSuffix: "Azure portal"
description: Learn how you can apply company specific branding to the Intune Company Portal app. "
keywords:
author: Erikre
ms.author: erikre
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: dec6f258-ee1b-4824-bf66-29053051a1ae

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---

# How to configure the Microsoft Intune Company Portal app

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

The Microsoft Intune company portal is where users access company data and can do common tasks like enrolling devices, installing apps, and locating information for assistance from your IT department.		

> [!Tip]		
> When you customize the Company Portal, the configurations apply to both the Company Portal website and Company Portal apps.		

Customizing the Company Portal helps provide a familiar and helpful experience for your end users. To do it, from the **Mobile apps** workload, choose  **Setup** > **Company Portal Branding**, then configure the required settings.		

## Company contact information and privacy statement		
The company name is displayed as the Company Portal title. The contact information and details are displayed to users in the **Contact IT** screen of the Company Portal. The privacy statement is displayed when a user clicks on the privacy link.		


|Field name|Max length|More information|		
|-|-|-|		
|**Company name**|40|This name is displayed as the title of the Company Portal.|		
|**IT department contact name**|40|This name is displayed on the **Contact IT** page.|		
|**IT department phone number**|20|This contact number is displayed on the **Contact IT** page.|		
|IT department email address|40|This contact address is displayed on the **Contact IT** page. You must enter a valid email address in the format **alias@domainname.com**.|		
|**Additional information**|120|Displayed on the **Contact IT** page.|		
|**Company privacy statement URL**|79|You can specify your own company privacy statement that appears when users click the privacy links from the Company Portal. You must enter a valid URL in the format **https://www.contoso.com**.|		

## Support contacts		
The support website is displayed to users in the Company Portal to enable them to access online support.		



|Field name|Max length|More information|		
|-|-|-|		
|**Support website URL**|150|If you have a support website that you want your users to use, specify the URL here. The URL must be in the format **https://www.contoso.com**. If you don't specify a URL, nothing is displayed for the support website on the **Contact IT** page in the Company Portal.|		
|**Support website name**|40|This name is the friendly name that is displayed for the URL to the support website. If you specify a support website URL and no friendly name, then Go to IT website is displayed on the **Contact IT** page in the Company Portal.		

## Company branding customization		
You can customize your Company Portal with your company logo, company name, theme color and background.		



|Field name|More information|		
|-|-|		
|**Theme color**|Select a theme color to apply to the Company Portal.|		
|**Show company logo**|When you enable this option, you can upload your company logo to show in your Company Portal. You can upload two logos: one logo that is displayed when the Company Portal background is white, and one logo that is displayed when the Company Portal background uses your selected theme color. Each logo must be a .png or .jpg file type and have a maximum resolution of 400 x 100 pixels and be 750 KB or less in size.<br>You can also show the company name you entered next to the uploaded logo.|		

After you save your changes, you can choose **Preview your settings in the Intune Web Portal** to see how your configurations will look.
