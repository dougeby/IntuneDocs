---
title: Manage email access with Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 09c82f5d-531c-474d-add6-784c83f96d93
author: karthikaraman
---
# Manage email access with Microsoft Intune
Use the [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)]**conditional access policies** for Exchange to manage access to Exchange email based on conditions you specify.

You can manage access to:

-   Microsoft Exchange On-premises

-   Microsoft Exchange Online

-   Exchange Online Dedicated

If you configure conditional access, before a user can connect to their email, the device they use must:

-   Be enrolled with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] or a domain joined PC.

-   Register the device in Azure Active Directory (this happens automatically when the device is enrolled with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] (for Exchange Online only). Additionally, the client Exchange ActiveSync ID must be registered with Azure Active Directory (does not apply to Windows and Windows Phone devices connecting to Exchange On-premises).

    For a domain joined PC, you must set it to automatically register with Azure Active Directory.  **Conditional Access for PCs** section in the [Manage access to email and SharePoint with Microsoft Intune](../Topic/Manage_access_to_email_and_SharePoint_with_Microsoft_Intune.md) topic lists the full set of requirements to enable conditional access for PCs.

-   Be compliant with any [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] compliance policies deployed to that device

If a conditional access condition is not met, the user is presented with one of the following messages when they log in.

**For mobile devices:**

-   If the device is not enrolled with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], or is not registered in Azure Active Directory, a message is displayed with instructions about how to install the company portal app, enroll the device, activate email, which associates the device’s Exchange ActiveSync ID with the device record in Azure Active Directory.

-   If the device is not compliant, a message is displayed that directs the user to the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] web portal, or the company portal app where they can find information about the problem and how to remediate it.

**For PCs:**

-   If the conditional access policy requirement is to allow **domain joined** or **compliant**, a message with instructions about how to enroll the device is displayed. If the PC does not meet either of the requirements, the user will be asked to enroll the device with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].

-   If the conditional access policy requirement is set to allow only domain joined windows devices, the device is blocked and a message to contact the IT admin is displayed.

You can block access to Exchange email from the devices built-in Exchange ActiveSync email client on the following platforms:

-   Android 4.0 and later, Samsung Knox Standard 4.0 and later

-   iOS 7.1 and later

-   Windows Phone 8.1 and later

-   The **Mail** application on Windows 8.1 and later

Outlook app for iOS and Android, and Outlook desktop 2013 is supported for Exchange Online only.

## Step 1: Evaluate the effect of the conditional access policy
If you have configured a connection between [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] and Exchange by using the **Microsoft Intune service to service connector** or the **on-premises Exchange connector**, you can use the **Mobile Device Inventory Reports** to identify EAS mail clients that will be blocked from accessing Exchange after you configure the conditional access policy.

In the report parameters, select the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] group you want to evaluate and, if required, the device platforms to which the policy will apply.

For more information about how to run reports, see [Understand Microsoft Intune operations by using reports](../Topic/Understand_Microsoft_Intune_operations_by_using_reports.md).

After you run the report, examine these four columns to determine whether a user will be blocked:

-   **Management Channel** – Indicates whether the device is managed by Intune, Exchange ActiveSync, or both.

-   **AAD Registered** – Indicates whether the device is registered with Azure Active Directory (known as Workplace Join).

-   **Compliant** – Indicates whether the device is compliant with any compliance policies you deployed.

-   **Exchange ActiveSync ID** – iOS and Android devices are required to have their Exchange ActiveSync ID associated with the device registration record in Azure Active Directory. This happens when the user clicks the Activate Email link in the quarantine email.

    > [!NOTE]
    > Windows Phone devices always display a value in this column.

Devices that are part of a targeted group will be blocked from accessing Exchange unless the column values match those listed in the following table:

|Management channel|AAD registered|Compliant|Exchange ActiveSync ID|Resulting action|
|----------------------|------------------|-------------|--------------------------|--------------------|
|**Managed by Microsoft Intune and Exchange ActiveSync**|Yes|Yes|A value is displayed|Email access allowed|
|Any other value|No|No|No value is displayed|Email access blocked|
You can export the contents of the report and use the **Email Address** column to help you inform users that they will be blocked.

## Step 2: Configure user groups for the conditional access policy
You target conditional access policies to different groups of users depending on the policy types. These groups contain the users that will be targeted, or exempt from the policy. When a user is targeted by a policy, each device they use must be compliant in order to access email.

