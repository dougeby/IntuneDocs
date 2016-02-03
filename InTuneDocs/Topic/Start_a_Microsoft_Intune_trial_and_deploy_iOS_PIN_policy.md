---
title: Start a Microsoft Intune trial and deploy iOS PIN policy
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 06cb9a73-0f17-44b3-b334-86c98020316e
author: Staciebarker
---
# Start a Microsoft Intune trial and deploy iOS PIN policy
These step-by-step instructions help you set up an Intune trial and configure a PIN policy for iOS devices. For a list of other common Intune evaluation tasks  that you can try, see [Common Microsoft Intune evaluation tasks](Common_Microsoft_Intune_evaluation_tasks.md).

These instructions explain:

-   [Review prerequisites for this task](#BKMK_30day_review_prereqs)

-   [Create a free Intune trial account](#BKMK_30day_create_trial_acct)

-   [Create a test user](#BKMK_30day_create_test_user)

-   [Configure an iOS pin policy for the test user](#BKMK_30day_cfg_ios_pin_pol)

-   [Validate that the policy is enforced on an iOS device](#BKMK_30day_validate_pol)

## <a name="BKMK_30day_review_prereqs"></a>Review prerequisites for this task

-   Windows PC with Internet Explorer - for doing administrative tasks

-   iOS 7.1 or later device for testing user policy validation

-   Phone to authenticate yourself during trial sign-up

## <a name="BKMK_30day_create_trial_acct"></a>Create a free Intune trial account
> [!NOTE]
> If you already have an Intune subscription, skip this section and go to the next section.

1.  Using a Windows PC, right-click **Internet Explorer** (IE) and select **InPrivate Browsing**.

    ![](../Image/30-day_trial_walkthrus/30day-start_trial_1-InPrivate.png)

2.  Go to the [Intune sign-up portal](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1), provide the requested information, and click **Next**.

    ![](../Image/30-day_trial_walkthrus/30day-start_trial_2-abt-you.png)

3.  Enter a user ID and password for your admin account and click **Next**. You'll use this ID to log in to the Intune portal to do your admin tasks.

    ![](../Image/30-day_trial_walkthrus/30day-start_trial_3-createID.png)

4.  Enter your cell phone number and click **Text me** to validate your number.

    ![](../Image/30-day_trial_walkthrus/30day-start_trial_4-textme.png)

5.  Save the information shown on the screen, and then click **You're ready to go...**.

    ![](../Image/30-day_trial_walkthrus/30day-start_trial_5-ReadyToGo.png)

## <a name="BKMK_30day_create_test_user"></a>Create a test user

1.  Using a Windows PC, click **Start** to go to the user management page.

    ![](../Image/30-day_trial_walkthrus/30day-crt-user_6-click-start.png)

2.  Click the **+** button to add a user.

    ![](../Image/30-day_trial_walkthrus/30day-crt-user_7-click-plus.png)

3.  On the **Create new user account** page:

    1.  Provide the test user information.

    2.  Select the **Type password** option.

    3.  Clear the **Make this person change their password the next time they sign in** check box.

    4.  Click **Create**.

    ![](../Image/30-day_trial_walkthrus/30day-crt-user_8-add-user-info.png)

4.  On the user creation confirmation page, click **Close**.

    ![](../Image/30-day_trial_walkthrus/30day-crt-user_9-close-confirm.png)

5.  Click the **Refresh** button to see the test user you created.

    ![](../Image/30-day_trial_walkthrus/30day-crt-user_10-refresh-user.png)

## <a name="BKMK_30day_cfg_ios_pin_pol"></a>Configure an iOS pin policy for the test user

1.  Using a Windows PC, set the MDM authority to be Intune:

    1.  Go to [Intune Management console](http://manage.microsoft.com/), log in with your admin account, and click **Start Managing Mobile Devices**. The Mobile Device Management authority page opens.

        ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_11-start-mg-mobl-dev.png)

    2.  Click the **Set Mobile Device Management Authority** link.

        ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_12-link-set-mdm.png)

2.  Enable iOS devices for enrollment. This process sets up a trusted certificate between the Apple Push Notification Service (APNs) and your Intune subscription.

    1.  Click **Enable the iOS and Mac OS X platform**.

        ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_13-enbl-ios-plat.png)

    2.  Click **Download the APNs Certificate Request**.

        ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_14-dwnld-cert-reqst.png)

    3.  Specify a file name and location for your Certificate Signing Request (CSR), and then click **Save**. This file holds the public key that corresponds to a private key held by your Intune subscription.

        ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_15-cert-name-loc.png)

    4.  Click **Apple Push Certificates portal** to open a new tab.

        ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_16-cert-portl-link.png)

    5.  Enter your Apple ID and password, and click **Sign in**. This ID can be the one you use on your iOS device to get apps from the iOS App Store.

        ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_17-id-passw-signin.png)

    6.  Click **Create a Certificate**.

        ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_18-create-cert.png)

    7.  Read Apple’s Terms of Use, select the check box, and click **Accept**.

        ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_19-TOU.png)

    8.  Click **Browse**.

        ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_20-browse.png)

    9. Select the CSR file that you saved earlier, and click **Open**.

        ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_21-CSRfile-open.png)

    10. Click the **Upload** button.

        ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_22-upld-reqst.png)

    11. When you are prompted to download a JSON file, click **Save as**.

        ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_23-json-saveas.png)

    12. Specify a location for your JSON file and click **Save**.

        ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_24-json-save-loc.png)

        If your page doesn’t redirect automatically after a few seconds, click **Cancel**.

        ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_25-json-pg-cancel.png)

    13. To retrieve your newly created certificate file, click **Download**.

        ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_26-dwnld-retrv-cert.png)

    14. When you are prompted to download a PEM file, click **Save as**.

        ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_27-pem-saveas.png)

    15. Specify a location for the PEM file and click **Save**.

        ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_28-pem-save-loc.png)

    16. Return to the Intune Management Console tab, and click the **Upload the APNs Certificate**.

        ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_29-upld-cert.png)

    17. Enter your Apple ID and click **Browse**.

        ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_30-app-id-browse.png)

    18. Select the PEM file you just saved, and click **Open**.

        ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_31-sel-pem-open.png)

    19. Click **Upload**.

        ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_32-pem-upload.png)

        Your APNs certificate is now configured.

        ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_33-apns-confgd.png)

