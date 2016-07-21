---
# required metadata

title: Set up email access for iOS devices | Microsoft Intune
description: set up email access for iOS devices using Intune
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 3853673d-290a-400f-8e45-d55e39d42acd

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Set up email access for iOS devices using Microsoft Intune
When devices are enrolled with Intune, you can configure the devices so that their users can access company email. One way to accomplish that for specific device types is to create and deploy an **email profile**. Email profiles are a kind of Intune policy that sets up and connects a user’s device to your company email service.
Using an email profile makes email access automatic for enrolled devices, which prevents you from having to manually set up the device. An email profile also ensures that all end users are setting up access in the same way and with the same basic settings.

## Goals of this walkthrough

- To create and deploy an email profile for iOS devices
- To verify that the email profile policy has been applied successfully

## What you need before starting this walkthrough

- An Exchange Server, either on-premises or hosted on Azure as part of your Office/E3 subscription.
- The host name of your company’s Exchange server. This is the fully qualified domain name (FQDN), for example, **contosodemo55.onmicrosoft.com**.
- A user group to deploy the email profile to. If you completed the [Start a Microsoft Intune trial and deploy iOS PIN policy](start-a-microsoft-intune-trial-and-deploy-ios-pin-policy.md) walkthrough, you can use the **GroupDemo** user group you created for it.
- Enrolled iOS devices to deploy the profile to. Again, if you completed the [Start a Microsoft Intune trial and deploy iOS PIN policy](start-a-microsoft-intune-trial-and-deploy-ios-pin-policy.md) walkthrough, you will have enrolled some iOS devices.

## Steps for creating and deploying an email profile for iOS devices

For this walkthrough we will be using the hosted Exchange server that comes with a trial subscription.
1. In the Intune console, click **Policy**, and then click **Add Policy**.
![<add-policy>](./media/Email-Walkthrough/Email-Walkthrough-1.png)
2. In the **Create a New Policy** dialog box, expand **iOS**, select **Email Profile**, and then click **Create Policy**.  
![<ios-email-profile-policy>](./media/Email-Walkthrough/Email-Walkthrough-2.png)
3. On the create policy page, enter a name for the policy, like **iOS email profile - user-password**, and a description. You might have multiple email profiles for different device types and different authentication methods, so you can use the name to show what the profile is for.
4. Enter the Exchange host name. Since we are using the Exchange server hosted on Azure, for hostname we simply input: **outlook.office365.com**
![<add-exchange-host-name>](./media/Email-Walkthrough/Email-Walkthrough-3.png)
5. Enter the account name that will be shown to users of the device to help them identify the email service. For example, **Contoso Email**.
6. Since we’re using username and password to authenticate the user for the Exchange service, just leave the username and password settings the way they are.
7. Adjust the synchronization settings to meet your requirements. For now, just use the defaults, unless there’s a specific one you want to change.  
8. Click **Save Policy**.
9. A dialog box appears asking if you want to deploy the policy now. Click **Yes**.
![<deploy-policy-now-dialog>](./media/Email-Walkthrough/Email-Walkthrough-4.png)
10. In the window that appears next, select the user group you want to deploy the email profile to, click **Add**, and then click **OK**.  
![<finish-add-policy>](./media/Email-Walkthrough/Email-Walkthrough-5.png)  
After you click **OK**, the policy will start to flow down to enrolled devices in a minute or two.

## Steps to verify that the profile has been successfully applied

To verify that the profile has been applied, you will need access to one of the devices to which you deployed the email profile.
1. On the iOS device, open the Mail app.
The app will prompt you for the user’s email username and password.  
![<verify-policy-add-password>](./media/Email-Walkthrough/Email-Walkthrough-6.png)
2. Enter the username and password for the user’s Exchange email account, and then tap **OK**.
 The Mail app opens to the Exchange account, and email begins synchronizing to the device.
![<exchange-account-opens>](./media/Email-Walkthrough/Email-Walkthrough-7.png)
3. Check the account settings in for the Mail app to make sure the account name is the same one you entered in the email profile (for example, **Contoso Mail**) and the synchronization settings are set correctly.
![<check-account-settings>](./media/Email-Walkthrough/Email-Walkthrough-8.png)
![<check-email-account-name>](./media/Email-Walkthrough/Email-Walkthrough-9.png)  
  If it appears the email profile hasn’t been automatically applied to the device, you can manually apply the policy using the Company Portal app on the device.
1. Open the Company Portal app.
2. Tap **My Devices**.
3. Tap the name of your device.
![<tap-device-name](./media/Email-Walkthrough/Email-Walkthrough-10.png)
4. Tap **Sync** > **Check Compliance**.
![<tap-sync-check-device>](./media/Email-Walkthrough/Email-Walkthrough-11.png)
After a few moments the email profile gets applied to the device. After that, you can follow the verification steps to make sure the profile was applied correctly.

## See Also
[Intune evaluation guide](get-started-with-a-30-day-trial-of-microsoft-intune.md)
