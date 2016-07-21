---
# required metadata

title: Application rollout | Microsoft Intune
description: Recommendations for a phased rollout of apps in Microsoft Intune.
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 0fc32ed3-bcf4-472a-80e7-eb20986f78fa

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: tscott
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Application rollout
This topic provide specific recommendations for a phased rollout of apps in Microsoft Intune. For general information about rollout phases, see [Rollout phases for Microsoft Intune deployment](rollout-phases-for-microsoft-intune-deployment.md).

### Phases of app rollout
The phases of app rollout are:

-   Project scope

-   Proof of concept

-   Pilot

-   Enterprise rollout

-   Operations and maintenance

## Project scope
Consider the following:

-   The user task the app is meant to enable.

-   The suitability of  the app for your users and their devices (all operating systems that are likely to be used).

-   Check that the installer for the app you chose is supported by Intune app distribution, as described in  [Add apps with Microsoft Intune](/intune/deploy-use/add-apps).

-   Ensure that app distribution prerequisites are installed. <!---, as described in [Plan for app deployment in Microsoft Intune](plan-for-app-deployment-in-microsoft-intune.md).--->

-   Determine that the app type is supported by Intune.

-   Check that  you have sufficient cloud storage space available to upload the app. Instructions for purchasing additional storage are provided in [Add apps with Microsoft Intune](/intune/deploy-use/add-apps).

> [!NOTE]           
> You can download this [planning template for mobile apps](https://gallery.technet.microsoft.com/Mobile-app-planning-18689d59) to assist in your rollout process.

## Proof of concept
In the Proof of concept phase test your app deployment in a laboratory environment on devices and users that you've configured strictly for testing purposes.

-   Have your help desk participate in this phase to learn what issues can arise during pilot and production deployment. Troubleshooting information is available in [Troubleshoot app deployment problems in Microsoft Intune](/intune/troubleshoot/troubleshoot-app-deployment-problems-in-microsoft-intune).

-   At this point in the process you should develop communication plans for pilot and production users. At a minimum the plan should include what app is being deployed, how and when users will obtain it,  the business purpose of the deployment, and what to do if they encounter issues, both self-help information and how to contact the help desk.

## Pilot
During the pilot you will deploy the app to a small group of test users and devices. Consider the following:

-   Ensure that the test group is representative of the users and devices that will be using the app after production rollout.

-   Educate the help desk regarding the app deployment, and ensure that they are prepared to help users in the test group.

-   Choose test users who will subject the app to typical usage and will reliably report issues to the pilot administrators.

-   Activate your pilot user communication plan.

## Enterprise rollout

-   Use the pilot results to adjust your enterprise rollout.

-   Notify your help desk of the app rollout schedule. Have mechanisms in place to respond to help requests, and to adjust the rollout as necessary.

-   Be prepared to troubleshoot the deployment if issues arise.

-   Activate your production user communication plan.

-   Use a phased approach for deploying the app, adding groups incrementally to ensure that the rollout is proceeding smoothly.

## Operations and maintenance
**Operations:** Monitor your Intune console for alerts and user or device issues, and to ensure that application distribution is functioning according to your design.

**Help desk:** Ensure that your help desk is aware of any changes to app availability that may result in support requests.

### See also
[Deploy apps](/intune/deploy-use/deploy-apps)

[Troubleshoot app deployment problems in Microsoft Intune](/intune/troubleshoot/troubleshoot-app-deployment-problems-in-microsoft-intune)
