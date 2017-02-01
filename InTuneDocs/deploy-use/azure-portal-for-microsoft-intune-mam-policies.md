---
# required metadata

title: Azure portal for MAM policies | Microsoft Docs
description: Create mobile app management policies by using the Azure portal. The policies you create here can be applied to devices with or without enrollment in Intune.
keywords:
author: andredm7ms.author: andredmmanager: angrobe
ms.date: 10/22/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 7d6dae94-a833-40b7-9016-14ea234bb33c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: joglocke
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Azure portal for Microsoft Intune MAM policies

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

The Azure portal is used to create and manage mobile app management (MAM) policies for:

- Apps running on devices that are **enrolled and managed in Intune**.

- Apps running on devices that are **not enrolled** in any MDM solution.
- Apps running on devices that are **enrolled in a third-party MDM solution**.

>[!IMPORTANT]
> The Azure portal is the new admin console for creating MAM policies, but you can also create a MAM policy that supports apps for devices enrolled into Intune by using the [Intune admin console](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) for MDM scenarios.

> You might not see all the MAM policy settings available on the Intune admin console. Additionally, if you create MAM policies both on the Intune admin console and in the Azure portal, the policies created in the Azure portal will override the ones created on the Intune admin console. In this scenario, the Azure portal MAM policies will be applied to the apps and deployed to users.


## Sign in to the Azure portal and customize your start page

1.  Go the [Azure portal](https://portal.azure.com) and sign in with your [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] credentials.

    ![Screenshot of the Azure portal sign-in page](../media/AppManagement/AzurePortal_MAMSigninPage.png)

2.  After you've successfully signed in, you see the **Dashboard**. The **Dashboard** page can be customized.

    ![Screenshot of the Azure portal dashboard](../media/AppManagement/AzurePortal_MAMStartboard_NoMAM.png)

3.  On the **Browse** menu, find **Intune**.

	![Screenshot of the Browse menu with Intune highlighted](../media/AppManagement/MAM-Azure-Portal-1.png)

4.  Choose **Intune** > **Intune mobile application management** > **Settings**.

    ![Screenshot of the Intune mobile application management blade](../media/AppManagement/MAM-Azure-Portal-2.png)

5. (Optional): To pin a blade to the **Start** page, you can use the **pin** option on the blade. Click the pin icon on the **Intune mobile application management blade** to pin that blade to the **Start** page.

    ![Screenshot of the Intune mobile application management blade with the pin icon highlighted](../media/AppManagement/AzurePortal_MAM_PinBladeAction.png)

    ![Screenshot of the dashboard with the pinned Intune tile](../media/AppManagement/AzurePortal_MAM_Startboard_withMAM.png)

## Next steps
[Get ready to configure mobile app management policies](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)
