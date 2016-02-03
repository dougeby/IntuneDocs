---
title: Troubleshoot Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: c86a4e4a-6b9f-4835-a3d3-61a3f5f4c1ec
author: Lindavr
---
# Troubleshoot Microsoft Intune
[![](../Image/Nav_Icons/WIT_Tile_W_Overview.png)](https://technet.microsoft.com/library/dn646960.aspx/?WT.mc_id=IntuneOverview20150801)[![](../Image/Nav_Icons/WIT_Tile_W_GetStarted.png)](https://technet.microsoft.com/library/dn646953.aspx/?WT.mc_id=IntuneGS20150801)[![](../Image/Nav_Icons/WIT_Tile_W_EnrollDevices.png)](https://technet.microsoft.com/library/dn646962.aspx/?WT.mc_id=IntuneEnroll20150801)[![](../Image/Nav_Icons/WIT_Tile_W_ManageDevices.png)](https://technet.microsoft.com/library/mt313202.aspx/?WT.mc_id=IntuneConfig20150801)[![](../Image/Nav_Icons/WIT_Tile_W_ManageApps.png)](https://technet.microsoft.com/library/dn646965.aspx/?WT.mc_id=IntuneDeploy20150801)[![](../Image/Nav_Icons/WIT_Tile_W_ProtectResources.png)](https://technet.microsoft.com/library/mt313203.aspx/?WT.mc_id=IntuneProtect20150801)[![](../Image/Nav_Icons/WIT_Tile_W_RetireData.png)](https://technet.microsoft.com/library/mt313204.aspx/?WT.mc_id=IntuneRetire20150801)[![](../Image/Nav_Icons/WIT_Tile_W_TechnicalReference.png)](https://technet.microsoft.com/library/mt282239.aspx/?WT.mc_id=IntuneTR20150801)![](../Image/Nav_Icons/WIT_Tile_W_TroubleshootingHighlight.png)
![](../Image/Nav_Icons/WIT_Banner_Troubleshooting.png)

You may find  after you deploy [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)], that you're encountering problems with your configuration or with clients. It's possible that your end users are experiencing difficulties with their devices. The resources below may help you find out what could be causing the problem so that you can resolve it.

> [!NOTE]
> To create a support request, or to view an existing request,  click [here](https://portal.office.com/admin/default.aspx) to visit the Office 365 admin center. For more information about support options, see [How to get support for Microsoft Intune](../Topic/How_to_get_support_for_Microsoft_Intune.md).

## Troubleshooting resources
The following troubleshooting information is available in this section:

-   [How to get support for Microsoft Intune](../Topic/How_to_get_support_for_Microsoft_Intune.md)

    If your troubleshooting efforts don't result in a solution to the issue you're experiencing, Microsoft provides support options. You can learn more about those options in this topic.

-   [Troubleshoot Endpoint Protection in Microsoft Intune](../Topic/Troubleshoot_Endpoint_Protection_in_Microsoft_Intune.md)

    [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] provides endpoint protection to help you secure your managed computers. If you encounter issues with this feature,  this topic provides possible causes and solutions for errors and warnings you may see.

-   [Troubleshoot company resource access problems with Microsoft Intune](../Topic/Troubleshoot_company_resource_access_problems_with_Microsoft_Intune.md)

    When you've enabled access to company resources from mobile devices, you may receive one of the error messages described  in this topic.

-   [Troubleshoot app deployment problems in Microsoft Intune](../Topic/Troubleshoot_app_deployment_problems_in_Microsoft_Intune.md)

    This topic  describes common app deployment issues and how to resolve them.

-   [Troubleshoot device enrollment in Intune](../Topic/Troubleshoot_device_enrollment_in_Intune.md)

    If your users are having difficulty enrolling their devices, check the information in  this topic for common problems and resolutions.

-   [Troubleshoot policies in Microsoft Intune](../Topic/Troubleshoot_policies_in_Microsoft_Intune.md)

    You may find that your policies are not resulting in the behavior you planned, or are triggering error messages. This topic provides tips for these kinds of issues.

-   [Troubleshoot client setup in Microsoft Intune](../Topic/Troubleshoot_client_setup_in_Microsoft_Intune.md)

    You can learn how to use alerts and error codes to troubleshoot client installation in this topic .

-   [Troubleshoot software updates in Microsoft Intune](../Topic/Troubleshoot_software_updates_in_Microsoft_Intune.md)

    If you receive an error related to software updates, use the information in this topic to better understand the errors.

## Community resources
You can find other helpful information in these community resources:

-   The [Microsoft Intune Survival Guide](http://social.technet.microsoft.com/wiki/contents/articles/23431.microsoft-intune-survival-guide.aspx) contains links to many resources that can help you configure, maintain, and troubleshoot [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].

-   [The Intune blog](http://blogs.technet.com/b/windowsintune/)

-   [Follow Intune on Twitter](https://twitter.com/MSIntune)

-   [The Intune forums](https://social.technet.microsoft.com/Forums/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc)

## General troubleshooting guidelines
Here are some general troubleshooting guidelines that can help you resolve issues in [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].

Start by **defining the problem**:

-   What is the behavior?

-   Who experiences this behavior, and on what platforms and devices?

-   Did the device work properly previously?

-   What changes did you make to the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] or device configuration?

-   Consider whether other changes were made to the environment in which you operate, other than configuration changes.

-   How frequently does this problem occur, and is it sporadic or consistent?

-   Could the user be experiencing an authentication issue? If this is a possiblity, check if the user can log in to other services that use Azure Active Directory. Also, see if the user can log in from a different device.

After you've defined the problem, **collect available data**. This can include:

-   Device logs. Learn how to collect device logs in [Intune: sending troubleshooting info to IT](https://www.microsoft.com/en-us/download/details.aspx?id=46391).

-   Admin console data, for example, for policy implementation issues you should examine the intended policy and the status of that policy, as described in [Use groups to manage users and devices with Microsoft Intune](../Topic/Use_groups_to_manage_users_and_devices_with_Microsoft_Intune.md).

After you've defined the problem and collected data you can **research the solution**:

-   Search the Web for a solution. For example, if you receive the error 0x80073CF0, you can search for **technet intune 0x80073cf0** on the Web, and find the article [Troubleshoot app deployment problems in Microsoft Intune](../Topic/Troubleshoot_app_deployment_problems_in_Microsoft_Intune.md), which offers suggestions for addressing this issue.

-   You can search for an answer in the [Intune TechNet forum](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod).  If the issue has not been previously addressed you should post the question to see what suggestions the community might have.

-   You can open a support request. Intune Support will be better able to help you resolve an issue when you've defined the problem and have collected the available data.

    To create a support request click [here](https://portal.office.com/admin/default.aspx) to visit the Office 365 admin center. For more information about support options, see [How to get support for Microsoft Intune](../Topic/How_to_get_support_for_Microsoft_Intune.md).

## See Also
[Documentation for Microsoft Intune](../Topic/Documentation_for_Microsoft_Intune.md)
[Frequently asked questions for Microsoft Intune](../Topic/Frequently_asked_questions_for_Microsoft_Intune.md)

