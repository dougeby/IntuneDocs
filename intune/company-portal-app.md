---
# required metadata

title: How to configure the Company Portal app
titleSuffix: Microsoft Intune
description: Learn how you can apply company specific branding to the Intune Company Portal app.
keywords:
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/21/2018
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

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

The Microsoft Intune company portal is where users access company data and can do common tasks like enrolling devices, installing apps, and locating information for assistance from your IT department.		

> [!Tip]		
> When you customize the Company Portal, the configurations apply to both the Company Portal website and Company Portal apps.		

Customizing the Company Portal helps provide a familiar and helpful experience for your end users. To do it, from the **Mobile apps** workload, choose  **Setup** > **Company Portal Branding**, then configure the required settings.	

> [!Note]		
> The Company Portal for Windows 10 will now send app logs directly to Microsoft when the user initiates the workflow to get help with an issue. This will make it easier to troubleshoot and resolve issues that are raised to Microsoft.	

## Company information and privacy statement		
The company name is displayed as the Company Portal title. The privacy statement is displayed when a user clicks on the privacy link.

Fields marked with an asterisk (*) are mandatory.		


| Field name | Max length | More information |
|---|---|---|
|**Company name**| 40 | This name is displayed as the title of the Company Portal and appears as text throughout the Intune user experience. |
| **Privacy statement URL** |     79     | You can specify your own company privacy statement that appears when users click the privacy links from the Company Portal. You must enter a valid URL in the format `<https://www.contoso.com>`. |

## Support information		
Enter your company's support infomation to provide your employee with a contact for Intune-related questions.  		

|Field name|Max length|More information|
|---|---|---|
|**Contact name** | 40 | This name is displayed on the **Contact IT** page. |
|**Phone number** | 20 | This contact number is displayed on the **Contact IT** page to enable employees to contact you for support. |
|**Email address**| 40 | This contact address is displayed on the **Contact IT** page. You must enter a valid email address in the format `alias@domainname.com`. |
|**Website name**| 40 | This name is the friendly name that is displayed for the URL to the support website. If you specify a support website URL and no friendly name, then Go to IT website is displayed on the **Contact IT** page in the Company Portal. |
|**Website URL**| 150 | If you have a support website that you want your users to use, specify the URL here. The URL must be in the format **https://www.contoso.com**. If you don't specify a URL, nothing is displayed for the support website on the **Contact IT** page in the Company Portal. |
| **Additional information**| 120 | Displayed on the **Contact IT** page. |


## Company branding customization		
You can customize your Company Portal with your company logo, company name, theme color and background.		

### Theme color
Apply a theme color to the Company Portal. Select a standard color or enter a six-digit hex code for a custom color.

|Field name|More information|
|---|---|
|**Color type**| Select a theme color to apply to the Company Portal. You can choose from a standard color, or enter a specific hex code. |
|**Choose color** or **Hex color code**| Select a theme color to apply to the Company Portal. You can choose from a standard color, or enter a specific hex code. These options are provided based on the **Color type** you select.  |

### Company logo
Upload your company logo to make it visible throughout the Intune user experience.

|Field name|More information|
|---|---|
|**Show company logo**|When you enable this option, you can upload your company logo to show in your Company Portal. You can upload two logos: one logo that is displayed when the Company Portal background is white, and one logo that is displayed when the Company Portal background uses your selected theme color. |
|**Upload a logo to use on theme color backgrounds**| This option is available if you have chosen to show the company logo. The logo must be a .png or .jpg file type and have a maximum resolution of 400 x 400 pixels and be 750 KB or less in size. |
|**Upload logo to use on light backgrounds**| This option is available if you have chosen to show the company logo. The logo must be a .png or .jpg file type and have a maximum resolution of 400 x 400 pixels and be 750 KB or less in size. |
|**Show company name next to logo**| Select this option to show the company name you entered next to the uploaded logo. |

After you save your changes, you can choose **Preview your settings in the Intune Web Portal** at the top of the blade to see how your configurations will look.
