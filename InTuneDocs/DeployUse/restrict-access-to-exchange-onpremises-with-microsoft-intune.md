---
title: Restrict email access to Exchange On-premises and legacy Exchange Online Dedicated| Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid:
author: karthikaraman
---
# Restrict email access to Exchange On-premises and legacy Exchange Online Dedicated with Intune

The information in this topics applies to both Exchange Online and the legacy Exchange Online Dedicated environment.

If you have an Exchange Online Dedicated environment and need to find out whether it is in the new or the legacy configuration, please contact your account manager.


To control email access to Exchange On-premises or to your legacy Exchange Online dedicated environment, configure conditional access to Exchange On-premises in Intune.
If you want to learn more about how conditional access works, read the [Restrict access to email and O365 services]( restrict-access-to-email-and-o365-services-with-microsoft-intune.md) article.

Before you can configure conditional access verify the following:

-   Your Exchange version must be **Exchange 2010 or later**. Exchange server Client Access Server (CAS) array is supported.

-   You must use the **on-premises Exchange connector** which connects [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] to Microsoft Exchange On-premises. This lets you manage devices through the [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] console. For details on the connector, see [Mobile device management with Exchange ActiveSync and Microsoft Intune](intune-on-premises-exchange-connector.md).

    -   Make sure that you are using the latest version of the **on-premises Exchange connector**. The on-premise Exchange connector available to you in the Intune console is specific to your Intune tenant and cannot be used with any other tenant. You should also ensure that the exchange connector for your tenant is installed on exactly one machine and not on multiple machines.

        This connector should be downloaded from the Intune admin console.  For a walkthrough on how to configure the on-premises Exchange connector, see [Configure Exchange on-premises connector for on-premises or hosted Exchange](intune-on-premises-exchange-connector.md).

    -   The connector can be installed on any machine as long as that machine is able to communicate with the Exchange server.

    -   The connector indeed supports **Exchange CAS environment**. You can technically install the connector on the Exchange CAS server directly if you wish to, but it is not recommended as it will increase the load on the server.
    When configuring the connector, you must set it up to talk to one of the Exchange CAS servers.

-   **Exchange ActiveSync** must be configured with certificate based authentication, or user credential entry.

When conditional access policies are configured and targeted to a user, before a user can connect to their email, the **device** they use must be:

-   **Enrolled** with [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] or is a domain joined PC.

-  **Registered in Azure Active Directory**. Additionally, the client Exchange ActiveSync ID must be registered with Azure Active Directory.

  AAD DRS will be activated automatically for Intune and Office 365 customers. Customers who have already deployed the ADFS Device Registration Service will not see registered devices in their on-premises Active Directory. **This does not apply to Windows PCs and Windows Phone devices**.

-   **Compliant** with any [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] compliance policies deployed to that device.

The following diagram illustrates the  flow is used by conditional access policies for Exchange on-premises to evaluate whether to allow or block devices.

![](../media/ConditionalAccess8-2.png)
If a conditional access policy is not met, the user is presented with one of the following messages when they log in.

- If the device is not enrolled with [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], or is not registered in Azure Active Directory, a message is displayed with instructions about how to install the Company Portal  app, enroll the device, and activate email. This process also associates the device’s Exchange ActiveSync ID with the device record in Azure Active Directory.

-   If the device is not compliant, a message is displayed that directs the user to the [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] Company Portal   website, or the Company Portal   app where they can find information about the problem and how to remediate it.

## Support for mobile devices
-   Windows Phone 8 and later

-   Native email app on iOS.

-   Native email app on Android 4 or later

## Support for PCs
>[!IMPORTANT]
>Conditional access for PCs is not currently available to all Intune customers. If you are already using conditional access for PCs, you do not need to take any action. You can continue to use it.
If you have not created conditional access policies for PCs you will need to submit a request for access.  You can find out more information about known issues as well as how to get access to this feature at the [connect site](http://go.microsoft.com/fwlink/?LinkId=761472)

The **Mail** application on Windows 8 and later (when enrolled with [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)])

## <a name="BKMK_enableXchngOnprem"></a>Configure a conditional access policy

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Policy** &gt; **Conditional Access** &gt; **Exchange On-premises policy**.
![IntuneSA5aSelectExchOnPremPolicy](../media/IntuneSA5aSelectExchOnPremPolicy.png)

