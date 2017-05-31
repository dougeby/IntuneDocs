---
# required metadata

title: App based conditional access policy for Exchange Online with Intune | Microsoft Docs
description: This topic describes how you can configure an app-based conditional access policy for Exchange Online with Intune.
keywords:
author: andredm7ms.author: andredmmanager: angrobe
ms.date: 05/31/2017
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

# Set up app-based conditional access policies for Exchange Online

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

This topic gives you step-by-step instructions on how to set up conditional access for Exchange Online to only allow mobile apps that support Intune app protection policies.


## To create an app-based conditional access policy
1.  Go the [Azure portal](https://portal.azure.com) and sign in with your credentials.

2.  Choose **More services**, and type: "Intune".

3.  Choose **Intune App Protection**.

4.  On the **Intune mobile application management** blade choose **All Settings**.

5.  On the **Conditional access** section, choose **Exchange Online**.

	![Screenshot of the settings blade showing the conditional access section wiht Exchange Online option highlighted](../media/MAM-conditional-access-1.png)

6. On the **Allowed apps** blade, choose the **Allow apps that support Intune app policies** option to allow only apps that are supported by Intune app protection policies to have the ability to access Exchange Online. When you select this option, the list of supported apps is displayed.

	>[!NOTE]
	>All Exchange Active Sync mail clients, including the built-in mail clients on iOS and >Android that connect to Exchange Online, will be prevented from sending or receiving >email. Users will instead receive a single email informing them that they need to use the >Outlook mail app.

7. To apply this policy to users, open the **Restricted user groups** blade, and choose **Add user group**. Select one or more user groups that should get this policy.

	![Screenshot of the restricted user group blade with add user group option highlighted](../media/mam-ca-add-user-group.png)

8. You may want some users in the user group you selected in the previous step not to be affected by this policy. In such cases, add the group of users to the exempted user groups list. From the **Exchange Online** blade, choose **Exempted user groups**. Choose **Add user group** to open the list of user groups. Select the groups you want to exempt from this policy.

## To modify or delete user groups from an existing app-based CA policy

1. Open the **Restricted user groups** blade, then highlight the user group you want to delete.
2. Click on the ellipse to see the delete options.
3. Choose **Delete** to remove the user group from the list.

## Next steps
[Block apps that do not have modern authentication](app-modern-authentication-block.md)

### See also

[Protect app data with app protection policies](app-protection-policies.md)
[Create app-based CA policies for SharePoint Online](app-based-conditional-access-intune-sharepoint-on-line-create.md)
