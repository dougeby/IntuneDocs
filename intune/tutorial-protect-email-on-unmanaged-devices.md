---
# required metadata

title: Tutorial - Protect Exchange Online email on unmanaged devices
titlesuffix: Microsoft Intune
description: Learn to secure Office 365 Exchange Online with Intune app protection policies and Azure AD conditional access.
keywords:
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 10/02/2018
ms.topic: tutorial
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Tutorial: Protect Exchange Online email on managed devices

Learn about using app protection policies with conditional access to protect Exchange Online, even when devices aren't enrolled in a device management solution like Intune. In this tutorial, you'll learn how to: 
  - Create an Intune app protection policy for the Outlook app. You'll limit what the user can do with app data by preventing "Save As" and restriction cut, copy, and paste actions. 
  - Create Azure Active Directory (Azure AD) conditional access policies that allow only the Outlook app to access company email in Exchange Online. Also require multi-factor authentication (MFA) for Modern authentication clients, like Outlook for iOS and Android.

## Prerequisites
  - You'll need a test tenant with the following subscriptions for this tutorial:
    - Azure Active Directory Premium ([free trial](https://azure.microsoft.com/free/?WT.mc_id=A261C142F))
    - Intune subscription ([free trial](free-trial-sign-up.md))
    - Office 365 Business subscription that includes Exchange ([free trial](https://go.microsoft.com/fwlink/p/?LinkID=510938))
  - Before you begin, create a test device profile for iOS devices by following the steps in [Quickstart: Create an email device profile for iOS](quickstart-email-profile.md).

## Sign in to Intune

Sign in to [Intune](https://aka.ms/intuneportal) as a Global Administrator or an Intune Service Administrator. Intune is located in the Azure portal by choosing **All services** > **Intune**.

## Create the app protection policy
For this tutorial, we’ll set up an Intune app protection policy for the Outlook app to put app-layer protections in place. We will require a PIN to open the app in a work context, limit data sharing between Outlook and other apps, and prevent company app data from being saved to a personal storage location.

1.	In Intune, select **Client apps** > **App protection policies** > **Add a policy**.
2.	In **Name**, enter **Outlook app policy test**.
3.	In **Description**, enter **Outlook app policy test**.
4.	Select **Apps**. In the apps list, select **Outlook**, and then choose **Select**.
5.	Select **Settings**. 
6.	Select **Create**.
7.	Under **Data relocation**, for this tutorial select these settings:

    - For **Allow app to transfer data to other apps**, select **None**.
    - For **Allow app to receive data from other apps**, select **None**.
    - For **Prevent “Save As” **, select **Yes**.
    - For **Restrict cut, copy, and paste with other apps**, select **Blocked**.
   
     ![Select the Outlook app protection policy data relocation settings](media/tutorial-protect-email-on-enrolled-devices/outlook-app-data-relocation.png)
    
8.	Under **Access Actions**, for this tutorial select these settings:

    - For **Require PIN for access**, select **Yes**.
    - For **Require corporate credentials for access**, select **Yes**.
    - Leave all other settings at their default values.
 
     ![Select the Outlook app protection policy access actions](media/tutorial-protect-email-on-enrolled-devices/outlook-app-access-actions.png)

9.	Select **OK**.
10.	Select **Create**.

## Create conditional access policies
Now we’ll create two conditional access policies that require devices to use the approved Outlook app: one for clients that use Modern Authentication (like Outlook for iOS and Outlook for Android), and one for Exchange Active Sync clients. We need two separate policies because Exchange Active Sync doesn't currently support MFA or any condition other than device platform. Because we want to require MFA for Modern authentication clients, a separate policy is needed. Conditional access policies are configurable in either the Azure AD portal or the Intune portal. Since we’re already in the Intune portal, we’ll create the policy here.
### Create an MFA policy for Modern Authentication clients
1.	In Intune, select **Conditional access** > **Policies** > **New policy**.
1.  In **Name**, enter **Test policy for modern auth clients**. 
3.	Under **Assignments**, select **Users and groups**. On the **Include** tab, select **All users**, and then select **Done**.

4.	Under **Assignments**, select **Cloud apps**. Because we want to protect Office 365 Exchange Online email, we'll select it by following these steps:
     
    1. On the **Include** tab, choose **Select apps**.
    2. Choose **Select**. 
    3. In the applications list, select **Office 365 Exchange Online**, and then choose **Select**. 
    4. Select **Done**.
  
    ![Select the Office 365 Exchange Online app](media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-cloud-apps.png)

5.	Under **Assignments**, select **Conditions** > **Device platforms**.
     
    1. Under **Configure**, select **Yes**.
    2. On the **Include** tab, select **All platforms (including unsupported)**, and then select **Done**. 
    3. Select **Done** again.
   
    ![Select the Office 365 Exchange Online app](media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-cloud-device-platforms.png)

6.	Under **Assignments**, select **Conditions** > **Client apps**.
     
    1. Under **Configure**, select **Yes**.
    2. Select **Mobile apps and desktop clients** and **Modern authentication clients** (which refers to apps like Outlook for iOS and Outlook for Android). Clear all other check boxes.
    3. Select **Done**, and then select **Done** again.
    
    ![Select the Office 365 Exchange Online app](media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-client-apps.png)

7.	Under **Access controls**, select **Grant**. 
     
    1. On the **Grant** pane, select **Grant access**.
    2. Select **Require multi-factor authentication**.
    4. Select **Require approved client app**.
    5. Under **For multiple controls**, select **Require all the selected controls**. This setting ensures that both requirements you selected are enforced when a device tries to access email.
    6. Choose **Select**.
     
    ![Select the Office 365 Exchange Online app](media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-grant-access.png)

8.	Under **Enable policy**, select **On**.
     
    ![Select the Office 365 Exchange Online app](media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-enable-policy.png)

9.	Select **Create**.

### Create a policy for Exchange Active Sync clients
1.	In Intune, select **Conditional access** > **Policies** > **New policy**.
2.  In **Name**, enter **Test policy for EAS clients**. 
3.	Under **Assignments**, select **Users and groups**. On the **Include** tab, select **All users**, and then select **Done**.

4.	Under **Assignments**, select **Cloud apps**. Because we want to protect Office 365 Exchange Online email, we'll select it by following these steps:
     
    1. On the **Include** tab, choose **Select apps**.
    2. Choose **Select**. 
    3. In the applications list, select **Office 365 Exchange Online**, and then choose **Select**. 
    4. Select **Done**.
  
    ![Select the Office 365 Exchange Online app](media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-cloud-apps.png)

5.	Under **Assignments**, select **Conditions** > **Device platforms**.
     
    1. Under **Configure**, select **Yes**.
    2. On the **Include** tab, select **All platforms (including unsupported)**, and then select **Done**. 
    3. Select **Done** again.
   
    ![Select the Office 365 Exchange Online app](media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-cloud-device-platforms.png)

6.	Under **Assignments**, select **Conditions** > **Client apps**.
     
    1. Under **Configure**, select **Yes**.
    2. Select **Mobile apps and desktop clients**.
    3. Select **Exchange ActiveSync clients** and **Apply policy only to supported platforms**. Clear all other check boxes.
    4. Select **Done**, and then select **Done** again.
    
    ![Select the Office 365 Exchange Online app](media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-client-apps.png)

7.	Under **Access controls**, select **Grant**. 
     
    1. On the **Grant** pane, select **Grant access**.
    4. Select **Require approved client app**. Clear all other check boxes.
    6. Choose **Select**.
     
    ![Select the Office 365 Exchange Online app](media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-grant-access.png)

8.	Under **Enable policy**, select **On**.
     
    ![Select the Office 365 Exchange Online app](media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-enable-policy.png)

9.	Select **Create**.

## Try it out
With the policies you’ve created, any iOS device that attempts to sign in to Office 365 email will need to enroll in Intune and use the Outlook mobile app for iOS. To test this scenario on an iOS device, try signing in to Exchange Online using credentials for a user in your test tenant. You’ll be prompted to enroll the device and install the Outlook mobile app.
1. To test on an iPhone, go to **Settings** > **Passwords & Accounts** > **Add Account** > **Exchange**.
2. Enter the email address for a user in your test tenant, and then press **Next**.
3. Press **Sign In**.
4. Enter the test user's password, and press **Sign in**.
5. The message **More information is required** appears, which means you're being prompted to set up MFA. Go ahead and set up an additional verification method.
6. Next you'll see a message that says you are trying to open this resource with an app that hasn't been approved by your IT department. This means you are being blocked from using the native mail app. Cancel the sign-in.
7.  Open the Outlook app and select Settings > Add Account > Add Email Account.
8. Enter the email address for a user in your test tenant, and then press **Next**.
9. Press **Sign in with Office 365**. You'll be prompted for additional authentication and registration.

## Clean up resources
When the test policies are no longer needed, you can remove them.
1. Sign in to the [Intune](https://aka.ms/intuneportal) as a Global Administrator or an Intune Service Administrator.
2. Select **Device Compliance** > **Policies**.
3. In the **Policy Name** list, select the context menu (**...**) for your test policy, and then select **Delete**. Select **OK** to confirm.
4. Select **Conditional Access** > **Policies**.
5. In the **Policy Name** list, select the context menu (**...**) for each of your test policies, and then select **Delete**. Select **Yes** to confirm.

 ## Next steps 
In this tutorial, you created policies that require iOS devices to enroll in Intune and use the Outlook app to access Exchange Online email. To learn about using Intune with conditional access to protect other apps and services, including Exchange Active Sync clients for Office 365 Exchange Online, see [Set up conditional access](conditional-access.md).
