---
title: Get started with a 30-day trial of Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: get-started-article
ms.assetid: 619a1d11-3d22-4635-8f70-770eba3e1712
author: Staciebarker
---
# Get started with a 30-day trial of Microsoft Intune
Setting up a free Microsoft Intune 30-day trial to manage your mobile devices and computers is quick and easy. With just a few simple steps in the trial, you can add up to 100 users and devices, set up groups, configure compliance policies, and enroll and manage mobile devices and computers. In this topic, you'll learn the basics  to get an Intune trial up and running and get an overview of the service so you can evaluate Intune's features and capabilities.

Watch this five-minute demo video to learn how easy it is to get started with a free trial of Microsoft Intune and to manage your devices:

<iframe width="675" height="480" src="https://www.youtube.com/embed/ltcZvm4VOFU" frameborder="0" allowfullscreen></iframe>

## Before you begin
Before you get started with Intune, you'll need the following:

-   A device with a Silverlight-enabled web browser that you can use to access the websites where you'll  create Intune user accounts (the **Intune Account Portal**) and where you manage devices, groups, and policies  (the **Intune administration console**).

-   A second device with a web browser that you'll use  to test how [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] users will enroll and manage their devices using the company portal. You'll also test how users find and install apps and request help from administrators. If you don't have a second device, you can use the “privacy mode” setting on the same browser that you use for [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] administration (for example: in Internet Explorer, you can click **Tools** &gt; **InPrivate Browsing**).

-   If you have an existing Microsoft Online Services account, you'll need the  administrator credentials for that account. If you don’t have such an account, or if you want to use this Intune tenant for evaluation purposes only, you don't need these administrator credentials.

-   If you'll manage iOS or Windows Phone devices with the Intune trial, you'll need certificates (or keys) and accounts to retrieve those certificates (see the following table). Android devices don't need any additional certificates.

    |Platform|Certificate Requirements|More information|
    |------------|----------------------------|--------------------|
    |Windows Phone 8.1 and [!INCLUDE[winphone8_client_1](./includes/winphone8_client_1_md.md)]|No certificate is required for Windows Phone 8.1 users who install the company portal app from the Store. A Symantec certificate is required for Windows Phone 8.0 or to use Intune to deploy the company portal app to Windows Phone 8.1 devices.|This guidance assumes your users get the company portal app from the Store on a Windows Phone 8.1 or later device. For information about Windows Phone 8.0 support, see [Set up Windows Phone management with Microsoft Intune](set-up-windows-phone-management-with-microsoft-intune.md).|
    |Windows 10, [!INCLUDE[winblue_winrt_2](./includes/winblue_winrt_2_md.md)], [!INCLUDE[win8RT_client_1](./includes/win8RT_client_1_md.md)], or [!INCLUDE[winblue_client_2](./includes/winblue_client_2_md.md)] devices|There are no certificate requirements for enrolling Windows RT and Windows devices.|[Install the Windows PC client with Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md).|
    |iOS 7.1 or later|Get an Apple Push Notification service certificate.|Request an Apple Push Notification service certificate from Apple, as described here: [Set up iOS and Mac management with Microsoft Intune](set-up-ios-and-mac-management-with-microsoft-intune.md).|

## <a name="Step1"></a>Step 1: Sign up or sign in to Intune
Before  you sign up or sign in to Intune,  you should consider the following:

-   Whether your organization already has a Microsoft Online Services work or school account

-   Whether you have an Enterprise Agreement or equivalent volume licensing agreement with Microsoft

-   Whether you plan to use the Intune tenant after the 30-day trial

|Sign up for a NEW account if either of the following is true:|Sign in with your WORK or SCHOOL account if:|
|-----------------------------------------------------------------|------------------------------------------------|
|**You don’t have a work or school account.** A work or school account is provided when you sign a volume licensing agreement with Microsoft or subscribe to Office 365. If your organization has not signed an Enterprise Agreement or equivalent volume licensing agreement with Microsoft (or has an Office 365 account), then you do not have a Microsoft Online Services account that you can use to sign in to Microsoft Online Services.<br /><br />**You will discard your Intune tenant after completing the 30-day trial.** You should sign up for a new account if you are using your [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] free trial subscription for evaluation purposes only, and you plan to redo your [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] service setup and device provisioning after the trial. This is the recommended option if you plan to use [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] with System Center 2012 Configuration Manager.<br /><br />If you sign up for a new account, you cannot later use an existing work or school account to manage that account, or combine it with existing volume licensing agreements.|**You have a work or school account provided with a volume licensing agreement or Office 365 subscription, and you are using this trial to evaluate [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)].**<br /><br />If you are setting up [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] on an existing account, we recommend that you review [Choose how to manage devices](introduction-to-microsoft-intune.md) before continuing with these steps.|

