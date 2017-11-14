---
# required metadata

title: Apply conditional access policies to Jamf-managed devices
titlesuffix: "Azure portal"
description: "Use conditional access to help secure Jamf-managed devices."
keywords:
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/14/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: c87fd2bd-7f53-4f1b-b985-c34f2d85a7bc

# optional metadata

#ROBOTS: NOINDEX, NOFOLLOW
#audience:
#ms.devlang:
ms.reviewer: elocholi
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---

# Assign conditional access policies to Macs with Jamf Pro

[!INCLUDE][azure_portal](/includes/azure_portal.md)]

[!INCLUDE][macos-preview-1708](/intune-user-help/includes/macos-preview-1708.md]

You can use Azure Active Directory and Microsoft Intune's conditional access policies ensure that your end users are compliant with organizational requirements. You can apply these policies to Macs that are [managed with Jamf Pro](conditional-access-integrate-jamf.md). This requires access to both the Intune and Jamf Pro consoles.

## Set up device compliance policies in Intune

1. Open Microsoft Azure, then navigate to **Intune** > **Device Compliance** > **Policies**. You can create policies for macOS, including choosing a series of actions (e.g., sending warning emails) to noncompliant users and groups.
2. Search for your desired groups, then apply the policies to them.

## Require the Company Portal app for macOS

1. Go to https://aka.ms/macoscompanyportal to download the current version of the Company Portal app for macOS.
2. Open Jamf Pro, then navigate to **Computer management** > **Packages**.
3. Create a new package with the Company Portal app for macOS, then click **Save**.
4. Open **Computers** > **Policies**, then select **New**.
5. Use the **General** payload to configure settings for the policy, including the trigger and execution frequency.
6. Select the **Packages** payload and click **Configure**.
7. Click **Add** to select the package with the Company Portal app.
8. Choose **Install** from the **Action** pop-up menu.
9. Configure the settings for the package.
10. Click the **Scope** tab to specify on which computers the Company Portal app should be installed. Click **Save**. The policy will run scoped devices the next time the selected trigger occurs on the computer and meets the criteria in the **General** payload.

## Direct your users to register Jamf Pro-managed devices with Azure Active Directory

> [!NOTE]
> You need to [deploy the Company Portal](conditional-access-assign-jamf.md#require-the-company-portal-app-for-macos) for macOS before going through the next steps.  

End users need to launch the Company Portal app as a Jamf Self Service policy to register the device with Azure AD as a device managed by Jamf Pro. If not, the user will only be registered with Azure AD.

1. In Jamf Pro, navigate to **Computers** > **Policies**, and create a new policy for device registration.
2. Configure the **Conditional Access** payload, including the trigger and execution frequency. Set the priority to **After**.
3. Click the **Scope** tab, and scope the policy to all targeted devices.
4. Click the **Self Service** tab to make the policy available in Jamf Self Service. Include the policy in the **Device Compliance** category. Click **Save**.
