---
title: Restrict access to new Exchange Online Dedicated |Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid:
author: karthikaraman
---
# Restrict access to new Exchange Online Dedicated environment with Microsoft Intune
If you have an Exchange Online Dedicated environment and need to find out whether it is in the new or the legacy configuration, please contact your account manager.

This topic is about how you can restrict to your  Exchange Online Dedicated environment in the new configuration.

If you have an Exchange Online Dedicated environment in the legacy configuration, go to [legacy Exchange Online Dedicated](restrict-access to-legacy-exchange-online-dedicated-with-microsoft-intune.md) article.

To control email access to the legacy Exchange Online Dedicated environment, configure conditional access in Intune.
If you want to learn more about how conditional access works, read the [Restrict access to email and O365 services]( restrict-access-to-email-and-o365-services-with-microsoft-intune.md) article.

Before you can configure conditional access you must:

-   Have an Office 365 subscription that includes Exchange Online (such as E3) and users must be licensed for Exchange Online.

-  Consider configuring the optional **Microsoft Intune service to service connector**  which connects [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] to Microsoft Exchange Online and helps you manage device information through the [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] console. You do not need to use the connector to use compliance policies or conditional access policies, but is required to run reports that help evaluate the impact of conditional access.

   > [!NOTE]
   > Do not configure the service to service connector if you intend to use conditional access for both Exchange Online and Exchange On-premises

   For instructions on how to configure the connector, see [Intune service to service connector](intune-service-to-service-exchange-connector.md)

When conditional access policies are configured and targeted to a user, before a user can connect to their email, the **device** they use must be:

-   **Enrolled** with [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] or is a domain joined PC.

-  **Registered in Azure Active Directory**. This happens automatically when the device is enrolled with [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]. Additionally, the client Exchange ActiveSync ID must be registered with Azure Active Directory.

  AAD DRS will be activated automatically for Intune and Office 365 customers. Customers who have already deployed the ADFS Device Registration Service will not see registered devices in their on-premises Active Directory.

-   **Compliant** with any [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] compliance policies deployed to that device.

If a conditional access policy is not met, the user is presented with one of the following messages when they log in.

- If the device is not enrolled with [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], or is not registered in Azure Active Directory, a message is displayed with instructions about how to install the company portal app, enroll the device, and activate email. This process also associates the device’s Exchange ActiveSync ID with the device record in Azure Active Directory.

-   If the device is not compliant, a message is displayed that directs the user to the [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] Company Portal website, or the Company Portal  app where they can find information about the problem and how to remediate it.


The diagram below illustrated the flow is used by conditional access policies for Exchange Online to evaluate whether to allow or block devices.

![](../media/ConditionalAccess8-1.png)

