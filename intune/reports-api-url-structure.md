---
# required metadata
title: API URL Structure | Microsoft Docs 
description: Reference topic describes the API URL structure.
keywords: Intune Data Warehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: A7A174EC-109D-4BB8-B460-F53AA2D033E6

# optional metadata
#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic
---

# API URL Structure

The Data Warehouse API endpoints read the entities for each set. The API supports a **GET** HTTP verb, and subset of query options.

## Format

The URL for intune uses the following format:  
https://fef.{***location***}.manage.microsoft.com/ReportingService/DataWarehouseFEService/{***entity-collection***}?api-version={***api-version***}

The URL contains the contains the following elements:

| Element | Example | Description |
|-------------------|------------|--------------------------------------------------------------------------------------------------------------------|
| location | msua06 | The base URL can be found by viewing the Data Warehouse API blade in the Azure portal. |
| entity-collection | dates | The name of the OData entity collection. For more information on collections and entities in the data model, see [Data Model](reports-ref-data-model.md). |
| api-version | beta | Version is the version of the API to access. For more information see [Version](#Version). |


## Version

The current version of the API is: `beta`. 

## OData queries options

The current version supports the following OData query parameters: `$skip, $top, $filter, $orderby`.