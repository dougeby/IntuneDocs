---
title: Get started with a paid subscription to Microsoft Intune-Step 6
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: get-started-article
ms.assetid: d158503c-1276-422b-ab81-5f66c1cd7e7a
author: Staciebarker
---
# Step 6: Create policies and publish an app
[!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] policies provide settings that help you control the security settings on mobile devices, maintain Windows Firewall and Endpoint Protection settings for computers, and deploy applications. If you are planning to use Intune for devices that you configure for production use after the trial, it's absolutely essential that you follow the instructions in [Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) and [Help secure Windows PCs with Endpoint Protection for Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md).

You can perform two types of app installations using Intune. The first is a **required install**, which automatically deploys the app to managed computers. The other is an **available install**, which deploys the app, or a link to the app, to the Intune company portal so that users can choose whether to install it on their computers or on their mobile devices.

Before using Intune to deploy apps, make sure that you have the appropriate licenses to publish, distribute, and use the app. The Licenses workspace lets you add and manage license agreement information for apps or software purchased through Microsoft Volume Licensing agreements, and for Microsoft or non-Microsoft software that was purchased by other means. You can then create license reports that display managed license usage information throughout your company to stay informed of license usage activity.

In these steps, you'll set up a mobile device configuration policy and a Windows computer firewall policy, and configure Skype as an available install for mobile devices after they're enrolled. After you add and deploy a new policy, all users or devices in the group to which you deployed the policy inherit the settings as their baseline policy. You can always review and edit the details of these policies later from the Policy workspace.

## Create and deploy a mobile device configuration policy

1.  Open the [Intune administration console](https://manage.microsoft.com/).

2.  In the left pane, click the **Policy** icon.

3.  In the **Tasks** list on the **Policy Overview** page, click **Add Policy**.

4.  In the policy list, expand the platform you want to create a policy for, then select **General Configuration**, choose **Create and Deploy a Policy with the Recommended Settings**, and then click **Create Policy**.

5.  When prompted to **Select the groups to which you want to deploy this policy**, select **My Trial Users** from the list, and click **Add** &gt; **OK**.

Your policy appears in the list of configuration policies, and has been deployed to the **My Trial Users** group. Double-click the policy to view its settings.

## Publish the Skype app for mobile devices

1.  In the [Intune administration console](https://manage.microsoft.com/), click the **Apps** icon, then click **Apps** &gt; **Add App**. If prompted, enter your [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] credentials.

    > [!NOTE]
    > When you start the **Intune Software Publisher** for the first time, a short delay occurs while the application is installed.

2.  Review the security warning and click **Run**.

3.  On the **Before you begin** page, click **Next**.

4.  On the **Software setup** page in **Select how this software is made available to devices**, select **External link**.

5.  Enter the external link for the software in **Specify the URL**, and then click **Next**. Make sure that you preface the URL with **http://**. For the Skype app, use the link below that matches the mobile device platform you're using:

    -   **iOS:**[https://itunes.apple.com/us/app/skype-for-iphone/id304878510?mt%3D8](https://itunes.apple.com/us/app/skype-for-iphone/id304878510?mt%3D8)

    -   **Android:**[https://play.google.com/store/apps/details?id=com.skype.raider](https://play.google.com/store/apps/details?id=com.skype.raider)

    -   **Windows Phone 8 or Windows Phone 8.1:**[http://www.windowsphone.com/en-us/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51](http://www.windowsphone.com/en-us/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51)

6.  On the **Software description** page, provide the information that you want users to see in the company portal for the software, and then click **Next**. The following settings are available (this example refers to Skype):

    -   **Publisher:** Enter the name of the publisher, "Microsoft"

    -   **Name:** Enter **Skype**

    -   **Description:** Enter a description for the software, such as **Skype communication app**

    -   **Category:** Select the category that best fits this software, such as **Collaboration**

    -   **Display this as a featured app and highlight it in the company portal:** Select this option to display the app prominently in the company portal on mobile devices.

    -   **Icon:** Choose whether to associate an icon with the software. The maximum size for the icon is 250 x 250 pixels. The recommended size is 32 x 32 pixels. This setting is optional for the Intune trial tenant.

7.  On the **Summary** page, verify the software information, and then click **Upload**. Click **Close** to exit the wizard.

8.  In the [Intune administration console](https://manage.microsoft.com/), click **Apps** &gt; **Apps** &gt; **Skype** &gt; **Manage Deployment**.

9. On the **Select Groups** page, select **My Trial Users** to deploy the software to that user group, and then click **Add** &gt; **Next**.

10. On the **Deployment Action** page, select **Available Install** from the **Approval** column for your group.

11. Click **Finish**.

The Skype app is now available to install on mobile devices from the company portal, but first you need to install [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] software on computers and mobile devices.

**Prev** Step 5
**Next** Step 7
