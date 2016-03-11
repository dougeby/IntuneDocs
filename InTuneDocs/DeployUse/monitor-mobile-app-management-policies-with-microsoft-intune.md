---
title: Monitor mobile app management policies with Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: d3aa6c74-6b5d-4b50-aa66-a040ec44393e
author: karthikaraman
---
# Monitor mobile app management policies with Microsoft Intune
Use the information in this topic to monitor your mobile application management policies in the Azure preview portal.
If you have not used the Azure portal before, read [Get started with MAM policies in the Azure portal]( get-started-with-mobile-app-management-policies-in-the-azure-portal.md) topic.

## Monitor compliance
The **User status** tile in the **Intune mobile application management** blade displays the compliance status of your app policies as described below:

![](../media/AppManagement/AzurePortal_MAM_MonitorUsers.png)

-   **Users**- The total number of users in your company who are using work apps on their devices.

-   **POLICY**-This is the number of users who have used at least one of the apps associated with the policy.

-   **NO POLICY**- The number of users actively using work apps but not protected by the mobile application management policy.

    The **Flagged users** tile gives you the aggregated information on how many users are experiencing issues. Currently only users with jailbroken devices are marked as flagged.

    ![](../media/AppManagement/AzurePortal_MAM_FlaggedUserDetails.png)

## Monitor wipe requests
The **Wipe requests** tile shows you the summary report of the status of the wipe requests you made. Clicking on this tile will open a new blade that has more detailed information. For a detailed description of the wipe request information that is displayed in this blade, read the [Wipe managed company app data with Microsoft Intune](wipe-managed-company-app-data-with-microsoft-intune.md) topic.

  ![](../media/AppManagement/AzurePortal_MAM_WipeRequestsSummary.png)

### See Also
[Create and deploy mobile app management policies with Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)
[Configure data loss prevention app policies with Microsoft Intune](configure-data-loss-prevention-app-policies-with-microsoft-intune.md)
