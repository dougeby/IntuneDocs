---
# required metadata

title: Create groups to organize users and devices 
description: Create users and groups for your Intune subscription
keywords:
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 5fdf98c8-fe67-4d7a-9837-ed1234348014
ROBOTS: NOINDEX,NOFOLLOW

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---


# Create groups to organize users and devices

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

This topic tells administrators how they can create groups of users in Intune.

Groups in Intune give you great flexibility for managing your devices and users. You can set up groups to suit your organizational needs (for example, by geographic location, department, or hardware characteristics) and use them to perform a wide variety of administrative tasks, from deploying policies for a set of users to deploying applications to a set of devices.

## Group management moving to Azure AD

**Starting in November 2016**, new accounts will manage user and device groups in the Azure Active Directory (AD) portal. In December 2016, the Intune product team will begin to migrate existing customers to the new Azure AD-based group management experience. All user and device groups will be migrated to Azure AD security groups. We won’t start migrations until we can minimize any effect on your day-to-day work, and when we expect there will be no effect on your users. We also will give you notice before we migrate your account.


>[!IMPORTANT]
>
>If you open the Groups workspace in the Intune portal and see **Intune user groups are now managed as groups in Azure Active Directory** with a link to the Azure Active Directory portal, then you are already using the *new* Azure AD security groups approach to group management in Intune. To learn how to create groups, see [Managing groups in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).
>
>If you do not see the link to the Azure AD portal, you are still using the Intune portal for groups management.

## Group management in the Intune portal

Device and user groups are both created in the GROUPS workspace of the Intune administration console.

![Admin console groups workspace](./media/groups.png)


> [!TIP]
> To learn more about using groups, see [Use groups to manage users and devices with Microsoft Intune](/intune-classic/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune).


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

>[!div class="step-by-step"]
/intune/licenses-assign
>[&larr; **Manage Intune licenses**](/intune/licenses-assign)       [**Create policies and apps** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-6.md)  
