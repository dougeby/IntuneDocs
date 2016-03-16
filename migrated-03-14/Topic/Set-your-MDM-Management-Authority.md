---
title: Set your MDM Management Authority
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 1bc5a59e-8402-4e46-a5f6-95af6147118b
author: NathBarn
---
# Set your MDM Management Authority
Before you can enroll mobile devices, you must declare [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] or [!INCLUDE[cmshort](../Token/cmshort_md.md)] as your *mobile device management authority*. A  *mobile device management authority* defines the single management service with permission to manage a set of devices.  Solutions for the mobile device management authority include [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], Configuration Manager with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], or Office 365 MDM solutions.

> [!IMPORTANT]
> Consider carefully whether you want to manage mobile devices using Intune only, System Center Configuration Manager with Intune integration, or using Office 365. After you set the mobile device management authority to either of these options, it cannot be changed again. If you're unsure of your options, see [Ways to do enterprise mobility](../Topic/Ways-to-do-enterprise-mobility.md).

## Make Intune your MDM authority
**Set mobile device management authority**

### <a name="BKMK_Set_MDM_Authority"></a>Set mobile device management authority as Intune

1.  In the [Microsoft Intune administration console](http://manage.microsoft.com) click **Admin** &gt; **Mobile Device Management**.

2.  In the **Tasks** list, click **Set Mobile Device Management Authority**. The **Set MDM Authority** dialog box opens.

    ![](../Image/Intune-MDM-Authority.bmp)

3.  Intune requests confirmation that you want Intune as your MDM authority. Check the box and then click **Yes** to use Microsoft Intune to manage mobile devices.

## Make Configuration Manager your MDM authority
To set [!INCLUDE[cmshort](../Token/cmshort_md.md)] as your mobile device management authority and begin managing devices with [!INCLUDE[cmshort](../Token/cmshort_md.md)], you must complete the following steps:

1.  Subscribe to [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]

2.  Set [!INCLUDE[cmshort](../Token/cmshort_md.md)] as your MDM authority

3.  Configure the Microsoft Intune Connector role

### <a name="bkmk_witsub"></a>Configuring the Microsoft Intune Subscription
The [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] subscription lets you specify your configuration settings for the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] service. This includes specifying which users can enroll their devices and defining which mobile device platforms to manage. When you have created your subscription, you can then install the Microsoft Intune connector site system role that lets you connect to the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] service. This connector site system role will push settings and applications to the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] service. The [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] subscription performs the following:

-   Retrieves the certificate that the Microsoft Intune connector requires to connect to the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] service.

-   Defines the user collection that enables users to enroll mobile devices.

-   Defines and configures the mobile platforms that you want to support.

#### <a name="bkmk_subscription"></a>To create the Microsoft Intune subscription

1.  In the [!INCLUDE[cmshort](../Token/cmshort_md.md)] console, click **Administration**.

2.  Choose the steps that are appropriate for your version of [!INCLUDE[cmshort](../Token/cmshort_md.md)]:

    **For [!INCLUDE[cm5short](../Token/cm5short_md.md)] SP1:**

    -   In the **Administration** workspace, expand **Hierarchy Configuration**, and click **Microsoft Intune Subscriptions**.

    -   On the **Home** tab, click **Create Microsoft Intune Subscription**.

    **For [!INCLUDE[cm5long](../Token/cm5long_md.md)] SP2 and**
    **System Center R2 Configuration Manager 2012 SP1:**

    1.  In the **Administration** workspace, expand **Cloud Services**, and click **Microsoft Intune Subscriptions**.

    2.  On the **Home** tab, click **Add Microsoft Intune Subscription**.

3.  On the **Introduction** page of the Create Microsoft Intune Subscription Wizard, review the text and click **Next**.

4.  On the **Subscription** page, click **Sign in** and sign in by using your work or school account. In the **Set the Mobile Device Management Authority** dialog, select the check box to only manage mobile devices by using [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] through the [!INCLUDE[cmshort](../Token/cmshort_md.md)] console. To continue with your subscription, you must select this option.

    > [!IMPORTANT]
    > Once you select [!INCLUDE[cmshort](../Token/cmshort_md.md)] as your management authority, you cannot change the management authority to [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] in the future.

5.  Click the privacy links to review them, and then click **Next**.

6.  On the **General** page, specify the following options, and then click **Next**.

    -   **Collection**: Specify a user collection that contains users who will enroll their mobile devices.

        > [!NOTE]
        > If a user is removed from the collection, the user’s device will continue to be managed for up to 24 hours when the user record is removed from the user database.

    -   **Company name**: Specify your company name.

    -   **URL to company privacy documentation**: If you publish your company privacy information to a link that is accessible from the Internet, provide a link that users can access from the company portal, for example http://www.contoso.com/CP_privacy.html. Privacy information can clarify what information users are sharing with your company.

    -   **Color scheme for company portal**: Optionally, change the default color of blue for the company portals.

    -   **Configuration Manager site code**: Specify a site code for a primary site to manage the mobile devices.

        > [!NOTE]
        > Changing the site code affects only new enrollments and does not affect existing enrolled devices.

7.  On the **Company Contact Information** page, specify the company contact information that is displayed in the company portal, and then click **Next**.

8.  On the **Company Logo** page, choose whether to display a logo in the company portal, and then click **Next**.

9. Prior to [!INCLUDE[cmshort](../Token/cmshort_md.md)] SP2, on the **Platforms** page, select the device types that you want to manage and review the platform requirements, and then click **Next**. For each device type that you select, you must configure additional options. Use the procedures that follow for more information about those options. After you have configured these additional options, click **Next**.

10. Complete the wizard.

### <a name="bkmk_WITconn"></a>The Microsoft Intune Connector Site System Role
The Microsoft Intune connector sends settings and software deployment information to [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] and retrieves status and inventory messages from mobile devices. The [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] service acts as a gateway that communicates with mobile devices and stores settings.

> [!NOTE]
> The Microsoft Intune connector site system role may only be installed on a central administration site or stand-alone primary site.

#### <a name="bkm_connector"></a>To configure the Microsoft Intune Connector role

1.  In the [!INCLUDE[cmshort](../Token/cmshort_md.md)] console, click **Administration**.

2.  In the **Administration** workspace, expand **Site Configuration**, and then click **Servers and Site System Roles**.

3.  Add the [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] connector role to a new or existing site system server by using the associated step:

    -   New site system server: On the **Home** tab, in the **Create** group, click **Create Site System Server** to start the Create Site System Server Wizard.

    -   Existing site system server: Click the server on which you want to install the Microsoft Intune connector role. Then, on the **Home** tab, in the **Server** group, click **Add Site System Roles** to start the Add Site system Roles Wizard.

4.  On the **System Role Selection** page, select **Microsoft Intune Connector**, and click **Next**.

5.  Complete the wizard.

#### How does the Microsoft Intune Connector Authenticate with the Microsoft Intune Service?
The Microsoft Intune Connector extends [!INCLUDE[cmshort](../Token/cmshort_md.md)] by establishing a connection to the cloud-based [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] service that manages mobile devices over the Internet. The Microsoft Intune Connection authenticates with the [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] service as follows:

1.  When you create a [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] subscription in the [!INCLUDE[cmshort](../Token/cmshort_md.md)] console, the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] admin is authenticated by connecting to Azure Active Directory, which redirects to the respective ADFS server to prompt for user name and password. Then, [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] issues a certificate to the tenant.

2.  The certificate from step 1 is installed on the Microsoft Intune Connector site role and is used to authenticate and authorize all further communication with the Microsoft Intune service.

