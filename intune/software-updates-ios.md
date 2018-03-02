---
# required metadata

title: Configure iOS update policies in Microsoft Intune
titlesuffix:
description: Configure update policies for iOS to force supervised iOS devices to automatically install the latest available software update.
keywords:
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/02/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: [ALIAS]
#ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Configure iOS update policies in Microsoft Intune
Update policies for iOS let you force supervised iOS devices to automatically install the latest available software update. You have the option to configure the days and times when you do not want devices to install the update.

## Configure the iOS update policy
1. Go to the Intune page in the Azure portal.
2. On the **Intune** page, choose **Software updates** > **iOS Update Policies**.
4. On the policies page, choose **Create**, and then enter a name and description for the policy.
5. Select **Settings** > **Configure**, and enter the details for when iOS devices are not be forced to install the latest update.
6. Choose **OK** to save this configuration. You are now back in the **Create update policy** page. Choose **Create** to create the policy and save your settings.

The profile is created and appears on the iOS update policies list page.

## Assign an iOS update policy to users
To assign an iOS update policy to users, choose a policy that you have configured. Existing policies are found in the **Software updates** > **iOS Update Policies** page.
1. Choose the policy you want to assign to users and choose **Assignments**. The page where you can select Azure Active Directory security groups and assign them to the policy is opened.
2. Choose **Select groups** to open the page that displays the Azure AD security groups. Choose **Select** to deploy the policy to users.

You have applied the policy to users. The devices used by the users who are targeted by the policy are evaluated for update compliance.

## Change the restricted days for the policy
1. On the **Software updates** page, choose **iOS Update Policies**.
2. Select the iOS update policy that you want to update.
3. Select **Properties** and update the restricted days information.

## Monitor iOS devices with older iOS versions 
<!-- 1352223 -->
The **Out-of-date iOS Devices** report is available from the **Software updates** > **iOS Update Policies** page. In the report, you can view a list of supervised iOS devices that were targeted by an iOS update policy and could not be updated. For each device, you can view a status for why the device has not been automatically updated.