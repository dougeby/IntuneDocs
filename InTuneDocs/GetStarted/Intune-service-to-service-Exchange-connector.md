---
title: Configure the Microsoft Intune Exchange connector for hosted Exchange
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 
author: jeffgilb
---
# Configure the Intune service to service connector 

Use this information to connect [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] and hosted Exchange without an on-premises infrastructure.



## Set up the Service-to-Service Connector
> [!IMPORTANT]
> Before you being installing and configuring the service-to-service connector, ensure that you meet the [Exchange connector installation requirements](Intune-Exchange-connector-requirements.md).

1.  Open the [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)].

2.  In the workspace shortcuts pane, choose **ADMIN**.

3.  In the navigation pane, under **Mobile Device Management**, expand **Microsoft Exchange** and then choose **Set Up Exchange Connection**.

4.  On the **Set Up Exchange Connection** page, choose **Set Up Service to Service Connector**.
![IntuneSA5cServiceToServiceConnector](./media/IntuneSA5cServiceToServiceConnector.PNG)

The Service-to-Service Connector will automatically configure and synchronize with your Hosted Exchange environment.

## Validate your Exchange connection

After you have successfully configured the [!INCLUDE[wit_exch_2](../includes/wit_exch_2_md.md)], in the [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] choose the **ADMIN** workspace, and under **Mobile Device Management**, choose **Microsoft Exchange** and validate that the details you provided appear under **Exchange Connection Information**.

You can also check the time and date of the last successful synchronization attempt.