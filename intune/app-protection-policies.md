---
# required metadata

title: Create and deploy app protection policies 
titleSuffix: "Azure portal"
description:  Learn how Intune app protection policies can help protect company data used by apps you manage."
keywords:
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 02/16/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f31b2964-e932-4cee-95c4-8d5506966c85

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: joglocke
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---

# How to create and assign app protection policies

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## Before you begin

If you're looking for instructions in the Intune classic portal, see [how to create app protection policies](https://docs.microsoft.com/intune-classic/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune).

App protection policies can be applied to apps running on devices that may or may not be managed by Intune. For a more detailed description of how app protection policies work and the scenarios supported by Intune app protection policies, see [What is Microsoft Intune app protection policies](app-protection-policy.md).

If you're looking for a list of MAM supported apps, see [MAM apps list](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

##  Create an app protection policy
1.  In the **Mobile apps** workload, select **App protection policies** from the **Manage** section. This selection opens the **App protection policies** blade, where you create new policies and edit existing policies. 
2. Choose **Add a policy**. 

  ![Screenshot of the 'Add a policy' blade](./media/app-protection-add-policy.png)

3.  Type a name for the policy, add a brief description, and select the platform type for your policy. Note at you can create more than one policy for each platform.

4.  Choose **Apps** to open the **Apps blade**, where a list of available apps is displayed. Select one or more apps from the list that you want to associate with the policy that you are creating. 
5. Once you have selected the apps, choose **Select** at the bottom of the **Apps** blade to save your selection.

    > [!IMPORTANT]
    > You must select at least one app to create a policy.

6.  Choose **Configure required settings** on the **Add a policy** blade to open **Settings** blade.

    There are two categories of policy settings, **Data relocation** and **Access**.  Data relocation policies are applicable to data movement in and out of the apps. The access polices determine how the end user accesses the apps in a work context.
    To get you started, the policy settings have default values. If the default values meet your requirements, you do not have to make any changes/

    > [!TIP]
    > These policy settings are enforced only when using apps in the work context. When end user uses the app to do a personal task, they are not be affected by these policies.

7. Choose **OK** to save this configuration. You are now back in the **Add a policy** blade. 
8. Choose **Create** to create the policy and save your settings.

