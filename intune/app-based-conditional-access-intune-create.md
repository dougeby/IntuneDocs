---
# required metadata

title: App based conditional access policy with Intune
description: This topic describes how you can configure an app-based conditional access policy with Intune.
keywords:
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: d1693515-de18-4553-91ef-801976cd3ec7

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: chrisgre
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Set up app-based conditional access policies

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

This topic provides instructions on how to set up app-based conditional access policies for apps that are part of the list of approved apps. The list of approved apps consists of apps that were tested by Microsoft.

> [!IMPORTANT]
> This topic walks through the steps to add an app-based conditional access policy using Exchange Online, but you can use the same steps when adding other apps like SharePoint Online, Microsoft Teams, etc. from the list of approved apps.

## To create an app-based conditional access policy
1.  Go the [Azure portal](https://portal.azure.com) and sign in with your credentials.

2.  Choose **More services**, and type: "Intune".

3.  Choose **Intune App Protection**.

4.  On the **Intune mobile application management** blade choose **All Settings**.

5.  On the **Conditional access** section, choose **Exchange Online**.

	![Screenshot of the settings blade showing the conditional access section wiht Exchange Online option highlighted](./media/MAM-conditional-access-1.png)

6. On the **Allowed apps** blade, choose the **Allow apps that support Intune app policies** option to allow only apps that are supported by Intune app protection policies to have the ability to access Exchange Online. When you select this option, the list of supported apps is displayed.

	> [!NOTE]
	> All Exchange Active Sync mail clients, including the built-in mail clients on iOS and Android that connect to Exchange Online, will be prevented from sending or receiving email. Users will instead receive a single email informing them that they need to use the Outlook mail app.

7. To apply this policy to users, open the **Restricted user groups** blade, and choose **Add user group**. Select one or more user groups that should get this policy.

	![Screenshot of the restricted user group blade with add user group option highlighted](./media/mam-ca-add-user-group.png)

8. You may want some users in the user group you selected in the previous step not to be affected by this policy. In such cases, add the group of users to the exempted user groups list. From the **Exchange Online** blade, choose **Exempted user groups**. Choose **Add user group** to open the list of user groups. Select the groups you want to exempt from this policy.

## To modify or delete user groups from an existing app-based CA policy

1. Open the **Restricted user groups** blade, then highlight the user group you want to delete.
2. Click on the ellipse to see the delete options.
3. Choose **Delete** to remove the user group from the list.

## Create app-based conditional access policies in Azure AD workload

Beginning with Intune 1708 release, IT admins can create app-based conditional access policies from the Azure AD workload. This gives convenience so you don't need to switch between the Azure and the Intune workloads.

> [!IMPORTANT]
> You need to have an Azure AD Premium license to create Azure AD conditional access policies from the Intune Azure portal.

### To create an app-based conditional access policy

> [!IMPORTANT]
> You need to have [Intune app protection policies](app-protection-policies.md) applied to your apps before using app-based conditional access policies.

1. In the **Intune Dashboard**, choose **Conditional access**.

2. In the **Policies** blade, choose **New policy** to create your new app-based conditional access policy.

4. Once you enter a policy name and configure the settings available in the **Assignments** section, then choose **Grant** under the **Access controls** section.

5. Choose **Require approved client app**, choose **Select**, then choose **OK** to save the new policy.

## Next steps
[Block apps that do not have modern authentication](app-modern-authentication-block.md)

### See also

[Protect app data with app protection policies](app-protection-policies.md)
[Conditional Access in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)
