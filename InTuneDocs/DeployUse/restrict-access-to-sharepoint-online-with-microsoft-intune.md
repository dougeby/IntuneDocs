---
title: Restrict access to SharePoint Online | Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: b088e5a0-fd4a-4fe7-aa49-cb9c8cfb1585
author: karthikaraman
---
# Restrict access to SharePoint Online with Microsoft Intune
Use the [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] **SharePoint Online** conditional access to control access to OneDrive for Business files located on SharePoint online. You can restrict access to only compliant devices to be able to access SharePoint Online.
Conditional access has two components:
- Device compliance policy that the device must comply with in order to be considered compliant.
- Conditional access policy that where you specify the conditions that the device must meet in order to access the service.
To learn more about how conditional access works, read the [restrict access to email and O365 services](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) article.

When a targeted user attempts to connect to a file using a supported app such as OneDrive on their device, the following evaluation occurs:

![](../media/ConditionalAccess8-6.png)

>[!IMPORTANT]
>Conditional access for PCs and Windows 10 Mobile devices with apps using modern authentication is not currently available to all Intune customers. If you are already using these features, you do not need to take any action. You can continue to use them.

>If you have not created conditional access policies for PCs or Windows 10 Mobile for apps using modern authentication, and would like to do so, you must to submit a request.  You can find out more information about known issues as well as how to get access to this feature at the [connect site](http://go.microsoft.com/fwlink/?LinkId=761472).

**Before** configuring conditional access policy for SharePoint Online, you must:
- Have a **SharePoint Online subscription** is required and users must be licensed for SharePoint Online.
- Have a subscription for the **Enterprise Mobility Suite** or **Azure Active Directory Premium**.

  To connect to the required files, the device must:
-   Be **enrolled** with [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] or a domain joined PC.

-   **Register the device** in Azure Active Directory (this happens automatically when the device is enrolled with [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].


-   Be compliant with any deployed [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] compliance policies

The device state is stored in Azure Active Directory which grants or blocks access to the files, based on the conditions you specify.

If a condition is not met, the user is presented with one of the following messages when they log in:

-   If the device is not enrolled with [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], or is not registered in Azure Active Directory, a message is displayed with instructions about how to install the Company Portal  app and enroll.

-   If the device is not compliant, a message is displayed that directs the user to the [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] Company Portal website where they can find information about the problem, and how to remediate it.

## Support for mobile devices
- iOS 7.1 and later
- Android 4.0 and later, Samsung Knox Standard 4.0 or later
- Windows Phone 8.1 and later

## Support for PCs
- Windows 8.1 and later (when enrolled with Intune)
- Windows 7.0 or Windows 8.1 (when domain joined)

  - For domain joined PC, you must set it up to [automatically register](https://azure.microsoft.com/en-us/documentation/articles/active-directory-conditional-access-automatic-device-registration/) with Azure Active Directory.
AAD DRS will be activated automatically for Intune and Office 365 customers. Customers who have already deployed the ADFS Device Registration Service will not see registered devices in their on-premises Active Directory.

  - If the policy is set to require domain join, and the PC is not domain joined, a message is displayed to contact the IT admin.

  - If the policy is set to require domain join or compliant, then the PC does not meet either requirement, a message is displayed with instructions about how to install the Company Portal  app and enroll.
-    [Office 365 modern authentication must be enabled](https://blogs.office.com/2015/03/23/office-2013-modern-authentication-public-preview-announced/), and have all the latest Office updates.

    Modern authentication brings Active Directory Authentication Library (ADAL) based sign-in to Office 2013 Windows clients and enables better security like **multi-factor authentication**, and **certificate-based authentication**.


## Configure conditional access for SharePoint Online

### Step 1: Configure Active Directory security groups
Before you start, configure Azure Active Directory security groups for the conditional access policy. You can configure these groups in the **Office 365 admin center**, or the **Intune account portal**. These groups contain the users that will be targeted, or exempt from the policy. When a user is targeted by a policy, each device they use must be compliant in order to access resources.

You can specify two group types in a SharePoint Online policy:

-   **Targeted groups** – Contains groups of users to which the policy will apply

-   **Exempted groups** – Contains groups of users that are exempt from the policy.

If a user is in both groups, they will be exempt from the policy.

### Step 2: Configure and deploy a compliance policy
If you have not already done so, create and deploy a compliance policy to all devices that the SharePoint Online policy will be targeted to.

> [!NOTE]
> While compliance policies are deployed to [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] groups, conditional access policies are targeted to Azure Active Directory security groups.

For details about how to configure the compliance policy, see [create a  compliance policy](create-a-device-compliance-policy-in-microsoft-intune.md).

> [!IMPORTANT]
> If you have not deployed a compliance policy and then enable the SharePoint Online policy, all targeted devices will be allowed access.

When you are ready, continue to **Step 3**.

### <a name="BKMK_OneDrive"></a>Step 3: Configure the SharePoint Online policy
Next, configure the policy to require that only managed and compliant devices can access SharePoint Online. This policy will be will be stored in Azure Active Directory.

#### <a name="bkmk_spopolicy"></a>

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Policy** &gt; **Conditional Access** &gt; **SharePoint Online Policy**.
![SharePoint Online Policy page](../media/IntuneSASharePointOnlineCAPolicy.png)

2.  Select **Enable conditional access policy for SharePoint Online**.

3.  Under **Application access**, you can choose to apply conditional access policy to:

    -   **All platforms**

        This will require that any device used to access **SharePoint Online**,  to be enrolled in Intune and compliant with the policies.  Any client application using **modern authentication** is subject to the conditional access policy. If the platform is currently not supported by Intune, access to **SharePoint Online** is blocked.
        >[!TIP]
        >You may not see this option if you not already using conditional access for PCs.  Use the **Specific platforms** instead. Conditional access for PCs is not currently available to all Intune customers.   You can find out more information about known issues as well as how to get access to this feature at the [connect site](http://go.microsoft.com/fwlink/?LinkId=761472).

    -   **Specific platforms**

        If you choose the **Specific platforms** option, you will see a list of platforms that you can individually select.   Conditional access policy will apply to any client app that is using modern authentication on the platforms you specify.

     **Modern authentication** brings Active Directory Authentication Library (ADAL)-based sign in to Office clients.
     -   The ADAL based authentication enables Office clients to engage in browser-based authentication (also known as passive authentication).  To authenticate, the user is directed to a sign-in web page.
     -   This new sign-in method enables new scenarios such as, conditional access, based on **device compliance** and whether **multi-factor authentication** was performed.

     This [article](https://blogs.office.com/2014/11/12/office-2013-updated-authentication-enabling-multi-factor-authentication-saml-identity-providers/) has more detailed information on how modern authentication works.

     For windows PCs, the PC must either be domain joined, or enrolled with [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] and compliant. You can set the following requirements:

    -   **Devices must be domain joined or compliant.** This means that the PCs must either be domain joined or compliant with the policies set in [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]. If the PC does not meet either of these requirements, the user is prompted to enroll the device with [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

    -   **Devices must be domain joined.** This means that the PCs must be domain joined to access Exchange Online. If the PC is not domain joined access to email is blocked and the user is prompted to contact the IT admin.

    -   **Devices must be compliant.** This means that the PCs must be enrolled in [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] and compliant. If the PC is not enrolled, a message with instructions on how to enroll is displayed.

4.  Under **Targeted Groups**, click **Modify** to select the Azure Active Directory security groups to which the policy will apply. You can choose to target this to all users or just a select groups of users.

5.  Under **Exempted Groups**, optionally, click **Modify** to select the Azure Active Directory security groups that are exempt from this policy.

6.  When you are done, click **Save**.

You do not have to deploy the conditional access policy, it takes effect immediately.

### Step 4: Monitor the compliance and conditional access policies
In the **Groups** workspace, you can view the conditional access status of your devices.

Select any mobile device group and then, on the **Devices** tab, select one of the following **Filters**:

-   **Devices that are not registered with AAD** – These devices are blocked from SharePoint Online.

-   **Devices that are not compliant** – These devices are blocked from SharePoint Online.

-   **Devices that are registered with AAD and compliant** – These devices can access SharePoint Online.

### See also
[Restrict access to email and O365 services with Microsoft Intune](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)
