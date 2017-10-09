---
# required metadata

title: Protect SharePoint Online 
description: Protect and control access to company data on SharePoint Online by using conditional access.
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: b088e5a0-fd4a-4fe7-aa49-cb9c8cfb1585ROBOTS: NOINDEX,NOFOLLOW

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: chrisgre
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Protect access to SharePoint Online with Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Use Microsoft Intune conditional access to control access to files that are located on SharePoint Online.
Conditional access has two components:
- A device compliance policy that the device must comply with in order to be considered compliant.
- A conditional access policy where you specify the conditions that the device must meet in order to access the service.
To learn more about how conditional access works, read the [Protect access to email, O365, and other services](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) topic.

You deploy the compliance and conditional access policies to users. Any device that a user uses to access the services is checked for compliance with the policies.

When a user attempts to connect to a file by using a supported app such as OneDrive on their device, the following evaluation occurs:

![Diagram that shows the decision points that determine whether a device is allowed access to SharePoint or is blocked](../media/ConditionalAccess8-6.png)


**Before** configuring a conditional access policy for SharePoint Online, you must:
- Have a **SharePoint Online subscription**, and users must be licensed for SharePoint Online.
- Have an **Enterprise Mobility + Security (EMS) subscription** or an **Azure Active Directory (Azure AD) Premium subscription**, and users must be licensed for EMS or Azure AD. For more details, see the [Enterprise Mobility pricing page](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) or the [Azure Active Directory pricing page](https://azure.microsoft.com/pricing/details/active-directory/).


  To connect to the required files, a device must be:
-   **Enrolled** with Intune or a domain-joined PC.

-   **Registered** in Azure Active Directory (this happens automatically when the device is enrolled with Intune).


-   **Compliant** with any deployed Intune compliance policies.

The device state is stored in Azure Active Directory, which grants or blocks access to the files, based on the conditions that you specify.

If a condition isn't met, the user sees one of the following messages when they sign in:

-   If the device isn't enrolled with Intune or isn't registered in Azure Active Directory, a message is displayed with instructions about how to install the Company Portal app and enroll.

-   If the device isn't compliant, a message is displayed that directs the user to the Intune Company Portal website, where they can find information about the problem and how to remediate it.

**Conditional access doesn't apply to external sharing**. To learn how to prevent external sharing in your tenant or site collection, see [Manage external sharing for your SharePoint Online environment](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85).

>[!NOTE]
>If you enable conditional access for SharePoint Online, we recommend that you disable the domain on the list, as described in the [Remove-SPOTenantSyncClientRestriction](https://technet.microsoft.com/library/dn917451.aspx) topic.  

## Support for mobile devices
The following are supported:
- iOS 8.0 and later
- Android 4.0 and later, Samsung Knox Standard 4.0 or later
- Windows Phone 8.1 and later

You can protect access to SharePoint Online when **iOS** and **Android** devices access it from a browser. Access is only allowed from supported browsers on compliant devices:
* Safari (iOS)
* Chrome (Android)
* Intune Managed Browser (iOS and Android 5.0 and later)

**Unsupported browsers are blocked**.

## Support for PCs
The following are supported:
- Windows 8.1 and later (when PCs are enrolled with Intune)
- Windows 7.0, Windows 8.1, or Windows 10 (when PCs are domain joined),
> [!NOTE]
>To use conditional access with Windows 10 PCs, you must update those PCs with the Windows 10 Anniversary Update.

  - You must set up domain-joined PCs to [automatically register](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access-automatic-device-registration/) with Azure Active Directory. The Azure AD Device Registration service will be activated automatically for Intune and Office 365 customers. Customers who have already deployed the ADFS Device Registration service will not see registered devices in on-premises Active Directory.

  - If the policy is set to require a domain join and the PC isn't domain joined, a message is displayed to contact the IT admin.

  - If the policy is set to require a domain join or compliance, and the PC doesn't meet either requirement, a message is displayed with instructions about how to install the Company Portal app and enroll.
  >[!NOTE]
  >Conditional access is not supported on PCs that are running the Intune computer client.

[Office 365 modern authentication must be enabled](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) and have all the latest Office updates.

Modern authentication brings sign-in based on Active Directory Authentication Library (ADAL) to Office 2013 Windows clients and enables better security, like **multi-factor authentication** and **certificate-based authentication**.


## Configure conditional access for SharePoint Online

### Step 1: Configure Active Directory security groups
Before you start, configure Azure Active Directory security groups for the conditional access policy. You can configure these groups in the **Office 365 admin center** or in the **Intune account portal**. You use these groups to target or exempt users from the policy. When a user is targeted by a policy, each device that they use must be compliant in order to access resources.

You can specify two group types in a SharePoint Online policy:

-   **Targeted groups**: Contains groups of users that the policy applies to.

-   **Exempted groups**: Contains groups of users that are exempt from the policy.

If a user is in both groups, they are exempt from the policy.

### Step 2: Configure and deploy a compliance policy
If you haven't already done so, create a compliance policy, and deploy it to the users that the SharePoint Online policy targets.

> [!NOTE]
> While compliance policies are deployed to Intune groups, conditional access policies are targeted to Azure Active Directory security groups.

For details about how to configure the compliance policy, see [Create a compliance policy](create-a-device-compliance-policy-in-microsoft-intune.md).

> [!IMPORTANT]
> If you haven't deployed a compliance policy, the devices are treated as compliant.

When you're ready, continue to **Step 3**.

### Step 3: Configure the SharePoint Online policy
Next, configure the policy to require that only managed and compliant devices can access SharePoint Online. This policy is stored in Azure Active Directory.

#### <a name="bkmk_spopolicy"></a>

>[!NOTE]
> You can also create a conditional access policy for Intune devices in the Azure AD management console (the policy is referred to as the **device-based conditional access policy** in Azure AD). In addition, you can create other conditional access policies like multi-factor authentication. You can also set conditional access policies for third-party enterprise apps that Azure AD supports, like Salesforce and Box. For more details, see [How to set Azure Active Directory device-based conditional access policy for access control to Azure Active Directory connected applications](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access-policy-connected-applications/).


1.  In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Policy** > **Conditional Access** > **SharePoint Online Policy**.
![Screenshot of the SharePoint Online Policy page](../media/mdm-ca-spo-policy-configuration.png)

2.  Select **Enable conditional access policy for SharePoint Online**.

3.  Under **Application access**, you can choose to apply the conditional access policy to:

    -   **All platforms**

        This requires that any device used to access **SharePoint Online** is enrolled in Intune and is compliant with the policies. Any client application that uses **modern authentication** is subject to the conditional access policy. If the platform isn't currently supported by Intune, access to **SharePoint Online** is blocked.

        Selecting the **All platforms** option means that Azure Active Directory applies this policy to all authentication requests, regardless of the platform that is reported by the client application. All platforms are required to be enrolled and become compliant, except for:
        *	Windows devices, which are required to be enrolled and compliant, domain joined with on-premises Active Directory, or both.
	    * Unsupported platforms like Mac. However, apps using modern authentication that come from these platforms are still blocked.

    -   **Specific platforms**

         The conditional access policy applies to any client app that is using modern authentication on the platforms that you specify.

     For Windows PCs, a PC must either be domain joined, or enrolled with Intune and compliant. You can set the following requirements:

     -   **Devices must be domain joined or compliant.** Choose this option to require that PCs must either be domain joined or compliant with the policies that are set in Intune. If a PC doesn't meet either of these requirements, the user is prompted to enroll the device with Intune.

     -   **Devices must be compliant.** Choose this option to require that PCs must be enrolled in Intune and compliant. If a PC isn't enrolled, a message with instructions on how to enroll is displayed.

4.   Under **Browser access** to SharePoint Online and OneDrive for Business, you can choose to allow access to Exchange Online only through the supported browsers: Safari (iOS) and Chrome (Android). Access from other browsers is blocked. The same platform restrictions that you selected for Application access for OneDrive also apply here.

  On **Android** devices, users must enable browser access. To do this, a user must choose the **Enable Browser Access** option on the enrolled device as follows:
  1.	Open the **Company Portal** app.
  2.	Go to the **Settings** page from the ellipsis (…) or hardware menu button.
  3.	Press the **Enable Browser Access** button.
  4.    In the Chrome browser, sign out of Office 365 and restart Chrome.

  On **iOS** and **Android** platforms, to identify the device that is used to access the service, Azure Active Directory issues a Transport Layer Security (TLS) certificate to the device. The device displays the certificate with a prompt to the user to select the certificate, as shown in the following screenshots. The user must select this certificate before they can use the browser.

  **iOS**

  ![Screenshot of the certificate prompt on an iPad](../media/mdm-browser-ca-ios-cert-prompt.png)

  **Android**

  ![Screenshot of the certificate prompt on an Android device](../media/mdm-browser-ca-android-cert-prompt.png)
5.  Under **Targeted Groups**, choose **Modify** to select the Azure Active Directory security groups that the policy applies to. You can choose to target this to all users or just a select group of users.

6.  Under **Exempted Groups**, optionally, choose **Modify** to select the Azure Active Directory security groups that are exempt from this policy.

7.  When you're done, choose **Save**.

You don't have to deploy the conditional access policy—it takes effect immediately.

### Step 4: Monitor the compliance and conditional access policies
In the **Groups** workspace, you can view the status of your devices.

Select any mobile device group. Then, on the **Devices** tab, choose one of the following **Filters**:

-   **Devices that are not registered with AAD**. These devices are blocked from SharePoint Online.

-   **Devices that are not compliant**. These devices are blocked from SharePoint Online.

-   **Devices that are registered with AAD and compliant**. These devices can access SharePoint Online.

### See also
[Protect access to email and O365 services with Microsoft Intune](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)
