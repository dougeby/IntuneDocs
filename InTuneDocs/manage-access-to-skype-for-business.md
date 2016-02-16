---
title: Manage access to Skype for Business
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 1b2d7125-f63f-43cf-ac1e-94fbedf2a7e8
author: karthikaraman
---
# Manage access to Skype for Business
Use conditional access policy for  **Skype for Business Online** to manage access to Skype for Business Online, based on conditions you specify.

When a targeted user attempts to use Skype for Business Online on their device, the following evaluation occurs:

![](../Image/ConditionalAccess_SkypeforBusiness.png)

The device that needs access to Skype for Business Online must:

-   Be an Android or iOS device.

-   Be enrolled with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]

-   Be compliant with any deployed [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] compliance policies

The device state is stored in Azure Active Directory which grants or blocks access, based on the conditions you specify.

If a condition is not met, the user is presented with one of the following messages when they log in:

-   If the device is not enrolled with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], or is not registered in Azure Active Directory, a message is displayed with instructions about how to install the company portal app and enroll.

-   If the device is not compliant, a message is displayed that directs the user to the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] web portal where they can find information about the problem, and how to remediate it.

## Steps to configure conditional access for Skype for Business Online

### Step 1: Configure Active Directory security groups
Before you start, configure Azure Active Directory security groups for the conditional access policy. You can configure these groups in the **Office 365 admin center**. These groups contain the users that will be targeted, or exempt from the policy. When a user is targeted by a policy, each device they use must be compliant in order to access resources.

You can specify two group types to use for the Skype for Business policy:

-   **Targeted groups** – Contains groups of users to which the policy will apply

-   **Exempted groups** – Contains groups of users that are exempt from the policy (optional)

If a user is in both groups, they will be exempt from the policy.

### Step 2: Configure and deploy a compliance policy
Ensure that you create and deploy a compliance policy to all devices that the Skype for Business Online policy will be targeted to.

> [!NOTE]
> While compliance policies are deployed to [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] groups, conditional access policies are targeted to Azure Active Directory security groups.

For details about how to configure the compliance policy, see [Manage device compliance policies for Microsoft Intune](../Topic/Manage-device-compliance-policies-for-Microsoft-Intune.md).

> [!IMPORTANT]
> If you have not deployed a compliance policy and then enable the Skype for Business Online policy, all targeted devices will be allowed access.

When you are ready, continue to **Step 3**.

### <a name="BKMK_OneDrive"></a>Step 3: Configure the Skype for Business Online policy
Next, configure the policy to require that only managed and compliant devices can access Skype for Business Online. This policy will be will be stored in Azure Active Directory.

#### <a name="bkmk_spopolicy"></a>

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Policy** &gt; **Conditional Access** &gt; **Skype for Business Online Policy**.

2.  Select **Enable conditional access policy.**.

3.  Under **Device platforms**, you can choose to apply conditional access policy to:

    -   **iOS**

    -   **Android**

4.  Under **Targeted Groups**, click **Modify** to select the Azure Active Directory security groups to which the policy will apply. You can choose to target this to all users or just a select groups of users.

5.  Under **Exempted Groups**, optionally, click **Modify** to select the Azure Active Directory security groups that are exempt from this policy.

6.  When you are done, click **Save**.

You do not have to deploy the conditional access policy, it takes effect immediately.

### Step 4: Monitor the compliance and conditional access policies
In the **Groups** workspace, you can view the conditional access status of your devices.

Select any mobile device group and then, on the **Devices** tab, select one of the following **Filters**:

-   **Devices that are not registered with AAD** – These devices are blocked from Skype for Business Online.

-   **Devices that are not compliant** – These devices are blocked from Skype for Business Online.

-   **Devices that are registered with AAD and compliant** – These devices can access Skype for Business Online.