### <a name="BKMK_ToSignUpforSubscription"></a>Sign up or sign in to Intune

1.  First, [click here to visit the Intune Sign up page](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20).

2.  On the **Sign up** page, you have two options:

    -   **Subscribe using your Microsoft Online Services work or school account**: Click **Sign in** if you already have a work or school account, and you want to use the same account to subscribe to both services. When you use the same account for multiple services, those services use the same Azure AD infrastructure and are tenants of Azure AD. Azure AD provides the core directory and identity management capabilities for Microsoft cloud services.

    -   **Subscribe to Intune only**: If you do not yet subscribe to a cloud service, complete the form on the sign-up page to subscribe to [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)].

        > [!NOTE]
        > By default, the domain name is associated with your subscription and user accounts that you add to [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)]. After you subscribe, you can add and use a custom domain name that you already own, or continue to use the free **onmicrosoft.com** domain.

After you complete the sign-up form and accept the Microsoft Online Subscription Agreement, you're automatically signed in to the [!INCLUDE[wit_icp_1](./includes/wit_icp_1_md.md)] with the tenant administrator account. An email message that contains your account information is also sent to the email address that you provided during sign-up. This email confirms that your subscription is active.

## <a name="Step2"></a>Step 2: Add users to Intune
Now that you have set up your account, you'll use either the **New Users** wizard to add individual user accounts to [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)], or the **Bulk add users** wizard to add users in bulk (see the instructions in this section).  Before you get started, it's important that you understand how Intune handles administrator accounts.

A tenant administrator  uses the account portal to add  users to the Microsoft Intune **Users Group**. Adding users to the  **Users Group** assigns Intune subscription licenses to users and is also how you make those users to show up in the Microsoft Intune administration console.

Administrator accounts for Intune aren't created in the account portal,  as regular user accounts are. Instead, you  assign  either read-only access or full access administrative rights to users by using the administration console in the **Administration** workspace under **Administration Management**. Service administrators that are assigned read-only access cannot change Intune settings, but they can view data and run reports. Service administrators with full access have all available administrative rights.

You can view tenant administrator information by using the Intune administration console, but you cannot create tenant administrators there. By default, the subscription owner becomes a tenant administrator for your Microsoft Intune service and has full access to both the Intune account portal and the Intune administration console. We recommend that you create a least one extra tenant administrator account by using the account portal to help delegate tasks and to ensure that you don’t get locked out of your Intune service administrator account if you forget your password.

### Add individual user accounts
Use the following steps to create additional user accounts in your trial tenant. Remember, each user account that you add counts as one of the 100 licenses that  you get as part of your [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] free trial.

