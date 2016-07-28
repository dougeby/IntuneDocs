---
# required metadata

title: Policy rollout | Microsoft Intune
description: Recommendations for a phased rollout of policy in Microsoft Intune.
keywords:
author: Nbigman
manager: angrobe
ms.date: 07/21/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 390d5adf-86d2-4e23-ba93-1e61e6b1028b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: tscott
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Policy rollout
This topic provide specific recommendations for a phased rollout of policies in Microsoft Intune. This approach applies to the first policies you apply in a new Intune deployment, or policies you add to an existing deployment.

For general information about rollout phases, see [Rollout phases for Microsoft Intune deployment](rollout-phases-for-microsoft-intune-deployment.md).

### Phases of policy rollout
The phases of policy rollout are:

-   Project scope

-   Proof of concept

-   Pilot

-   Enterprise rollout

-   Operations and maintenance

## Project scope
Define the scope of your Intune policy deployment:

-   For a new implementation, this will require defining all of the desired device behaviors and security requirements that you want to create with your policy set.

-   Decide what users and devices you want to impact with these policies.

-   Design your user and device groups to enable you to apply the new policies appropriately.

-   Determine whether there are limitations or requirements associated with each operating system that will affect the intentions of your policy.

-   Consider policy design specifics, such as policy type and template to be used.

-   Whether you are launching your first set of policies or adding new policies to an existing policy set, consider how various policies interact, and what the likely device behavior will be. Issues with policy interactions and conflicts can be discovered in the Pilot phase, but catching policy conflicts in early planning will simplify execution of the Pilot.

## Proof of concept
In the Proof of concept phase, test your policy deployment in a laboratory environment on devices and users that you've configured strictly for testing purposes.

-   Have your help desk participate in this phase to learn what issues can arise during pilot and production deployment. Troubleshooting information is available in [Troubleshoot policies in Microsoft Intune](/intune/troubleshoot/troubleshoot-policies-in-microsoft-intune).

-   At this point in the process you should develop communication plans for pilot and production users. At a minimum the plan should include what device behaviors will change and when, the business purpose for the change, and what to do if users or IT staff encounter issues, both self-help information and how to contact the help desk.

## Pilot
During the pilot you will deploy the policy to a small group of test users and devices. There are specific considerations for piloting policy in Intune:

-   The test  group should be representative of the group to which the policy will be applied for production rollout.

-   Educate the help desk  regarding the changes in policy, and ensure they are prepared to help users in the test group.

-   Activate your pilot user communication plan.

-   The pilot can first be done in isolated mode, where the device is not subject to other policies that may cause conflict and unintended behavior.

-   The final test must consider the new policy and all the existing policies that will be applied to the same device.

## Enterprise rollout

-   Based on the results of the pilot, adjust your planned policy to correct for policy conflicts and unanticipated behavior.

-   Notify your help desk of the enterprise rollout schedule. Have mechanisms in place to respond to help requests and to adjust the rollout as necessary.

-   Be prepared to troubleshoot the policy if issues arise.

-   Activate your production user communication plan.

-   Apply the policies incrementally to additional groups, monitoring the policy state for affected devices and tracking help desk requests that may be related to the new policy.

## Operations and maintenance
**Operations:** Monitor your Intune console for alerts and user or device issues, and check that polices are performing according to your design.

**Help desk:** Ensure that your help desk is aware of any changes to policies that will affect the user experience, as these may result in support requests.


### See also
[Get ready to configure mobile app management policies with Microsoft Intune](/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune)

[Troubleshoot policies in Microsoft Intune](/intune/troubleshoot/troubleshoot-policies-in-microsoft-intune)
