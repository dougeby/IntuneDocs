---
# required metadata

title: Create and deploy Windows Information Protection (WIP) app protection policy with Intune
titlesuffix: "Azure portal"
description: "Create and deploy WIP app protection policy with Intune"
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 4e3627bd-a9fd-49bc-b95e-9b7532f0ed55

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: joglocke
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Create and deploy Windows Information Protection (WIP) app protection policy with Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Beginning with Intune 1704 release, you can use app protection policies with Windows 10 in to protect apps without device enrollment.

## Before you begin

Let’s talk about a few concepts when adding a WIP policy.

### List of allowed and exempt apps

-   **Allowed apps:** These are the apps that need to adhere to this policy.

-   **Exempt apps:** These apps are exempt from this policy and can access corporate data without restrictions.

### Types of apps

-   **Recommended apps:** a pre-populated list of (mostly Microsoft Office) apps that allow you easily import into policy. <!---I really don't know what you mean by "easily import into policy"--->

-   **Store apps:** You can add any app from the Windows store to the policy.

-   **Windows desktop apps:** You can add any traditional Windows desktop apps to the policy (for example, .exe, .dll)

## Pre-requisites

You need to configure the MAM provider before you can create a WIP app protection policy. Learn more about [how to configure your MAM provider with Intune](https://docs.microsoft.com/app-protection-policies-configure-windows-10.md).

Additionally, you need to have the following:

-   [Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) license.
-   [Windows Creators Update](https://blogs.windows.com/windowsexperience/2017/04/11/how-to-get-the-windows-10-creators-update/#o61bC2PdrHslHG5J.97)

> [!IMPORTANT]
> WIP does not support multi-identity, only one managed identity can exist at a time.
<!---Should you be linking to a topic that explains what multi-identity is?--->

## To add a WIP policy

After you set up Intune in your organization, you can create a WIP-specific policy through the [Azure portal](https://docs.microsoft.com/intune-classic/deploy-use/azure-portal-for-microsoft-intune-mam-policies). <!---Is there an azure topic you can use instead of a classic? if not, should this topic be moved into the azure docset?--->

1.  Go to the **Intune mobile application management dashboard**, choose **All settings**, > **App policy**.

2.  In the **App policy** blade, choose **Add a policy**, then enter the following values:

    a.  **Name:** Type a name (required) for your new policy.

    b.  **Description:** Type an optional description.

    c.  **Platform:** Choose **Windows 10** as the supported platform for your app protection policy.

    d.  **Enrollment state:** Choose **Without enrollment** as the enrollment state for your policy.

3.  Choose **Create**. The policy is created and appears in the table on the **App Policy** blade.

## To add recommended apps to your allowed apps list

1.  From the **App policy** blade, choose the name of your policy, then choose **Allowed apps** from the **Add a policy** blade. The **Allowed apps** blade opens, showing you all apps that are already included in the list for this app protection policy.

2.  From the **Allowed apps** blade, choose **Add apps**. The **Add apps** blade opens, showing you all apps that are part of this list.

3.  Select each app you want to access your corporate data, and then choose **OK**. The **Allowed apps** blade gets updated showing you all selected apps.

## Add a Store app to your allowed apps list

**To add a Store app**

1.  From the **App policy** blade, choose the name of your policy, then choose **Allowed apps** from the menu that appears showing all apps that are already included in the list for this app protection policy.

2.  From the **Allowed apps** blade, choose **Add apps**.

3.  On the **Add apps** blade, choose **Store apps** from the dropdown list. The blade changes to show boxes for you to add a **publisher** and app **name**.

4.  Type the name of the app and the name of its publisher, and then choose **OK**.

	> [!TIP]
	> Here’s an app example, where the **Publisher** is *CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US* and the Product **name** is *Microsoft.MicrosoftAppForWindows*.

5.  After you’ve entered the info into the fields, choose **OK** to add the app to your **Allowed apps** list.

> [!NOTE]
> To add multiple Store apps at the same time, you can click the menu **(…)** at the end of the app row, then continue to add more apps. Once you’re done, choose **OK**.

## Add a desktop app to your allowed apps list

**To add a desktop app**

1.  From the **App policy** blade, choose the name of your policy, and then choose **Allowed apps.** The **Allowed apps** blade opens showing you all apps that are already included in the list for this app protection policy.

2.  From the **Allowed apps** blade, choose **Add apps**.

3.  On the **Add apps** blade, choose **Desktop apps** from the drop-down list.

4.  After you entered the info into the fields, choose **OK** to add the app to your **Allowed apps** list.

> [!NOTE]
> To add multiple **desktop apps** at the same time, you can click the menu **(…)** at the end of the app row, then continue to add more apps. Once you’re done, choose **OK**.

## WIP Learning
<!---You've already defined WIP earlier in the topic. You don't need to keep doing so. --->
After you add the apps you want to protect with WIP, you need to apply a protection mode by using **WIP Learning**.

### Before you begin

WIP Learning is a report that allows you to monitor your WIP-unknown apps. The unknown apps are the ones not deployed by your organization’s IT department. You can export these apps from the report and add them to your WIP policies to avoid productivity disruption before they enforce WIP in “Hide Override” mode.

We recommend that you start with **Silent** or **Allow Overrides** while verifying with a small group that you have the right apps on your allowed apps list. After you're done, you can change to your final enforcement policy, **Hide Overrides**.

### What are the protection modes?

#### Hide Overrides
WIP looks for inappropriate data sharing practices and stops the user from completing the action. This can include sharing info across non-corporate-protected apps, and sharing corporate data between other people and devices outside of your organization.

#### Allow Overrides
WIP looks for inappropriate data sharing, warning users if they do something deemed potentially unsafe. However, this mode lets the user override the policy and share the data, logging the action to your audit log.

#### Silent
WIP runs silently, logging inappropriate data sharing, without blocking anything that would have been prompted for employee interaction while in Allow Override mode. Unallowed actions, like apps inappropriately trying to access a network resource or WIP-protected data, are still stopped.

#### Off (not recommended)
WIP is turned off and doesn't help to protect or audit your data.

After you turn off WIP, an attempt is made to decrypt any WIP-tagged files on the locally attached drives. Be aware that your previous decryption and policy info isn’t automatically reapplied if you turn WIP protection back on.

### Add a protection mode

1.  From the **App policy** blade, choose the name of your policy, then chose **Required settings**.

	![Learning Mode screen-shot](./media/learning-mode-sc1.png)

1.  Choose **Save**.

### Use WIP Learning

1. Go to the Azure Dashboard. <!---since they're changing from Intune MAM to Intune proper, a screenshot might be helpful.--->

2. Choose **More services** from the left menu, then type **Intune** in the text box filter.

3. Choose **Intune**, the **Intune dashboard** opens, choose **Mobile Apps**.

4. Choose **WIP Learning** under **Monitor**. You see the unknown apps logged by the WIP Learning.

> [!IMPORTANT]
> Once you have the apps showing up in the WIP Learning logging report, you can them into your app protection policies.

## Deploy your WIP app protection policy

> [!IMPORTANT]
> This applies for WIP without device enrollment.

<!---not sure why you need the Important note. Isn't this what the topic is about? app protection w/o enrollment?--->

After you created your WIP app protection policy, you need to deploy it to your organization using MAM.

1.  On the **App policy** blade, choose your newly-created app protection policy, choose **User groups** > **Add user group**.

	A list of user groups, made up of all the security groups in your Azure Active Directory, opens in the **Add user group** blade.

1.  Choose the group you want your policy to apply to, then choose **Select** to deploy the policy.