2.  Configure the policy with the settings you require:
![IntuneSA5bExchangeOnPremPolicy](../media/IntuneSA5bExchangeOnPremPolicy.png)

  - **Block email apps from accessing Exchange On-premises if the device is noncompliant or not enrolled to Microsoft Intune:** When you select this option, devices that are not managed by [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], or are not compliant with a compliance policy that was deployed to them are blocked from accessing Exchange services. <need to verify this: unless they have been defined as exempt>

  - **Default rule override - Always allow  enrolled and compliant devices to access Exchange:** When you check this option, devices that are enrolled in Intune and compliant with the compliant policies are allowed to access Exchange.  
  This rule overrides the **Default Rule**, which means that even if you set the **Default Rule** to quarantine or block access, enrolled and compliant devices will still be able to access Exchange.

  - **Targeted Groups:** Select the [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] user groups that must enroll their device with [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] before they can access Exchange.

  - **Exempted Groups:**Select the [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] user groups that are exempt from the conditional access policy. Settings in this list override those in the **Targeted Groups** list.

  - **Platform Exceptions:** Choose **Add Rule** to configure a rule that defines access levels for specified mobile device families and models. Because these devices can be of any type, you can also configure device types that are unsupported by [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

  - **Default Rule:** For a device that is not covered by any of the other rules, you can choose to allow it to access Exchange, block it, or quarantine it. When you set the rule to allow access, for devices that are enrolled and compliant, email access is granted automatically for iOS, Windows, and Samsung Knox devices. The end-user does not have to go through any process to get their email.  On Android devices that are not Knox based, end-users will get a quarantine email which includes a guided walkthrough to verify enrollment and compliance before they can access email. If you set the rule to block access or quarantine it, all devices are blocked from getting access to exchange regardless of whether they are already enrolled in Intune or not. To prevent enrolled and compliant devices from being affected by this rule, check the **Default Rule Override.**
>[!TIP]
>If you intention is to first block all devices before granting access to email, checking the Block access, or Quarantine rule can be useful. The default rule will apply to all device types, so device types you configure as platform exceptions and that are unsupported by [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] are also affected.

  - **User Notification:** In addition to the notification email sent from Exchange, Intune sends an email that you can configure which contains steps to unblock the device. You can edit the default message and use HTML tags to format how the text appears. Because the Intune notification email containing remediation instructions is delivered to the user’s Exchange mailbox, in the event that the user’s device gets blocked before they receive the email message, they can use an unblocked device or other method to access Exchange and view the message. This is especially true when the **Default Rule** is set to block or quarantine.  In this case, the end-user will have to go to their app store, download the Microsoft Company Portal   app and enroll their device. This is applicable to iOS, Windows, and Samsung Knox devices.  For  Android devices that are not Knox-based, the IT admin will need to send the quarantine email to an alternate email account, which then  the end-user has to copy to their blocked device to complete the enrollment and compliance process.|
  > [!NOTE]
  > In order for Exchange to be able to send the notification email, you must configure the account that will be used to send the notification email.
  >
  > For details, see [Configure Exchange on-premises connector for on-premises or hosted Exchange](intune-on-premises-exchange-connector.md).

3.  When you are done, choose **Save**.

-   You do not have to deploy the conditional access policy, it takes effect immediately.

-   After a user sets up an Exchange ActiveSync profile, it might take from 1-3 hours for the device to be blocked (if it is not managed by [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]).

-   If a blocked user then enrolls the device with [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] (or remediates noncompliance), email access will be unblocked within 2 minutes.

-   If the user un-enrolls from [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] it might take from 1-3 hours for the device to be blocked.

## Next steps
[Restrict access to SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)

[Restrict access to Skype for Business Online](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)


### See also
[Restrict access to Exchange Online](restrict-access to-exchange-online-with-microsoft-intune.md)

[Restrict access to new Exchange Online Dedicated](restrict-access to-new-exchange-online-dedicated-with-microsoft-intune.md)

[Restrict access to legacy Exchange Online Dedicated](restrict-access to-legacy-exchange-online-dedicated-with-microsoft-intune.md)
