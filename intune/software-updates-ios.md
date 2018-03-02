---
# required metadata

title: Configure iOS update policies
titlesuffix: "Azure portal"
description: Configure update policies for iOS to force supervised iOS devices to automatically install the latest available software update.
keywords:
author: dougeby
manager: dougeby
ms.date: 02/28/2018
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

# Configure iOS update policies
Update policies for iOS let you force supervised iOS devices to automatically install the latest available software update. You have the option to configure the days and times when you do not want devices to install the update.

## Configure the iOS update policy
1. Sign into the [Azure portal](https://portal.azure.com).
2. Choose **All services** > **Intune**. Intune is located in the **Monitoring + Management** section.
2. On the **Intune** pane, choose **Software updates** > **iOS Update Policies**.
4. On the policies pane, choose **Create**, and then enter a name and description for the policy.
5. Select **Settings** > **Configure**, and enter the details for when iOS devices are not be forced to install the latest update.
6. Choose **OK** to save this configuration. You are now back in the **Create update policy** pane. Choose **Create** to create the policy and save your settings.

The profile is created and appears on the iOS update policies list pane.

## Assign an iOS update policy to users
To assign an iOS update policy to users, choose a policy that you have configured. Existing policies are found in the **Software updates** > **iOS Update Policies** pane.
1. Choose the policy you want to assign to users and choose **Assignments**. The pane where you can select Azure Active Directory security groups and assign them to the policy is opened.
2. Choose **Selected groups** to open the pane that displays the Azure AD security groups. 
3. Choose **Save** to deploy the policy to users.

You have applied the policy to users. The devices used by the users who are targeted by the policy are evaluated for update compliance.

## Change the restricted days for the policy
1. On the **Software updates** pane, choose **iOS Update Policies**.
2. Select the iOS update policy that you want to update.
3. Select **Properties** > **Settings** to update the restricted days information.

## Monitor iOS devices with older iOS versions 
<!-- 1352223 -->
The **Out-of-date iOS Devices** report is available from the **Software updates** > **iOS Update Policies** pane. In the report, you can view a list of supervised iOS devices that were targeted by an iOS update policy and could not be updated. For each device, you can view a status for why the device has not been automatically updated.