---
title: Microsoft apps you can use with Microsoft Intune mobile application management policies
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 49023822-0aa7-4508-8119-3be8976d21d1
author: robstackmsft
---
# Microsoft apps you can use with Microsoft Intune mobile application management policies
Use this topic to find out which Microsoft apps you can use with [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] mobile application management (MAM) policies.

For information about how to use mobile application management policies, see [Configure and deploy mobile application management policies in the Microsoft Intune console](../Topic/Configure_and_deploy_mobile_application_management_policies_in_the_Microsoft_Intune_console.md).

> [!IMPORTANT]
> The [Microsoft Intune application partners](http://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx) page contains the latest information about apps from Microsoft and other companies that you can use with mobile application management policies and will, in future, replace this topic.

If you have devices that are not enrolled in Intune, see [Get started with mobile app management policies in the Azure portal](../Topic/Get_started_with_mobile_app_management_policies_in_the_Azure_portal.md).

## <a name="BKMK_Availapps"></a>List of Microsoft apps you can use with mobile application management (MAM) policies

### Apps for iOS devices

-   [Intune Managed Browser](https://itunes.apple.com/us/app/microsoft-intune-managed-browser/id943264951?mt=8) - A web browser that lets you manage the actions that users can perform, including the sites they can visit, and how links to content within the browser are opened.

    When you deploy the managed browser, you can also configure a managed browser policy which lets you restrict the websites that users can visit. For more information, see [Manage Internet access using managed browser policies with Microsoft Intune](../Topic/Manage_Internet_access_using_managed_browser_policies_with_Microsoft_Intune.md).

-   [Microsoft Word](https://itunes.apple.com/us/app/microsoft-word/id586447913?mt=8)<sup>*</sup>

-   [Microsoft Excel](https://itunes.apple.com/us/app/microsoft-excel/id586683407?mt=8)<sup>*</sup>

-   [Microsoft PowerPoint](https://itunes.apple.com/us/app/microsoft-powerpoint/id586449534?mt=8)<sup>*</sup>

-   [Microsoft OneDrive](https://itunes.apple.com/us/app/onedrive/id477537958?mt=8)<sup>*</sup>

-   [Microsoft OneNote](https://itunes.apple.com/us/app/microsoft-onenote-for-iphone/id410395246?mt=8)

-   [Work Folders](https://itunes.apple.com/us/app/work-folders/id950878067?mt=8) – Gives access to a location where you can store work files and access them from computers and devices, even if you are offline.

-   [Microsoft Outlook](https://itunes.apple.com/us/app/microsoft-outlook/id951937596?mt=8)<sup>*</sup>

-   [Microsoft Power BI](https://itunes.apple.com/us/app/microsoft-power-bi/id929738808?mt=8)

-   [Microsoft Remote Desktop](https://itunes.apple.com/app/microsoft-remote-desktop/id714464092?mt=8)

-   [Microsoft Rights Management (RMS) sharing app](https://itunes.apple.com/us/app/rms-sharing/id689516635?mt=8)

    For more information on RMS sharing app, [read the FAQ on RMS sharing app for mobile platforms](https://technet.microsoft.com/dn451248).

<sup>*</sup>Supports multi-identity. This means that Intune only applies management settings to corporate accounts or data in the app.

### Apps for Android devices

-   [Intune Managed Browser](https://play.google.com/store/apps/details?id=com.microsoft.intune.mam.managedbrowser&hl=en) - A web browser that lets you manage the actions that users can perform, including the sites they can visit, and how links to content within the browser are opened.

    When you deploy the managed browser, you can also configure a managed browser policy which lets you restrict the websites that users can visit. For more information, see [Manage Internet access using managed browser policies with Microsoft Intune](../Topic/Manage_Internet_access_using_managed_browser_policies_with_Microsoft_Intune.md).

-   [Intune PDF Viewer](https://play.google.com/store/apps/details?id=com.microsoft.intune.mam.pdfviewer)<sup>**</sup> – Lets users view PDF files from [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] managed apps.

-   [Intune AV Player](https://play.google.com/store/apps/details?id=com.microsoft.intune.mam.avplayer)<sup>**</sup> – Lets users access audio and video content from [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] managed apps.

-   [Intune Image Viewer](https://play.google.com/store/apps/details?id=com.microsoft.intune.mam.imageviewer)<sup>**</sup> – Lets users view images from [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] managed apps.

-   [Microsoft Office Mobile](https://play.google.com/store/apps/details?id=com.microsoft.office.officehub)

-   [Microsoft Word](https://play.google.com/store/apps/details?id=com.microsoft.office.word)

-   [Microsoft Excel](https://play.google.com/store/apps/details?id=com.microsoft.office.excel)

-   [Microsoft PowerPoint](https://play.google.com/store/apps/details?id=com.microsoft.office.powerpoint)

-   [Microsoft OneDrive](https://play.google.com/store/apps/details?id=com.microsoft.skydrive)<sup>*</sup>

-   [Microsoft Outlook](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)<sup>*</sup>

-   [Microsoft Power BI](https://play.google.com/store/apps/details?id=com.microsoft.powerbim)

-   [Microsoft Remote Desktop](https://play.google.com/store/apps/details?id=com.microsoft.rdc.android)

-   [Microsoft Rights Management (RMS) sharing app](https://play.google.com/store/apps/details?id=com.microsoft.ipviewer)

    For more information, [read the FAQ on RMS sharing app for mobile platforms](https://technet.microsoft.com/dn451248)

<sup>*</sup>Supports multi-identity. This means that Intune only applies management settings to corporate accounts or data in the app.

<sup>**</sup> These viewer apps are only supported for devices that are enrolled in Intune. For devices that are not enrolled in Intune, you can use the Microsoft Rights Management (RMS) sharing app instead. For more information see [Create and deploy mobile app management policies with Microsoft Intune](../Topic/Create_and_deploy_mobile_app_management_policies_with_Microsoft_Intune.md) and [Viewing media files with the Rights Management sharing app](../Topic/End-user_experience_for_apps_associated_with_Microsoft_Intune_mobile_app_management_policies.md#bkmk_RMS).

## See Also
[Configure and deploy mobile application management policies in the Microsoft Intune console](../Topic/Configure_and_deploy_mobile_application_management_policies_in_the_Microsoft_Intune_console.md)

