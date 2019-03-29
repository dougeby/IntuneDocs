---
# required metadata
title: Connect to the Data Warehouse with Power BI
titlesuffix: Microsoft Intune
description: You can download a file for use with Microsoft Power BI that allows you to load interactive, dynamically generated reports for your Microsoft Intune tenant.
keywords: Intune Data Warehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/28/2019
ms.topic: reference
ms.prod:
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology:
ms.assetid: 5E5A35D3-88F8-441B-8A0B-C5D7A1E5137B

# optional metadata
#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-classic
ms.collection: M365-identity-device-management
---

# Connect to the Data Warehouse with Power BI

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

You can use the Power BI Compliance app to load interactive, dynamically generated reports for your Intune tenant. Additionally, you can load your tenant data in Power BI using the OData link. Intune provides connection settings to your tenant so that you can view the following sample reports and charts related to:  

  -  Devices
  -  Enrollment
  -  App protection policy
  -  Compliance policy
  -  Device configuration profiles
  -  Software updates
  -  Device inventory logs

There are also trends highlighted for the enrollment, compliance, device configuration profile, and software updates. Sample charts and reports apply user-friendly filters to the canvas. To use advanced filters, check out the **Filter** pane in Power BI Desktop.

The following steps show you how to download the Power BI file and how to use the OData link with Power BI.

[!INCLUDE [reports-credential-reqs](./includes/reports-credential-reqs.md)]

## Install Power BI

Install the latest version of [Power BI Desktop](https://aka.ms/intune/datawarehouseapi/installpowerbi). For more information, see [Power BI Desktop](https://powerbi.microsoft.com/desktop)

## Load the data and reports using the Power BI Compliance app

The Power BI Compliance app contains information for your tenant and a set of prebuilt reports based on the Data Warehouse data model. Open the report in Power BI Desktop and sign in to the Azure AD. The report loads the data from your Intune tenant.

> [!Important]  
> Your Power BI reports may be different depending on tenant location. If you are managing multiple Intune tenants, be sure to use the report from the Azure portal while logged in to that tenant.  

1.  Sign in to the Azure portal and choose **Monitoring + Management** > **Intune**. You can also search resources for **Intune**.  
2.  Open the **Set up Intune Data Warehouse** blade.
3.  Select **Get Power BI App** to access and share pre-created Power BI reports for your tenant in the browser.

> [!NOTE]
> If Power BI has not authenticated with your Azure Active Directory credentials, Power BI prompts you to provide your credentials. When selecting your credentials, choose **Organizational account** as your authentication method.

### Add additional filters to the Intune Compliance app

If you would like to use additional filters for your Power BI reports, use the followin steps:

1. Open the [Power BI Compliance](https://app.powerbi.com/groups/me/getapps/services/Intune_dw_compliance) app in your web browser.
2. Click **Non-Compliant Devices** and select **Non-Compliant** in the **complianceStatus** filter. 
3. Click on **Unknown Devices** and select **Not Yet Available** in the **complianceStatus** filter. 

## Load the data in Power BI using the OData link

With a client authenticated to Azure AD, the OData URL connects to the RESTful endpoint in the Data Warehouse API that exposes the data model to your reporting client. Follow these instructions to use Power BI Desktop to connect and create your own reports. You are not limited to Power BI Desktop, but can use your favorite analytic tool with the OData URL provided the client supports OAUTH2.0 authentication and the OData v4.0 standard.

1.  Sign in to the Azure portal and choose **Monitoring + Management** > **Intune**. You can also search resources for **Intune**.  
2.  Open the **Set up Intune Data Warehouse** blade.
3. Retrieve the custom feed URL from the reporting blade, for example `https://fef.{yourinfo}.manage.microsoft.com/ReportingService/DataWarehouseFEService/dates?api-version=beta`
4. Open **Power BI Desktop**.
5. Choose **Home** > **Get Data**. Select **OData feed**.
6. Choose **Basic**.
7. Type or paste the **OData URL** into the URL box.
8. Select **OK**.
9. If you have not authenticated to Azure AD for your tenant from the Power BI desktop client, type your credentials. To gain access to your data, you must authorize with Azure Active Directory (Azure AD) using OAuth 2.0.  
    1.  Select **Organizational account**.  
    2.  Type your username and password.  
    3.  Select **Sign In.**  
    4.  Select **Connect**.  
10. Select **Load**.

## Next steps

You can find the answers to questions about your environment such as the number of devices enrolled by day over the last week. You can gain insight into your Intune tenant and client population using the Intune Data Warehouse Power BI reports retrieved from the blade in Azure. However, Intune provides a number of additional ways to extend or reuse the data. Power BI and the Intune Data Warehouse API provide additional functionality, for example:

<!-- -  You can use Power BI Desktop to create additional report types with your data. For example, you could create a custom chart representing the ratio of device manufactures in your enterprise. For more information about creating custom reports with Power BI and the Intune Data Warehouse, see `BLOG POST ON POWER BI`. -->
 -  Your tenant data is organized to help you pull insight from your data. For more information about how the data is organized, see [Data Warehouse Data Model](reports-ref-data-model.md).
 -  You can also access the data from a RESTful interface and incorporate the data into your own app. For more information, see [Get data from the Data Warehouse API with a REST client](reports-proc-data-rest.md).
