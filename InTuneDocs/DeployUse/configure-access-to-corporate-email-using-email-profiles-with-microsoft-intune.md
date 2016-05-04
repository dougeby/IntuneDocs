---
# required metadata

title: Configure access to corporate email using email profiles | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 10f0cd61-e514-4e44-b13e-aeb85a8e53ae

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Configure access to corporate email using email profiles with Microsoft Intune
Many mobile platforms include a *native* email client that ships as part of the operating system.  Some of these clients can be configurable using email profiles, described in this topic.

If you need additional data loss prevention (DLP), choose [Conditional access](restrict-access-to-email-and-o365-services-with-microsoft-intune.md), which controls access to the user's
 mailbox for any email client, including native email clients.

Email profile settings can be used to configure email access settings for specific email clients on mobile devices.   Most mobile platforms include a *native* email client that ships as part of the operating system.  On supported platforms the native email clients can be configured by Microsoft Intune to enable users to access their corporate email on the personal devices without any setup.  

IT administrators or users may also choose to install alternative email clients, for example, Microsoft Outlook for Android or iOS.  These email clients may not support email profiles and are not configurable using Microsoft Intune email profiles.  

You can use email profiles to configure the native email client on the following device types:
-	Windows Phone 8 and later
-	Windows 10 desktop, Windows 10 Mobile, and later
-	iOS 7.1 and later
-	Samsung KNOX Standard (4.0 and later)


In addition to configuring an email account on the device you can configure synchronization settings such as how much email to synchronize, and depending on the device type, the content types to synchronize.

## Secure email profiles
You can secure email profiles using one of two methods:

### Certificates
When you create the email profile, you choose a certificate profile that you have previously created in Intune. This is known as the identity certificate and is used to authenticate against a trusted certificate profile (or a root certificate) to establish that the user’s device is allowed to connect. The trusted certificate is deployed to the computer that authenticates the email connection, typically, the native mail server.

For more information about how to create and use certificate profiles in Intune, see [Secure resource access with  certificate profiles](secure-resource-access-with-certificate-profiles.md).

### Username and password
The user authenticates to the native mail server by providing their username and password.

The password is not contained in the email profile, so the user will need to supply this when they connect to email.

### Create an email profile

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Policy** &gt; **Add Policy**.

2.  Configure one of the following policy types:

    -   **Email Profile for Samsung KNOX Standard (4.0 and later)**

    -   **Email Profile (iOS 7.1 and later)**

    -   **Email Profile (Windows Phone 8 and later)**

    -   **Email Profile (Windows 10 Desktop and Mobile and later)**

    You can only create and deploy a custom email profile policy. Recommended settings are not available.

3.  Use the following table to help you configure email profile settings:
    |Setting name|More information|
    |----------------|--------------------|
    |**Name**|Unique name for the email profile.|
    |**Description**|A description that help you identify this profile.|
    |**Host**|The hostname of your company server that hosts your native email service.|
    |**Account name**|The display name for the email account as it will appear to users on their devices.|
    |**Username**|How the username for the email account will be obtained. Select **Username** for an On-premises Exchange server or select **User Principal Name** for Office 365.|
    |**Email address**|How the email address for the user on each device is generated. Select **Primary SMTP Address** to use the primary SMTP address to log into Exchange or use  **User Principal Name** to use the full principal name as the email address.|
    |**Authentication method** (Samsung KNOX and iOS)|Select either **Username and Password** or **Certificates** as the authentication method used by the email profile.|
    |**Select a client certificate for client authentication (Identity Certificate)** (Samsung KNOX and iOS)|Select the client SCEP certificate that you previously created that will be used to authenticate the Exchange connection. For more information about how to use certificate profiles in Intune, see [Secure resource access with  certificate profiles](secure-resource-access-with-certificate-profiles.md).<br /><br />This option is displayed only when the authentication method is **Certificates**.|
    |**Use S/MIME** (Samsung KNOX and iOS)|Send outgoing email using S/MIME encryption.|
    |**Signing certificate** (Samsung KNOX and iOS)|Select the signing certificate that will be used to sign outgoing email.<br /><br />This option is displayed only when you select **Use S/MIME**.|
    |**Number of days of email to synchronize**|The number of days of email that you want to synchronize or select **Unlimited** to synchronize all available email.|
    |**Sync schedule** (Samsung KNOX, Windows Phone 8 and later, Windows 10)|Select the schedule by which devices will synchronize data from the Exchange Server. You can also select **As Messages arrive** which synchronizes data as soon as it arrives, or **Manual**, where the user of the device must initiate the synchronization.|
    |**Use SSL**|Use Secure Sockets Layer (SSL) communication when sending emails, receiving emails, and communicating with the Exchange Server.<br /><br />For devices that run Samsung KNOX 4.0 or later, you must export your Exchange Server’s SSL certificate and deploy it as an Android Trusted Certificate Profile in Intune. Intune does not support accessing this certificate if it is installed on the Exchange Server by other means.|
    |**Content type to synchronize**|Select the content types that you want to synchronize to devices.|

    > [!IMPORTANT]
    > If you have deployed an email profile and then wish to change the values for **host** or **Email address**, you must delete the existing email profile and create a new one with the required values.

4.  When you are finished, click **Save Policy**.

The new policy displays in the **Configuration Policies** node of the **Policy** workspace.

## Deploy the policy

1.  In the **Policy** workspace, select the policy you want to deploy, then click **Manage Deployment**.

2.  In the **Manage Deployment** dialog box:

    -   **To deploy the policy** - Select one or more groups to which you want to deploy the policy, then click **Add** &gt; **OK**.

    -   **To close the dialog box without deploying it** - Click **Cancel**.

A status summary and alerts on the **Overview** page of the **Policy** workspace identify issues with the policy that require your attention. Additionally, a status summary appears in the Dashboard workspace.

> [!NOTE]
> If you want to remove an email profile from a device, edit the deployment and remove any groups of which the device is a member.