3.  Create a test user group for policy targeting:

    1.  In the left pane, click **Groups**.

        ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_34-clk-groups.png)

    2.  At the far right, click **Create Group**.

        ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_35-crt-group.png)

    3.  Provide a group name, select **All Users** as the parent group, and click **Next**.

        ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_36-name-group.png)

    4.  In the **Start group membership with** field, select **All Users in the Parent group**, and click **Finish**.

        ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_37-all-users-group.png)

4.  Create an iOS PIN policy and target it to the test user group:

    1.  In the left pane, click **Policy**.

        ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_38-clk-policy.png)

    2.  At the far right, click **Add Policy**.

        ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_39-add-policy.png)

    3.  Expand the iOS node, select the **General Configuration** row, and click **Create Policy**.

        ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_40-gen_cfg_pol.png)

    4.  Type a name for the policy,  turn on the option **Require a password to unlock mobile devices**, and set the **Minimum password length** to **4**.

        ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_41-name-policy.png)

    5.  Click **Yes** to deploy the policy.

        ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_42-yes-deploy-pol.png)

    6.  Click the user group previously created, click **Add**, and click **Ok**.

        ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_43-add-pol-to-grp.png)

        You now have an iOS PIN policy that targets your test user group.

        ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_44-policy-applied.png)

## <a name="BKMK_30day_validate_pol"></a>Validate that the policy is enforced on an iOS device

1.  On an iPad, launch the iOS App Store, install the free **Microsoft Intune Company Portal** app, and open it.

    ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_45-cportal-installed.jpg)

2.  Enter your test user account name and password, and tap **Sign in**.

    ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_46-cportal-signin.jpg)

3.  Tap **Enroll** to start enrolling the device in Intune.

    ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_47-tap-enroll.jpg)

4.  On the **Install Profile** screen, tap **Install**.

    ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_48-profile-install-1.jpg)

5.  On the **Install Profile** dialog, tap **Install**.

    ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_49-profile-install-2.jpg)

6.  On the **Warning** screen, tap **Install**.

    ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_50-warning-install-3.jpg)

7.  On the **Remote Management** dialog, tap **Trust**.

    ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_51-remt-mgmt-trust.jpg)

8.  When the management profile finishes installing, tap **Done**. Enrollment is now complete.

    ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_52-profile-done.jpg)

9. When enrollment is complete, tap **OK** and then close the Company Portal app.

    ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_53-devc-enrolled-ok.jpg)

10. When you are prompted to configure a passcode, tap **Continue**.

    ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_54-passcode-req-cont.jpg)

11. Enter your passcode, tap **Continue**, enter your passcode again, and tap **Save**.

    ![](../Image/30-day_trial_walkthrus/30day-cfg-pol_55-passcode-enter.jpg)

12. Press the power button to lock your iPad, slide to unlock it, and see that you now need to enter your passcode to unlock the device.

## See Also
[Get started with a paid subscription to Microsoft Intune](../Topic/Get_started_with_a_paid_subscription_to_Microsoft_Intune.md)
[Common Microsoft Intune evaluation tasks](Common_Microsoft_Intune_evaluation_tasks.md)
[Set up email access for iOS devices using Microsoft Intune](Set_up_email_access_for_iOS_devices_using_Microsoft_Intune.md)

