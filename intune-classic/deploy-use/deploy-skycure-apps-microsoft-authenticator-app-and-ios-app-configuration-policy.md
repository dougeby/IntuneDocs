---
# required metadata

title: Deploy Skycure apps, Microsoft Authenticator app and iOS configuration policy 
description: Deploy Skycure apps, Microsoft Authenticator app and iOS configuration policy into Intune classic portal.
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 45826fbc-6df5-41b2-8e80-d1353f904b43

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Deploy Skycure apps, Microsoft Authenticator app and iOS app configuration policy

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## Before you begin

-   The below steps need to be completed in the [Intune classic portal](https://manage.microsoft.com/).

-   Use the same Azure AD account previously configured in the Skycure Management console, which should be the same account used to log in into the Intune classic portal.

-   Make sure you’re familiar with the process of:

    -   [Deploying an app with Intune](/intune-classic/deploy-use/deploy-apps-in-microsoft-intune).

    -   [Deploying an iOS app configuration policy](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

## To deploy Skycure apps, Microsoft Authenticator app and the iOS app configuration policy

1.  In the Intune classic portal, choose **Apps** &gt; **Apps** to view the list of apps that you can manage.

2.  Select the following apps:

    a.  Microsoft Authenticator

    b.  Skycure app for Android

    c.  Skycure app for iOS

       ![Intune classic portal all apps to deploy](../media/mtp/skycure-deploy-app-1.png)

3.  Choose **Manage Deployments,** select the Azure AD security group that has the Skycure users, then click **Next**.

4.  On the **Deployment Action** page, select the option **Required Install** from the **Approval** drop-down list, then click **Next**.

    ![Intune classic portal Deployment Action](../media/mtp/skycure-deploy-app-2.png)

5.  On the **VPN profile** page, select the option **None** from the **VPN Policy** drop-down list, then click **Next**.

6.  On the **Mobile App Configuration** page, select the iOS App Configuration Policy previously created from the **App Configuration Policy** drop-down list, then click **Finish**.

    ![Intune classic portal Mobile app configuration](../media/mtp/skycure-deploy-app-3.png)

## Next steps

[Set up the Skycure integration with Intune](/intune-classic/deploy-use/setup-the-skycure-integration-with-Intune)