-   **For the Exchange Online policy** – to Azure Active Directory security user groups. You can configure these groups in the **Office 365 admin center**, or the **Intune account portal**.

-   **For the Exchange On-premises policy** – to [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] user groups. You can configure these in the **Groups** workspace of the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] console.

You can specify two group types in each policy:

-   **Targeted groups** – User groups to which the policy is applied

-   **Exempted groups** – User groups that are exempt from the policy (optional)

If a user is in both groups, they will be exempt from the policy.

Only the groups which are targeted by the conditional access policy are evaluated for Exchange access.

## Step 3: Configure and deploy a compliance policy
Ensure that you have created and deployed a compliance policy to all devices that the Exchange conditional access policy will be targeted to.

For details about how to configure the compliance policy, see [Manage device compliance policies for Microsoft Intune](../Topic/Manage_device_compliance_policies_for_Microsoft_Intune.md).

> [!IMPORTANT]
> If you have not deployed a compliance policy and then enable an Exchange conditional access policy, all targeted devices will be allowed access.

When you are ready, continue to **Step 4**.

## Step 4: Configure the conditional access policy

### For Exchange Online (and tenants in the new Exchange Online Dedicated environment)
The following flow is used by conditional access policies for Exchange Online to evaluate whether to allow or block devices.

![](../Image/ConditionalAccess8-1.png)

To access email, the device must:

-   Enroll with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]

-   PCs must either be domain joined or be enrolled and compliant with the policies set in [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].

-   Register the device in Azure Active Directory (this happens automatically when the device is enrolled with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].

    For domain joined PCs, you must  set it up to [automatically register the device](https://azure.microsoft.com/en-us/documentation/articles/active-directory-conditional-access-automatic-device-registration/) with Azure Active Directory.

-   Have activated email, which associates the device’s Exchange ActiveSync ID with the device record in Azure Active Directory (applies to iOS and Android devices only).

-   Be compliant with any deployed [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] compliance policies

The device state is stored in Azure Active Directory which grants or blocks access to email, based on the evaluated conditions.

If a condition is not met, the user will be presented with one of the following messages when they log in:

-   If the device is not enrolled, or registered in Azure Active Directory, a message is displayed with instructions about how to install the company portal app and enroll.

-   If the device is not compliant, a message is displayed that directs the user to the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] web portal where they can find information about the problem and how to remediate it.

-   For a PC:

    -   If the policy is set to require domain join, and the PC is not domain joined, a message is displayed to contact the IT admin.

    -   If the policy is set to require domain join or compliant, then the PC does not meet either requirement, a message is displayed with instructions about how to install the company portal app and enroll.

The message is displayed on the device for Exchange Online users and tenants in the new Exchange Online Dedicated environment, and is delivered to the users email inbox for Exchange On-premises and legacy Exchange Online Dedicated devices.

> [!NOTE]
> [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] conditional access rules override, allow, block and quarantine rules that are defined in the Exchange Online admin console.

#### <a name="BKMK_ExoCA"></a>To enable the Exchange Online policy

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Policy** &gt; **Conditional Access** &gt; **Exchange Online Policy**.

2.  On the **Exchange Online Policy** page, select **Enable conditional access policy for Exchange Online**. If you check this, the device must be compliant. If this is not checked then conditional access is not applied.

    > [!NOTE]
    > If you have not deployed a compliance policy and then enable the Exchange Online policy, all targeted devices are reported as compliant.
    > 
    > Regardless of the compliance state, all users who are targeted by the policy will be required to enroll their devices with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].

3.  Under **Device platforms**, you can choose to apply conditional access policy to:

    -   **All platforms**

        This will require that any device used to access **Exchange  Online**,  to be enrolled in Intune and compliant with the policies.  Any client application using **modern authentication** is subject to the conditional access policy, and if the platform is currently not supported by Intune, access to **Exchange Online** is blocked.

    -   **Specific platforms**

        If you choose the **Specific platforms** option, you will see a list of platforms that you can individually select.   Conditional access policy will apply to any client app that is using **modern authentication**, but only on the device platforms you select.

    > [!TIP]
    > **Modern authentication** brings Active Directory Authentication Library (ADAL)-based sign in to Office clients.
    > 
    > -   The ADAL based authentication enables Office clients to engage in browser-based authentication (also known as passive authentication).  To authenticate, the user is directed to a sign-in web page.
    > -   This new sign-in method enables new scenarios such as, conditional access, based on **device compliance** and whether **multi-factor authentication** was performed.
    > 
    > This [article](https://blogs.office.com/2014/11/12/office-2013-updated-authentication-enabling-multi-factor-authentication-saml-identity-providers/) has more detailed information on how modern authentication works.

    For windows PCs, the PC must either be domain joined, or enrolled with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] and compliant. You can set the following requirements:

    -   **Devices must be domain joined or compliant.** This means that the PCs must either be domain joined or compliant with the policies set in [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]. If the PC does not meet either of these requirements, the user is prompted to enroll the device with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].

    -   **Devices must be domain joined.** This means that the PCs must be domain joined to access Exchange Online. If the PC is not domain joined access to email is blocked and the user is prompted to contact the IT admin.

    -   **Devices must be compliant.** This means that the PCs must be enrolled in [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] and compliant. If the PC is not enrolled, a message with instructions on how to enroll is displayed.

