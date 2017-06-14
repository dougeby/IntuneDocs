---
# required metadata

title: Deploy Skycure apps with Intune
titleSuffix: "Intune Azure preview"
description: Deploy Skycure apps, Microsoft Authenticator app and iOS configuration policy with Intune.
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/09/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 008c1df5-0b91-4a8f-ac2e-e269465500ed

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Deploy Skycure apps, Microsoft Authenticator app and iOS app configuration policy

## Before you begin

-   The below steps need to be completed in the [Intune classic console](https://manage.microsoft.com/).

-   Use the same Azure AD account previously configured in the Skycure Management console, which should be the same account used to log in into the Intune classic console.

-   Make sure you’re familiar with the process of:

    -   [Deploying an app with Intune](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune).

    -   [Deploying an iOS app configuration policy](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

## To deploy Skycure apps, Microsoft Authenticator app and the iOS app configuration policy

1.  In the Intune classic console, choose **Apps** &gt; **Apps** to view the list of apps that you can manage.

2.  Select the following apps:

    a.  Microsoft Authenticator

    b.  Skycure app for Android

    c.  Skycure app for iOS

       ![Intune classic console all apps to deploy](./media/skycure-deploy-app-1.png)

3.  Choose **Manage Deployments,** select the Azure AD security group that has the Skycure users, then click **Next**.

4.  On the **Deployment Action** page, select the option **Required Install** from the **Approval** drop-down list, then click **Next**.

    ![Intune classic console Deployment Action](./media/skycure-deploy-app-2.png)

5.  On the **VPN profile** page, select the option **None** from the **VPN Policy** drop-down list, then click **Next**.

6.  On the **Mobile App Configuration** page, select the iOS App Configuration Policy previously created from the **App Configuration Policy** drop-down list, then click **Finish**.

    ![Intune classic console Mobile app configuration](./media/skycure-deploy-app-3.png)

## Next steps

[Set up the Skycure integration with Intune](skycure-mtd-connector-integration.md)
