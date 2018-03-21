---
# required metadata

title: App access for Exchange Online 
description: This topic describes how you can configure a conditional access policy for MAM apps.
keywords:
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 10/15/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f2cd1a1f-fd29-4081-8dfa-c40993a107d5
ROBOTS: NOINDEX,NOFOLLOW

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: chrisgre
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Create an Exchange Online conditional access to only allow apps supported by MAM

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

This topic gives you step-by-step instructions on how to set up conditional access for  Exchange Online to only allow mobile apps that support Intune app protection policies.


## Create an Exchange Online policy
1.  Sign into the [Azure portal](https://portal.azure.com) that includes the app access feature. If you
are new to the Azure portal experience read the [Azure portal for app protection policies](azure-portal-for-microsoft-intune-mam-policies.md) topic.

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

## Modify an existing policy
### Add or delete user groups

To **delete a user group** from the **restricted user groups** list, open the **Restricted user groups** blade, highlight the user group you want to delete, and click on the **ellipses(...)** to see the **Delete** option. Choose **Delete** to remove the user group from the list. You can follow the same procedure to remove a user group from the **exempted user group** list.


## Next steps
[Block apps that do not have modern authentication](block-apps-with-no-modern-authentication.md)
### See also
[Protect app data with app protection policies](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)
