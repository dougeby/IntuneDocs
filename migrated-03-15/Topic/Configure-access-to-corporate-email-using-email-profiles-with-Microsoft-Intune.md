---
title: Configure access to corporate email using email profiles with Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 10f0cd61-e514-4e44-b13e-aeb85a8e53ae
author: Nbigman
---
# Configure access to corporate email using email profiles with Microsoft Intune
Email profiles in [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] help you create, deploy and monitor Exchange ActiveSync email settings on devices. This lets user’s access corporate email on their personal devices without any required setup on their part.

You can use email profiles to configure the following device types:

-   Devices that run Windows Phone 8 and later

-   Devices that run iOS 7.1 and later

-   Devices that run Samsung KNOX Standard (4.0 and later)

-   Devices that run Windows 10 desktop, Windows 10 Mobile, and later

In addition to configuring an email account on the device, you can also configure synchronization settings such as how much email to synchronize, and depending on the device type, the content types to synchronize.

> [!IMPORTANT]
> Whenever possible, choose the most secure options that your email infrastructure and client operating systems can support. Email profiles provide a convenient method to centrally distribute and manage email settings that your devices already support. [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] does not add email functionality.

## How email profiles are secured
Email profiles can be secured using one of two methods:

### Certificates
When you create the email profile, you choose a SCEP certificate profile that you have previously created in [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]. This is known as the identity certificate and is used to authenticate against a trusted certificate profile (or a root certificate) you created to establish that the user’s device is allowed to connect. The trusted certificate is deployed to the computer that authenticates the email connection, typically, the Exchange server.

For more information about how to create and use certificate profiles in [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], see [Enable access to company resources using certificate profiles with Microsoft Intune](../Topic/Enable-access-to-company-resources-using-certificate-profiles-with-Microsoft-Intune.md).

### Username and password
The user authenticates to the Exchange server by providing their username and password.

The password is not contained in the email profile, so the user will need to supply this when they connect to email.

### Create an email profile

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Policy** &gt; **Add Policy**.

2.  Configure one of the following policy types:

    -   **Email Profile for Samsung KNOX Standard (4.0 and later)**

    -   **Email Profile (iOS 7.1 and later)**

    -   **Email Profile (Windows Phone 8 and later)**

    -   **Email Profile (Windows 10 Desktop and Mobile and later)**

    You can only create and deploy a custom email profile policy. Recommended settings are not available.

    For more information about how to create and deploy policies, see the [Use policies to manage computers and mobile devices with Microsoft Intune](../Topic/Use-policies-to-manage-computers-and-mobile-devices-with-Microsoft-Intune.md) topic.