1.  In the [Office 365 admin center](http://go.microsoft.com/fwlink/p/?LinkId=698854), click **Add Users** &gt; **New**&gt; **User** to start the **New users** wizard.

2.  On the **Details** page, complete the required fields.

3.  On the **Settings** page, set the **location** for the user.

4.  On the **Group** page, click **Next** to accept the default and assign a license for [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] to the user’s account.

5.  On the **Email** page, specify up to five email addresses that will receive notification of the user name and temporary password for the account. Separate multiple email addresses by semicolons (;). When you're done, click **Create** to add the user to your subscription.

6.  On the **Results** page, you can view the new account name and its temporary password. [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] automatically creates the temporary password.

7.  When the new user  appears in the **Users** node of the account portal, verify that the new user was created successfully:

    1.  In the [Intune administration console](https://manage.microsoft.com/), click **Admin** &gt; **Company Portal**, and then scroll to the bottom of the screen. Copy the URL shown under  **Intune company portal**.

    2.  Open a new browser window in “privacy mode” (in Internet Explorer, click **Tools** &gt; **InPrivate Browsing**), or open a new browser window on a different device, and then navigate to the URL that you copied in the previous step. When users sign in for the first time, they must provide a new password for the account.

### Add users in bulk
To add users in bulk to Intune,  use the **Bulk add users** wizard to upload a comma-separated values (CSV) file that contains your user data. Links in the wizard enable you to download a blank template and sample CSV file. The first row of your CSV file must contain, in the correct order, each of the user data column labels. Then, for each user in the CSV file, you must include the **user name** (like **bob@contoso.com**) and a **display name** (like **Bob Kelly**).

1.  In the [Office 365 admin center](http://go.microsoft.com/fwlink/p/?LinkId=698854), click **Users** &gt; **New**.

2.  Click **Bulk add** to start the Bulk add users wizard.

3.  On the **Select file** page, click **Browse** to specify and load an existing CSV file from your computer. You can also download a sample CSV file or blank template file by using the links in the wizard.

4.  On the **Verification** page, review the results, and then click **View** for more details.

5.  On the **Settings** page, confirm that the sign-in status is **Allowed**, and set the **location**. These settings apply to all user accounts added by the CSV file.

6.  On the **Group** page, click **Next** to accept the default and assign a license for [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] to all user accounts added by the CSV file. By default, the check box is selected, which assigns a license for [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] to each account.

7.  On the **Email** page, specify up to five email addresses to receive notification of the user names and temporary passwords that [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] creates for each account. Separate multiple email addresses with semicolons (;). When ready, click **Create** to add the users to your subscription.

8.  On the **Results** page, you can view the account names and temporary password for each user account.

Each user account that you added by importing it now appears in the **Users** node of the account portal. When new users sign in for the first time, they must specify a new password for their user account.

## <a name="Step3"></a>Step 3: Create groups to organize users and devices
Groups in [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] give you great flexibility for managing your devices and users. You can set up groups to suit your organizational needs (for example, by geographic location, department, or hardware characteristics) and use them to perform a variety of administrative tasks at scale, from setting policies for a set of users to deploying applications to a set of devices.

### Create a device group
Use device groups to deploy software and updates, and configure Microsoft Intune Agent Settings and Windows Firewall Settings policies. For example, set up a "My Trial Devices" group using the following steps:

1.  In the [Intune administration console](https://manage.microsoft.com/), click **Groups** &gt; **Overview** &gt; **Create Group**.

2.  For the **Group name**, type “My Trial Devices” and, from the parent group list, select **All Devices**, and then click **Next**.

3.  On the **Define Membership Criteria** page, select **All devices** to indicate that the group includes both mobile devices and computers.

4.  On the **Define Direct Membership** page, click **Next**. If you previously created a group that does not include all devices, and you wanted to add specific devices to your new group, you can do that here.

5.  On the **Summary** page, review the actions that will be taken, and then click **Finish**.

You can find the newly created group in the **Groups** list, in the **Groups** workspace under **All Devices**. From here, you can also edit or delete the group.

### Create a user group
Use user groups to deploy software and device policies. For example, set up a "My Trial Users" group using the following steps:

1.  In the [Intune administration console](https://manage.microsoft.com/), click **Groups** &gt; **Overview** &gt; **Create Group**.

2.  For the **Group name**, type “My Trial Users” and, from the parent group list, select **All Users**, and then click **Next**.

3.  On the **Define Membership Criteria** page, set **Start group membership with** to **All users in the Parent group**.

4.  Beside **Exclude members from these security groups**, click **Browse** and then select **Company Administrator**. This exclusion lets you manage the My Trial Users group without affecting the Company Administrator account (also known as the tenant administrator).

5.  On the **Define Direct Membership** page, click **Next**. You don’t need to do anything here because you want the My Trial Users group to include all users, except for the Company Administrator.

6.  On the **Summary** page, review the actions that will be taken, and then click **Finish**.

You can find the newly created group in the **Groups** list, in the **Groups** workspace under **All Users**. From here, you can also edit or delete the group.

To learn more about using groups, see [Use groups to manage users and devices with Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).

## <a name="Step4"></a>Step 4: Create policies and publish an app
[!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] policies provide settings that help you control the security settings on mobile devices, maintain Windows Firewall and Endpoint Protection settings for computers, and deploy applications. If you are planning to use Intune for devices that you configure for production use after the trial, it's absolutely essential that you follow the instructions in [Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) and [Help secure Windows PCs with Endpoint Protection for Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md).

You can perform two types of app installations using Intune. The first is a **required install**, which automatically deploys the app to managed computers. The other is an **available install**, which deploys the app, or a link to the app, to the Intune company portal so that users can choose whether to install it on their computers or on their mobile devices.

Before using Intune to deploy apps, make sure that you have the appropriate licenses to publish, distribute, and use the app. The **Licenses** workspace lets you add and manage license agreement information for apps or software purchased through Microsoft Volume Licensing agreements, and for Microsoft or non-Microsoft apps or software purchased by other means. You can then create license reports, which display managed license usage information throughout your company, to stay informed of license usage activity.

In these steps, you'll set up a mobile device configuration policy and a Windows computer firewall policy, and configure Skype as an available install for mobile devices after they're enrolled. After you add and deploy a new policy, all users or devices in the group to which you deployed the policy inherit the settings as their baseline policy. You can always review and edit the details of these policies later from the **Policy** workspace in the administration console.

#### Create and deploy a mobile device configuration policy

1.  Open the [Intune administration console](https://manage.microsoft.com/).

2.  In the left pane, click the **Policy** icon.

3.  In the **Tasks** list on the **Policy Overview** page, click **Add Policy**.

4.  In the policy list, expand the platform you want to create a policy for, select **General Configuration**, choose **Create and Deploy a Policy with the Recommended Settings**, and then click **Create Policy**.

5.  When prompted to **Select the groups to which you want to deploy this policy**, select **My Trial Users** from the list, and click **Add** &gt; **OK**.

Your policy appears in the list of configuration policies, and has been deployed to the **My Trial Users** group. Double-click the policy to view its settings.

#### Publish the Skype app for mobile devices

1.  In the [Intune administration console](https://manage.microsoft.com/), click the **Apps** icon, then click **Apps** &gt; **Add App**. If prompted, enter your [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] credentials.

    > [!NOTE]
    > When you start the **Intune Software Publisher** for the first time, a short delay occurs while the application is installed.

2.  Review the security warning and click **Run**.

3.  On the **Before you begin** page, click **Next**.

4.  On the **Software setup** page in **Select how this software is made available to devices**, select **External link**.

5.  Enter the external link for the software in **Specify the URL**, and then click **Next**. Make sure that you preface the URL with **https://**. For the Skype app, use the link below that matches the mobile device platform you're using:

    -   **iOS:** [https://itunes.apple.com/us/app/skype-for-iphone/id304878510?mt%3D8](https://itunes.apple.com/us/app/skype-for-iphone/id304878510?mt%3D8)

    -   **Android:** [https://play.google.com/store/apps/details?id=com.skype.raider](https://play.google.com/store/apps/details?id=com.skype.raider)

    -   **Windows Phone 8 or Windows Phone 8.1:** [http://www.windowsphone.com/en-us/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51](http://www.windowsphone.com/en-us/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51)

6.  On the **Software description** page, provide the information that you want users to see in the company portal for the software, and then click **Next**. The following settings are available (this example refers to Skype):

    -   **Publisher:** Enter the name of the publisher, "Microsoft"

    -   **Name:** Enter **Skype**

    -   **Description:** Enter a description for the software, such as **Skype communication app**

    -   **Category:** Select the category that best fits this software, such as **Collaboration**

    -   **Display this as a featured app and highlight it in the company portal:** Select this option to display the app prominently in the company portal on mobile devices.

    -   **Icon:**  (Optional) Choose whether to associate an icon with the software. The maximum icon size is 250 x 250 pixels, but the recommended icon size is 32 x 32 pixels.

7.  On the **Summary** page, verify the software information, and then click **Upload**. Click **Close** to exit the wizard.

8.  In the [Intune administration console](https://manage.microsoft.com/), click **Apps** &gt; **Apps** &gt; **Skype** &gt; **Manage Deployment**.

9. On the **Select Groups** page, select **My Trial Users** to deploy the software to that user group, and then click **Add** &gt; **Next**.

10. On the **Deployment Action** page, select **Available Install** from the **Approval** column for your group.

11. Click **Finish**.

The Skype app is now available to install on mobile devices from the company portal, but first you need to install [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] software on PCs and mobile devices.

## <a name="Step5"></a>Step 5: Enroll PCs in Intune
You can install the [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] client software on PCs in the following ways:

-   Users can use an installer provided by the administrator to manually enroll

-   [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] software can be included in an OS image, or deployed using Group Policy

-   End users can self-enroll their device through the [!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)] company portal

Each enrolled PC is linked to the user account that was used to install the client software. Microsoft Intune Endpoint Protection is also installed by default during Intune client installation on PCs. Endpoint Protection helps to secure PCs in your organization by providing real-time protection against potential threats, keeping malicious software definitions up to date, and automatically running scheduled scans. For added security, you can also use Intune policies to manage Windows Firewall settings on managed PCs.

What to know before you start:

-   The user must be an administrator on the PC to install the client software.

-   Self-enrolling requires that Internet Explorer is installed on the client PC.

-   Each time a user self-enrolls a PC, a [!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)] license is used

-   You must use a Microsoft Online Services work or school account to self-enroll a PC. This is the account that you used to sign in, or the administrator account that was created when you signed up for the free trial.

For this trial, follow these steps, which use the self-enrollment approach:

1.  In the [Intune administration console](https://manage.microsoft.com/), click **Admin** &gt; **Company Portal**, and then scroll to the bottom of the screen. Copy the URL shown under **Intune company portal**.

2.  Use Internet Explorer to browse to the company portal URL that you acquired in the previous step, and log in with your administrator credentials.

3.  Click **Add Device**.

4.  Click **Download Software** and then click **Run**.

5.  Click **Next** to start the [!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)] Setup wizard.

6.  When the Setup wizard has completed, click **Finish**.

To learn more about PC management using [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)], see [Install the Windows PC client with Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md).

To learn more about software management using [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)], see [Deploy and configure apps with Microsoft Intune](deploy-and-configure-apps-with-microsoft-intune.md).

## <a name="Step6"></a>Step 6: Enroll mobile devices and install an app
To set up mobile device management with Intune, you must  first set the mobile device management authority,  enable management for device platforms, and enroll your devices with the company portal app. You can then deploy the Microsoft Skype application that you published.

1.  **Make Intune your mobile device management authority**
    In the [Intune administration console](https://manage.microsoft.com/), click **Admin** &gt; **Mobile Device Management**, and click **Set MDM Authority** under **Tasks**.  Click **Yes** in the **MDM Authority** dialog box.

2.  **Enable MDM for your device platform**
    Enable mobile device management for the device platform you want to manage. Depending on your platform, different requirements are needed:

    -   **iOS and Mac OS X**: see [Set up iOS and Mac management with Microsoft Intune](set-up-ios-and-mac-management-with-microsoft-intune.md).

    -   **Android**: Android mobile devices allow users to enroll using the company portal app available from Google Play. No additional configuration in Intune is required.

    -   **Windo ws Phone**: see [Set up Windows Phone management with Microsoft Intune](set-up-windows-phone-management-with-microsoft-intune.md).

3.  **Enroll devices:**

    -   **iOS and Mac OS X** - Install the **Microsoft Intune Company Portal** app from Microsoft Corporation available in the App Store and sign in with Intune user credentials added above. View **Enrolled devices** to add your device.

    -    **Android** - Install the **Intune Company Portal** app from Microsoft Corporation, available on [Google Play](http://go.microsoft.com/fwlink/p/?LinkId=386612), and sign in with the Intune user credentials added above.


    -   **Windows Phone 8.1**- Users install the **Company Portal** app from Microsoft Corporation, available in the Windows Phone store, and sign in with the Intune user credentials added above.  View **Enrolled devices** to add your device.

    -   **Windows Phone 8.0**  - Users click **system settings** &gt; **company apps**, and sign in with Intune user credentials added above. The company portal app is deployed to your phone.

    If prompted for a **Server address**, type “manage.microsoft.com”.

4.  Open the company portal on the mobile device, choose **Apps**, and then install **Microsoft Skype**.

To learn more about mobile device management using [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)], see [Get ready to enroll devices in Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md).

## <a name="Step7"></a>Step 7: Review other Intune options and extras you might want

### Alerts, notifications and reports
In the [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] administration console, **alerts** are used to quickly assess the overall health of managed devices in your organization. You can configure and customize alerts so that they report and display only the information you need for your organization. You can set whether an alert is enabled or disabled, configure the severity, use the display threshold to determine how frequently an alert event must be triggered before an alert is displayed, and also configure settings that are specific to certain types of alerts.

**Notifications** are emails used to inform administrators (and other users)  when certain types of alerts are triggered.

**Reports** are used to answer a range of questions, such as how many PCs have a particular application or update installed, what malware was blocked, or which users needed Remote Assistance over the last month.

To learn more about alerts, notifications, and reports, see [Monitoring and reports with Microsoft Intune](monitoring-and-reports-with-microsoft-intune.md).

### Intune capabilities
[!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] has a wide variety of capabilities beyond those shown in these short setup steps. A few examples of these capabilities include:

-   **Control access to Exchange and Office 365.** For details, see [Manage access to email and SharePoint with Microsoft Intune](manage-access-to-email-and-sharepoint-with-microsoft-intune.md).

-   **Management of corporate-owned iOS devices.** For details, see [Enroll corporate-owned iOS devices in Microsoft Intune](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

-   **Mobile application management.** Managed mobile apps work with mobile application management policies to restrict certain app operations, such as copy and paste and screenshot functionality. For details, see [Configure and deploy mobile application management policies in the Microsoft Intune console](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) and [Manage Internet access using managed browser policies with Microsoft Intune](manage-internet-access-using-managed-browser-policies-with-microsoft-intune.md).

-   **Control access to company resources.** You can deploy certificates, e-mail profiles, VPN profiles and Wi-Fi profiles to mobile devices, making it easier to quickly set up mobile devices. For details, see [Enable access to company resources with Microsoft Intune](enable-access-to-company-resources-with-microsoft-intune.md).

To learn about the full capabilities of [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)], see [Mobile device management capabilities in Microsoft Intune](mobile-device-management-capabilities-in-microsoft-intune.md) and [Windows PC management capabilities in Microsoft Intune](windows-pc-management-capabilities-in-microsoft-intune.md).

To learn more about capabilities that were recently introduced to [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)], see [What's new in Microsoft Intune](what-s-new-in-microsoft-intune.md).

Support options are described in [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md), and you can join discussions about [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] in [Microsoft Intune forums](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod).

## <a name="BKMK_BuyIntune"></a>Step 8: Prepare to move to an Intune paid subscription
If you purchase at least 150 licenses for Microsoft Intune in an eligible plan, you can use the "FastTrack Center Benefit," a service where Microsoft specialists work with you to get your environment ready for Intune. See [Microsoft Intune Service Benefit Description](https://technet.microsoft.com/library/mt228265.aspx).

You can convert your free Intune trial to a paid subscription in the following ways:

-   **Intune Subscription** - Licensed on a per-user basis. For more information, see [How to buy Microsoft Intune](http://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/Purchasing.aspx). After completing your purchase, follow the steps in  [Get started with a paid subscription to Microsoft Intune](get-started-with-a-paid-subscription-to-microsoft-intune.md) and review the additional configuration steps when you're getting started with Intune.

-   **Enterprise Mobility Suite** - Provides [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)], Azure Active Directory Premium, Azure RMS services. Contact your Microsoft account manager or local reseller for more details, or see [information on the Enterprise Mobility Suite](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx) or [Enterprise Mobility Suite pricing](http://www.microsoft.com/en-us/server-cloud/products/enterprise-mobility-suite/Purchasing.aspx).

-   **Enterprise Agreement** (&gt;250 users) - The best licensing program for organizations with more than 250 users. The EA gives you the flexibility to choose among on-premises software and online services to best suit your user needs and help you optimize your technology spend. Contact your Microsoft account manager or local reseller for more details, or see the [Enterprise Volume Licensing site](http://www.microsoft.com/licensing/licensing-options/enterprise.aspx).

-   **Online subscription program** (&lt;250 users) - [Online Services volume licensing](http://www.microsoft.com/licensing/online-services/default.aspx) program is designed specifically for organizations with less than 250 users. Use this program to subscribe, manage, and deploy your [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] services.

### See also
[Get started with a paid subscription to Microsoft Intune](get-started-with-a-paid-subscription-to-microsoft-intune.md)
