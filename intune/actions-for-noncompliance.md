---
# required metadata

title: Actions for noncompliance with Intune
titleSuffix: "Intune on Azure"
description: "Learn how to create actions for noncompliance with Intune"
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 09/08/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 6d0e0c4b-a562-44f3-82a4-80eb688d4733

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: muhosabe
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Set up actions for non-compliance

The **actions for non-compliance** allow you to configure a time-ordered sequence of actions that are applied to devices that fall out of compliance. By default, once a device is reported as non-compliant by an Intune device compliance policy, conditional access immediately blocks that device, and the user receives an e-mail with instructions to be compliant. The **actions for non-compliance** give you more flexibility to decide what to do when a device is not-compliant. For example, you can decide to not block the device immediately, then give the user a grace period to be compliant.

There are two types of actions:

-   **Send e-mail to end user**: You can customize your email notification before sending it to the end user. Intune provides customization of the subject, message body, including company logo, contact information and additional recipients.

-   **Mark device non-compliant**: You can determine a schedule in number of days which the device should be marked non-compliant. This can be immediately, but you can also give the user a grace period to be compliant with your device compliance policies.

## Before you begin

You need to have at least one device compliance policy created to set up actions for non-compliance.

-   Learn how to create a device compliance policy for:

    -   [Android](compliance-policy-create-android.md)

    -   [Android for Work](compliance-policy-create-android-for-work.md)

    -   [iOS](compliance-policy-create-ios.md)
    
    -   [macOS](compliance-policy-create-mac-os.md)

    -   [Windows](compliance-policy-create-windows.md)

You need to have Azure AD conditional access set up ready when planning to use device compliance policies to block devices from using corporate resources.

- Learn [how to setup EMS conditional access](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access).

Additionally, you need to have a notification message template created. The notification message template is used later in the process of creating actions for non-compliance to send e-mail to your users.

### To create a notification message template

1. Go to the [Azure portal](https://portal.azure.com), and sign in with your Intune credentials.

2. Choose **More services** from the left menu, then type **Intune** in the text box filter.

3. Choose **Intune**

4. Choose **Device compliance**, then choose **Notifications** under the **Manage** section.

5. Choose **Create notification**, then enter the following:

    a.  Name

    b.  Subject

    c.  Message

    d.  E-mail header – Include company logo

    e.  E-mail footer – Include company name

    f.  E-mail footer – Include contact information

Once you're done adding the information, choose **Create**. The Notification message template is available for use.

> [!NOTE] 
> You can also edit a Notification template previously created.

## To create actions for non-compliance

You can add an action by the time you’re creating a new device compliance policy or by editing an existing device compliance policy.

1.  In the Intune workload, from the **Device compliance policies** blade, choose **Policies** under the **Manage** section.

2.  Choose a device compliance policy by clicking on it, then choose **Properties** under the **Manage** section.

3.  The **device compliance policy properties** blade opens, choose **Actions for noncompliance**.

4.  The Actions for noncompliance blade opens, choose **Add** to specify action parameters. You can choose the message template previously created, additional recipients, and the grace period schedule.

	> [!IMPORTANT]
	> You can specify the number of days (0 to 365) on the schedule, then you can enforce the conditional access policies. If you specify **0** number of days, this means conditional access must **immediately** block access to corporate resources once the devices are non-compliant with device compliance policies.

5.  Once you're done adding your information, choose **Add**, then **OK**.

## Monitor device compliance

You can monitor the device compliance activity by running the reports available in the device compliance blade. Learn more [how to monitor device compliance with Intune](device-compliance-monitor.md).git 

