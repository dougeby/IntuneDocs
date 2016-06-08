---
# required metadata

title: Troubleshoot device enrollment| Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 05/26/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 6982ba0e-90ff-4fc4-9594-55797e504b62

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Troubleshoot device enrollment in Intune

Here are some device enrollment issues and how to troubleshoot and resolve them.

> [!NOTE]
> Your managed device users can collect enrollment and diagnostic logs for you to review. User instructions for collecting logs are provided in:
>- [Send Android diagnostic data logs to your IT administrator using a USB cable](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)
>- [Send Android diagnostic data logs to your IT administrator using email](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-email-android)
>- [Send Android enrollment errors to your IT administrator](/intune/enduser/send-enrollment-errors-to-your-it-administrator-android)
>- [Send iOS enrollment errors to your IT administrator](/intune/enduser/send-errors-to-your-it-admin-ios)


If this information does not solve your problem, see [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) to find more ways to get help.

## General enrollment issues
These issues may occur on all device platforms.

### Device Cap reached
**Issue:** A user receives an error on their device during enrollment, such as a **Company Portal Temporarily Unavailable** error on an iOS device, and the DMPdownloader.log on Configuration Manager contains the error **DeviceCapReached**.

**Resolution:** By design, users can enroll no more than 5 devices.

#### Check number of devices enrolled and allowed

1.  Validate in the Intune admin portal that the user has no more than 5 devices assigned

2.  Check in the Intune admin portal under Admin\Mobile Device Management\Enrollment Rules that the Device enrollment limit is set to 5

