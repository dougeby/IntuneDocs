---
# required metadata

title: Prerequisites for mobile device enrollment 
description: Set up mobile device management (MDM) prerequisites and get ready to enroll different operating systems.
keywords:
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 05/31/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 44fd4af0-f9b0-493a-b590-7825139d9d40

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: damionw
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Prerequisites for mobile device management in Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

You can enable employees to enroll their mobile devices with Intune requires the following steps. These same steps are required to manage company-owned devices.

|Steps|Details|  
|-----------|-------------|  
|**Step 1:** [Enable connections](#step-1-enable-connections)|Ensure your custom domain name is configured and network communication is ready|  
|**Step 2:** [Set MDM authority](#step-2-set-mdm-authority)|The mobile device management authority defines the service assigned to your devices|
|**Step 3:** [Create groups](#step-3-create-groups)|Configure user-facing settings for the Company Portal app|  
|**Step 4:** [Configure Company Portal](#step-4-configure-company-portal)|Configure user-facing settings for the Company Portal app|  
|**Step 5:** [Assign user licenses](#step-5-assign-user-licenses)|Assign Intune licenses to users so they can enroll devices|
|**Step 6:** [Enable enrollment](#step-6-enable-enrollment)|Enable platform-specific settings for iOS and Windows management. Android devices need no additional configuration.|
|**Step 7:** [Next steps](#step-7-next-steps)|Enable platform-specific settings for iOS and Windows management. Android devices need no additional configuration.|

Looking for Intune with Configuration Manager?
> [!div class="button"]
[View SCCM docs >](https://docs.microsoft.com/sccm/mdm/deploy-use/setup-hybrid-mdm)

## Step 1: Enable connections

Before you enable mobile device enrollment, be sure you've done the following:
- [Review required network URLs and ports](/intune/network-bandwidth-use)
- [Add and verify your domain name](/intune/custom-domain-name-configure)

## Step 2: Set MDM authority
The MDM authority defines the management service that has permission to manage a set of devices. The options for the MDM authority include Intune by itself and Configuration Manager with Intune. If you set Configuration Manager as the management authority, no other service can be used for mobile device management.

>[!IMPORTANT]
> In Configuration Manager version 1610 or later and Microsoft Intune version 1705, you change the MDM authority without having to contact Microsoft Support, and without having to unenroll and reenroll your existing managed devices. For details, see [What to do if you choose the wrong MDM authority setting](/intune-classic/deploy-use/prerequisites-for-enrollment#what-to-do-if-you-choose-the-wrong-mdm-authority-setting).

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Admin** &gt; **Mobile Device Management**.

2.  In the **Tasks** list, click **Set Mobile Device Management Authority**. The **Set MDM Authority** dialog box opens.

    ![Set MDM authority dialog box](../media/intune-mdm-authority.png)

3.  Intune requests confirmation that you want Intune as your MDM authority. Select the check box, and then choose **Yes** to use Microsoft Intune to manage mobile devices.

## Step 3: Create groups

You can create user and device groups to simplify management and improve targeting of deployed apps, policies, and company resources. [Learn how to create groups](use-groups-to-manage-users-and-devices-with-microsoft-intune.md#create-groups).

## Step 4: Configure Company Portal

The Intune Company Portal is where users access company data and can do common tasks like enrolling devices, installing apps, and locating information for assistance from your IT department.

> [!TIP]
> When you customize the Company Portal, the configurations apply to both the Company Portal website and Company Portal apps.

Customizing the Company Portal helps to provide a familiar and helpful experience for your end users. To do this, just sign in to the [Microsoft Intune administration console](https://manage.microsoft.com) as a tenant or service administrator, choose **Admin** &gt; **Company Portal**, and configure the Company Portal settings.

![admin-console-admin-workspace-comp-portal-settings](../media/cp_sa_cpsetup.PNG)

### Company contact information and privacy statement

The company name is displayed as the Company Portal title. The contact information and details are displayed to users in the Contact IT screen of the Company Portal. The privacy statement is displayed when a user clicks the privacy link.

|Field name|Max length|More information|
    |----------|------------------------|----------------|
    |Company name|40|This name is displayed as the title of the Company Portal. **Note**: Alpha-numeric characters only. This field doesn't support special characters.|
    |IT department contact name|40|This name is displayed on the **Contact IT** page.|
    |IT department phone number|20|This contact number is displayed on the **Contact IT** page.|
    |IT department email address|40|This contact address is displayed on the **Contact IT** page. You must enter a valid email address in the format **alias@domainname.com**.|
    |Additional information|120|This information is displayed on the **Contact IT** page.|
    |Company privacy statement URL|79|You can specify your own company privacy statement that appears when users click the privacy links from the Company Portal. You must enter a valid URL in the format https://www.contoso.com.|

### Support contacts
The support website is displayed to users in the Company Portal to enable them to access online support.

|Field name|Max length|More information|
    |----------|------------------------|----------------|
    |Support website URL|150|If you have a support website that you want your users to use, specify the URL here. The URL must be in the format https://www.contoso.com. If you don't specify a URL, nothing is displayed for the support website on the **Contact IT** page in the Company Portal.|
    |Website name|40|This name is the friendly name that is displayed for the URL to the support website. If you specify a support website URL and no friendly name, then **Go to IT website** is displayed on the **Contact IT** page in the Company Portal.|


### Company branding customization

You can customize your Company Portal with your company logo, company name, theme color, and background.

|Field name|More information|
    |----------|----------------|
    |Theme color|Select a theme color to apply to the Company Portal.|
    |Include company logo|When you enable this option, you can upload your company logo to show in your Company Portal. You can upload two logos: one logo that is displayed when the Company Portal background is white, and one logo that is displayed when the Company Portal background uses your selected theme color. Each logo must be a .png or .jpg file, have a maximum resolution of 400 x 100 pixels, and be 750 KB or less in size.|
    |Choose a background for the Company Portal app|This setting affects the background for the Company Portal app only.|


After you save your changes, you can use the links that are provided at the bottom of the **Company Portal** page of the administration console to view the Company Portal website. These links cannot be changed. When a user signs in, these links display your subscriptions in the Company Portal.

## Step 5: Assign user licenses

You use the **Office 365 management portal** to manually add cloud-based users and assign licenses to both cloud-based user accounts and accounts that are synchronized from your on-premises Active Directory to Azure Active Directory (Azure AD). You can [synchronize on-premises users to Azure AD](/intune/users-permissions-add#how-to-sync-on-premises-users-with-azure-ad).

1.  Sign in to the [Office 365 management portal](https://portal.office.com/Admin/Default.aspx) by using your tenant administrator credentials.

2.  Select the user account that you want to assign an Intune user license to, and then select the **Microsoft Intune** check box on the user account properties.

3.  The user account will now be added to the Microsoft Intune user group, which grants the user permissions to use the service and enroll their devices into management.

### To synchronize on-premises users with Azure AD

1. [Add the UPN suffix](https://technet.microsoft.com/library/cc772007.aspx) for your custom domain in your on-premises Active Directory.
2. Set the new UPN suffix for the on-premises users that you plan to import.
3. Run [Azure AD Connect sync](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) to integrate your on-premises users with Azure AD.
4. Once the user account information has successfully synchronized, you can then assign Microsoft Intune licenses using the [Office 365 Management Portal](https://portal.office.com/Admin/Default.aspx).

## Step 6: Enable enrollment
After setting up the MDM authority, you need to set up device management for the operating systems that your organization wants to support. The steps that are required to set up device management vary by operating system. For example, the Android OS does not require you to do anything in the Intune administration console. On the other hand, Windows and iOS require a trust relationship between devices and Intune to allow management.

Set up management for the following platforms:
- [iOS and Mac](set-up-ios-and-mac-management-with-microsoft-intune.md)
- [Android](set-up-android-management-with-microsoft-intune.md)
- [Android for Work](set-up-android-for-work.md)
- [Windows 10 Mobile and Windows Phone](set-up-windows-device-management-with-microsoft-intune.md)
- [Windows PCs and laptops](manage-windows-pcs-with-microsoft-intune.md) (Intune client software)

You can also enable [enrollment of corporate-owned devices](manage-corporate-owned-devices.md).

## Step 7: Next steps

Now that enrollment is enabled, you should set up management to meet your business's needs. The following are some  management options:

- [Deploy policies that manage settings and features on devices](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
- [Enable access to company resources like email, Wi-Fi, and VPN](enable-access-to-company-resources-with-microsoft-intune.md)
- [Add apps](add-apps.md) and [deploy app](deploy-apps.md) to managed devices
- [Create device compliance policies](introduction-to-device-compliance-policies-in-microsoft-intune.md) and [restrict access based on compliance](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)

## What to do if you choose the wrong MDM authority setting

If you decide that you've chosen the wrong MDM authority setting and need to change it, you have the following options.

### Change the MDM authority yourself
Beginning in Configuration Manager version 1610 and Microsoft Intune version 1705, you can change the MDM authority from Microsoft Intune to Configuration Manager (hybrid) or vice versa without having to contact Microsoft Support, and without having to unenroll and reenroll your existing managed devices. For details, see [Change your MDM authority]( /sccm/mdm/deploy-use/change-mdm-authority).

### Contact Microsoft Support
When you have Configuration Manager prior to version 1610, you must contact Microsoft Support. You cannot change the setting yourself. Before contacting Microsoft Support, review the following information, which describes the information that Microsoft Support will need from you to make the change.

There are three possible ways that your MDM authority can be reset. In your Support request, you'll need to choose the way that applies to your situation. If the scenario you are requesting is not listed, follow up with Microsoft Support.

Microsoft Support will ask you to confirm the following information:

- Tenant ID: the domain used to log in to the service (for example, intune.onmicrosoft.com)
- The MDM authority that you want to change to
- Confirmation of prerequisite steps that you completed, as listed below

If you are using coexistence, you need to verify both the Intune and Office 365 checklists.

#### Reset MDM authority from Intune to Configuration Manager

Complete these steps before contacting Microsoft Support to reset your MDM authority.

- Retire all devices from the Intune admin console. Do not try to retire a device from the device itself. 
- Delete the Service To Service Connector (under **Administration** > **Mobile Device Management** > **Microsoft Exchange**), or disable the Exchange Connector if you have set that up.
- Remove the Device Enrollment Manager role from **Admin** > **Device Enrollment Manager**.
- Turn off Device Group Mapping in **Admin** > **Mobile Device Management** > **Device Group Mapping**.
- Delete sideloading keys from **Admin** > **Mobile Device Management** > **Windows** > **Side Loading Keys**.
- Delete the iOS APNs certificate in **Admin** > **Mobile Device Management** > **iOS** page.
- Delete the iOS DEP token in **Admin** > **Mobile Device Management** > **iOS** page.
- Delete all polices that are for MDM Devices under **Policy** > **Configuration Policies**.
- Delete all published applications that are for MDM Devices in **Apps** > **Managed Software**.

#### Reset MDM authority from Configuration Manager to Intune

Complete these steps before contacting Microsoft Support to reset your MDM authority.

- Retire all devices (that are managed as mobile devices) from the Configuration Manager Console. Do not try to retire a device from the device itself. 
- Remove all users from the Intune User Group. Point the Intune subscription to an empty user collection, or remove all users from the targeted collection.  Confirm in the CloudUserSync.log that users are removed. 
- Uncheck the iOS platform to purge the APNs certificate.
- Delete all published applications that are for MDM devices.
- Delete all polices that are for MDM devices.
- Remove the Windows Intune Connector from the Configuration Manager Console (applicable only to R2 SP1 or below).
-Remove the Intune subscription by right-clicking the subscription and selecting **Delete**.
- Restart the SMS Executive Service.
- Provide us with some example users so that we can verify, after the process completes, that Configuration Manager licenses were removed.

#### Reset MDM authority from Office 365 to Configuration Manager

1. Navigate to [https://protection.office.com](https://protection.office.com).
2. Select the **Security Policies** tab, and select **Device Management**.
3. Retire all devices by choosing **Selective Wipe**. Do not try to retire a device from the device itself. If selective wipe is disabled, no further action is required.
4. Select the **Security Policies** tab, and select **Device Security Policies**.
5. Select **Delete** for all existing policies. If the polices are in a pending state, no further action is required.

>[!NOTE]
>The iOS APsN certificate cannot be deleted and remains attached to the account.

#### Next steps for MDM authority resets

Once Microsoft Support verifies the items on the applicable checklist, resetting the MDM authority can take up to three business days, but typically occurs within one day.

>[!IMPORTANT]
>Do not try to configure your subscription until Microsoft Support confirms that the reset has completed successfully! Premature configuration may cause corruption and/or impact your ability to use the Intune service.
