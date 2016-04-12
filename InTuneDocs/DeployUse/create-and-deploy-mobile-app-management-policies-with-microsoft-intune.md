---
title: Create and deploy MAM policies | Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: c1b9a343-1737-4a65-a9c6-aca48acad11c
author: karthikaraman
---
# Create and deploy mobile app management policies with Microsoft Intune
Mobile app management (MAM) policies can be applied to apps running on devices that may or may not be managed by Intune. For a more detailed description of how MAM policies work and the scenarios supported by Intune MAM policies, read the [protect app data using mobile app managment policies](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md) article.

This topic describes the process of creating a MAM policy in the **Azure portal**. The MAM policy you create in the Azure portal is supported for all MAM scenarios:
- Devices enrolled in Intune
- Devices managed by a third-party MDM solution
- Devices that are not managed by any MDM solution (BYOD).

If you are currently using the **Intune admin console** to manage your devices, you can [create a MAM policy](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) that supports apps for devices enrolled in Intune using the Intune admin console.
>[!IMPORTANT]
> You may not see all MAM policy settings in the Intune admin console. The Azure portal is the new admin console for creating MAM policies.

To see a list of policy settings supported for Android and iOS platforms, select one of the following:

> [!div class="op_single_selector"]
- [iOS policies](android-mam-policy-settings.md)
- [Android policies](ios-mam-policy-settings.md)

##  Create a MAM policy
1.  Choose **Intune mobile application management &gt; Settings** to open the **Settings** blade.

    ![](../media/AppManagement/AzurePortal_MAM_Mainblade.png)

    > [!TIP]
    > If this is the first time you are using the Azure portal, read [Azure portal for Microsoft Intune MAM policies](azure-portal-for-microsoft-intune-mam-policies.md) first to get familiar with the portal.

2.  In the **Settings** blade, choose **App policy**.  This opens the **App policy** blade where you'll  create new policies and edit existing policies.

    ![](../media/AppManagement/AzurePortal_MAM_AppPolicy.png)

3.  Choose **Add a policy**.

    ![](../media/AppManagement/AzurePortal_MAM_AddPolicy.png)

4.  Type  a name for the policy, add  a brief description, and select the platform type to create a policy for iOS or Android.  You can create more than one policy for each platform.

    ![](../media/AppManagement/AzurePortal_MAM_AddPolicy_only.png)

5.  Choose **Apps** to open the **Apps blade** where a list of available apps is displayed. You can select one or more apps from the list that you want to associate with the policy that you are creating. One you have selected the apps, choose the **Select** button at the bottom of the **Apps** blade to save your selection.

    > [!IMPORTANT]
    > You must select at least one app to create a policy.

6.  On the **Add a policy blade**, choose **Configure required settings** to open the policy settings blade.

    There are two categories of policy settings-**Data relocation** and **Access**.  Data relocation policies are applicable to data movement in and out of the apps, while the access polices determine how the end-user accesses the apps in a work context.
    To get you started the policy settings have default values.  You do not have to make any changes if the default values meet your requirements.

    > [!TIP]
    > These policy settings are enforced only when using apps in the work context.  When the end-user uses the app to do a personal task, they will not be affected by these policies.

    ![](../media/AppManagement/AzurePortal_MAM_PolicySettings.png)

7.  Choose **OK** to save this configuration.  You are now back in the **Add a policy** blade. Choose **Create** to create the policy and save your settings.

    ![](../media/AppManagement/AzurePortal_MAM_CreatePolicy.png)

    ![](../media/AppManagement/AzurePortal_MAM_AddingPolicyNotification.png)

When you finish creating a policy as described in the previous procedure, it is not deployed to any users.  Follow the steps described below to deploy the policy.

