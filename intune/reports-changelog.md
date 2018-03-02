---
# required metadata
title: Intune Data Warehouse Change log | Microsoft Docs
description: A list of changes in the Intune Data Warehouse API.
keywords: Intune Data Warehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/23/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: E85DBB2D-67BB-4E10-82D6-E43046B9C43C

# optional metadata
#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: aanavath
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic
---

# Change log for the Intune Data Warehouse API

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Keep current on updates to the Intune Data Warehouse.

## 1801
_Released January 2018_

### Intune Data Warehouse application-only authentication <!-- 1867540 -->

You can set up an application using Azure Active Directory (Azure AD) and authenticate to the Intune Data Warehouse. For more information see, [Intune Data Warehouse application-only authentication](data-warehouse-app-only-auth.md).

### Azure AD and Intune credential requirements <!-- 2077525 -->

- An Intune license is no longer required to be assigned to the user when accessing the Intune Data Warehouse (including the API).
- The Intune role name has been changed from **Reports** to **Intune data warehouse**. 

    For more information, see [Azure AD and Intune credential requirements](reports-api-url.md#azure-ad-and-intune-credential-requirements).

### OData query options <!-- 2077711 -->

You can use <code>$select</code> as an OData query parameter. The current version supports the following OData query parameters: <code>$filter</code>, <code>$orderby</code>, <code>$select</code>, <code>$skip</code>, and <code>$top</code>. For more information, see [OData query options](reports-api-url.md#odata-query-options).

### New entities in the in Data Warehouse data model <!-- 2077804 -->

 - The entity, [**MobileAppDeviceuserInstallStatus**](reports-ref-application.md#mobileappdeviceuserinstallstatus), has been added. The **MobileAppDeviceUserInstallStatus** represents a mobile app install status for a given device and user.
 - The entity, [**MobileAppInstallState**](reports-ref-application.md#mobileappinstallstate), has been added. The **MobileAppInstallState** entity represents the install state for a mobile application after it has been assigned to a group containing devices, users, or both. 

## 1710
_Released November  2017_

### A new entity collection named Current User is limited to currently active user data <!-- 1544273 -->

The **Users** entity collection contains all the Azure Active Directory (Azure AD) users with assigned licenses in your enterprise. These records include user states during the data collection period, even if the user has been removed. For example, a user may be added to Intune and then removed during the course of the last month. While this user is not present at the time of the report, the user and state are present in the data. You could create a report that would show the duration of the user's historic presence in your data.

In contrast, the new **Current User** entity collection only contains users who have not been removed. The **Current User** entity collection only contains currently active users. For information about the **current user** entity collection, see [Reference for current user entity](reports-ref-current-user.md).

## 1709
_Released October  2017_

### User device association entity collection added to Intune Data Warehouse data model <!-- 1187917 -->

You can now build reports and data visualizations using the user device association information that associates user and device entity collections. The data model can be accessed through the Power BI file (PBIX) retrieved from the Data Warehouse Intune page, through the OData endpoint, or by developing a custom client. For more information, see the [User Device Association](reports-ref-user-device.md).

### New entities in the in Data Warehouse data model <!-- 1479526 --><!-- -->

 - The entity, [**UserDeviceAssociation**](reports-ref-user-device.md), added. **UserDeviceAssociation** contains user device associations in your organization. You can now build reports and data visualizations using the user device association information that associates user and device entity collections.  
 - The entity, [**IntuneManagementExtension**](reports-ref-intunemanagementextension.md), added. **IntuneManagementExtension** contains entities for mobile devices that track information such as version and installation status.

## Next steps
 - Learn [what’s new each week in Intune](whats-new.md). You can also find out about upcoming changes, important notices about the service, and information about past releases.
 - Read the [Microsoft Intune Blog](http://go.microsoft.com/fwlink/?LinkID=273882).
