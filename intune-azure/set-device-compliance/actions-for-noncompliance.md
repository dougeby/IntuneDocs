---
# required metadata

title: Actions for noncompliance
titleSuffix: "Intune Azure preview"
description: "Intune Azure preview: Learn how to create actions for noncompliance devices"
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/13/2017
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

# Create Actions for non-compliance

The **Actions for non-compliance** allow you to configure a time-ordered sequence of actions that are applied to devices that fall out of compliance. For example, you can notify users of non-compliant devices via e-mail or block those devices from accessing corporate resources through conditional access.

## Use case scenario

By default, once a device is reported as non-compliant by an Intune device compliance policy, conditional access immediately blocks that device, and the user receives an e-mail with instructions to be compliant. The **Actions for non-compliance** gives you more flexibility to decide what to do when a device is not-compliant. For example, you can decide to not block the device immediately, then give the user a grace period to be compliant.

There are two types of actions:

-   Notify the user via email

-   Block corporate resource access through conditional access

## Notify the user via email

You can choose from pre-created default email templates or create a fully customized email notification. We provide customization of the subject, message body, including company logo, contact information and additional recipients.

## Block corporate resource access through conditional access

You can determine a schedule in number of days which the device should be blocked from accessing corporate resources. This can be immediately, but you can also give the user a grace period to be compliant with the device compliance policies.

## Before you begin

You need to have at least one device compliance policy created to set up actions for non-compliance.

-   Learn how to create a device compliance policy for:

    -   [Android](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-android)

    -   [Android for Work](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-android-for-work)

    -   [iOS](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-ios)

    -   [Windows](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-windows)

You need to have EMS conditional access set up ready when planning to use device compliance policies to block devices from using corporate resources.

- Learn [how to setup EMS conditional access](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access).

Additionally, you need to have a notification message template created. The notification message template is used later in the process of creating actions for non-compliance to send e-mail to your users.

### To add a notification message template

From the **Device compliance policies** blade:

1.  Under **Manage**, choose **Notifications**, the Notification message templates blade opens.

    ![How to add a notification template](./media/afnc-1.png)

2.  Choose **Add**, then you’ll need to define the following:

    a.  Description

    b.  From

    c.  Subject

    d.  Message

    e.  E-mail header – Include company logo

    f.  E-mail footer – Include company name

    g.  E-mail footer – Include contact information

     ![The notification message template](./media/afnc-2.png)

After you’re done adding the information, you can click on **Create**. The Notification message template is available for use.

> [!NOTE] 
> You can also edit a Notification template previously created.

## To create actions for non-compliance

You can add an action by the time you’re creating a new device compliance policy or by editing an existing device compliance policy.

1.  From the **Device compliance policies** blade, under **Manage**, choose **Policies**.

2.  Choose a device compliance policy by clicking on it.

    ![Compliance policies](./media/afnc-3.png)

3.  The **device compliance policy properties** blade opens, choose **Actions for noncompliance**.

4.  The Actions for noncompliance blade opens, choose **Add** to specify action parameters.

    ![Actions for noncompliance blade](./media/afnc-4.png)

The Actions for non-compliance are:

-   **Enforce conditional access policy**

-   **Send e-mail to end user**

### Enforce conditional access policy

To add this action for non-compliance:

1.  From the **Actions for noncompliance** blade, choose **Add**.

2.  From the **Action parameters blade**, select **Enforce conditional access policy** from the Action drop-down list.

3.  On **Schedule**, you can specify the number of days (0 to 255) to enforce the conditional access policy. If you specify **0** number of days, this means conditional access must **immediately** block access to corporate resources once the devices are not-compliant with device compliance policies.

    ![Schedule Actions for noncompliance](./media/afnc-5.png)

4.  Choose **Add**, then choose **OK** from the **Actions** blade.

5.  From the **Device compliance policy properties** blade, choose **Save**.

### Send e-mail to end user

You can use an e-mail template to send to non-compliant users. These e-mails help to drive device compliance throughout the organization.

To add this action for non-compliance:

1.  From the **Actions for noncompliance** blade, choose **Add**.

2.  From the **Action parameters blade**, select **Send e-mail to end user** from the Action drop-down list.

3.  Choose a message template previously created, by clicking on **Message template**. You can view the Message template content, then choose **Select**.

    ![Message template](./media/afnc-6.png)

> [!NOTE] 
> You can view the message template, but you can’t edit it. If you want to edit the Message template, you need to go back to the **Notifications** blade.

1.  On **Schedule**, enter the number of days after non-compliance the e-mail should be sent to users. If you specify **0** number of days, this means the e-mail will be **immediately** sent.

2.  Choose **Add**, then choose **OK** from the **Actions** blade.

3.  From the **Device compliance policy properties** blade, choose **Save**.
