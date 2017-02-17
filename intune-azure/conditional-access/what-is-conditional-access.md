---
# required metadata

title: What is conditional access? | Intune Azure preview | Microsoft Docs
description: "Intune Azure preview: Learn how to define the conditions users and devices must meet to access company resources in Microsoft Intune Azure preview."
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: a1973f38-ea55-43eb-a151-505fb34a8afb

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# What is conditional access?


[!INCLUDE[azure_preview](../includes/azure_preview.md)]


In this topic we will describe conditional access as it is applies to Enterprise Mobility + Security, and follow that with conditional access capabilities in Intune.

Conditional access from Enterprise Mobility + Security (EMS) harnesses the power of Azure Active Directory Premium and Microsoft Intune to provide the control you need to keep your corporate data secure, while giving your people an experience that allows them to do their best work from any device.

With conditional access, you can define conditions that limit access to your corporate data based on location, device and user state, and application sensitivity.

From the device perspective, Intune and Azure Active Directory work together to make sure only managed and compliant devices are allowed access to email and Office 365 services. For example, you can set a policy in Azure Active Directory to only enable computers that are domain-joined, or mobile devices that are enrolled in a mobile device management application like Intune, to have the ability to access Office 365 services. You can use to Intune to set a device compliance profile that evaluates the compliance status of the device. The compliance status is reported to Azure Active Directory to use for enforcement of the policy in Azure Active Directory when the user tries to access your company resources. To learn about device compliance in Intune, see [What is device compliance?](/intune-azure/set-device-compliance/what-is-device-compliance)

Conditional access for cloud apps such as Exchange Online can be configured through Azure Active Directory. For more information, see this [article](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-conditional-access-azure-portal).

## On-premises conditional access in Intune

Conditional access in Intune can be used to allow or block access to **Exchange on-premises** based on device management and enrollment.

Device compliance profile settings are used to evaluate the compliance of the device. Conditional access uses the evaluation to allow or block access to Exchange on-premises. When conditional access is used in combination with a device compliance profile, only compliant devices are allowed access to Exchange on-premises. You can configure advanced settings in conditional access for more granular control such as: allow or block certain platforms, or immediately block devices that are not managed by Intune.

The device compliance profile and conditional access are assigned to the user. Any device that the user uses to access Exchange on-premises is checked for compliance. Keep in mind that the user who is using the device must have a compliance profile assigned to them in order for the device to be evaluated for compliance. If no compliance policy is deployed to the user, the device is treated as compliant and no access restrictions are applied.

When devices do not meet the conditions set, the end user is guided through the process of enrolling the device and fixing the issue that is making the device noncompliant.

## Next steps

[How to create a conditional access policy for Exchange on-premises](create-conditional-access-policy-for-exchange-on-premises.md)

[How to configure conditional access in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-conditional-access-azure-portal)