Mobile device users can delete devices at the following URL: [https://byodtestservice.azurewebsites.net/](https://byodtestservice.azurewebsites.net/).

Administrators can delete devices in the Azure Active Directory portal.

#### To delete devices in the Azure Active Directory portal

1.  Browse to [http://aka.ms/accessaad](http://aka.ms/accessaad) or choose **Admin** &gt; **Azure AD** from [https://portal.office.com](https://portal.office.com).

2.  Login with your Org ID using the link on the left side of the page.

3.  Create an Azure Subscription if you don’t have one. This should not require a credit card or payment if you have a paid account (choose the **Register your free Azure Active Directory** subscription link).

4.  Select **Active Directory** and then select your organization.

5.  Select the **Users** tab.

6.  Select the user whose devices you want to delete.

7.  Choose **Devices**.

8.  Remove devices as appropriate, such as those that are no longer in use, or those that have inaccurate definitions.

> [!NOTE]

> You can avoid the device enrollment cap by using Device Enrollment Managers, as described in [Enroll corporate-owned devices with the Device Enrollment Manager in Microsoft Intune](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).
>
> A user account which is added to Device Enrollment Managers group will not be able to complete enrollment when Conditional Access policy is enforced for that specific user login.

### Company Portal Temporarily Unavailable
**Issue:** A user receives a **Company Portal Temporarily Unavailable** error on their device.

#### Troubleshooting Company Portal Temporarily Unavailable error

1.  Remove the Intune Company Portal app from the device.

2.  On the device, open the browser, browse to [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com), and attempt a user login.

3.  If the user fails to log in, have them try another network.

4.  If that fails, validate that the user’s credentials have synced correctly with Azure Active Directory.

5.  If the user successfully logs in, an iOS device will prompt you to install the Intune Company Portal app and enroll. On an Android device you will need to manually install the Intune Company Portal app, after which you can retry enrolling.

### MDM authority not defined
**Issue:** A user receives an **MDM authority not defined** error.

#### Troubleshooting MDM authority not defined error

1.  Verify that the MDM Authority has been set appropriately for the version of the Intune service you are using  , that is, for Intune, O365 MDM, or System Center Configuration Manager with Intune. For Intune,  the MDM Authority is set in **Admin** &gt; **Mobile Device Management**. For Configuration Manager with Intune, you set it when configuring the Intune connector, and in O365 it's a setting **Mobile Devices**.

    > [!NOTE]
    > Once you set the MDM authority, you can only change it by contacting Support, as described in [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md).

2.  Verify that the user’s credentials have synced correctly with Azure Active Directory, by checking that their UPN matches the Active Directory information in the Account Portal.
    If the UPN does not match the Active Directory information:

    1.  Turn off DirSync on the local server.

    2.  Delete the mismatched user from the **Intune Account Portal** user list.

    3.  Wait about one hour to allow the Azure service to remove the incorrect data.

    4.  Turn on DirSync again and check if the user is now synced properly.

3.  In a scenario where you are using System Center Configuration Manager with Intune, verify that the user has a valid Cloud User ID:

    1.  Open SQL Management Studio.

    2.  Connect to the appropriate DB.

    3.  Open the databases folder and find and open the **CM_DBName** folder, where DBName is the name of the customer database.

    4.  At the top, choose **New Query**  and execute the following queries:

        -   To see all users:
            `select * from [CM_ DBName].[dbo].[User_DISC]`

        -   To see Specific Users, use the following query, where %testuser1% represents username@domain.com for the user you want to look up:
            `select * from [CM_ DBName].[dbo].[User_DISC] where User_Principal_Name0 like '%testuser1%'`

        After writing the query choose **!Execute**.
        Once the results have been returned, look for the clouduser ID.  If no ID is found, the user isn't licensed to use Intune.

### Unable to create policy or enroll devices if the company name contains special characters
**Issue:** You can't create policy or enroll devices.

**Resolution:** In the [Office 365 admin center](https://portal.office.com/), remove the special characters from the company name and save the company information.

### Unable to log in or enroll devices when you have multiple verified domains
**Issue:** When you add a second verified domain to your ADFS, users with the user principal name (UPN) suffix of the second domain may not be able to log into the portals or enroll devices. 


**Resolution:** Microsoft Office 365 customers who utilize single sign-on (SSO) through AD FS 2.0 and have multiple top level domains for users' UPN suffixes within their organization (for example, @contoso.com or @fabrikam.com) are required to deploy a separate instance of the AD FS 2.0 Federation Service for each suffix.  There is now a [rollup for AD FS 2.0](http://support.microsoft.com/kb/2607496) that works in conjunction with the **SupportMultipleDomain** switch to enable the AD FS server to support this scenario without requiring additional AD FS 2.0 servers. See [this blog](https://blogs.technet.microsoft.com/abizerh/2013/02/05/supportmultipledomain-switch-when-managing-sso-to-office-365/) for more information.

### The machine is already enrolled - Error hr 0x8007064c
**Issue:** Enrollment fails with the error **The machine is already enrolled**. The enrollment log shows error **hr 0x8007064c**.
  
This may be because the computer had been previously enrolled, or has the cloned image of a computer that had been enrolled. The account certificate of the previous account is still present on the computer.



**Resolution:** 

1. From the **Start** menu, **Run** -> **MMC**. 
1. **File** -> **Add/ Remove Snap-ins**.
1. Double-click **Certificates**, choose **Computer account**, **Next**, select **Local Computer**.
1. Double-click **Certificates (Local computer)**, choose **Personal/ Certificates**. 
1. Look for the Intune cert issued by Sc_Online_Issuing, and delete it if present
1. Delete this registry key if it exists: ** HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\OnlineManagement regkey** and all sub keys.
1. Attempt re-enrollment. 
1. If the machine can still not enroll, look for and delete this key, if it exists: **KEY_CLASSES_ROOT\Installer\Products\6985F0077D3EEB44AB6849B5D7913E95**. 
1. Attempt re-enrollment. 

    > [!IMPORTANT]
    > This section, method, or task contains steps that tell you how to modify the registry. However, serious problems might occur if you modify the registry incorrectly. Therefore, make sure that you follow these steps carefully. For added protection, back up the registry before you modify it. Then, you can restore the registry if a problem occurs.
    > For more information about how to back up and restore the registry, read [How to back up and restore the registry in Windows](https://support.microsoft.com/en-us/kb/322756)


## Android issues
### Profile installation failed
**Issue:** A user receives a **Profile installation failed** error on an Android device.

### Troubleshooting steps for failed profile installation

1.  Confirm that the user has been assigned an appropriate license for the version of the Intune service you are using.

2.  Confirm that the device is not already enrolled with another MDM provider or that it does not already have a management profile installed.


4.  Confirm that Chrome for Android is the default browser and that cookies are enabled.
## iOS issues
### Profile installation failed
**Issue:** A user receives a **Profile installation failed** error on an iOS device.

### Troubleshooting steps for failed profile installation

1.  Confirm that the user has been assigned an appropriate license for the version of the Intune service you are using.

2.  Confirm that the device is not already enrolled with another MDM provider or that it does not already have a management profile installed.

3.  Navigate to [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com) and try to install the profile when prompted.

4.  Confirm that Safari for iOS is the default browser and that cookies are enabled.

### Enrolled iOS device doesn't appear in console when using System Center Configuration Manager with Intune
**Issue:** User enrolls iOS device but it does not appear in the Configuration Manager admin console. The device does not indicate that it's been enrolled. Possible causes:

- You may have enrolled your Intune Connector into one account, and then enrolled it into another account. 
- You may have downloaded the MDM certificate from one account and used it on another account.


**Resolution:** Perform the following steps:

1. Disable iOS inside of the Windows Intune Connector. 
	1. Right-click the Intune subscription and select **Properties**.
	1. On the "iOS" tab, uncheck "Enable iOS Enrollment".



1. In SQL, run the following steps on the CAS DB
  
	1. update SC_ClientComponent_Property set Value2 = '' where Name like '%APNS%' 
	1. delete from MDMPolicy where PolicyType = 7 
	1. delete from MDMPolicyAssignment where PolicyType = 7
	1. update SC_ClientComponent_Property set Value2 = '' where Name like '%APNS%' 
	1. delete from MDMPolicy where PolicyType = 11 
	1. delete from MDMPolicyAssignment where PolicyType = 11 
	1. DELETE Drs_Signals
1. Restart the SMS Executive Service or Restart the CM Server 



1. Get a new APN certificate and upload it: Right-click the Intune subscription in the left pane of Configuration Manager. Select **Create APNs certificate request** and follow the instructions.
## Issues when using System Center Configuration Manager with Intune
### Mobile devices disappear 
**Issue:** After successfully enrolling a mobile device to Configuration Manager it disappears from the mobile device collection, but the device still has the Management Profile and is listed in CSS Gateway.

**Resolution:** This may occur because you have a custom process removing non-domain-joined devices, or because the  user has retired the device from the subscription. To validate and check which process or user account removed the device from the Configuration Manager console, perform the following steps.

#### Check how device was removed

1.  In the Configuration Manager admin console select **Monitoring** &gt; **System Status** &gt; **Status Message Queries**.

2.  Right-click **Collection Member Resources Manually Deleted** and select **Show Messages**.

3.  Pick an appropriate time/date or the last 12 hours.

4.  Find the device in question and review how the device was removed. The Example below shows that the account SCCMInstall deleted the device via an Unknown Application.

    ![Screenshot for device deletion diagnosis](./media/CM_With_Intune_Unknown_App_Deleted_Device.jpg)

5.  Check that Configuration Manager does not have a scheduled task, script, or other process which could be automatically purging non-domain, mobile, or related devices.




### Other iOS enrollment errors
A list of iOS enrollment errors is provided in our device-user documentation, in [You see errors while trying to enroll your device in Intune](/intune/enduser/using-your-ios-or-mac-os-x-device-with-intune).

## General enrollment Error codes

|Error code|Possible problem|Suggested resolution|
|--------------|--------------------|----------------------------------------|
|0x80CF0437 |The clock on the client computer is not set to the correct time.|Make sure that the clock and the time zone on the client computer are set to the correct time and time zone.
|
|0x80240438, 0x80CF0438, 0x80CF402C|Cannot connect to the Intune service. Check the client proxy settings.|Verify that the proxy configuration on the client computer is supported by Intune, and that the client computer has Internet access.|
|0x80240438, 0x80CF0438|Proxy settings in Internet Explorer and Local System are not configured.|Cannot connect to the Intune service. Check the client proxy settings and confirm that the proxy configuration on the client computer is supported by Intune, and that the client computer has Internet access.|
|0x80043001, 0x80CF3001, 0x80043004, 0x80CF3004|Enrollment package is out of date.|Download and install the current client software package from the Administration workspace.|
|0x80043002, 0x80CF3002|Account is in maintenance mode.|You cannot enroll new client computers when the account is in maintenance mode. To view your account settings, sign in to your account.|
|0x80043003, 0x80CF3003|Account is deleted.|Verify that your account and subscription to Intune is still active. To view your account settings, sign in to your account.|
|0x80043005, 0x80CF3005|The client computer has been retired.|Wait a few hours, remove any older versions of the client software from the computer, and then retry the client software installation.|
|0x80043006, 0x80CF3006|The maximum number of seats allowed for the account has been reached.|Your organization must purchase additional seats before you can enroll more client computers in the service.|
|0x80043007, 0x80CF3007|Could not find the certificate file in the same folder as the installer program.|Extract all files before you start the installation. Do not rename or relocate any of the extracted files: all files must exist in the same folder or the installation will fail.|
|0x8024D015, 0x00240005, 0x80070BC2, 0x80070BC9, 0x80CFD015|The software cannot be installed because a restart of the client computer is pending.|Restart the computer and then retry the client software installation.|
|0x80070032|One or more prerequisites for installing the client software were not found on the client computer.|Make sure that all required updates are installed on the client computer and then retry the client software installation.|
|0x80043008, 0x80CF3008|Failed to start the Microsoft Online Management Updates service.|Contact Microsoft Support as described in [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md).|
|0x80043009, 0x80CF3009|The client computer is already enrolled into the service.|You must retire the client computer before you can re-enroll it in the service.|
|0x8004300B, 0x80CF300B|The client software installation package cannot run because the version of Windows that is running on the client is not supported.|Intune does not support the version of Windows that is running on the client computer.|
|0xAB2|The Windows Installer could not access VBScript run time for a custom action.|This error is caused by a custom action that is based on Dynamic-Link Libraries (DLLs). When troubleshooting the DLL, you might have to use the tools that are described in [Microsoft Support KB198038: Useful Tools for Package and Deployment Issues](https://support.microsoft.com/en-us/kb/198038).|
|0x80cf0440|The connection to the service endpoint terminated.|Trial or paid account is suspended. Create a new trial or paid account and re-enroll.|




### Next steps
If this troubleshooting information didn't help you, contact Microsoft Support as described in [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md).
