---
# required metadata

title: "Quickstart: Add a device compliance policy for a Windows 10 device"
description: Use this quickstart to create policies to help protect corporate data and manage the devices end users use to access company resources. Then, assign the policies to groups.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/21/2018
ms.topic: quickstart
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 1ac74ba5-7441-44ac-98b5-9d8bb8899747


# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Quickstart: Add a device compliance policy for a Windows 10 device
An Intune device compliance policy for Windows specifies the rules and settings that Windows devices must meet to be considered compliant. You can use these policies with [conditional access](https://docs.microsoft.com/intune/conditional-access) to allow or block access to company resources. You can also get device reports and take actions for non-compliance.

In this quickstart, you'll create a device compliance policy for a Windows 10 device and then assign a device group to the policy.

If you don’t have an Intune subscription, [sign up for a free trial account](free-trial-sign-up.md).

## Prerequisites
- To complete this quickstart, you must first [create a user](quickstart-create-user.md) and [create a group](quickstart-create-group.md).


## Sign in to Intune
Sign in to [Intune](https://aka.ms/intuneportal) as a Global Administrator or an Intune Service Administrator.

## Create a device compliance policy
1. Select **Device compliance** > **Policies** > **Create Policy**.
2. Enter **Windows 10 compliance** in **Name** and **Sample compliance policy for Windows 10** for **Description**.
3. For the **Platform**, select **Windows 10 and later**.
4. In **Settings**, select **System Security**, and then set **Require a password to unlock mobile devices** to **Require**. When finished setting up your policy, select **OK**.
   ![Compliance policy](/intune/media/quickstart-create-policy/compliance-policy.png)
5. Close the **Windows 10 compliance policy** pane. 
6. On the **Create policy** pane, select **Create**. This step creates the policy, and lists your policy in **Device compliance** > **Policies**.
7. Select your new policy, and choose **Assignments**. You can include or exclude Azure Active Directory (AD) security groups.
8. Choose **Selected groups** to see your existing Azure AD security groups. Select **Contoso Testers**, and choose **Save** to deploy the policy to users in the group. If you didn't create this group in [create a group](quickstart-create-group.md), you can use the group of your choice. 

## Clean up resources
When no longer needed, delete the policy. To do so, select the **Windows 10 compliance** policy and click **Delete**. 

## Next steps
In this quickstart, you've created and assigned a simple device compliance policy. To enroll a Windows 10 device that will receive the policy, continue to the quickstart to set up auto enrollment. 
 
> [!div class="nextstepaction"]
> [Set up auto enrollment](quickstart-setup-auto-enrollment.md)