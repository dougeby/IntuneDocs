---
title: Set up a telecom expense management service | Intune Azure preview | Microsoft Docs
description: "Intune Azure preview: Configure the Saaswedo telecom expense management service to integrate with Intune."
keywords: Saaswedo
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 01/24/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: b7bf5802-4b65-4aeb-ac99-8e639dd89c2a


# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: sumitp
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:
---

# Set up a telecom expense management service in Intune Azure preview
[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune has integrated with the third-party software developer Saaswedo’s Datalert telecom expense management solution. Datalert is real-time telecom expense management software that lets you manage telecom data usage and avoid costly and unexpected data and roaming overages for your Intune-managed devices. Intune's integration with Datalert enables you to centrally set, monitor and enforce roaming and domestic data usage limits by using automated alerts when the limits exceed defined thresholds. You can configure the service to apply different actions to individuals or groups of end users, including disabling roaming, when users exceed the threshold. Reports that provide data usage and monitoring information are available from the Datalert management console.

Before you can use the Datalert service with Intune, you need to configure settings in the Datalert console and in Intune. The connection must be turned on for the Datalert service and for Intune. If the Datalert side of the connection is enabled, but not the Intune side, Intune receives the communication, but ignores it.

>[!NOTE]
>To enable this feature in your trial tenant, please [contact Microsoft support](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune) for activation and Datalert support for the required software licenses.

## Supported platforms

- Samsung Knox
- iOS 8.0 and later

## Prerequisites

- A subscription to Microsoft Intune
- A subscription to the Datalert telecom expense management service

## List of telecom expense management providers

Intune currently integrates with the following telecom expense management providers:

[Saaswedo Datalert telecom expense management service](http://www.datalert.biz/)

## Configure Intune to work with the Datalert service

 

1. Sign into the Azure portal.
2. Choose **More Services** > **Other** > **Intune**.
3. On the **Intune** blade, choose **Configure devices**.
2. On the **Device Configuration** blade, choose **Setup** > **Telecom Expense Management**.
2. Under **Telecom Expense Management**, select **Connection status**.

3. Select **List of TEM service providers**, and then select your provider from the list shown. A page that is specific to your provider opens. For Saaswedo, the Datalert page opens. You'll need to work with Saaswedo Datalert to purchase a subscription.

4. In the **Datalert** management console:

    a. Go to the **Settings** tab, and then go to the **MDM configuration** section.

    b. Select **Unlock** to enable you to enter the settings on the page.

	c. For **Server MDM**, choose **Microsoft Intune**.

    d. For **Tenant ID**, enter your Intune tenant ID, and select the **Connection** button. Selecting **Connection** makes the Datalert service check in with Intune to ensure that there are no pre-existing Datalert connections with Intune. After a few seconds, a Microsoft log-in page appears, followed by the Datalert Azure authentication.

    e. On the Microsoft authentication page, select **Accept**. You are redirected to a Datalert “thank you” page, which closes after a few seconds. Datalert validates the connection, and displays green check marks beside a list of items that it validated. If the validation fails, you see a message in red. If this happens, contact Datalert Support for help.

5. Wait a few minutes, and then go to the Azure portal and check that the Connection status appears as **Active**. 

    >[!NOTE]
    >To enable this feature in your trial tenant, please [contact Microsoft support](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

6. Return to the Datalert management console, and configure your data lines:

    a. Go to the **Settings** tab.

    b. Go to the **Setup** wizard and follow the steps in the wizard.



The Datalert service is now active, and it starts monitoring data usage and disabling cellular and roaming data on devices that exceed the configured usage limits.

## Turning off the Datalert service

If you disable the Datalert service in the Azure portal:

- All of the actions that have been applied to devices, due to past violations of the usage limits, are undone.
- Users are no longer blocked from data access and roaming.
- Intune still receives the signals coming from the service, but ignores them.

**To turn off the service**

1. On the **Telecom Expense Management** blade in the Azure portal, select **Disable**.

2. Select **Save**.

## Viewing data usage and roaming reports

At this time, data usage reporting is available only in Saaswedo’s Datalert management console.