3.  Use the following table to help you configure Samsung KNOX email profile settings:

    |Setting name|More information|
    |----------------|--------------------|
    |**Name**|Enter a unique name for the email profile.|
    |**Description**|Provide a description that gives an overview of the email profile and other relevant information that helps you to locate it.|
    |**Host**|Specify the hostname of your company Exchange Server that hosts Exchange ActiveSync services.|
    |**Account name**|Specify the display name for the email account as it will appear to users on their devices.|
    |**Username**|Select how the username for the email account will be obtained. Select **Username** for an On-premises Exchange server or select **User Principal Name** for Office 365.|
    |**Email address**|Select how the email address for the user on each device is generated. Select **Primary SMTP Address** to use the primary SMTP address to log into Exchange or use  **User Principal Name** to use the full principal name as the email address.|
    |**Authentication method**|Select either **Username and Password** or **Certificates** as the authentication method used by the email profile.|
    |**Select a client certificate for client authentication (Identity Certificate)**|Select the client SCEP certificate that you previously created that will be used to authenticate the Exchange connection. For more information about how to use certificate profiles in [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], see [Enable access to company resources using certificate profiles with Microsoft Intune](../Topic/Enable-access-to-company-resources-using-certificate-profiles-with-Microsoft-Intune.md).<br /><br />This option is displayed only when the authentication method is **Certificates**.|
    |**Use S/MIME**|Send outgoing email using S/MIME encryption.|
    |**Signing certificate**|Select the signing certificate that will be used to sign outgoing email.<br /><br />This option is displayed only when you select **Use S/MIME**.|
    |**Number of days of email to synchronize**|From the drop-down list, select the number of days of email that you want to synchronize or select **Unlimited** to synchronize all available email.|
    |**Sync schedule**|Select the schedule by which devices will synchronize data from the Exchange Server. You can also select **As Messages arrive** which synchronizes data as soon as it arrives, or **Manual**, where the user of the device must initiate the synchronization.|
    |**Use SSL**|Use Secure Sockets Layer (SSL) communication when sending emails, receiving emails, and communicating with the Exchange Server.<br /><br />For devices that run Samsung KNOX 4.0 or later, you must export your Exchange Server’s SSL certificate and deploy it as an Android Trusted Certificate Profile in [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]. [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] does not support accessing this certificate if it is installed on the Exchange Server by other means.|
    |**Content type to synchronize**|Select the content types that you want to synchronize to devices. Choose from **Email, Contacts, Calendar, Tasks**, or **Notes**.|
    Use the following table to help you configure iOS email profile settings:

    |Setting name|More information|
    |----------------|--------------------|
    |**Name**|Enter a unique name for the email profile.|
    |**Description**|Provide a description that gives an overview of the email profile and other relevant information that helps you to locate it.|
    |**Host**|Specify the hostname of your company Exchange Server that hosts Exchange ActiveSync services.|
    |**Account name**|Specify the display name for the email account as it will appear to users on their devices.|
    |**Username**|Select how the user name for the email account on each device is generated. Select **Primary SMTP Address** to use the primary SMTP address to log into Exchange or use  **User Principal Name** to use the full principal name as the email address.|
    |**Email address**|Select how the email address for the user on each device is generated. Select **Primary SMTP Address** to use the primary SMTP address to log into Exchange or use  **User Principal Name** to use the full principal name as the email address.|
    |**Authentication method**|Select either **Username and Password** or **Certificates** as the authentication method used by the email profile.|
    |**Select a client certificate for client authentication (Identity Certificate)**|Select the client SCEP certificate that you previously created that will be used to authenticate the Exchange connection. For more information about how to use certificate profiles in [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], see [Enable access to company resources using certificate profiles with Microsoft Intune](../Topic/Enable-access-to-company-resources-using-certificate-profiles-with-Microsoft-Intune.md).<br /><br />This option is displayed only when the authentication method is **Certificates**.|
    |**Use S/MIME**|Send outgoing email using S/MIME encryption.|
    |**Signing certificate**|Optionally, select the signing certificate that will be used to sign outgoing email.<br /><br />This option is displayed only when you select **Use S/MIME**.|
    |**Number of days of email to synchronize**|From the drop-down list, select the number of days of email that you want to synchronize or select **Unlimited** to synchronize all available email.|
    |**Use SSL**|Use Secure Sockets Layer (SSL) communication when sending emails, receiving emails, and communicating with the Exchange Server.|
    |**Allow messages to be moved to other email accounts**|Allow users to move email messages between different accounts they have configured on their device.|
    |**Allow email to be sent from third-party applications**|Allow users to send email from apps other than the default email app.|
    |**Synchronize recently used email addresses**|Synchronize the list of email addresses that have been recently used on the device.|
    Use the following table to help you configure Windows Phone email profile settings:

    |Setting name|More information|
    |----------------|--------------------|
    |**Name**|Enter a unique name for the email profile.|
    |**Description**|Provide a description that gives an overview of the email profile and other relevant information that helps you to locate it.|
    |**Host**|Specify the hostname of your company Exchange Server that hosts Exchange ActiveSync services.|
    |**Account name**|Specify the display name for the email account as it will appear to users on their devices.|
    |**Username**|Select how the user name for the email account on each device is generated. Select **Primary SMTP Address** to use the primary SMTP address to log into Exchange or use  **User Principal Name** to use the full principal name as the email address.|
    |**Email Address**|Select how the email address for the user on each client device is generated. Select **Primary SMTP Address** to use the primary SMTP address to log into Exchange or use  **User Principal Name** to use the full principal name as the email address.|
    |**Number of days of email to synchronize**|From the drop-down list, select the number of days of email that you want to synchronize or select **Unlimited** to synchronize all available email.|
    |**Sync Schedule**|Select the schedule by which devices will synchronize data from the Exchange Server. You can also select **As Messages arrive** which synchronizes data as soon as it arrives, or **Manual**, where the user of the device must initiate the synchronization.|
    |**Use SSL**|Use Secure Sockets Layer (SSL) communication when sending emails, receiving emails, and communicating with the Exchange Server.|
    |**Content type to synchronize**|Select the content types that you want to synchronize to devices. Choose from **Email, Contacts, Calendar**, or **Tasks**.|
    > [!IMPORTANT]
    > If you have deployed an email profile and then wish to change the values for **Exchange ActiveSync host** or **Email address**, you must delete the existing email profile and create a new one with the required values.

4.  When you are finished, click **Save Policy**.

The new policy displays in the **Configuration Policies** node of the **Policy** workspace.

### Deploy an email profile

1.  Deploy the email profile to one or more groups of users or devices in your organization.

For more information about how to deploy policies, see [Use policies to manage computers and mobile devices with Microsoft Intune](../Topic/Use-policies-to-manage-computers-and-mobile-devices-with-Microsoft-Intune.md).

A status summary and alerts on the **Overview** page of the **Policy** workspace identify issues with the policy that require your attention. Additionally, a status summary appears in the **Dashboard** workspace.

> [!NOTE]
> If you want to remove an email profile from a device, edit the deployment and remove any groups of which the device is a member.

## Next Steps
After successful deployment, user’s devices will be provisioned with the correct settings to access corporate email.

## See Also
[Enable access to company resources with Microsoft Intune - deleted](../Topic/Enable-access-to-company-resources-with-Microsoft-Intune---deleted.md)