> [!IMPORTANT]
> If you create a MAM policy for an app using the Intune admin console and a MAM policy using the Azure portal, the policy you created using the Azure portal takes precedence. However, the reporting in the Intune or Configuration Manager console will report the policy settings created from the Azure  portal. For example:
>
> -   You created a mobile application management policy in the Intune admin console that blocks copy from an app.
> -   You created a mobile app management policy in the Azure console that allows copy from an app
> -   You associate both of these policies to the same app.
> -   The result is that the policy you created from the Azure console takes precedence and copy is allowed.
> -   However, status and reports in the Intune console will incorrectly indicate that copy is blocked.

## Deploy a policy to users

1.  In the **Policy** blade, choose  **User groups**, which opens the **User groups** blade. Choose **Add user group** in the **User groups** blade to open the **Add user group** blade.

    ![](../media/AppManagement/AzurePortal_MAM_AddUserstoPolicy.png)

2.  A list of user groups is displayed on the **Add user group** blade. This is a list of all the security groups in your **Azure Active Directory**.  You can select the user groups you want this policy to apply to and choose **Select**. Choosing **Select**, deploys the policy to users.

    ![](../media/AppManagement/AzurePortal_MAM_SelectUserstoDeploy.png)

    You have now created a policy and deployed it to users.

Only users with [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] licenses assigned to them will be affected by the policy.  Users who are in the security group that you selected that don’t have a [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] license assigned to them are not affected.

If you are using Intune with Configuration Manager to manage your iOS and Android devices, the policy is only applied to the users directly in the group that you selected.  Members of child groups  nested within the group you selected will not be affected.

The end users can download the apps from the App store or Google Play. For a detailed walkthrough of how MAM protects company data on the device see [Using apps with MAM policies](end-user-experience-for-apps-associated-with-microsoft-intune-mobile-app-management-policies.md) article.

##  Change existing policies
You can edit an existing policy and apply it to the targeted users. However, when you change existing policies,  users who are already signed  in to the apps won’t see the changes for a 8-hour period.

To see the effect of the changes immediately the end-user will have to log out of the app, and sign back in.

### To change the list of apps associated with the policy

1.  In  the **App policy** blade, choose the policy you want to change. This opens a blade specific to the policy you just selected.

    ![](../media/AppManagement/AzurePortal_MAM_OpenPolicy.png)

2.  In the policy blade, choose **Targeted apps** to open the list of apps.

3.  Remove or add apps from the list and choose the **Save icon** to save your changes.

### To change the list of user groups

1.  In  the **App policy** blade, choose the policy you want to change. This opens the blade specific to the policy you selected.

2.  In the policy blade, choose **User groups** to open the **User group** blade that shows the list of current user groups who have this policy.

3.  To **add a new user group** to the policy, choose **Add user group**, and select the user group. Choose **Select** to deploy the policy to the group you selected.

    ![](../media/AppManagement/AzurePortal_MAM_ChangePolicy_SelectUser.png)

4.  To **delete a user group**, highlight the user group you want to remove, choose the ellipses (…), then choose **Delete** to remove the user group.

    ![](../media/AppManagement/AzurePortal_MAM_ChangePolicy_DeleteUser.png)

### To change policy settings

1.  In the **App policy** blade, choose the policy you want to change. This opens a blade specific to the policy you just selected.

    ![](../media/AppManagement/AzurePortal_MAM_OpenPolicy.png)

2.  Choose **Policy settings** to open the **Policy settings** blade.

3.  Change the settings, and choose the **Save icon** to save your changes.

    ![](../media/AppManagement/AzurePortal_MAM_ChangePolicy_ChangeSettings.png)

## Policy settings
To see a full list of the policy setting for iOS and Andriod, select one of the following:

> [!div class="op_single_selector"]
  - [iOS policies](android-mam-policy-settings.md)
  - [Android policies](ios-mam-policy-settings.md)

## Next steps
[Monitor compliance and user status](monitor-mobile-app-management-policies-with-microsoft-intune.md)

### See also
[End-user experience for apps](end-user-experience-for-apps-associated-with-microsoft-intune-mobile-app-management-policies.md)
