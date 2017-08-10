---
# required metadata

title: Multi-factor authentication for Intune device enrollment
titleSuffix: "Intune on Azure"
description: How to require multi-factor authentication in Azure AD for device enrollment.
keywords:
author: nathbarn
ms.author: nathbarn
manager: angerobe
ms.date: 08/10/2017
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
>Do not configure **Device based access rules** for Microsoft Intune Enrollment.

1. Sign in to your [Microsoft Azure portal](https://portal.azure.com) with your credentials.
2. In the portal, choose **Azure Active Directory**.
2. On the **Azure Active Directory** blade, choose **Manage** > **Enterprise applications**.
3. On the **Enterprise applications** blade, choose **Manage** > **All applications**. You'll see a list of all Azure apps that you manage.
3. From the list, choose **Microsoft Intune enrollment**.
4. On the **Microsoft Intune Enrollment** blade, choose **Security** > **Conditional access**.
5. On the next blade, choose **New policy**.
6. On the **New** policy blade, enter a descriptive name for the policy.
7. In the **Assignments** section, choose **Users and groups**.
8. On the **Users and groups** blade, choose the users or groups that will receive this policy, then choose **Done**.
9. In the **Assignments** section, choose **Cloud apps**.
10. On the **Include** tab of the **Cloud apps** blade, choose **Select apps**, then choose **Select** > **Microsoft Intune Enrollment**, and then choose **Done**. If the app is already selected, close the blade.
11. In the **Assignments** section, choose **Conditions**.
12. On the **Conditions** blade, you do not need to configure any settings for MFA.
13. In the **Access controls** section, choose **Grant**.
14. On the **Grant** blade, choose **Grant access**, and then select **Require multi-factor authentication**.
	Do not select **Require device to be marked as compliant** because a device cannot be evaluated for compliance until it is enrolled.
15. Choose **Select**.
16. On the **New policy** blade, choose **Enable policy** > **On**, and then choose **Create**.



## Next steps

When end users enroll their device, they now must authenticate with a second form of identification, like a PIN, a phone, or biometrics.
