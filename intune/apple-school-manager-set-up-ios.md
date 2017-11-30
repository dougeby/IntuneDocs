---
# required metadata

title: Set up Apple School Manager Program enrollment for iOS devices
titlesuffix: "Azure portal"
description: Learn how to set up Apple School Manager program enrollment for corporate-owned iOS devices with Intune"
keywords:
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 09/13/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c

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

This topic helps you enable iOS device enrollment for devices purchased through the [Apple School Manager](https://school.apple.com/) program. Using Intune with Apple School Manager, you can enroll large numbers of iOS devices without ever touching them. When a student or teacher turns on the device, Setup Assistant runs with preconfigured settings and the device enrolls into management.

To enable Apple School Manager enrollment, you use both the Intune and Apple School Manager portals. A list of serial numbers or a purchase order number is required so you can assign devices to Intune for management. You create DEP enrollment profiles containing settings that applied to devices during enrollment.

By the way, Apple School Manager enrollment can't be used with [Apple's Device Enrollment Program](device-enrollment-program-enroll-ios.md) or the [device enrollment manager](device-enrollment-manager-enroll.md).

**Prerequisites**
- [Apple MDM Push certificate](apple-mdm-push-certificate-get.md)
- [MDM Authority](mdm-authority-set.md)
- [Apple MDM Push certificate](apple-mdm-push-certificate-get.md)
- User affinity requires [WS-Trust 1.3 Username/Mixed endpoint](https://technet.microsoft.com/library/adfs2-help-endpoints). [Learn more](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).
- Devices purchased from the [Apple School Management](http://school.apple.com) program

>[!NOTE]
>Multifactor authentication (MFA) doesn't work during enrollment on Apple School Manager devices with user affinity. After enrollment, MFA works as expected on these devices. After enrollment, MFA works as expected on devices. Devices can't prompt users who need to change their password when they first sign in. Additionally, users with expired passwords aren't prompted to reset their password during enrollment. Users must use a different device to reset the password.

## Get the Apple token and assign devices

Before you can enroll corporate-owned iOS devices with Apple School Manager, you need a token (.p7m) file from Apple. This token lets Intune sync information about Apple School Manager-participating devices. It also permits Intune to perform enrollment profile uploads to Apple and to assign devices to those profiles. While you are in the Apple portal, you can also assign device serial numbers to manage.

**Step 1. Download an Intune public key certificate required to create an Apple token.**<br>
1. In [Intune in the Azure portal](https://aka.ms/intuneportal), choose **Device enrollment** and then choose **Enrollment program token**.

  ![Screenshot of Enrollment Program Token pane in Apple Certificates workspace to download public key.](./media/enrollment-program-token-download.png)

2. In the **Enrollment program token** blade, choose **Download your public key** to download and save the encryption key (.pem) file locally. The .pem file is used to request a trust-relationship certificate from the Apple School Manager portal.

**Step 2. Download a token and assign devices.**<br>
1. Choose **Create a token via Apple School Manager**, and sign in with your company Apple ID. You can use this Apple ID to renew your Apple School Manager token.
2.  In the [Apple School Manager portal](https://school.apple.com), go to **MDM Servers**, and then choose **Add MDM Server** (upper right).
3.  Enter the **MDM Server Name**. The server name is for your reference to identify the mobile device management (MDM) server. It is not the name or URL of the Microsoft Intune server.
   ![Screenshot of Apple School Manager portal with Serial Number option selected](./media/asm-server-assignment.png)

4.  Choose **Upload File...** in the Apple portal, browse to the .pem file, and choose **Save MDM Server** (lower right).
5.  Choose **Get Token** and then download the server token (.p7m) file to your computer.
6. Go to  **Device Assignments**, and **Choose Device** by manual entry of **Serial Numbers**, **Order Number**, or **Upload CSV File**.
     ![Screenshot of Apple School Manager portal with Serial Number option selected](./media/asm-device-assignment.png)
7.	Choose the action **Assign to Server**, and choose the **MDM Server** you created.
8. Specify how to **Choose Devices**, then provide device information and details.
9. Choose **Assign to Server** and choose the &lt;ServerName&gt; specified for Microsoft Intune, and then choose **OK**.

**Step 3. Enter the Apple ID used to create your Apple School Manager token.**<br>This ID should be used to renew your Apple School Manager token and is stored for your future reference.

![Screenshot of specifying the Apple ID used to create the enrollment program token and browsing to the enrollment program token.](./media/enrollment-program-token-apple-id.png)

**Step 4. Locate and upload your token.**<br>
Go to the certificate (.p7m) file, choose **Open**, and then choose **Upload**. Intune automatically syncs your Apple School Manager devices from Apple.

## Create an Apple enrollment profile
A device enrollment profile defines the settings applied to a group of devices during enrollment.

1. In Intune in the Azure portal, choose **Device enrollment**, and then choose **Apple Enrollment**.
2. Under **Enrollment Program**, choose **Enrollment Program Profiles**.
3. On the **Enrollment Program Profiles** blade, choose **Create**.
4. On the **Create Enrollment Profile** blade, enter a **Name** and **Description** for the profile that is displayed in Intune.
5. For **User Affinity**, choose whether devices with this profile enroll with or without user affinity.

 - **Enroll with user affinity** - Affiliates the device with a user during setup.

  Apple School Manager's Shared iPad mode requires user enroll without user affinity.

 - **Enroll without user affinity** - Choose for device unaffiliated with a single user, such as shared devices. Use for devices that perform tasks without accessing local user data. Apps like the Company Portal app don’t work.

6. Choose **Device Management Settings**. These items are set during activation and require a factory reset to change. configure the following profile settings, and then choose **Save**:

  ![Screenshot of choosing the management mode. Device has the following settings: supervised, locked enrollment, allow pairing set to deny all. Apple Configurator Certificates is grayed out for a new enrollment program profile.](./media/enrollment-program-profile-mode.png)

	- **Supervised** - a management mode that enables more management options and disabled Activation Lock by default. If you leave the check box blank, you have limited management capabilities.

	 - **Locked enrollment** - (Requires Management Mode = supervised) Disables iOS settings that could allow removal of the management profile. If you leave the check box blank, it allows the management profile to be removed from the Settings menu.
   - **Shared iPad** - (Requires **Enroll without User Affinity** and Supervised mode.) Allows multiple users to log on to enrolled iPads by using a managed Apple ID. Managed Apple IDs are created in the Apple School Manager portal. Learn more about [shared iPad](education-settings-configure-ios-shared.md). You should also review [Apple's shared iPad requirements](https://help.apple.com/classroom/ipad/2.0/#/cad7e2e0cf56).

   >[!NOTE]
   >If **User Affinity** is set to **With user affinity**  or **Supervised** mode is set to **Off**, Shared iPad mode is disabled for the enrollment profile.

        - **Maximum Cached Users** - (Requires **Shared iPad** = **Yes**) Creates a partition on the device for each user. The recommended value is the number of students likely to use the device over a period of time. For example, if six students use the device regularly during the week, set this number to six.  

    - **Allow Pairing** - specifies whether iOS devices can sync with computers. If you choose **Allow Apple Configurator by certificate**, you must choose a certificate under **Apple Configurator Certificates**.

      - **Apple Configurator Certificates** - If you chose **Allow Apple Configurator by certificate** under **Allow Pairing**, choose an Apple Configurator Certificate to import.

7. Choose **Setup Assistant Settings**, configure the following profile settings, and then choose **Save**:

	- **Department Name** - Appears when users tap **About Configuration** during activation.

	- **Department Phone** - Appears when the user clicks the Need Help button during activation.
    - **Setup Assistant Options** - If excluded from Setup Assistant options, these settings can be set later in the iOS **Settings** menu.
        - **Passcode** - Prompt for passcode during activation. Always require a passcode unless the device is secured or has access controlled in some other manner (that is, kiosk mode that restricts the device to one app).
        - **Location Services** - If enabled, Setup Assistant prompts for the service during activation
        - **Restore** - If enabled, Setup Assistant prompts for iCloud backup during activation
        - **Apple ID** - If enabled, iOS prompts users for an Apple ID when Intune attempts to install an app without an ID. An Apple ID is required to download iOS App Store apps, including apps installed by Intune.
        - **Terms and Conditions** - If enabled, Setup Assistant prompts users to accept Apple's terms and conditions during activation
        - **Touch ID** - If enabled, Setup Assistant prompts for this service during activation
        - **Apple Pay** - If enabled, Setup Assistant prompts for this service during activation
        - **Zoom** - If enabled, Setup Assistant prompts for this service during activation
        - **Siri** - If enabled, Setup Assistant prompts for this service during activation
        - **Diagnostic Data** - If enabled, Setup Assistant prompts for this service during activation

8. To save the profile settings, choose **Create** on the **Create Enrollment Profile** blade.

## Connect School Data Sync
(Optional) Apple School Manager supports synching class roster data to Azure Active Directory (AD) using Microsoft School Data Sync (SDS). Complete the following steps to use SDS to sync school data.

1. On the **Enrollment Program Token** blade, choose either the blue information banner or **Connect SDS**.
2. Choose **Allow Microsoft School Data Sync to use this token**, setting to **Allow**. This setting allows Intune to connect with SDS in Office 365.
3. To enable a connection between Apple School Manager and Azure AD, choose **Set up Microsoft School Data Sync**. Learn more about [how to set up School Data Sync](https://support.office.com/article/Install-the-School-Data-Sync-Toolkit-8e27426c-8c46-416e-b0df-c29b5f3f62e1).
4. Click **OK** to save and continue.

## Sync managed devices
Now that Intune has been assigned permission to manage your Apple School Manager devices, you can synchronize Intune with the Apple service to see your managed devices in Intune.

1. In Intune in the Azure portal, choose **Device enrollment** > **Apple Enrollment** > **Enrollment Program Devices** > **Sync**. The progress bar shows the amount of time you must wait before requesting Sync again.

  ![Screenshot of Enrollment Program Devices node selected and Sync link being chosen.](./media/enrollment-program-device-sync.png)
2. On the **Sync** blade, choose **Request Sync**. The progress bar shows the amount of time you must wait before requesting Sync again.

  ![Screenshot of Sync blade with Request sync link being chosen.](./media/enrollment-program-device-request-sync.png)

  To comply with Apple’s terms for acceptable traffic, Intune imposes the following restrictions:
   -	A full sync can run no more than once every seven days. During a full sync, Intune refreshes every serial number that Apple has assigned to Intune whether the serial has previously been synced or not. If a full sync is attempted within seven days of the previous full sync, Intune only refreshes serial numbers that are not already listed in Intune.
   -	Any sync request is given 15 minutes to finish. During this time or until the request succeeds, the **Sync** button is disabled.

>[!NOTE]
>You can also assign Apple School Manager serial numbers to profiles from the **Enrollment Program Devices** blade.

## Assign a profile to devices
Apple School Manager devices managed by Intune must be assigned an enrollment profile before they are enrolled.

1. In Intune in the Azure portal, choose **Device enrollment** > **Apple Enrollment**, and then choose **Enrollment Program profiles**.
2. From the list of **Enrollment Program Profiles**, choose the profile you want to assign to devices and then choose **Device Assignments**

 ![Screenshot of Device Assignments with Assign being selected.](./media/enrollment-program-device-assign.png)

3. Choose **Assign** and then choose the Apple School Manager devices you want to assign this profile. You can filter to view available devices:
  - **unassigned**
  - **any**
  - **&lt;profile name&gt;**
4. Choose the devices you want to assign. The checkbox above the column selects up to 1000 listed devices. Click **Assign**. To enroll more than 1000 devices, repeat the assignment steps until all devices are assigned an enrollment profile.

  ![Screenshot of Assign button for assigning enrollment program profile in Intune](media/dep-profile-assignment.png)

## Distribute devices to users

You can now distribute corporate-owned devices to users. When an iOS Apple School Manager device is turned on, it is enrolled for management by Intune. If the device has been activated and is in use, the profile cannot be applied until the device is factory reset.
