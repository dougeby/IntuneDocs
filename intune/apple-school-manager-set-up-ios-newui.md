---
# required metadata

title: Set up Apple School Manager Program enrollment for iOS devices
titlesuffix: "Azure portal"
description: Learn how to set up Apple School Manager program enrollment for corporate-owned iOS devices with Intune (new UI)"
keywords:
author: ErikjeMS 
ms.author: erikje
manager: dougeby
ms.date: 02/08/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 4c35a23e-0c61-11e8-ba89-0ed5f89f718b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: dagerrit
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Enable iOS device enrollment with Apple School Manager

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

### Temporary user interface differences

The user interfaces for the features described on this page are in the process of being updated. These updates are rolling out across all user accounts through the end of April.

If your **Device enrollment** page looks like the image below, you have the updated user interfaces and can use this help page.

![New user interface](./media/appleenroll-newui.png)

Otherwise, if your **Device enrollment** page looks like the image below, your account has not yet been updated to the new user interface. Go to [this help page](apple-school-manager-set-up-ios.md).

![Old user interface](./media/appleenroll-oldui.png)

## iOS device enrollment

This topic helps you enable iOS device enrollment for devices purchased through the [Apple School Manager](https://school.apple.com/) program. Using Intune with Apple School Manager, you can enroll large numbers of iOS devices without ever touching them. When a student or teacher turns on the device, Setup Assistant runs with preconfigured settings and the device enrolls into management.

To enable Apple School Manager enrollment, you use both the Intune and Apple School Manager portals. A list of serial numbers or a purchase order number is required so you can assign devices to Intune for management. You create DEP enrollment profiles containing settings that applied to devices during enrollment.

Apple School Manager enrollment can't be used with [Apple's Device Enrollment Program](device-enrollment-program-enroll-ios.md) or the [device enrollment manager](device-enrollment-manager-enroll.md).

