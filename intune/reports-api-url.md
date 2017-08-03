---
# required metadata
title: Intune Data Warehouse API endpoint | Microsoft Docs 
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
# Intune Data Warehouse API endpoint

You can use the Intune Data Warehouse API with an account with specific role-based access controls and Azure AD credentials. You will then authorize your REST client with Azure AD using OAuth 2.0. And finally, you will form a meaningful URL to call a data warehouse resource.

## Azure AD and Intune credential requirements

Authentication and authorization are based on Azure AD credentials and Intune role-based access control (RBAC). All global administrators and Intune service administrators for your tenant have access to the API by default. Use Intune roles to provide access for more users by giving them access to the **Reporting resource**.

Requirements for accessing the API are:

  -  Intune license must be assigned to the user
  -  User must be one of:
      -  Azure AD global administrator
      -  An Intune service administrator
      -  User with role-based access to **Reports** resource

## Authorization

Azure Active Directory (Azure AD) uses OAuth 2.0 to enable you to authorize access to web applications and web APIs in your Azure AD tenant. This guide is language independent, and describes how to send and receive HTTP messages without using any of our open-source libraries. The OAuth 2.0 authorization code flow is described in [section 4.1](https://tools.ietf.org/html/rfc6749#section-4.1) of the OAuth 2.0 specification.

For more information, see [Authorize access to web applications using OAuth 2.0 and Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-protocols-oauth-code).

## API URL structure

The Data Warehouse API endpoints read the entities for each set. The API supports a **GET** HTTP verb, and a subset of query options.

The URL for Intune uses the following format:  
https://fef.{***location***}.manage.microsoft.com/ReportingService/DataWarehouseFEService/{***entity-collection***}?api-version={***api-version***}

The URL contains the following elements:

| Element | Example | Description |
|-------------------|------------|--------------------------------------------------------------------------------------------------------------------|
| location | msua06 | The base URL can be found by viewing the Data Warehouse API blade in the Azure portal. |
| entity-collection | dates | The name of the OData entity collection. For more information on collections and entities in the data model, see [Data Model](reports-ref-data-model.md). |
| api-version | beta | Version is the version of the API to access. For more information, see [Version](#API-version-information). |


## API version information

The current version of the API is: `beta`. 

## OData query options

The current version supports the following OData query parameters: `$skip, $top, $filter, $orderby`.