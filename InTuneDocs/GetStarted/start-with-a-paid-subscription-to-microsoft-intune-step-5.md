---
# required metadata

title: Create groups to organize users and devices | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 5fdf98c8-fe67-4d7a-9837-ed1234348014

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Create groups to organize users and devices
Groups in [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] give you great flexibility for managing your devices and users. You can set up groups to suit your organizational needs (for example, by geographic location, department, or hardware characteristics) and use them to perform a wide variety of administrative tasks, from deploying policies for a set of users to deploying applications to a set of devices.

Device and user groups are both created in the GROUPS workspace of the Intune administration console.

![alt text](./media/groups.png "GROUPS workspace of the Intune administration console")

<!-- can't find this topic anywhere below:
> [!TIP]
> To learn more about using groups, see [use groups to manage users and devices with Microsoft Intune](/intune/use-groups-to-manage-users-and-devices-with-microsoft-intune).
-->

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



### Next steps
Congratulations! You have just completed step 5 of the *Start with a paid subscription to Microsoft Intune* guide.

>[!div class="step-by-step"]

>[&larr; **Manage Intune licenses**](.\start-with-a-paid-subscription-to-microsoft-intune-step-4.md)       [**Create policies and apps** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-6.md)  
