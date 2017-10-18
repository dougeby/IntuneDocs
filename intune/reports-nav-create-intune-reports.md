---
# required metadata
title: Use the Intune Data Warehouse | Microsoft Docs 
description: Use the Intune Data Warehouse to build reports providing insight into your enterprise mobile environment. 
keywords: Intune Data Warehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/18/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 57019B11-DF9B-4D8A-95FE-254C75398DDE

# optional metadata
#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic
---

# Use the Intune Data Warehouse

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Use the Intune Data Warehouse to build reports that provide insight into your enterprise mobile environment. For example, some of the reports include:
-	Trend of users enrolling in Intune so you can optimize your license purchases
-	App and OS versions breakdown so you can review that status of mobile devices
-	Enrollment and device compliance trends so you can smoothly roll out policy updates

The Data Warehouse provides you access to more information about your mobile environment than the Azure portal. With the Intune Data Warehouse you can access:

  -  Historical Intune data
  -  Data refreshed on a daily cadence
  -  A data model using the OData standard

> [!Important]  
> You can try out the latest functionality of the Data Warehouse by using the beta version. To use the beta version, your URL must contain the query parameter `api-version=beta`. The beta version offers features before they are made generally available as a supported service. As Intune adds new features, the beta version may change behavior and data contracts. Any custom code or reporting tools dependent on the beta version may break with ongoing updates. <!-- If you experience problems with the beta service, follow [link to feedback process]() to report the issue or provide feedback.-->

**Next steps**

- Get a link and use Power BI to get insight. For instructions, see [Connect to the Intune Data Warehouse with Power BI](reports-proc-get-a-link-powerbi.md).
- With your link, create a custom report with Power BI. For instructions, see [Create a report from the OData feed with Power BI](reports-proc-create-with-odata.md).
- Get more information about the Intune Data Warehouse API, the data model, and relationships between entities<!-- , and an example of creating a custom client to retrieve data,--> see [Intune Data Warehouse API](reports-nav-intune-data-warehouse.md).