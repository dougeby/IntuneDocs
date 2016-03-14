---
title: Troubleshoot device enrollment in Intune
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 6982ba0e-90ff-4fc4-9594-55797e504b62
author: Nbigman
---
# Troubleshoot device enrollment in Intune

## Device enrollment issues
Listed here are some device enrollment issues and how to troubleshoot and resolve them.

> [!NOTE]
> Your managed device users can collect enrollment logs for you to review. Instructions for collecting the logs are provided in  [Intune: sending troubleshooting info to IT ](https://www.microsoft.com/en-us/download/details.aspx?id=46391).

### Device Cap reached
**Issue:** A user receives an error on their device during enrollment, such as a **Company Portal Temporarily Unavailable** error on an iOS device, and the DMPdownloader.log on Configuration Manager contains the error **DeviceCapReached**.

**Resolution:** By design, users can enroll no more than 5 devices.

##### Check number of devices enrolled and allowed

1.  Validate in the Intune admin portal that the user has no more than 5 devices assigned

2.  Check in the Intune admin portal under Admin\Mobile Device Management\Enrollment Rules that the Device enrollment limit is set to 5

Mobile device users can delete devices at the following URL: [https://byodtestservice.azurewebsites.net/](https://byodtestservice.azurewebsites.net/).

Administrators can delete devices in the Azure Active Directory portal:

##### To delete devices in the Azure Active Directory portal

1.  Browse to [http://aka.ms/accessaad](http://aka.ms/accessaad) or click **Admin** &gt; **Azure AD** from [https://portal.office.com](https://portal.office.com).

2.  Login with your Org ID using the link on the left side of the page.

3.  Create an Azure Subscription if you don’t have one. This should not require a credit card or payment if you have a paid account (click the **Register your free Azure Active Directory** subscription link).

4.  Select **Active Directory** and then select your organization.

5.  Select the **Users** tab.

6.  Select the user whose devices you want to delete.

7.  Click **Devices**.

8.  Remove devices as appropriate, such as those that are no longer in use, or those that have inaccurate definitions.

> [!NOTE]
> You can avoid the device enrollment cap by using Device Enrollment Managers, as described in [Enroll corporate-owned devices with the Device Enrollment Manager in Microsoft Intune](../Topic/Enroll-corporate-owned-devices-with-the-Device-Enrollment-Manager-in-Microsoft-Intune.md).
> 
> A user account which is added to Device Enrollment Managers group will not be able to complete enrollment when Conditional Access policy is enforced for that specific user login.

### Profile installation failed
**Issue:** A user receives a **Profile installation failed** error on an iOS or Android device.

##### Troubleshooting steps for failed profile installation

1.  Confirm that the user has been assigned an appropriate license for the version of the Intune service you are using.

2.  Confirm that the device is not already enrolled with another MDM provider or that it does not already have a management profile installed.

3.  For an iOS device, navigate to [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com) and try to install the profile when prompted.

4.  Confirm that Safari for iOS and Chrome for Android are the default browsers and that cookies are enabled.

### Company Portal Temporarily Unavailable
**Issue:** A user receives a **Company Portal Temporarily Unavailable** error on their device.

##### Troubleshooting Company Portal Temporarily Unavailable error

1.  Remove the Intune Company Portal app from the device.

2.  On the device, open the browser, browse to [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com), and attempt a user login.

3.  If the user fails to log in, have them try another network.

4.  If that fails, validate that the user’s credentials have synced correctly with Azure Active Directory.

5.  If the user successfully logs in, an iOS device will prompt you to install the Intune Company Portal app and enroll. On an Android device you will need to manually install the Intune Company Portal app, after which you can retry enrolling.

### MDM authority not defined
**Issue:** A user receives an **MDM authority not defined** error.

##### Troubleshooting MDM authority not defined error

1.  Verify that the MDM Authority has been set appropriately for the version of the Intune service you are using  , that is, for Intune, O365 MDM, or System Center Configuration Manager with Intune. For [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)],  the MDM Authority is set in **Admin** &gt; **Mobile Device Management**. For [!INCLUDE[cmshort](../Token/cmshort_md.md)] with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], you set it when configuring the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] connector,  and in O365 it's a setting **Mobile Devices**.

    > [!NOTE]
    > One you set the MDM authority, you can only change it by contacting Support, as described in [How to get support for Microsoft Intune](../Topic/How-to-get-support-for-Microsoft-Intune.md).

2.  Verify that the user’s credentials have synced correctly with Azure Active Directory, by checking that their UPN matches the Active Directory information in the Account Portal.
    If the UPN does not match the Active Directory information:

    1.  Turn off DirSync on the local server

    2.  Delete the mismatched user from the **Intune Account Portal** user list.

    3.  Wait about one hour to allow the Azure service to remove the incorrect data.

    4.  Turn on DirSync again and check if the user is now synced properly

3.  In a scenario where you are using System Center Configuration Manager with Intune, verify that the user has a valid Cloud User ID:

    1.  Open SQL Management Studio.

    2.  Connect to the appropriate DB

    3.  Open the databases folder and find and open the **CM_DBName** folder, where DBName is the name of the customer database.

    4.  At the top, click New Query  and execute the following queries:

        -   To see all users: 
            `select * from [CM_ DBName].[dbo].[User_DISC]`

        -   To see Specific Users, use the following query, where %testuser1% represents username@domain.com for the user you want to look up:
            `select * from [CM_ DBName].[dbo].[User_DISC] where User_Principal_Name0 like '%testuser1%'`

        After writing the query click **!Execute**. 
        Once the results have been returned, look for the clouduser ID.  If no ID is found, the user isn't licensed to use Intune.

### Mobile devices disappear when using System Center Configuration Manager with Intune
**Issue:** After successfully enrolling a mobile device to Configuration Manager it disappears from the mobile device collection, but the device still has the Management Profile and is listed in CSS Gateway.

**Resolution:** This may occur because you have a custom process removing non-domain-joined devices, or because the  user has retired the device from the subscription. To validate and check which process or user account removed the device from the Configuration Manager console, perform the following steps:

##### Check how device was removed

1.  In the Configuration Manager admin console select **Monitoring** &gt; **System Status** &gt; **Status Message Queries**.

2.  Right-click **Collection Member Resources Manually Deleted** and select **Show Messages**.

3.  Pick an appropriate time/date or the last 12 hours.

4.  Find the device in question and review how the device was removed. The Example below shows the account SCCMInstall deleted the device via an Unknown Application.

    ![](../Image/CM_With_Intune_Unknown_App_Deleted_Device.jpg)

5.  Check that Configuration Manager does not have a scheduled task, script, or other process which could be automatically purging non-domain, mobile, or related devices.

## iOS enrollment errors
A list of other iOS enrollment errors is provided in our device-user documentation, in   [You see errors while trying to enroll your device in Intune](../Topic/Using-your-iOS-device-with-Intune.md#BKMK_ios_error_enrolling_tbl).