4.  Under **Exchange ActiveSync mail apps**, you can choose to block email from accessing Exchange Online if the device is noncompliant, and select whether to allow or block access to email when Microsoft Intune cannot manage the device.

5.  Under **Targeted Groups**, select the Active Directory security groups of users to which the policy will apply. You can either choose to target all users or a selected list of user groups.

    > [!NOTE]
    > For users that are in the Targeted groups, the Intune polices will replace Exchange rules and policies.
    > 
    > Exchange will only enforce Exchange allow, block and quarantine rules, and Exchange policies if:
    > 
    > -   The user is not licensed for Intune.
    > -   The user is licensed for Intune, but the user does not belong to any security groups targeted in the conditional access policy.

6.  Under **Exempted Groups**, select the Active Directory security groups of users that are exempt from this policy. If a user  is in both the targeted and exempted groups, they will be exempt from the policy.

7.  When you are done, click **Save**.

-   You do not have to deploy the conditional access policy, it takes effect immediately.

-   After a user creates an email account, the device is blocked immediately.

-   If a blocked user enrolls the device with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] (or remediates noncompliance), email access is unblocked within 2 minutes.

-   If the user un-enrolls their device, email is blocked after around 6 hours.

### For Exchange on-premises (and tenants in the legacy Exchange Online Dedicated environment)
The following flow is used by conditional access policies for Exchange on-premises and tenants in the legacy Exchange Online Dedicated environment to evaluate whether to allow or block devices.

![](../Image/ConditionalAccess8-2.png)

##### To enable the Exchange On-premises policy

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Policy** &gt; **Conditional Access** &gt; **Exchange On-premises policy**.

2.  Configure the policy with the settings you require:

    |Setting|More information|
    |-----------|--------------------|
    |**Block email apps from accessing Exchange On-premises if the device is noncompliant or not enrolled to Microsoft Intune**|When you select this option, devices that are not managed by [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] or are not compliant with a compliance policy that was deployed to them are blocked from accessing Exchange services unless they have been defined as exempt.|
    |**Default rule override - Always allow  enrolled and compliant devices to access Exchange**|When you check this option, devices that are enrolled in Intune and compliant with the compliant policies are allowed to access Exchange.  This rule overrides the **Default Rule**, which means that even if you set the **Default Rule** to quarantine or block access, enrolled and compliant devices will still be able to access Exchange.|
    |**Targeted Groups**|Select the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] user groups that must enroll their device with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] before they can access Exchange.|
    |**Exempted Groups**|Select the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] user groups that are exempt from the conditional access policy.<br /><br />Settings in this list override those in the **Targeted Groups** list.|
    |**Platform Exceptions**|Click **Add Rule** to configure a rule that defines access levels for specified mobile device families and models.<br /><br />Because these devices can be of any type, you can also configure device types that are unsupported by [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].|
    |**Default Rule**|For a device that is not covered by any of the other rules, you can choose to allow it to access Exchange, block it, or quarantine it.<br /><br />When you set the rule to allow access, for devices that are enrolled and compliant, email access is granted automatically for iOS, Windows, and Samsung Knox devices. The end-user does not have to go through any process to get their email.  On Android devices that are not Knox based, end-users will get a quarantine email which includes a guided walkthrough to verify enrollment and compliance before they can access email.<br /><br />If you set the rule to block access or quarantine it, all devices are blocked from getting access to exchange regardless of whether they are already enrolled in Intune or not. To prevent enrolled and compliant devices from being affected by this rule, check the **Default Rule Override.** **Tip:** If you intention is to first block all devices before granting access to email, checking the Block access, or Quarantine rule can be useful.<br />The default rule will apply to all device types, so device types you configure as platform exceptions and that are unsupported by [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] are also affected.|
    |**User Notification**|In addition to the notification email sent from Exchange, Intune sends an email that you can configure which contains steps to unblock the device.<br /><br />You can edit the default message and use HTML tags to format how the text appears. **Note:** Because the Intune notification email containing remediation instructions is delivered to the user’s Exchange mailbox, in the event that the user’s device gets blocked before they receive the email message, they can use an unblocked device or other method to access Exchange and view the message.This is especially true when the **Default Rule** is set to block or quarantine.  In this case, the end-user will have to go to their app store, download the Microsoft Company Portal app and enroll their device. This is applicable to iOS, Windows, and Samsung Knox devices.  For  Android devices that are not Knox-based, the IT admin will need to send the quarantine email to an alternate email account, which then  the end-user has to copy to their blocked device to complete the enrollment and compliance process.|
    > [!NOTE]
    > In order for Exchange to be able to send the notification email, you must configure the account that will be used to send the notification email.
    > 
    > For details, see [Configure Microsoft Intune on-premises connector for on-premises or hosted Exchange](../Topic/Mobile_device_management_with_Exchange_ActiveSync_and_Microsoft_Intune.md#bkmk_EX_OP).

3.  When you are done, click **Save**.

-   You do not have to deploy the conditional access policy, it takes effect immediately.

-   After a user sets up an Exchange ActiveSync profile, it might take from 1-3 hours for the device to be blocked (if it is not managed by [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]).

-   If a blocked user then enrolls the device with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] (or remediates noncompliance), email access will be unblocked within 2 minutes.