**Prerequisites**
- [Apple MDM Push certificate](apple-mdm-push-certificate-get.md)
- [MDM Authority](mdm-authority-set.md)
- [Apple MDM Push certificate](apple-mdm-push-certificate-get.md)
- User affinity requires [WS-Trust 1.3 Username/Mixed endpoint](https://technet.microsoft.com/library/adfs2-help-endpoints). [Learn more](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).
- Devices purchased from the [Apple School Management](http://school.apple.com) program

## Get an Apple token and assign devices

Before you can enroll corporate-owned iOS devices with Apple School Manager, you need a token (.p7m) file from Apple. This token lets Intune sync information about Apple School Manager-participating devices. It also permits Intune to perform enrollment profile uploads to Apple and to assign devices to those profiles. While you are in the Apple portal, you can also assign device serial numbers to manage.

### Step 1. Download the Intune public key certificate required to create an Apple token

1. In [Intune](https://aka.ms/intuneportal), choose **Device enrollment** > **Apple enrollment** > **Enrollment program tokens** > **Add**.

  ![Get an enrollment program token.](./media/device-enrollment-program-enroll-ios/image01.png)

2. In the **Enrollment program token** blade, choose **Download your public key** to download and save the encryption key (.pem) file locally. The .pem file is used to request a trust-relationship certificate from the Apple School Manager portal.
     ![Enrollment Program Token blade.](./media/device-enrollment-program-enroll-ios/image02.png)

### Step 2. Download a token and assign devices
1. Choose **Create a token via Apple School Manager**, and sign in to Apple School with your company Apple ID. You can use this Apple ID to renew your Apple School Manager token.
2.  In the [Apple School Manager portal](https://school.apple.com), go to **MDM Servers**, and then choose **Add MDM Server** (upper right).
3.  Enter the **MDM Server Name**. The server name is for your reference to identify the mobile device management (MDM) server. It is not the name or URL of the Microsoft Intune server.
   ![Screenshot of Apple School Manager portal with Serial Number option selected](./media/asm-server-assignment.png)

4.  Choose **Upload File...** in the Apple portal, browse to the .pem file, and choose **Save MDM Server** (lower right).
5.  Choose **Get Token** and then download the server token (.p7m) file to your computer.
6. Go to  **Device Assignments**, and **Choose Device** by manual entry of **Serial Numbers**, **Order Number**, or **Upload CSV File**.
     ![Screenshot of Apple School Manager portal with Serial Number option selected](./media/asm-device-assignment.png)
7.  Choose the action **Assign to Server**, and choose the **MDM Server** you created.
8. Specify how to **Choose Devices**, then provide device information and details.
9. Choose **Assign to Server** and choose the &lt;ServerName&gt; specified for Microsoft Intune, and then choose **OK**.

### Step 3. Save the Apple ID used to create this token

In Intune in the Azure portal, provide the Apple ID for future reference.

![Screenshot of specifying the Apple ID used to create the enrollment program token and browsing to the enrollment program token.](./media/device-enrollment-program-enroll-ios/image03.png)

### Step 4. Upload your token
In the **Apple token** box, browse to the certificate (.pem) file, choose **Open**, and then choose **Create**. With the push certificate, Intune can enroll and manage iOS devices by pushing policy to enrolled mobile devices. Intune automatically synchronizes your Apple School Manager devices from Apple.

## Create an Apple enrollment profile
Now that you've installed your token, you can create an enrollment profile for Apple School devices. A device enrollment profile defines the settings applied to a group of devices during enrollment.

1. In [Intune](https://aka.ms/intuneportal), choose **Device enrollment** > **Apple Enrollment** > **Enrollment program tokens**.
2. Select a token, choose **Profiles**, and then choose **Create profile**.
3. Under **Create Profile**, enter a **Name** and **Description** for the profile for administrative purposes. Users do not see these details. You can use this **Name** field to create a dynamic group in Azure Active Directory. Use the profile name to define the enrollmentProfileName parameter to assign devices with this enrollment profile. Learn more about [Azure Active Directory dynamic groups](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal#using-attributes-to-create-rules-for-device-objects).
    ![Profile name and description.](./media/device-enrollment-program-enroll-ios/image05.png)
    
4. For **User Affinity**, choose whether devices with this profile must enroll with or without an assigned user.
    - **Enroll with User Affinity** - Choose this option for devices that belong to users and that want to use the company portal for services like installing apps. This option also lets users authenticate their devices by using the company portal. User affinity requires [WS-Trust 1.3 Username/Mixed endpoint](https://technet.microsoft.com/library/adfs2-help-endpoints). [Learn more](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).   Apple School Manager's Shared iPad mode requires user enroll without user affinity.

    - **Enroll without User Affinity** - Choose this option for devices unaffiliated with a single user, such as a shared device. Use this for devices that perform tasks without accessing local user data. Apps like the Company Portal app don’t work.

5. If you chose **Enroll with User Affinity**, you have the option to let users authenticate with Company Portal instead of the Apple Setup Assistant.

    ![Authenticate with Company Portal.](./media/device-enrollment-program-enroll-ios/authenticatewithcompanyportal.png)

    >[!NOTE]
    >Multifactor authentication (MFA) doesn't work during enrollment on Apple School Manager devices if you have profile properties set to **Use with User Affinity** and you aren't using a Company Portal. After enrollment, MFA works as expected on these devices. Devices can't prompt users who need to change their password when they first sign in. Additionally, users with expired passwords aren't prompted to reset their password during enrollment. Users must use a different device to reset the password.

6. Choose **Device Management Settings** and select whether or not you want devices using this profile to be supervised.
    **Supervised** devices give you more management options and disabled Activation Lock by default. Microsoft recommends using DEP as the mechanism for enabling supervised mode, especially for organizations that are deploying large numbers of iOS devices.

    Users are notified that their devices are supervised in two ways:

    - The lock screen says: "This iPhone is managed by Contoso."
    - The **Settings** > **General** > **About** screen says: "This iPhone is supervised. Contoso can monitor your Internet traffic and locate this device."

     > [!NOTE]
     > A device enrolled without supervision can only be reset to supervised by using the Apple Configurator. Resetting the device in this manner requires connecting an iOS device to a Mac with a USB cable. Learn more about this on [Apple Configurator docs](http://help.apple.com/configurator/mac/2.3).

7. Choose whether or not you want locked enrollment for devices using this profile. **Locked enrollment** disables iOS settings that allow the management profile to be removed from the **Settings** menu. After device enrollment, you cannot change this setting without factory resetting the device. Such devices must have the **Supervised** Management Mode set to *Yes*. 

8. If you want to let multiple users sign on to enrolled iPads by using a managed Apple Id, choose **Yes** under **Shared iPad**. This requires **Enroll without User Affinity** and **Supervised** mode set to **Yes**.) Managed Apple IDs are created in the Apple School Manager portal. Learn more about [shared iPad](education-settings-configure-ios-shared.md). You should also review [Apple's shared iPad requirements](https://help.apple.com/classroom/ipad/2.0/#/cad7e2e0cf56).

9. Choose whether or not you want the devices using this profile to be able to **Sync with computers**. If you choose **Allow Apple Configurator by certificate**, you must choose a certificate under **Apple Configurator Certificates**.

9. If you chose **Allow Apple Configurator by certificate** in the previous step, choose an Apple Configurator Certificate to import.

10. Choose **OK**.

11. Choose **Setup Assistant Settings** to configure the following profile settings:
    ![Setup Assistant Customization.](./media/device-enrollment-program-enroll-ios/setupassistantcustom.png)

    | Setting | Description |
    | --- | --- |
    | **Department Name** | Appears when users tap **About Configuration** during activation. |
    | **Department Phone** | Appears when the user clicks the **Need Help** button during activation. |
    | **Setup Assistant Options** | The following optional settings can be set up later in the iOS **Settings** menu. |
    | **Passcode** | Prompt for passcode during activation. Always require a passcode unless the device is secured or has access controlled in some other manner (that is, kiosk mode that restricts the device to one app). |
    | **Location Services** | If enabled, Setup Assistant prompts for the service during activation. |
    | **Restore** | If enabled, Setup Assistant prompts for iCloud backup during activation. |
    | **iCloud and Apple ID** | If enabled, Setup Assistant prompts the user to sign in an Apple ID and the Apps & Data screen will allow the device to be restored from iCloud backup. |
    | **Terms and Conditions** | If enabled, Setup Assistant prompts users to accept Apple's terms and conditions during activation. |
    | **Touch ID** | If enabled, Setup Assistant prompts for this service during activation. |
    | **Apple Pay** | If enabled, Setup Assistant prompts for this service during activation. |
    | **Zoom** | If enabled, Setup Assistant prompts for this service during activation. |
    | **Siri** | If enabled, Setup Assistant prompts for this service during activation. |
    | **Diagnostic Data** | If enabled, Setup Assistant prompts for this service during activation. |

12. Choose **OK**.

13. To save the profile, choose **Create**.

## Connect School Data Sync
(Optional) Apple School Manager supports synchronizing class roster data to the Azure Active Directory (AD) using Microsoft School Data Sync (SDS). You can only sync one token with SDS. If you set up another token with School Data Sync, SDS will be removed from the token that previously had it. A new connection will replace the current token. Complete the following steps to use SDS to sync school data.

1. In [Intune](https://aka.ms/intuneportal), choose **Device enrollment** > **Apple Enrollment** > **Enrollment program tokens**.
2. Select an Apple School Manager token and then choose **School Data Sync**.
3. Under **School Data Sync**, choose **Allow**. This setting allows Intune to connect with SDS in Office 365.
4. To enable a connection between Apple School Manager and Azure AD, choose **Set up Microsoft School Data Sync**. Learn more about [how to set up School Data Sync](https://support.office.com/article/Install-the-School-Data-Sync-Toolkit-8e27426c-8c46-416e-b0df-c29b5f3f62e1).
5. Click **Save** > **OK**.

## Sync managed devices

Now that Intune has been assigned permission to manage your Apple School Manager devices, you can synchronize Intune with the Apple service to see your managed devices in Intune.

In [Intune](https://aka.ms/intuneportal), choose **Device enrollment** > **Apple Enrollment** > **Enrollment program tokens** > choose a token in the list > **Devices** > **Sync**.
  ![Screenshot of Enrollment Program Devices node selected and Sync link being chosen.](./media/device-enrollment-program-enroll-ios/image06.png)
  
  To comply with Apple’s terms for acceptable enrollment program traffic, Intune imposes the following restrictions:
  - A full sync can run no more than once every seven days. During a full sync, Intune refreshes every Apple serial number assigned to Intune. If a full sync is attempted within seven days of the previous full sync, Intune only refreshes serial numbers that are not already listed in Intune.
  - Any sync request is given 15 minutes to finish. During this time or until the request succeeds, the **Sync** button is disabled.
  - Intune syncs new and removed devices with Apple every 24 hours.

>[!NOTE]
>You can also assign Apple School Manager serial numbers to profiles from the **Enrollment Program Devices** blade.

## Assign a profile to devices
Apple School Manager devices managed by Intune must be assigned an enrollment profile before they are enrolled.

1. In [Intune](https://aka.ms/intuneportal), choose **Device enrollment** > **Apple Enrollment** > **Enrollment program tokens** > choose a token in the list.
2. Choose **Devices** > choose devices in the list > **Assign profile**.
3. Under **Assign profile**, choose a profile for the devices and then choose **Assign**.

## Distribute devices to users

You have enabled management and syncing between Apple and Intune, and assigned a profile to  let your Apple School devices enroll. You can now distribute devices to users. When an iOS Apple School Manager device is turned on, it is enrolled for management by Intune. If the device has been activated and is in use, the profile cannot be applied until the device is factory reset.
