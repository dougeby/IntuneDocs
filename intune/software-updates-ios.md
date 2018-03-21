---
# required metadata

title: Configure iOS software update policies in Microsoft Intune
titlesuffix:
description: Configure update policies for iOS to force supervised iOS devices to automatically install the latest available software update.
keywords:
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 03/19/2018
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

Software update policies let you force supervised iOS devices running iOS 10.3 and later to automatically install the latest available OS update. This feature is only available for supervised devices. You have the option to configure the days and times when you do not want devices to install the update. 

When the device checks in, about every 8 hours, if there is an update available and it is not during a restricted time, the device will attempt to download and install the latest OS update. There is no user interaction needed to update the device. The policy would not prevent a user from updating the OS.

## Configure the iOS update policy
1. Sign into the [Azure portal](https://portal.azure.com).
2. Choose **All services** > **Intune**. Intune is located in the **Monitoring + Management** section.
3. On the **Intune** pane, choose **Software updates** > **iOS Update Policies**.
4. On the policies pane, choose **Create**, and then enter a name and description for the policy.
5. Select **Settings** > **Configure**, and enter the details for when iOS devices are not be forced to install the latest update. You can configure the days of the week, time zone, start time, and end time.
6. Choose **OK** to save this configuration. You are now back in the **Create update policy** pane. Choose **Create** to create the policy and save your settings.

The profile is created and appears on the iOS update policies list pane. Apple MDM does not allow for the ability to enforce that the device install the update by a certain time or date. 

## Change the restricted times for the policy

1.	On the **Software updates** blade, choose **iOS Update Policies**.
2.	Select the iOS update policy that you want to update.
3.	Select **Properties** and update the restricted times information.
4.	Choose the days of the week
5.	Time zone that this policy will be applied in
6.	Start and end time for the blacklisted hours

## Assign an iOS update policy to users

To assign an iOS update policy to users, choose a policy that you have configured. Existing policies are found in the **Software updates** > **iOS Update Policies** pane.

1. Choose the policy you want to assign to users and choose **Assignments**. The pane where you can select Azure Active Directory security groups and assign them to the policy is opened.
2. Choose **Selected groups** to open the pane that displays the Azure AD security groups. Determine who has access to the policy by assigning the groups to include, as well as exclude.
3. Choose **Save** to deploy the policy to users.

You have applied the policy to your users or devices. The devices used by the users who are targeted by the policy are evaluated for update compliance. This policy also supports userless devices.

## Monitor iOS device installation failures
<!-- 1352223 -->
The **Installation failures for iOS devices** report is available from the **Software updates** pane. In the report, you can view a list of supervised iOS devices that were targeted by an iOS update policy, attempted an update, and could not be updated. For each device, you can view a status for why the device has not been automatically updated. Healthy, up-to-date devices will not show up in the list. We define up-to-date as the latest update that the device itself can support.
