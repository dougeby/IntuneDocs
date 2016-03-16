---
title: Create groups to organize users and devices
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: get-started-article
ms.assetid:
author: Staciebarker
---

# 5. Create groups to organize users and devices
Groups in [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] give you great flexibility for managing your devices and users. You can set up groups to suit your organizational needs (for example, by geographic location, department, or hardware characteristics) and use them to perform a wide variety of administrative tasks, from deploying policies for a set of users to deploying applications to a set of devices.

## Create a device group
Use device groups to deploy apps and updates, and configure other features. For example, set up a "My Devices" group using the following steps:

1.  In the [Intune administration console](https://manage.microsoft.com/), choose **Groups** > **Overview** > **Create Group**.

2.  For the **Group name**, type “My Devices” and, from the parent group list, select **All Devices**, and then choose **Next**.

3.  On the **Define Membership Criteria** page, select **All devices** to indicate that the group includes both mobile devices and computers.

4.  On the **Define Direct Membership** page, choose **Next**. If you previously created a group that did not include all devices, and you wanted to add specific devices to your new group, you can do that here.

5.  On the **Summary** page, review the actions that will be taken, and then choose **Finish**.

You can find the newly created group in the **Groups** list, in the **Groups** workspace, under **All Devices**. From here, you can also edit or delete the group.

## Create a user group
Use user groups to deploy software and device policies. For example, set up an "Intune Users" group using the following steps:

1.  In the [Intune administration console](https://manage.microsoft.com/), choose **Groups** > **Overview** > **Create Group**.

2.  For the **Group name**, type “Intune Users” and, from the parent group list, select **All Users**, and then choose **Next**.

3.  On the **Define Membership Criteria** page, set **Start group membership with** to **All users in the Parent group**.

4.  Beside **Exclude members from these security groups**, choose **Browse** and then select **Company Administrator**. This exclusion lets you manage the Intune Users group without affecting the Company Administrator account (also known as the tenant administrator).

5.  On the **Define Direct Membership** page, choose **Next**. You don’t need to do anything here because you want the Intune Users group to include all users, except for the Company Administrator.

6.  On the **Summary** page, review the actions that will be taken, and then choose **Finish**.

You can find the newly created group in the **Groups** list, in the **Groups** workspace, under **All Users**. From here, you can also edit or delete the group.

To learn more about using groups, see [Use groups to manage users and devices with Microsoft Intune](/Intune/use-groups-to-manage-users-and-devices-with-microsoft-intune.html).

## Next steps
Congratulations! You have just completed step 5 of the *Get started with a paid subscription to Microsoft Intune* guide.
>[!div class="step-by-step"]
>[Previous](.\get-started-with-a-paid-subscription-to-microsoft-intune-step-4.md)  **Manage Intune licenses** **Create policies and publish an app** [Next](.\get-started-with-a-paid-subscription-to-microsoft-intune-step-6.md)  
