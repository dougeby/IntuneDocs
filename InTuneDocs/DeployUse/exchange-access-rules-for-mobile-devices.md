---
# required metadata

title: Exchange access rules for Microsoft Intune managed mobile devices | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 484156c7-c3c4-469d-b718-9fa33d9d0ec2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Exchange access rules for mobile devices
Exchange access rules for mobile devices determine the level of access to those devices have to Exchange. These setting affect all mobile devices, including those not enrolled in Microsoft Intune. You can start off by defining a **Default Rule** which will apply to any mobile device that does not have a custom rule applied to it. The following table contains the access levels managed by Exchange ActiveSync:

|Access level|Description|
|----------------|---------------|
|**Allow all mobile devices to access Exchange, unless a custom rule states otherwise**|In the *allow access* state, mobile devices can synchronize through Exchange ActiveSync and connect to the Exchange server to retrieve email and manage Calendar, Contacts, Tasks, and Notes. This continues as long as the device complies with the **Intune Mobile Device Security Policy** that you have configured, unless the user or the specific mobile device has been blocked by the Exchange administrator.|
|**Block all mobile devices from accessing Exchange, unless a custom rule states otherwise**|In the *block access* state, mobile devices are blocked and won't be allowed to connect to the Exchange server. Devices will receive an HTTP 403 Forbidden error. The user will receive an email message from the Exchange server telling them that the mobile device was blocked from accessing their mailbox. This message cannot be on the blocked mobile device. You can add customized text to this message to provide instructions for users whose devices are blocked with the **Set User Notification** task.|
|**Quarantine all mobile devices so I can decide later for each individual mobile device, unless a custom rule states otherwise**|When a mobile device is quarantined, the mobile device is allowed to connect to the Exchange server. However, it is given only limited access to data. The user can add content to their own Calendar, Contacts, Tasks, and Notes folders but the server will not allow the device to retrieve any content from the user's mailbox. The user will receive a single email message stating that the mobile device is quarantined. This message is received on the device and in the user's mailbox. You can add customized text to this message to provide instructions for users whose devices are quarantined through the **Set User Notification** task.|

An access strategy is a combination of a **Default Rule** and **Custom Rules** that apply to all mobile devices connected to exchange. The table below lists some example access strategies.

|Access strategy|Description|
|-------------------|---------------|
|Allow list|You can use an *allow list* to grant access to a list of known devices and restrict access for everything else. To do this, you must create custom rules so that the specific devices you want are allowed to access users' mailboxes. As soon as you create such a rule, you must set the default access rule to block or quarantine all other devices. To add a new device to the allow list, create a new custom rule|
|Block list|You can use a *block list* to grant access to all devices by default, but to block access for a set of devices that you do not want to access your organization. Create a block list by creating custom rules to block the devices that you do not want to synchronize with the organization’s mailboxes. The default rule should be set to allow access to all devices that are not explicitly blocked by the existing rules. To add a new device or set of devices to the block list, create a new custom rule.|
|Mixed allow and block|In addition to creating allow and block lists, you can quarantine new mobile devices as they are introduced into the organization while you evaluate them. For example, if you have a block list for mobile devices that are not allowed within your organization, and an allow list for mobile devices that are allowed within the organization, you can set the default rule to quarantine. All other devices will automatically be quarantined. This lets you discover new devices as they are introduced to the organization and decide whether to add them to the allow list or the block list.|
The following procedure describes how to create a custom rule.

## Create a default access rule

1.  In the [Microsoft Intune administration console](http://manage.microsoft.com) &gt; **Policy** &gt; **Exchange Access for Mobile Devices**.

2.  In the **Default Rule** list, select the Access Rule that you wish to apply to all mobile devices not covered by a rule or personal exemption. Choose **Save**.

The following procedure describes how to create a custom rule.

## Create a custom access rule

1. In the [Microsoft Intune administration console](http://manage.microsoft.com) &gt; **Policy** &gt; **Exchange Access for Mobile Devices**.

2.  In the **Custom Rules** list, Choose **Add Rule** and create a custom rule. Choose **Save**.

### Next steps
[Set Exchange access rules for mobile devices](exchange-access-rules-for-mobile-devices.md)
