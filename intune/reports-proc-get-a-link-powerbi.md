---
# required metadata
title: Connect to the Data Warehouse with Power BI | Microsoft Docs
description: You can download a file for use with Microsoft Power BI that allows you to load interactive, dynamically generated reports for your Intune tenant.
keywords: Intune Data Warehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/13/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 5E5A35D3-88F8-441B-8A0B-C5D7A1E5137B

# optional metadata
#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic
---

# Connect to the Data Warehouse with Power BI

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

You can download a file for use with Microsoft Power BI that allows you to load interactive, dynamically generated reports for your Intune tenant. The Data Warehouse Power BI file (pbix) contains connection settings to your tenant, and the following sample reports and charts:  

  -  Devices
  -  Enrollment
  -  App protection policy
  -  Compliance policy
  -  Device configuration profiles
  -  Software updates
  -  Device inventory logs

There are also trends highlighted for the enrollment, compliance, device configuration profile, and software updates. Sample charts and reports apply user-friendly filters to the canvas. To use advanced filters, check out the **Filter** pane in Power BI Desktop.

The following steps show you how to download the Power BI file and how to use the OData link with Power BI.

[!INCLUDE[reports-credential-reqs](./includes/reports-credential-reqs.md)]

## Install Power BI

Install the latest version of Power BI Desktop. You can download Power BI Desktop from: [PowerBI.microsoft.com](https://powerbi.microsoft.com/en-us/desktop)

## Load the data and reports using the Power BI file (pbix)

The Power BI file (pbix) contains connection information for your tenant and a set of prebuilt reports based on the Data Warehouse data model. Open the file in Power BI Desktop and sign in to the Azure AD. The report loads the data from your Intune tenant.

> [!Important]  
> Each Power BI file (pbix) may be different depending on tenant location. If you are managing multiple Intune tenants, then be sure to use the file downloaded from the Azure portal while logged in to that tenant.  

1.  Sign in to the Azure portal and choose **Monitoring + Management** > **Intune**. You can also search resources for **Intune**.  
2.  Open the **Microsoft Intune Data Warehouse API (Preview)** blade.
3.  Select **Download PowerBI file**. The file with a (pbix) extension downloads to the location you specified.
4.  Open the file with Power BI. The *Intune Data Warehouse Reports* loads, but may take a second to get your tenant data.
5.  Select **Refresh** to load your tenant data and review the reports.
6.  If Power BI has not authenticated with your Azure Active Directory credentials, Power BI prompts you to provide your credentials. When selecting your credentials, choose **Organizational account** as your authentication method.

## Load the data in Power BI using the OData link

With a client authenticated to Azure AD, the OData URL connects to the RESTful endpoint in the Data Warehouse API that exposes the data model to your reporting client. Follow these instructions to use Power BI Desktop to connect and create your own reports. You are not limited to Power BI Desktop, but can use your favorite analytic tool with the OData URL provided the client supports OAUTH2.0 authentication and the OData v4.0 standard.

1.  Sign in to the Azure portal and choose **Monitoring + Management** > **Intune**. You can also search resources for **Intune**.  
2.  Open the **Microsoft Intune Data Warehouse API (Preview)** blade.
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

You can find the answers to questions about your environment such as the number of devices enrolled by day over the last week. You can gain insight into your Intune tenant and client population using the reports using the Intune Data Warehouse Power BI file (pbix) retrieved from the blade in Azure. However, Intune provides a number of additional ways to extend or reuse the data. There is a lot more that you can do with Power BI and the Intune Data Warehouse API, for example:

<!-- -  You can use Power BI Desktop to create additional report types with your data. For example, you could create a custom chart representing the ratio of device manufactures in your enterprise. For more information about creating custom reports with Power BI and the Intune Data Warehouse, see `BLOG POST ON POWER BI`. -->
 -  Your tenant data is organized to help you pull insight from your data. For more information about how the data is organized, see [Data Warehouse Data Model](reports-ref-data-model.md).
 -  You can also access the data from a RESTful interface and incorporate the data into your own app. For more information, see [Get data from the Data Warehouse API with a REST client](reports-proc-data-rest.md).
