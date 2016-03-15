---
title: Manage app access to SharePoint Online
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 683850f9-7010-423e-aae4-d9a60feaec7e
author: karthikaraman
---
# Manage app access to SharePoint Online
You can choose which apps should be allowed to access SharePoint Online and the users who are affected by the policy.  This topic gives you step by step instructions on how to set up app access to SharePoint Online service..

## Create SharePoint Online policy

1.  Sign into this [Azure portal](https://portal.azure.com/?Microsoft_Intune=true#blade/Microsoft_Intune/SummaryBladeWithCA) that includes the app access feature.

2.  From **Browse**, click **Intune**. This opens the **Intune mobile application management** blade and the **Settings** blade. From the **Settings** blade, click **SharePoint Online** to open the SharePoint Online blade.
![AppAccess_SP](/Image/AppManagement/AppAccess_SP.png)
3.  On the **Allowed apps** blade, first select whether you want to allow all apps, or if only certain apps should have access to SharePoint Online. If you select to allow only certain apps to have access, you will be presented with a list of apps that you can choose from. Select one or more apps from the list and save your changes.
![AppAccess_SP_AllowedApps](/Image/AppManagement/AppAccess_SP_AllowedApps.png)
4.  To apply these restrictions  to users, open **Restricted user groups** blade, and click **Add user group**. This open the **Add user group** blade that lists your Azure AD user groups.  Select one or more groups, and click **Select**.
![AppAccess_SP_RestrictedUserGroup](/Image/AppManagement/AppAccess_SP_RestrictedUserGroup.png)
5.  You may want some users in the user group you selected in the previous step not to be affected by this restriction. In such cases, add the group of users to the Exempted user groups list.  From the **SharePoint Online** blade, click **Exempted user groups**. Click **Add user group** to open the list of user groups. Select the groups you want to exempt from this restriction, and click **Select** to create the access policy for SharePoint Online.
![AppAccess_SP_ExemptUserGroup](/Image/AppManagement/AppAccess_SP_ExemptUserGroup.png)
6.  To delete a user group from the restricted user groups list, open the **Restricted user groups** blade, highlight the user group you want to delete, and click on the **…** to see the delete option. Click **Delete** to remove the user group from the list.
![AppAccess_SP_DeleteUserGroup](/Image/AppManagement/AppAccess_SP_DeleteUserGroup.png)
    > [!NOTE]
    > You can follow the same step to remove a user group from the Exempted user group list.

