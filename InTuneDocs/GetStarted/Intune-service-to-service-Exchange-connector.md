---
title: Configure the Microsoft Intune Exchange connector for hosted Exchange
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid:
author: NathBarn
---
# Configure the Intune service to service connector

Use this information to connect Microsoft Intune and Office 365-hosted Exchange service without an on-premises infrastructure.

## Set up the Service-to-Service Connector
> [!IMPORTANT]
> Before you being installing and configuring the service-to-service connector, ensure that you meet the [Exchange connector installation requirements](./intune-exchange-connector-requirements.md).

1.  Open the [Microsoft Intune administration console](http://manage.microsoft.com) with a user with Exchange admin rights. Microsoft Intune uses the email address of the currently logged in user to set up the connection.

2.  In the workspace shortcuts pane, choose **ADMIN**, then go **Mobile Device Management** > **Microsoft Exchange** > **Set Up Exchange Connection**.

4.  On the **Set Up Exchange Connection** page, choose **Set Up Service to Service Connector**.

![IntuneSA5cServiceToServiceConnector](./media/IntuneSA5cServiceToServiceConnector.PNG)

The Service-to-Service Connector will automatically configure and synchronize with your Hosted Exchange environment.

## Validate your Exchange connection

After you have successfully configured the Exchange Connector, in the Intune admin console choose the **ADMIN** workspace and go **Mobile Device Management** > **Microsoft Exchange** and validate that the details you provided appear under **Exchange Connection Information**.

You can also check the time and date of the last successful synchronization attempt.
