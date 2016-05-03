---
title: Manage app access to Exchange Online
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 21033f37-6f4a-4a3d-8093-223f159c8742
author: karthikaraman
---
# Manage app access to Exchange Online
You can choose which apps should be allowed to access Exchange Online and the users who are affected by the policy.  This topic gives you step by step instructions on how to set up app access to Exchange Online service.

## Create Exchange Online policy

1.  Sign into this [Azure portal](https://portal.azure.com/?Microsoft_Intune=true#blade/Microsoft_Intune/SummaryBladeWithCA) that includes the app access feature.

2.  From **Browse**, click **Intune**. This opens the **Intune mobile application management** blade and the **Settings** blade. From the **Settings** blade, click **Exchange Online** to open the Exchange Online blade.
![App_Access_EXO](/Image/AppManagement/App_Access_EXO.png)
3.  On the **Allowed apps** blade, first select whether you want to allow all apps, or only certain apps. If you select to allow only certain apps to have access, you are presented with a list of apps that you can choose from. Select one or more apps from the list and save your changes.
![AppAccess_EXO_AllowedApps](/Image/AppManagement/AppAccess_EXO_AllowedApps.png)
4.  To apply these restrictions  to users, open **Restricted user groups** blade, and click **Add user group**. This open the **Add user group** blade that lists your Azure AD user groups.  Select one or more groups, and click **Select**.
![AppAccess_EXO_RestrictedUserGroup](/Image/AppManagement/AppAccess_EXO_RestrictedUserGroup.png)

5.  You may want some users in the user group you selected in the previous step not to be affected by this restriction. In such cases, add the group of users to the Exempted user groups list.  From the **Exchange Online** blade, click **Exempted user groups**. Click **Add user group** to open the list of user groups. Select the groups you want to exempt from this restriction, and click **Select** to create the access policy for Exchange Online.
![AppAccess_ExemptedUserGroup](/Image/AppManagement/AppAccess_ExemptedUserGroup.png)

6.  To delete a user group from the restricted user groups list, open the **Restricted user groups** blade, highlight the user group you want to delete, and click on the **…** to see the delete option. Click **Delete** to remove the user group from the list.
![AppAccess_EXO_DeleteUserGroup](/Image/AppManagement/AppAccess_EXO_DeleteUserGroup.png)
    > [!NOTE]
    > You can follow the same step to remove a user group from the Exempted user group list.

