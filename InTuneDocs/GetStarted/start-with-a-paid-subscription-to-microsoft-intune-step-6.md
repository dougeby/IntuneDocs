---
# required metadata

title: Create policies and publish an app | Microsoft Intune
description: Explains how to create policies and publish an example app for your Intune subscription
keywords:
author: Staciebarker
manager: angrobe
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e0d8e98f-7dd8-4cbf-887c-a9af63ffe970

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Create policies and publish an app
Intune policies provide settings that help you control the security settings on mobile devices, maintain Windows Firewall and Endpoint Protection settings for computers, and deploy applications. You can learn more at [Manage settings and features on your devices with Microsoft Intune policies](/Intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) and [Help secure Windows PCs with Endpoint Protection for Microsoft Intune](/Intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune).

You can perform two types of app installations using Intune. The first is a **required install**, which automatically deploys the app to managed computers. The other is an **available install**, which deploys the app, or a link to the app, to the Intune Company Portal so that users can choose whether to install it on their computers or on their mobile devices.

The following steps will help you set up a mobile device configuration policy, a Windows PC firewall policy, and configure Skype as an available install for mobile devices after they're enrolled.

> [!TIP]
> After you add and deploy a new policy, all users or devices in the group to which you deployed the policy inherit the settings as their baseline policy. You can always review and edit the details of these policies later from the Policy workspace.


## Create and deploy a mobile device configuration policy

1.  Open the [Intune administration console](https://manage.microsoft.com/).

2.  In the left pane, choose the **Policy** icon.

	![admin-console-policy-workspace](./media/policy.png)

3.  In the **Tasks** list on the **Policy Overview** page, choose **Add Policy**.

4.  In the policy list, expand the platform you want to create a policy for, then choose **General Configuration** > **Create and Deploy a Policy with the Recommended Settings** > **Create Policy**.

> [!NOTE]
> There are no recommended settings for device configuration policies, because there are many options you can choose from. You need to create a custom device configuration policy.


5.  When prompted to **Select the groups to which you want to deploy this policy**, choose a group from the list of available groups, choose **Add** > **OK**.

Your policy appears in the list of configuration policies, and has been deployed to the **Intune Users** group. Double-click the policy to view its settings.

## Publish the Skype app for mobile devices

1.  In the [Intune administration console](https://manage.microsoft.com/), choose the **Apps** icon, then choose **Apps** > **Add App**. If prompted, enter your [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] credentials.

	![admin-console-apps-workspace](./media/apps.png)

    > [!NOTE]
    > When you start the **Intune Software Publisher** for the first time, a short delay occurs while the application is installed.

2.  Review the security warning and choose **Run**.

3.  On the **Before you begin** page, choose **Next**.

4.  On the **Software setup** page in **Select how this software is made available to devices**, choose **External link**.

5.  Enter the external link for the software in **Specify the URL**, and then choose **Next**. Make sure that you preface the URL with **http://**. For the Skype app, use the link below that matches the mobile device platform you're using:

    -   **iOS:**   [https://itunes.apple.com/us/app/skype-for-iphone/id304878510?mt%3D8](https://itunes.apple.com/us/app/skype-for-iphone/id304878510?mt%3D8)

    -   **Android:**  [https://play.google.com/store/apps/details?id=com.skype.raider](https://play.google.com/store/apps/details?id=com.skype.raider)

    -   **Windows Phone 8 or Windows Phone 8.1:**  [http://www.windowsphone.com/en-us/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51](http://www.windowsphone.com/en-us/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51)

6.  On the **Software description** page, provide the information that you want users to see in the Company Portal for the software, and then choose **Next**. The following settings are available (this example refers to Skype):

    -   **Publisher:** Enter the name of the publisher, "Microsoft"

    -   **Name:** Enter **Skype**

    -   **Description:** Enter a description for the software, such as **Skype communication app**

    -   **Category:** Select the category that best fits this software, such as **Collaboration**

    -   **Display this as a featured app and highlight it in the company portal:** Select this option to display the app prominently in the Company Portal on mobile devices.

    -   **Icon:** Choose whether to associate an icon with the software. The maximum size for the optional icon is 250 x 250 pixels and the recommended size is 32 x 32 pixels.

7.  On the **Summary** page, verify the software information, and then choose **Upload**. Choose **Close** to exit the wizard.

8.  In the [Intune administration console](https://manage.microsoft.com/), choose **Apps** > **Apps** > **Skype** > **Manage Deployment**.

9. On the **Select Groups** page, choose **Intune Users** to deploy the software to that user group, and then choose **Add** > **Next**.

10. On the **Deployment Action** page, select **Available Install** from the **Approval** column for your group.

11. Choose **Finish**.

The Skype app is now available to install on mobile devices from the Company Portal, but first you need to install [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] software on computers and mobile devices.


### Next steps
Congratulations! You have just completed step 6 of the *Intune quick start guide*.

>[!div class="step-by-step"]

>[&larr; **Organize users and devices**](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)       [**Customize Company Portal** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-7.md)  
