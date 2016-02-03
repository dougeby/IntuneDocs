---
title: Use conditional access with Intune
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 1d876fb1-a857-4350-8970-3eb38c483111
---
# Use conditional access with Intune
More and more, companies are allowing employees to increase their productivity by accessing email, documents, and company resources through their mobile devices. However, the amount of confidential data that is stored within corporate emails and documents presents a significant security risk for companies.

You can use conditional access in Intune to help secure email and email data depending on the conditions you specify. Conditional access lets you manage access to Microsoft Exchange on-premises and Exchange Online.

## Introduction

Protecting your company's data is vitally important, and is an increasingly challenging task as more employees are using their mobile devices to access company resources, including email and email attachments. As an IT administrator, you want to make sure that company data is protected even when those mobile devices are not within the company’s physical location.

The Microsoft Enterprise Mobility Suite (EMS) solves this challenge by delivering comprehensive protection of corporate email and documents across four layers – Identity, Device, Application, and Data. Among other capabilities, EMS ensures that employees can access corporate email only from devices that are managed by Microsoft Intune and compliant with IT policies.

Similar to how you [Use conditional access with Intune and Configuration Manager](../Topic/Use_conditional_access_with_Intune_and_Configuration_Manager.md), you can implement conditional access in Intune by configuring two policy types:

-   **Compliance policies** are optional policies you can deploy to users and devices and evaluate settings like passcode and encryption. The conditional access policies set in Intune ensure that the devices can only access email if they are compliant with the compliance policies you set.
    If no compliance policy is deployed to a device, then any applicable conditional access policies will treat the device as compliant.

-   **Conditional access policies** are configured for a particular service, and define rules such as which Azure Active Directory security user groups or Intune user groups will be targeted and how devices that cannot enroll with Intune will be managed.
    > [!NOTE] Intune groups are not security groups. Rather, they are a collection of users that you can create by using the Intune admin console.

Unlike other Intune policies, you do not deploy conditional access policies. Instead, you configure these once, and they apply to all targeted users.

When devices do not meet the conditions you configure, the user is guided through the process of enrolling the device and/or fixing the issue that prevents the device from being compliant.

