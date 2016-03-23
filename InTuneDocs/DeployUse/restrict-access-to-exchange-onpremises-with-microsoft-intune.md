---
title: Restrict email access to Exchange On-premises | Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 09c82f5d-531c-474d-add6-784c83f96d93
author: karthikaraman
---
# Restrict email access to Exchange On-premises


### For Exchange on-premises (and tenants in the legacy Exchange Online Dedicated environment)
The following flow is used by conditional access policies for Exchange on-premises and tenants in the legacy Exchange Online Dedicated environment to evaluate whether to allow or block devices.

![](../Image/ConditionalAccess8-2.png)

##### <a name="BKMK_enableXchngOnprem"></a>To enable the Exchange On-premises policy

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Policy** &gt; **Conditional Access** &gt; **Exchange On-premises policy**.
![IntuneSA5aSelectExchOnPremPolicy](/Image/IntuneSA5aSelectExchOnPremPolicy.png)

2.  Configure the policy with the settings you require:
![IntuneSA5bExchangeOnPremPolicy](/Image/IntuneSA5bExchangeOnPremPolicy.png)

    |Setting|More information|
    |-----------|--------------------|
    |**Block email apps from accessing Exchange On-premises if the device is noncompliant or not enrolled to Microsoft Intune**|When you select this option, devices that are not managed by [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] or are not compliant with a compliance policy that was deployed to them are blocked from accessing Exchange services unless they have been defined as exempt.|
    |**Default rule override - Always allow  enrolled and compliant devices to access Exchange**|When you check this option, devices that are enrolled in Intune and compliant with the compliant policies are allowed to access Exchange.  This rule overrides the **Default Rule**, which means that even if you set the **Default Rule** to quarantine or block access, enrolled and compliant devices will still be able to access Exchange.|
    |**Targeted Groups**|Select the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] user groups that must enroll their device with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] before they can access Exchange.|
    |**Exempted Groups**|Select the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] user groups that are exempt from the conditional access policy.<br /><br />Settings in this list override those in the **Targeted Groups** list.|
    |**Platform Exceptions**|Choose **Add Rule** to configure a rule that defines access levels for specified mobile device families and models.<br /><br />Because these devices can be of any type, you can also configure device types that are unsupported by [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].|
    |**Default Rule**|For a device that is not covered by any of the other rules, you can choose to allow it to access Exchange, block it, or quarantine it.<br /><br />When you set the rule to allow access, for devices that are enrolled and compliant, email access is granted automatically for iOS, Windows, and Samsung Knox devices. The end-user does not have to go through any process to get their email.  On Android devices that are not Knox based, end-users will get a quarantine email which includes a guided walkthrough to verify enrollment and compliance before they can access email.<br /><br />If you set the rule to block access or quarantine it, all devices are blocked from getting access to exchange regardless of whether they are already enrolled in Intune or not. To prevent enrolled and compliant devices from being affected by this rule, check the **Default Rule Override.** **Tip:** If you intention is to first block all devices before granting access to email, checking the Block access, or Quarantine rule can be useful.<br />The default rule will apply to all device types, so device types you configure as platform exceptions and that are unsupported by [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] are also affected.|
    |**User Notification**|In addition to the notification email sent from Exchange, Intune sends an email that you can configure which contains steps to unblock the device.<br /><br />You can edit the default message and use HTML tags to format how the text appears. **Note:** Because the Intune notification email containing remediation instructions is delivered to the user’s Exchange mailbox, in the event that the user’s device gets blocked before they receive the email message, they can use an unblocked device or other method to access Exchange and view the message.This is especially true when the **Default Rule** is set to block or quarantine.  In this case, the end-user will have to go to their app store, download the Microsoft Company Portal app and enroll their device. This is applicable to iOS, Windows, and Samsung Knox devices.  For  Android devices that are not Knox-based, the IT admin will need to send the quarantine email to an alternate email account, which then  the end-user has to copy to their blocked device to complete the enrollment and compliance process.|
    > [!NOTE]
    > In order for Exchange to be able to send the notification email, you must configure the account that will be used to send the notification email.
    >
    > For details, see [Configure Microsoft Intune on-premises connector for on-premises or hosted Exchange](../Topic/Mobile-device-management-with-Exchange-ActiveSync-and-Microsoft-Intune.md#bkmk_EX_OP).

3.  When you are done, choose **Save**.

-   You do not have to deploy the conditional access policy, it takes effect immediately.

-   After a user sets up an Exchange ActiveSync profile, it might take from 1-3 hours for the device to be blocked (if it is not managed by [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]).

-   If a blocked user then enrolls the device with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] (or remediates noncompliance), email access will be unblocked within 2 minutes.

-   If the user un-enrolls from [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] it might take from 1-3 hours for the device to be blocked.
