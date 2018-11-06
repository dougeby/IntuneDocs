---
# required metadata

title: Quickstart - Set a required password length for Android devices
titlesuffix: Microsoft Intune
description: In this quickstart you will use Microsoft Intune to set a length of the password required for Android devices.
keywords:
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/17/2018
ms.topic: quickstart
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 81b4fa08-5333-4c54-9f49-8db5f6984ed2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Quickstart: Set a required password length for Android devices

In this quickstart, you will use Microsoft Intune to require your workforce's Android users to enter a password of a specific length before access is granted to information on their Android devices. 

> [!IMPORTANT]
> In addition to password settings, you should also consider other system security settings to protect your workforce. For more information, see [System security settings](compliance-policy-create-android-for-work.md#system-security-settings).

If you don’t have an Intune subscription, [sign up for a free trial account](free-trial-sign-up.md).

## Sign in to Intune

Sign in to the [Intune](https://aka.ms/intuneportal) as a Global Administrator or an Intune Service Administrator. 

## Create a device compliance policy

For this quickstart, you'll use Intune to require your workforce's Android users to enter a password of a specific length before access is granted to information on their Android devices.

1. In Intune, select **Device compliance** > **Policies** > **Create Policy**.
2. Add **Android compliance** as the  **Name**. Also, add a **Description**.
3. For **Platform**, select **Android**. 
4. Select **Settings** > **System Security** to display the Android **System Security** blade.
5. Click **Require** next to **Require a password to unlock mobile devices**.
6. Enter **6** next to **Minimum password length**. 

    ![Screenshot of creating a group in Microsoft Intune](media/quickstart-set-password-length-android/quickstart-set-password-length-android-01.png)

7. When done, click **OK** > **OK** > **Create** to create the policy.

When you've successfully created the policy, it will appear in your list of device complice policies. 

## Next steps

In this quickstart, you used Intune to create a compliance policy for your workforce's Android devices to require a password of at least six characters in length.

> [!div class="nextstepaction"]
> [Send notifications to noncompliant devices](quickstart-send-notification.md)
