---
# required metadata

title: Multi-factor authentication for Intune device enrollment
titlesuffix: "Azure portal"
description: How to require multi-factor authentication in Azure AD for device enrollment.
keywords:
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 94280c73-c05c-4e72-b0dd-a7cb997782f9

# optional metadata

ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: damionw
#ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---

# Multi-factor authentication for Intune device enrollments

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune can use Azure Active Directory (AD) multi-factor authentication (MFA) for device enrollment to help you secure your corporate resources.

MFA works by requiring any two or more of the following verification methods:

- Something you know (typically a password or PIN).
- Something you have (a trusted device that is not easily duplicated, like a phone).
- Something you are (biometrics, like a fingerprint).

MFA is supported for iOS, Android, Windows 8.1 or later, Windows Phone 8.1, or Windows 10 Mobile or later devices.

When you enable MFA, end users must supply two forms of credentials to enroll a device.

## Configure Intune to require multi-factor authentication at device enrollment

To require MFA when a device is enrolled, follow these steps:

>[!Important]
>Do not configure **Device based access rules** for Microsoft Intune enrollment.

1. Sign in to your [Microsoft Azure portal](https://portal.azure.com) with your credentials.
2. In the portal, choose **Azure Active Directory**.
2. In **Azure Active Directory**, choose **Manage** > **Enterprise applications**.
3. In **Enterprise applications**, choose **Manage** > **All applications**. You see a list of all Azure apps that you manage.
3. From the list, choose **Microsoft Intune enrollment**.
4. In **Microsoft Intune Enrollment**, choose **Security** > **Conditional access**.
5. Choose **New policy**.
6. In **New** policy, type a descriptive name for the policy.
7. In the **Assignments** section, choose **Users and groups**.
8. In **Users and groups**, choose the users or groups that will receive this policy, then choose **Done**.
9. In the **Assignments** section, choose **Cloud apps**.
10. On the **Include** tab of **Cloud apps**, choose **Select apps**, then choose **Select** > **Microsoft Intune Enrollment**, and then choose **Done**.
11. In the **Assignments** section, choose **Conditions**.
12. In **Conditions**, you do not need to configure any settings for MFA.
13. In the **Access controls** section, choose **Grant**.
14. In **Grant**, choose **Grant access**, and then select **Require multi-factor authentication**.
	Do not select **Require device to be marked as compliant** because a device cannot be evaluated for compliance until it is enrolled.
15. Choose **Select**.
16. In **New policy**, choose **Enable policy** > **On**, and then choose **Create**.



## Next steps

When end users enroll their device, they now must authenticate with a second form of identification, like a PIN, a phone, or biometrics.