-   If the user un-enrolls from [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] it might take from 1-3 hours for the device to be blocked.

## Step 5: Monitor the compliance and conditional access policies

#### To view devices that are blocked from Exchange

1.  On the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] dashboard, click the **Blocked Devices from Exchange** tile to show the number of blocked devices and links to more information.

## <a name="BKMK_Scenario"></a>Example Scenarios

### All iOS devices that access Exchange On-premises must be managed by Intune
In this example, the organization only uses devices that run iOS and they require that all of these devices are managed by [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] before they can access Exchange.

To accomplish this, in the conditional access policy, they configure the following:

-   Select the option **Enable conditional access policy for Exchange Online**.

-   For apps using modern authentication, select **iOS** for the platform

-   For Exchange ActiveSync apps, select **Require mobile devices to be compliant**  and block access to email on devices that are not supported by [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].

-   A platform exception that allows devices that run iOS to access Exchange.

-   A default rule that specifies when a device is not covered by other rules, then it should be blocked.

The following flow is used to decide which devices can access Exchange:

![](../Image/ConditionalAccess8-3.png)

### No Android devices can access Exchange On-premises. All other devices that access Exchange must be managed by Intune
In this example, the organization does not want to allow devices that run Android access to Exchange. All other supported devices can access Exchange as long as they are managed by [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].

To accomplish this, in the conditional access policy, they configure the following:

-   Select the option **Enable conditional access policy for Exchange online**.

-   A platform exception that blocks devices that run Android from accessing Exchange.

-   A default rule that specifies when a device is not covered by other rules, then it should be allowed.

The following flow is used to decide which devices can access Exchange:

![](../Image/ConditionalAccess8-4.png)

### Block users of noncompliant devices from Exchange Online in a specified Active Directory security group. Exempt devices in another security group
In this scenario, all users in the **Accounting** Active Directory security group must be blocked from accessing Exchange Online if their device is not compliant with a compliance policy you deployed. Additionally, any users in the **Finance** Active Directory security group must be exempt from the policy, even if they are also in the **Accounting** security group. Finally, if any users exist in this group whose devices are not supported by [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], they must be blocked from accessing Exchange Online on that device.

To accomplish this, in the conditional access policy, they configure the following:

-   Select the option **Enable conditional access for Exchange Online.**.

-   Select **Accounting** under **Targeted Groups**.

-   Select **Finance** under **Exempted Groups**.

-   Under **Exchange ActiveSync mail apps**, select **Require mobile devices to be compliant**option.

The following flow is used to decide which devices can access Exchange:

![](../Image/ConditionalAccess8-5.png)

## See Also
[Manage access to email and SharePoint with Microsoft Intune](../Topic/Manage_access_to_email_and_SharePoint_with_Microsoft_Intune.md)

