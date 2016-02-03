---
title: Rolling out apps with Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 0521099d-1c23-47bf-b937-751baca78862
author: Nbigman
---
# Rolling out apps with Microsoft Intune
This topic provide specific recommendations for a phased rollout of apps in [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)]. For general information about rollout phases, see [Rollout phases for Microsoft Intune deployment](../Topic/Rollout_phases_for_Microsoft_Intune_deployment.md).

## Phases of app rollout
The phases of app rollout are:

-   Project scope

-   Proof of concept

-   Pilot

-   Enterprise rollout

-   Operations and maintenance

### Project scope
Consider the following:

-   The user task the app meant to enable.

-   The suitability of  the app for your users and their devices (all operating systems that are likely to be used).

-   Check that the installer for the app you chose is supported by [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] app distribution, as described in  [Plan for app deployment in Microsoft Intune](../Topic/Plan_for_app_deployment_in_Microsoft_Intune.md).

-   Ensure that app distribution prerequisites are installed, as described in [Plan for app deployment in Microsoft Intune](../Topic/Plan_for_app_deployment_in_Microsoft_Intune.md).

-   Determine that the app type is supported by [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].

-   Check that  you have sufficient  cloud storage space available to upload the app. Instructions for purchasing additional storage are provided in [Plan for app deployment in Microsoft Intune](../Topic/Plan_for_app_deployment_in_Microsoft_Intune.md).

### Proof of concept
In the Proof of concept phase, test your app deployment in a laboratory environment on devices and users that you've configured strictly for testing purposes.

-   Have your help desk participate in this phase to learn what issues can arise during pilot and production deployment. Troubleshooting information is available in [Troubleshoot app deployment problems in Microsoft Intune](../Topic/Troubleshoot_app_deployment_problems_in_Microsoft_Intune.md).

-   At this point in the process you should develop communication plans for pilot and production users. At a minimum the plan should include what app is being deployed, how and when they will obtain it,  the business purpose of the deployment, and what to do if they encounter issues, both self-help information and how to contact the help desk.

### Pilot
During the pilot you will deploy the app to a small group of test users and devices. Consider the following:

-   Ensure that the test group is representative of the users and devices that will be using the app after production rollout.

-   Educate the help desk  regarding the app deployment, and ensure they are prepared to help users in the test group.

-   Choose test users who will subject the app to typical usage and will reliably report issues to the pilot administrators.

-   Activate your pilot user communication plan.

### Enterprise rollout

-   Use the pilot results to adjust your enterprise rollout.

-   Notify your help desk of the app rollout schedule. Have mechanisms in place to respond to help requests, and to adjust the rollout as necessary.

-   Be prepared to troubleshoot the deployment if issues arise.

-   Activate your production user communication plan.

-   Use a phased approach for deploying the app, adding groups incrementally to ensure that the rollout is proceeding smoothly.

### Operations and maintenance
**Operations:** Monitor your [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] console for alerts and user or device issues, and to ensure that application distribution is functioning according to your organizational plan.

**Help desk:** Ensure that your help desk is aware of any changes to app availability that may result in support requests.

## See Also
[Troubleshoot app deployment problems in Microsoft Intune](../Topic/Troubleshoot_app_deployment_problems_in_Microsoft_Intune.md)
[Plan for app deployment in Microsoft Intune](../Topic/Plan_for_app_deployment_in_Microsoft_Intune.md)