When you finish creating a policy as described in the previous procedure, it is not deployed to any users. To deploy a policy, see [Deploy a policy to users](app-protection-policies#deploy-a-policy-to-users)."

## Data transfer exceptions
As an administrator, you can create exceptions to the Intune Mobile Application Management (MAM) data transfer policy. An exception allows you to specifically choose which unmanaged apps can transfer data to and from managed apps. The unmanaged apps that you included in the exception list must be trusted by IT. 

>[!WARNING] 
> You are responsive for making changes to the data transfer exception policy. Additions to this policy allow unmanaged apps (apps that are not managed by Intune) to access data protected by managed apps. This access to protected data may result in data security leaks. Only add data transfer exceptions for apps that your organization must use, but that do not support Intune APP (Application Protection Policies). Additionally, only add exceptions for apps that you do not consider to be data leak risks.

This feature applies when you create an Intune Application Protection Policy with data transfer set to **Managed apps only**. Other than the exceptions you create, when your data transfer policy is set to **Managed apps only**, data transfer is still restricted to apps that are managed by Intune. You can create the restrictions by using protocols (iOS) or packages (Android).

You can configure this feature to enable exceptions to the Intune MAM App Protection policy **restrict data transfer**. This policy is only required if you want to allow data to be transferred to an app that does not support Intune APP. This policy allows applications managed by Intune, with data transfer settings set to **Managed apps only**, to invoke unmanaged applications based on URL protocol (iOS) or package name (Android). Intune adds vital native applications to the default list of exceptions. 

### iOS data transfer exceptions
For a policy targeting iOS, you can configure data transfer exceptions by URL protocol. To add an exception, check the documentation provided by the developer of the app to find information about supported URL protocols.

### Android data transfer exceptions
For a policy targeting Android, you can configure data transfer exceptions by app package name. You can check the **Google Play** store page for the app you would like to add an exception for to find the app package name.

#### Example
By adding the **Webex** package as an exception to the MAM data transfer policy, Webex links inside a managed Outlook email message are allowed to open directly in the Webex application. Data transfer is still restricted in other unmanaged apps.

- iOS **Webex** example:
    To exempt the **Webex** app so that it is allowed to be invoked by Intune managed apps, you must add a data transfer exception for the following string: <code>wbx</code>. This is true, even for apps that do not support APP. 

- Android **Webex** example:
    To exempt the **Webex** app so that it is allowed to be invoked by Intune managed apps, you must add a data transfer exception for the following string: <code>com.cisco.webex.meetings</code>. This is true, even for apps that do not support APP. 

## Deploy a policy to users

1.  In the **Policy** blade, choose  **User groups**, which opens the **User groups** details. Choose **Add user group** to open the **Add user group** details.

  ![Screenshot of the User groups information with the Add user group menu option highlighted](./media/app-protection-policy-add-users.png)

2.  A list of user groups is displayed on the **Add user group** blade. This list is a list of all the security groups in your **Azure Active Directory**. Select the user groups you want this policy to apply to, and then choose **Select**. Choosing **Select**, deploys the policy to users.
  ![Screenshot of the Add user group information showing the list of Azure Active Directory users](./media/azure-ad-user-group-list.png)

You have now created a policy and deployed it to users.

Only users with assigned Microsoft Intune licenses are affected by the policy. Users in the selected security group that don’t have an assigned Intune license are not affected.

>[!IMPORTANT]
> If you are using Intune with Configuration Manager to manage your devices, the policy is only applied to the users directly in the group that you selected. Members of child groups nested within the group you selected are not affected.

End users can download the apps from the App store or Google Play. For more information, see:
* [What to expect when your Android app is managed by app protection policies](app-protection-enabled-apps-android.md)
* [What to expect when your iOS app is managed by app protection policies](app-protection-enabled-apps-ios.md)

##  Change existing policies
You can edit an existing policy and apply it to the targeted users. However, when you change existing policies,  users who are already signed  in to the apps won’t see the changes for an 8-hour period.

To see the effect of the changes immediately, the end user will have to log out of the app, and sign back in.

### To change the list of apps associated with the policy

1.  In  the **App policy** blade, choose the policy you want to change. This opens the details specific to the policy you just selected.

2.  In the policy blade, choose **Targeted apps** to open the list of apps.

3.  Remove or add apps from the list and choose the **Save** icon to save your changes.

### To change the list of user groups

1.  In  the **App policy** blade, choose the policy you want to change. This opens the details specific to the policy you selected.

2.  Choose **User groups** to open the **User group** blade that shows the list of current user groups who have this policy.

3.  To add a new user group to the policy, choose **Add user group**, and select the user group. Choose **Select** to deploy the policy to the group you selected.

4.  To delete a user group, highlight the user group you want to remove. Then choose the ellipses (…), and choose **Delete** to remove the user group.
  ![Screenshot showing Delete option ](./media/app-protection-policy-delete-user.png)

### To change policy settings

1.  In the **App policy** blade, choose the policy you want to change. This opens the details specific to the policy you just selected.


2.  Choose **Policy settings** to open the **Policy settings** details.

3.  Change the settings, and choose the **Save** icon to save your changes.

## Policy settings
To see a full list of the policy settings for iOS and Android, select one of the following:

- [iOS policies](app-protection-policy-settings-ios.md)
- [Android policies](app-protection-policy-settings-android.md)

## Next steps
[Monitor compliance and user status](app-protection-policies-monitor.md)

### See also
* [What to expect when your Android app is managed by app protection policies](app-protection-enabled-apps-android.md)
* [What to expect when your iOS app is managed by app protection policies](app-protection-enabled-apps-ios.md)
