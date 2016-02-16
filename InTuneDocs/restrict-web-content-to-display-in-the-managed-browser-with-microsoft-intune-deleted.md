---
title: Restrict web content to display in the Managed Browser with Microsoft Intune - deleted
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 35aa5d98-72ff-40d9-8954-f38d42f34e5b
author: karthikaraman
---
# Restrict web content to display in the Managed Browser with Microsoft Intune - deleted
The managed browser is a web browsing application.  For devices that are not enrolled in Intune, you can restrict web content from policy-managed apps to only display in the Managed Browser app using the mobile app management policy.

If you are using Intune to manage your devices, see the [Manage Internet access using managed browser policies with Microsoft Intune](../Topic/Manage-Internet-access-using-managed-browser-policies-with-Microsoft-Intune.md) topic to learn how to deploy a Managed Browser app.

## Create a policy with Managed Browser policy setting

1.  In the Azure  portal, create an iOS or Android policy.  See the [Create and deploy mobile app management policies with Microsoft Intune](../Topic/Create-and-deploy-mobile-app-management-policies-with-Microsoft-Intune.md) for detailed instructions on how to create a policy.

2.  In the policy settings, set the **Restrict web content to display in a corporate managed browser** setting to **Yes**. When this setting is set to Yes, it opens any web links from other policy-managed apps to open only in the Managed Browser app.

3.  Deploy the policy to users. For devices that you are not managing, the end-user must install the Managed Browser app from the Apple store or Google Play to have the ability to open web links from policy-managed apps.

## See Also
[Create and deploy mobile app management policies with Microsoft Intune](../Topic/Create-and-deploy-mobile-app-management-policies-with-Microsoft-Intune.md)
[Configure data loss prevention app policies with Microsoft Intune](../Topic/Configure-data-loss-prevention-app-policies-with-Microsoft-Intune.md)