> [!TIP]
> Get a downloadable copy of this entire topic at the [TechNet Gallery](https://gallery.technet.microsoft.com/Deploying-Enterprise-16499404).

### Evaluating your desired implementation
With all of the different design and configuration options for managing mobile devices, it’s difficult to determine which combination will best meet the needs of your company. The [Mobile Device Management Design Considerations Guide](https://technet.microsoft.com/en-us/library/mt143180.aspx) helps you understand mobile device management design requirements and details a series of steps and tasks that you can follow to design a solution that best fits the business and technology needs for your company.

### High level end-user experience 
After the solution is implemented, end-users will be able to access the company email only on managed **and** compliant devices. Access can be revoked at any time if the device becomes noncompliant.

Specifically, the conditional access policies set in Intune ensure that the devices can only access email if they are compliant with the compliance policies you set. Actions such as copy and paste or saving to personal cloud storage services can be restricted using mobile application management policies. Azure Rights Managements service can be used to ensure that the sensitive email data, and forwarded attachments, can only be read by intended recipients. The end-user experience is described in more detail in [End-user experience of conditional access](../Topic/End-user_experience_of_conditional_access.md).

## Using conditional access with Intune
Use conditional access in Intune to help secure email and other services depending on conditions you specify.

### Prerequisites
You can control access to Exchange Online and Exchange on-premises from the following mail apps:

-   The built-in app for Android 4.0 and later, Samsung Knox 4.0 Standard and later

-   The built-in app for iOS 7.1 and later

-   The built-in app for Windows Phone 8.1 and later

-   The mail application on Windows 8.1 and later

-   The Microsoft Outlook app for Android and iOS (for Exchange Online only)

Before you start using conditional access, ensure that you have the correct requirements in place:

#### For Exchange Server on-premises
Conditional access to Exchange on-premises supports:

-   Windows 8 and later (when enrolled with Intune)

-   Windows Phone 8 and later

-   Any iOS device that uses an Exchange ActiveSync (EAS) email client

-   Android 4 and later

Additionally:

-   Your Exchange version must be Exchange 2010 or later. Exchange server Client Access Server (CAS) configuration is supported.

    > [!TIP]
    > If your Exchange environment is in a CAS server configuration, then you must configure the on-premises Exchange connector to point to any one of the CAS servers.

-   Exchange ActiveSync can be configured with certificate based authentication, or user credential entry.

-   You must use the **on-premises Exchange connector** which connects Intune to Microsoft Exchange Server on-premises. This lets you manage devices through the Intune console (see [Mobile device management with Exchange ActiveSync and Microsoft Intune](https://technet.microsoft.com/en-us/library/dn646988.aspx)).

> [!IMPORTANT]
> Make sure that you are using the latest version of the on-premises Exchange connector. The on-premise Exchange connector available to you in the Intune console is specific to your Intune tenant and cannot be used with any other tenant. You should also ensure that the exchange connector for your tenant is installed on exactly one machine and not on multiple machines.

### For Exchange Online
Conditional access to Exchange Online supports devices that run:

-   Windows 8.1 and later (when enrolled with Intune)

-   Windows 7.0 or later (when domain joined)

-   Windows Phone 8.1 and later

-   iOS 7.1 and later

-   Android 4.0 and later, Samsung Knox Standard 4.0 and later

Additionally, devices must be registered with the Azure Active Directory Device Registration Service (AAD DRS).

AAD DRS will be activated automatically for Intune and Office 365 customers. Customers who have already deployed the ADFS Device Registration Service will not see registered devices in their on-premises Active Directory.

-   You must use an Office 365 subscription that includes Exchange Online (such as E3) and users must be licensed for Exchange Online.

-   The optional **Microsoft Intune service to service connector** connects Intune to Microsoft Exchange Online and helps you manage device information through the Intune console (see [Mobile device management with Exchange ActiveSync and Microsoft Intune](https://technet.microsoft.com/en-us/library/dn646988.aspx)). You do not need to use the connector to use compliance policies or conditional access policies, but is required to run reports that help evaluate the impact of conditional access.

    If you configure the connector, some Exchange ActiveSync policies from Intune might be visible in the Office console but are not set as default policies and do not affect devices.

    > [!IMPORTANT]
    > Do not configure the service to service connector if you intend to use conditional access for both Exchange Online and Exchange on-premises.

## Deployment Steps for using Exchange on-premises with Intune

### Step 1: Install and configure the Microsoft Intune on-premises Exchange Server connector.
This step will help you configure your on-premises infrastructure with Exchange on-premises.

> [!NOTE]
> You can only set up one Exchange connection per Intune account. If you try to configure an additional connection, it will replace the original connection with the new one.

#### Requirements
To prepare to connect Intune to your Exchange Server, you must first fulfill the following requirements. You may have already fulfilled these requirements when you set up Intune.

|Requirement|More information|
|---------------|--------------------|
|Set the Mobile Device Management Authority to Intune|[Set mobile device management authority as Microsoft Intune](https://technet.microsoft.com/en-us/library/mt346013.aspx)|
|Verify you have hardware requirements for the on-premises connector|[Requirements for the On-Premises Connector](https://technet.microsoft.com/en-us/library/dn646950.aspx#BKMK_ExchanceConnectorReqs)|
|Configure a user account with permission to run the designated list of Windows PowerShell cmdlets|Powershell Cmdlets for On-Premises Exchange Connector (see below)|
Follow the steps at [Mobile device management with Exchange ActiveSync and Microsoft Intune](https://technet.microsoft.com/en-us/library/dn646988.aspx#bkmk_EX_OP) to download, install and configure the Microsoft Intune Exchange Connector.

### Step 2: Identify users who will be impacted by conditional access policy.
After the Exchange Server connector is successfully configured, it begins to inventory devices that are not yet enrolled to Intune, but are connecting to your organization’s Exchange resources using Exchange Active Sync.  To view the mobile device inventory report:

1.  Navigate to **Reports &gt; Mobile Device Inventory Reports**.

2.  Select the device groups for which you plan to roll out the conditional access policy, as well as filter by OS status.

3.  Once you’ve decided on the criteria that meets your organization’s needs, select **View Report**.

    The Report Viewer will open in a new window.

Follow the instructions at [Step 1: Evaluate the effect of the conditional access policy](https://technet.microsoft.com/en-us/library/dn705841.aspx) to identify those users who will be impacted by conditional access policy.

### Step 3: Create compliance policies and deploy to users.
Compliance policies define the rules and settings that a device must comply with in order to be considered compliant by conditional access polices. Follow the steps at [Manage device compliance policies for Microsoft Intune](https://technet.microsoft.com/en-us/library/dn705843.aspx) to create compliance policies.

> [!NOTE]
> If you want the ability to remove all corporate email from an iOS device after it is no longer part of your company, you must create and deploy an email profile and then set the compliance policy that specifies that email profiles are managed by Intune. You must deploy the email profile to the same set of users that you target with this compliance policy.
> 
> If you specify this compliance policy, a user who has already set up their email account must manually remove it and then Intune will add it back in through the registration process described in [End-user experience of conditional access](../Topic/End-user_experience_of_conditional_access.md).

After the compliance policy is created, you can deploy it by following these steps:

1.  In the **Policy** workspace on the Intune console, select the policy you want to deploy, then click **Manage Deployment**.

2.  In the **Manage Deployment** dialog box, select one or more groups to which you want to deploy the policy, then click **Add &gt; OK**.

Ensure that you have created and deployed a compliance policy to all devices that the Exchange conditional access policy will be targeted to.

Use the status summary and alerts on the **Overview** page of the **Policy** workspace to identify issues with the policy that require your attention. Additionally, a status summary appears in the **Dashboard** workspace.

> [!IMPORTANT]
> If you have not deployed a compliance policy and then enable an Exchange conditional access policy, all targeted devices will be allowed access.

### Step 4: Configure user groups for the conditional access policy.
You target conditional access policies to different groups of users depending on the policy types. These groups contain the users that will be targeted, or exempt from the policy. When a user is targeted by a policy, each device they use must be compliant in order to access email.

For the Exchange on-premises policy – to Intune user groups, you can configure these in the Groups workspace of the Intune console. You can specify two group types in each policy:

-   **Targeted groups** – User groups to which the policy is applied

-   **Exempted groups** – User groups that are exempt from the policy (optional)

If a user is in both groups, they will be exempt from the policy.
Only the groups which are targeted by the conditional access policy are evaluated for Exchange access.

### Step 5: Configure conditional access policy.
The following flow is used by conditional access policies for an Exchange on-premises environment to evaluate whether to allow or block devices.

![](../Image/ConditionalAccess8-2.png)

Follow the information provided under [Step 4: Configure the conditional access policy for Exchange on-premises ](https://technet.microsoft.com/en-us/library/dn705841.aspx) to set up your conditional access policy.

## Deployment Steps for using Exchange Online with Intune

### Step 1: Evaluate the effect of the conditional access policy.
If you have configured a connection between Intune and Exchange by using the **Microsoft Intune service to service connector**, you can use the **Mobile Device Inventory Reports** to identify EAS mail clients that will be blocked from accessing Exchange after you configure the conditional access policy.

Follow the instructions under [Step 1: Evaluate the effect of the conditional access policy](https://technet.microsoft.com/en-us/library/dn705841.aspx)

### Step 2: Create compliance policies and deploy to users.
Compliance policies define the rules and settings that a device must comply with in order to be considered compliant by conditional access polices. Follow the steps at [Manage device compliance policies for Microsoft Intune](https://technet.microsoft.com/en-us/library/dn705843.aspx) to create compliance policies.

> [!NOTE]
> If you want the ability to remove all corporate email from an iOS device after it is no longer part of your company, you must create and deploy an email profile and then set the compliance policy that specifies that email profiles are managed by Intune. You must deploy the email profile to the same set of users that you target with this compliance policy.
> 
> If you specify this compliance policy, a user who has already set up their email account must manually remove it and then Intune will add it back in through the registration process described in [End-user experience of conditional access](../Topic/End-user_experience_of_conditional_access.md).

After the compliance policy is created, you can deploy it by following these steps:

1.  In the **Policy** workspace on the Intune console, select the policy you want to deploy, then click **Manage Deployment**.

2.  In the **Manage Deployment** dialog box, select one or more groups to which you want to deploy the policy, then click **Add &gt; OK**.

Ensure that you have created and deployed a compliance policy to all devices that the Exchange conditional access policy will be targeted to.

Use the status summary and alerts on the **Overview** page of the **Policy** workspace to identify issues with the policy that require your attention. Additionally, a status summary appears in the **Dashboard** workspace.

> [!IMPORTANT]
> If you have not deployed a compliance policy and then enable an Exchange conditional access policy, all targeted devices will be allowed access.

### Step 3: Configure user groups for the conditional access policy.
You target conditional access policies to different groups of users depending on the policy types. These groups contain the users that will be targeted, or exempt from the policy. When a user is targeted by a policy, each device they use must be compliant in order to access email.

For the Exchange Online policy – to Azure Active Directory security user groups. You can configure these groups in the **Office 365 admin center**, or the **Intune account portal**. You can specify two group types in each policy:

-   **Targeted groups** – User groups to which the policy is applied

-   **Exempted groups** – User groups that are exempt from the policy (optional)

If a user is in both groups, they will be exempt from the policy.
Only the groups which are targeted by the conditional access policy are evaluated for Exchange access.

### Step 4: Configure conditional access policy.
The following flow is used by conditional access policies for Exchange Online to evaluate whether to allow or block devices.

![](../Image/ConditionalAccess8-1.png)

Follow the information provided under [Step 4: Configure the conditional access policy for Exchange Online ](https://technet.microsoft.com/en-us/library/dn705841.aspx) to set up your conditional access policy.

## Reporting

### Monitor the compliance and conditional access policies
To view devices that are blocked from Exchange:

1.  On the Intune dashboard, click the **Blocked Devices from Exchange** tile to show the number of blocked devices and links to more information.

### View devices that do not conform to a compliance policy

1.  In the Intune administration console, click **Groups**.

2.  Open the **Policy** tab for any device that is compatible with compliance policies.

3.  From the **Filters** drop-down list, select **Does not conform to compliance policy**.

When conflicts occur due to multiple Intune settings being applied to a device, the following rules apply:

-   If the conflicting settings are from an Intune configuration policy and a compliance policy, the settings in the compliance policy take precedence over the settings in the configuration policy, even if the settings in the configuration policy are more secure.

-   If you have deployed multiple compliance policies, the most secure of these policies will be used.

## See Also
[Use conditional access with Intune and Configuration Manager](../Topic/Use_conditional_access_with_Intune_and_Configuration_Manager.md)
[End-user experience of conditional access](../Topic/End-user_experience_of_conditional_access.md)

