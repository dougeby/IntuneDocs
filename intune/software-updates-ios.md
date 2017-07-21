---
# required metadata

title: Configure software updates for iOS devices
description: Configure
keywords:
author: dougeby
manager: dougeby
ms.date: 07/31/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e6334421-85e1-4457-9c44-e5db8d4ee00e

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: [ALIAS]
#ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Configure software updates for supervised iOS devices
Update policies for iOS let you force supervised iOS devices to automatically install the latest available software update. You have the option to configure the days and times when you do not want devices to install the update.

## Configure the iOS update policy
1. Go to the Intune blade in the Azure portal.
2. On the **Intune** blade, choose **Software updates** > **iOS Update Policies**.
4. On the policies blade, choose **Create**, and then enter a name and description for the policy.
5. Select **Settings** > **Configure**, and enter the details for when iOS devices will not be forced to install the latest update.
6. Choose **OK** to save this configuration. You are now back in the **Create update policy** blade. Choose **Create** to create the policy and save your settings.

The profile is created and appears on the iOS update policies list blade.

## Assign an iOS update policy to users
To assign an iOS update policy to users, choose a policy that you have configured. Existing policies are found in the **Software updates** > **iOS Update Policies** blade.
1. Choose the policy you want to assign to users and choose **Assignments**. This opens the blade where you can select Azure Active Directory security groups and assign them to the policy.
2. Choose **Select groups** to open the blade that displays the Azure AD security groups. Choose **Select** to deploy the policy to users.

You have applied the policy to users. The devices used by the users who are targeted by the policy will be evaluated for update compliance.

## Change the restricted days for the policy
1. On the **Software updates** blade, choose **iOS Update Policies**.
2. Select the iOS update policy that you want to update.
3. Select **Properties** and update the restricted days information.
