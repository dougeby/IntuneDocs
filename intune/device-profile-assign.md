---
# required metadata

title: Assign device profiles in Microsoft Intune - Azure | Microsoft Docs
description: Use the Azure portal to assign device profiles and policies to users and devices. Learn how to exclude groups from a profile assignment in Microsoft InTune.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/01/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f6f5414d-0e41-42fc-b6cf-e7ad76e1e06d

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Assign user and device profiles in Microsoft Intune

After you create a profile, you can assign the profile to Azure Active Directory (Azure AD) groups.

## Assign a device profile

1. In the [Azure portal](https://portal.azure.com), select **All Services**, and search for **Microsoft Intune**.
2. In **Microsoft Intune**, select **Device configuration**, and select **Profiles**.
3. In the list of profiles, select the profile you want to assign, and then select **Assignments**.
4. Choose to **Include** groups or **Exclude** groups, and then select groups.  

    ![Screenshot of options to include or exclude groups from a profile assignment](./media/group-include-exclude.png)

5. When you select your groups, you're choosing an Azure AD group. To select multiple groups, hold down the **Ctrl** key.
6. When you are done, select **Save**.

## Exclude groups from a profile assignment

Intune device configuration profiles let you exclude groups from policy assignment. For example, you can assign a device profile to the **All corporate users** group, but exclude any members of the **Senior Management Staff** group.

When you exclude groups from an assignment, exclude only users, or only exclude device groups (not a mixture of groups), Intune doesn't consider any user-to-device relationship. Including user groups while excluding device groups might not create the results you expect. When mixed groups are used, or if there are other conflicts, inclusion takes precedence over exclusion.

For example, you want to assign a device profile to all devices in your organization, except kiosk devices. You include the **All Users** group, but exclude the **All Devices** group. In this case, all your users and their devices get the policy, even if the user’s device is part of the **All Devices** group.

Exclusion only looks at the direct members of the groups, and doesn't include devices that are associated with a user. However, devices that don't have a user don't get the policy. This occurs because those devices have no relationship to the **All Users** group.

If you include **All Devices**, and exclude **All Users**, then all the devices receive the policy. In this scenario, the intent is to exclude devices that have an associated user from this policy. However, it doesn't exclude the devices because the exclusion only compares direct group members.

>[!TIP]
>Exclusions aren't available for compliance policies or app assignment. To exclude members from an assignment, you can use the **Available** and **Not applicable** assignments. For example, you assign an app to **All corporate users** with the **Available** intent, and assign the app to **Senior Management Staff** with the **Not applicable** intent. The app is assigned to all users *except* users in the **Senior Management Staff** group. If you assign the app to **All corporate users** with the **Required** intent, the users in the **Senior Management Staff** group are also included.

## Next steps
See [How to monitor device profiles](device-profile-monitor.md) for guidance on monitoring device profile assignments.
