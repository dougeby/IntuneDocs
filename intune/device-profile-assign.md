---
# required metadata

title: Assign device profiles in Microsoft InTune - Azure | Microsoft Docs
description: Use the Azure portal to assign device profiles and policies to users and devices, and how to exclude groups from a profile assignment in Microsoft InTune
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

## Assign a device profile

1. In the [Azure portal](https://portal.azure.com), select **All Services**, and search for **Microsoft Intune**.
2. In **Microsoft Intune**, select **Device configuration**, and select **Profiles**. 
3. In the list of profiles, select the profile you want to assign, and then select **Assignments**.
4. Choose to **Include** groups or **Exclude** groups, then **Select groups**:  

    ![Include or exclude groups from a profile assignment](./media/group-include-exclude.png)

5. When you select your groups, you're choosing an Azure Activity Directory group. Hold down the **CTRL** key to select multiple groups.
6. When done, **Save** your changes.

## Exclude groups from a profile assignment

InTune device configuration profiles let you exclude groups from policy assignment. For example, you can assign a device profile to the **All corporate users** group, but exclude any members of the **Senior Management Staff** group.

When you exclude groups from an assignment, exclude only users, or only exclude device groups (basically not a mixture of groups), InTune does not consider any user-to-device association. Including user groups while excluding device groups is unlikely to create the results you may expect. When mixed groups are used, or if there are other conflicts, inclusion takes precedence over exclusion.

For example, you want to assign a device profile to all devices in your organization, except kiosk devices. You include the **All Users** group, but exclude the **All Devices** group.

In this case, all your users and their devices get the policy, even if the user’s device is part of the **All Devices** group. 

Exclusion only evaluates the direct members of the groups, and does not include devices that are associated with a user. However, devices that don't have a user don't get the policy because they have no association to the **All Users** group. 

If you include **All Devices**, but exclude **All Users**, all the devices receive the policy. The intent in this case is to exclude devices that have an associated user from this policy. However, it does not because the exclusion feature only compares direct group members. 

>[!TIP]
>Exclusions are not currently available for compliance policies or app assignment. To exclude members from an assignment, you can use the Available, and Not applicable assignment intents. For example, you assign an app to **All corporate users** with the **Available** intent, and to **Senior Management Staff** with the **Not applicable** intent. The app is assigned to all users *except* users in the **Senior Management Staff** group. If you assign the app to **All corporate users** with the **Required** intent, the users in the **Senior Management Staff** group are not excluded.
 	
## Next steps
See [How to monitor device profiles](device-profile-monitor.md) for guidance on monitoring device profile assignments.