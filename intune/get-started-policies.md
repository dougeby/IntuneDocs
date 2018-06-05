---
# required metadata

title: Get started with policies in Microsoft Intune - Azure | Microsoft Docs
description: Create policies to help protect corporate data and manage the devices end users use to access company resources. Then, assign the policies to groups.
keywords:
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/04/2018
ms.topic: article
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

# Get started with creating policies

Intune policies are a great way to enroll devices, and make sure they comply with your corporate policies. Compliance policies help manage specialized device types, such as corporate-owned kiosks, and personal (Bring Your Own) devices, tablets, and user-less devices.

![Compliance dashboard with little data](/intune/media/generic-compliance-dashboard.png)

Mobile devices can be managed using compliance policies, including:

* Regulate the number of devices a user enrolls in Intune
* Manage device settings, such as device-level encryption, password length, and camera usage
* Deliver apps, email profiles, VPN profiles, and more
* Evaluate device-level criteria for security compliance policies

Compliance polidies are created for each platform, such as iOS, Android, Windows, and more. For this exercise, use iOS. The following policies are available for iOS devices:

* PIN or password configuration
* Device encryption
* Jailbroken device
* Email profile
* Minimum OS version
* Maximum OS version

## Create a policy

1. Sign in to the [Azure portal](https://portal.azure.com).
2. Select **All services**, filter on **Intune**, and select **Microsoft Intune**.
3. Select **Device compliance** > **Policies** > **Create Policy**.
4. Enter a policy **Name** and a **Description**. 
5. For the **Platform**, select **iOS**.
6. In **Settings**, select **System Security**, and then set **Require a password to unlock mobile devices** to **Require**. 

    You can also set other rules, such as: 
    - **Minimum password length**
    - **Required password type**
    - **Number of non-alphanumeric characters in password**
    
    When finished setting up your policy, select **OK**.
  
7. Go back to **Create policy**, and select **Create**. This step creates the policy, and lists your policy in **Device compliance** > **Policies**.
8. Select your new policy, and choose **Assignments**. You can include or exclude Azure Active Directory (AD) security groups.
Choose Selected groups to see your existing Azure AD security groups. Select the user groups you want this policy to apply, and choose **Save** to deploy the policy to users.

To be compliant with the new corporate policy, after a few minutes, your enrolled device prompts for an updated password. You can manually check for the update in the **Company Portal app for iOS**. Open the Company Portal app, select the device name, and then select **Sync**.

> [!NOTE]
> New policies applied to a dynamic device group may take up to eight hours to apply to all devices in the group.

## Next steps

[Get started enrolling devices](get-started-enroll.md) - Learn the enrollment experience by going through a full enrollment experience of an iOS device.

## Learn more

* [Monitor Intune Device compliance policies](compliance-policy-monitor.md)
* [Common ways to use conditional access policies with Intune](conditional-access-intune-common-ways-use.md)