## Support for mobile devices
You can restrict access to Exchange Online email from **Outlook** and other apps that use modern authentication on iOS and Android devices.
- Android 4.0 and later, Samsung Knox Standard 4.0 and later
- iOS 7.1 and later
- Windows Phone 8 and later
> [!TIP]
> **Modern authentication** brings Active Directory Authentication Library (ADAL)-based sign in to Office clients.
>
> -   The ADAL based authentication enables Office clients to engage in browser-based authentication (also known as passive authentication).  To authenticate, the user is directed to a sign-in web page.
> -   This new sign-in method enables new scenarios such as, conditional access, based on **device compliance** and whether **multi-factor authentication** was performed.
>
> This [article](https://blogs.office.com/2014/11/12/office-2013-updated-authentication-enabling-multi-factor-authentication-saml-identity-providers/) has more detailed information on how modern authentication works.


You can restrict access to Exchange email from the built-in **Exchange ActiveSync email client** on the following platforms:

- Android 4.0 and later, Samsung Knox Standard 4.0 and later

- Any iOS device

- Windows Phone 8.1 and later



## Support for PCs
>[!IMPORTANT]
>Conditional access for PCs is not currently available to all Intune customers. If you are already using conditional access for PCs, you do not need to take any action. You can continue to use it.
If you have not created conditional access policies for PCs you will need to submit a request for access.  You can find out more information about known issues as well as how to get access to this feature at the [connect site](http://go.microsoft.com/fwlink/?LinkId=761472)

You can setup conditional access for PCs that run Office desktop applications to access **Exchange Online** and **SharePoint Online** for PCs that meet the following requirements:

-   The PC must be running Windows 7.0 or Windows 8.1.

-   The PC must either be domain joined, or compliant with the compliance policy. Domain joined PCs must be tenants in the new Exchange Online Dedicated environment.

    In order to be compliant, the PC must be enrolled in [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] and comply with the policies.

    For domain joined PCs, you must  set it up to [automatically register the device](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access-automatic-device-registration/) with Azure Active Directory.

-   [Office 365 modern authentication must be enabled](https://blogs.office.com/2015/03/23/office-2013-modern-authentication-public-preview-announced/), and have all the latest Office updates.

    Modern authentication brings Active Directory Authentication Library (ADAL) based sign-in to Office 2013 Windows clients and enables better security like **multi-factor authentication**, and **certificate-based authentication**.

-   Setup ADFS claims rules to block non-modern authentication protocols. Step by step instructions are detailed in scenario 3 - [block all access to O365 except browser based applications](https://technet.microsoft.com/library/dn592182.aspx).

## Configure conditional access
### Step 1: Configure and deploy a compliance policy
Make sure you [create](create-a-device-compliance-policy-in-microsoft-intune.md) and [deploy](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md) a compliance policy to all devices that the Exchange conditional access policy will be targeted to.


> [!IMPORTANT]
> If you have not deployed a compliance policy and then enable an Exchange conditional access policy, all targeted devices will be allowed access.

### <a name="bkmk_Eval_FX_CAP"></a>Step 2: Evaluate the effect of the conditional access policy
You can use the **Mobile Device Inventory Reports** to identify devices that might be blocked from accessing Exchange after you configure the conditional access policy.

To do this, configure a connection between [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] and Exchange by using the [Microsoft Intune service to service connector](intune-service-to-service-exchange-connector.md).
1.  Navigate to **Reports -> Mobile Device Inventory Reports**.
![IntuneSA2bMobileDeviceInventoryReport](../media/IntuneSA2bMobileDeviceInventoryReport.png)

2.  In the report parameters, select the [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] group you want to evaluate and, if required, the device platforms to which the policy will apply.
3.  Once you’ve selected the criteria that meets your organization’s needs, choose **View Report**.
The Report Viewer opens in a new window.
![IntuneSA2cViewReport](../media/IntuneSA2cViewReport.PNG)

After you run the report, examine these four columns to determine whether a user will be blocked:

-   **Management Channel** – Indicates whether the device is managed by Intune, Exchange ActiveSync, or both.

-   **AAD Registered** – Indicates whether the device is registered with Azure Active Directory (known as Workplace Join).

-   **Compliant** – Indicates whether the device is compliant with any compliance policies you deployed.

-   **Exchange ActiveSync ID** – iOS and Android devices are required to have their Exchange ActiveSync ID associated with the device registration record in Azure Active Directory. This happens when the user chooses the Activate Email link in the quarantine email.

    > [!NOTE]
    > Windows Phone devices always display a value in this column.

Devices that are part of a targeted group will be blocked from accessing Exchange unless the column values match those listed in the following table:

--------------------------
|Management channel|AAD registered|Compliant|Exchange ActiveSync ID|Resulting action|
|----------------------|------------------|-------------|--------------------------|--------------------|
|**Managed by Microsoft Intune and Exchange ActiveSync**|Yes|Yes|A value is displayed|Email access allowed|
|Any other value|No|No|No value is displayed|Email access blocked|
----------------------
You can export the contents of the report and use the **Email Address** column to tell your users that they will be blocked.

### <a name="BKMK_configUserGroups"></a>Step 3: Configure user groups for the conditional access policy
Conditional access policies are targeted to different Azure Active Directory security groups of users depending on whether or not this policy should apply to them or be exempted from the policy. When a user is targeted by a policy, each device they use must be compliant in order to access email.

You can configure these groups in the **Office 365 admin center**, or the **Intune account portal**.

You can specify two group types in each policy:

-   **Targeted groups** – User groups to which the policy is applied.

-   **Exempted groups** – User groups that are exempt from the policy (optional)

If a user is in both groups, they will be exempt from the policy.

Only the groups which are targeted by the conditional access policy are evaluated.

### Step 4: Configure the conditional access policy

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Policy** &gt; **Conditional Access** &gt; **Exchange Online Policy**.
![IntuneSA5dExchangeOnlinePolicy](../media/IntuneSA5dExchangeOnlinePolicy.png)

2.  On the **Exchange Online Policy** page, select **Enable conditional access policy for Exchange Online**. If you check this, the device must be compliant with the compliance policies and the restrictions you set here. If this is not checked then conditional access is not applied.

    > [!NOTE]
    > If you have not deployed a compliance policy and then enable the Exchange Online policy, all targeted devices are reported as compliant.
    >
    > Regardless of the compliance state, all users who are targeted by the policy will be required to enroll their devices with [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

3.  Under **Application access**, for apps that use modern authentication, you can choose to apply conditional access policy to:

    -   **All platforms**

        This will require that any device used to access **Exchange  Online**,  to be enrolled in Intune and compliant with the policies.  Any client application using **modern authentication** is subject to the conditional access policy, and if the platform is currently not supported by Intune, access to **Exchange Online** is blocked.
        >[!TIP]
           You many not see this option if you not already using conditional access for PCs.  Use the **Specific platforms** instead. Conditional access for PCs is not currently available to all Intune customers.   You can find out more information about known issues as well as how to get access to this feature at the [connect site](http://go.microsoft.com/fwlink/?LinkId=761472).

    -   **Specific platforms**

        If you choose the **Specific platforms** option, you will see a list of platforms that you can individually select.   Conditional access policy will apply to any client app that is using **modern authentication**, but only on the device platforms you select.

4.  Under **Exchange ActiveSync apps**, you can choose to block noncompliant devices from accessing Exchange Online if the device is noncompliant, and select whether to allow or block access to email when the device is not Android, iOS, Windows, or Windows Phone.

5.  Under **Targeted Groups**, select the Active Directory security groups of users to which the policy will apply. You can either choose to target all users or a selected list of user groups.
![IntuneSA5eTargetedExemptedGroups](../media/IntuneSA5eTargetedExemptedGroups.PNG)
    > [!NOTE]
    > For users that are in the Targeted groups, the Intune polices will replace Exchange rules and policies.
    >
    > Exchange will only enforce Exchange allow, block and quarantine rules, and Exchange policies if:
    >
    > -   The user is not licensed for Intune.
    > -   The user is licensed for Intune, but the user does not belong to any security groups targeted in the conditional access policy.

6.  Under **Exempted Groups**, select the Active Directory security groups of users that are exempt from this policy. If a user  is in both the targeted and exempted groups, they will be exempt from the policy.

7.  When you are done, choose **Save**.

-   You do not have to deploy the conditional access policy, it takes effect immediately.

-   After a user creates an email account, the device is blocked immediately.

-   If a blocked user enrolls the device with [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] (or remediates noncompliance), email access is unblocked within 2 minutes.

-   If the user un-enrolls their device, email is blocked after around 6 hours.


## Step 5: Monitor the compliance and conditional access policies

#### To view devices that are blocked from Exchange

On the [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] dashboard, choose the **Blocked Devices from Exchange** tile to show the number of blocked devices and links to more information.
![IntuneSA6BlockedDevices](../media/IntuneSA6BlockedDevices.PNG)

## Next steps
[Restrict access to SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)

[Restrict access to Skype for Business Online](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)


### See also

[Restrict access to legacy Exchange Online Dedicated](restrict-access to-legacy-exchange-online-dedicated-with-microsoft-intune.md)
