---
# required metadata

title: Protect Dynamics CRM Online 
description: Protect and control access to Dynamics CRM online with  conditional access.
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f1c4522b-5a34-4f5a-89d2-7809c4352af7

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: chrisgre
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Protect access to Dynamics CRM Online with Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

You can control access to Microsoft Dynamics CRM Online from iOS and Android devices by using Microsoft Intune conditional access.  Intune conditional access has two components:
* A [device compliance policy](introduction-to-device-compliance-policies-in-microsoft-intune.md) that the device must comply with in order to be considered compliant.
* A [conditional access policy](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) where you specify the conditions that the device must meet in order to access the service.

To learn more about how conditional access works, read the [protect access to email, 0365, and other services](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) article.

> [!IMPORTANT]
> To deploy conditional access, you must have subscriptions for Intune and Azure Active Directory Premium, and users must be licensed for both products. The **Enterprise Mobility + Security (EMS) subscription** includes both Intune and Azure Active Directory Premium subscriptions. For more details, see the [Enterprise Mobility pricing page](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing). If you don't have the EMS subscription, you can get a subscription for Azure Active Directory Premium. See the [Azure Active Directory pricing page](https://azure.microsoft.com/pricing/details/active-directory/).

When a targeted user attempts to use the Dynamics CRM app on their device, the following evaluation occurs:

![Diagram that shows the decision points that are used to determine whether a device is allowed access to a service or is blocked](../media/mdm-ca-dynamics-crm-flow-diagram.png)

The device that needs access to Dynamics CRM Online must be:
* An **Android** or **iOS** device.
* **Enrolled** with Intune.
* **Compliant** with any deployed Intune compliance policies.

The device state is stored in Azure Active Directory, which grants or blocks access based on the conditions that you specify.

If a condition is not met, the user is presented with one of the following messages when they sign in:
* If the device is not enrolled with Intune or is not registered in Azure Active Directory, a message is displayed with instructions about how to install the Company Portal app and enroll.
* If the device is not compliant, a message is displayed that directs the user to the Microsoft Intune Company Portal website or Company Portal app, where they can find information about the problem and how to remediate it.

## Configure conditional access for Dynamics CRM Online  
### Step 1: Configure Active Directory security groups

Before you start, configure Azure Active Directory security groups for the conditional access policy. You can configure these groups in the **Office 365 admin center**. You use these groups to target or exempt users from the policy. When a user is targeted by a policy, each device they use must be compliant in order to access resources.

You can specify two group types to use for the Dynamics CRM policy:
* **Targeted groups**. Contains groups of users that the policy applies to.
* **Exempted groups**. Contains groups of users that are exempt from the policy.

If a user is in both groups, they are exempt from the policy.

### Step 2: Configure and deploy a compliance policy
[Create](create-a-device-compliance-policy-in-microsoft-intune.md) a compliance policy and [deploy](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md) it to all devices that will be affected by the policy. These are all the devices that are used by the users in the Targeted groups.

> [!NOTE]
> While compliance policies are deployed to Intune groups, conditional access policies are targeted to Azure Active Directory security groups.

> [!IMPORTANT]
> If you have not deployed a compliance policy, the devices will be treated as compliant.

When you are ready, continue to Step 3.
### Step 3: Configure the Dynamics CRM policy
Next, configure the policy to require that only managed and compliant devices can access Dynamics CRM. This policy will be stored in Azure Active Directory.

1.  In the Intune administration console, choose **Policy > Conditional Access > Dynamics CRM Online Policy**.

  ![Screenshot of the Dynamics CRM Online conditional access policy page](../media/mdm-ca-dynamics-crm-policy-configuration.png)

2.  Choose the **Enable conditional access** policy.
3.  Under **Application access**, you can choose to apply conditional access policy to:
  * **iOS**
  * **Android**
4.  Under **Targeted Groups**, choose **Modify** to select the Azure Active Directory security groups that the policy will apply to. You can choose to target this to all users or just a select group of users.
5.	Under **Exempted Groups**, optionally, choose **Modify** to select the Azure Active Directory security groups that are exempt from this policy.
6.	When you are done, choose **Save**.

You have now configured conditional access for Dynamics CRM. You do not have to deploy the conditional access policy—it takes effect immediately.
##  Monitor the compliance and conditional access policies

In the **Groups** workspace, you can view the conditional access status of your devices.

Choose any mobile device group and then, on the **Devices** tab, choose one of the following **Filters**:
* **Devices that are not registered with AAD**. These devices are blocked from Dynamics CRM.
* **Devices that are not compliant**. These devices are blocked from Dynamics CRM.
* **Devices that are registered with AAD and compliant**. These devices can access Dynamics CRM.

##  Next steps
* [Protect access to Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md)

* [Protect access to Exchange on-premises](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
* [Protect access to SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)

* [Protect access to Skype for Business Online](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
