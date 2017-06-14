---
# required metadata

title: Set up Apple School Manager Program enrollment for iOS devices
titleSuffix: "Intune on Azure"
description: Learn how to set up Apple School Manager program enrollment for corporate-owned iOS devices with Intune"
keywords:
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/12/2017
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

This topic helps IT administrators enable iOS device enrollment for devices purchased through the [Apple School Manager](https://school.apple.com/) (ASM) program. Microsoft Intune can deploy an enrollment profile “over the air” that enrolls ASM devices into management. The administrator never has to touch each managed device. An ASM profile contains management settings that are applied to devices during enrollment including Setup Assistant options.

**ASM Enrollment steps**
1. [Get an ASM token and assign devices](#get-the-asm-token-and-assign-devices)
2. [Create an enrollment profile](#create-an-apple-enrollment-profile)
3. [Connect School Data Sync](#connect-school-data-sync) (Optional)
4. [Sync ASM-managed devices](#sync-asm-managed-devices)
5. [Assign ASM profile to devices](#assign-an-asm-profile-to-devices)
6. [Distribute devices to users](#distribute-devices-to-users)

>[!NOTE]
>ASM enrollment can't be used with Apple's [Device Enrollment Program (DEP)](device-enrollment-program-enroll-ios.md) or Intune's [device enrollment manager](device-enrollment-manager-enroll.md) account.

## Get the Apple ASM token and assign devices

Before you can enroll corporate-owned iOS devices with Apple School Manager (ASM), you need an ASM token (.p7m) file from Apple. This token lets Intune sync information about ASM-participating devices. It also permits Intune to perform enrollment profile uploads to Apple and to assign devices to those profiles. While you are in the Apple portal, you can also assign device serial numbers to manage.

**Prerequisites**
- [Apple MDM Push certificate](apple-mdm-push-certificate-get.md)
- Signed up for [Apple School Management](http://school.apple.com)

**Step 1. Download an Intune public key certificate required to create an Apple ASM token.**<br>
1. In the Azure [Intune portal](https://aka.ms/intuneportal), choose **Device enrollment** and then select **Enrollment program token**.
2. In the **Enrollment program token** blade, select **Download your public key** to download and save the encryption key (.pem) file locally. The .pem file is used to request a trust-relationship certificate from the Apple School Manager portal.

**Step 2. Download an ASM token and assign devices.**<br>
Select **Create a token via Apple School Manager**, and sign in with your company Apple ID. You can use this Apple ID to renew your ASM token.

   1.  In the [Apple School Manager portal](https://school.apple.com), go to **MDM Servers**, and then select **Add MDM Server** (upper right).
   2.  Enter the **MDM Server Name**. The server name is for your reference to identify the mobile device management (MDM) server. It is not the name or URL of the Microsoft Intune server.
   3.  Select **Upload File...** in the Apple portal, browse to the .pem file, and select **Save MDM Server** (lower right).
   4.  Select **Get Token** and then download the server token (.p7m) file to your computer.
   5. Go to  **Device Assignments**, and **Choose Device** by manual entry of **Serial Numbers**, **Order Number**, or **Upload CSV File**.
   6.	Choose the action **Assign to Server**, and select the **MDM Server** you created.
   7. Specify how you will **Choose Devices**, and then provide device information and specify details by device **Serial Number**, **Order Number**, or **Upload CSV File**.
   8. Choose **Assign to Server** and choose the &lt;ServerName&gt; specified for Microsoft Intune, and then choose **OK**.

**Step 3. Enter the Apple ID used to create your ASM token.**<br>This ID should be used to renew your Apple ASM token and is stored for your future reference.

**Step 4. Locate and upload your token.**<br>
Go to the certificate (.p7m) file, choose **Open**, and then choose **Upload**. Intune automatically syncs your ASM devices from Apple.

## Create an Apple enrollment profile
A device enrollment profile defines the settings applied to a group of devices during enrollment.

1. In the Intune portal, choose **Device enrollment**, and then choose **Apple Enrollment**.
2. Under **Enrollment Program**, select **Enrollment Program Profiles**.
3. On the **Enrollment Program Profiles** blade, select **Create**.
4. On the **Create Enrollment Profile** blade, enter a **Name** and **Description** for the profile that is displayed in the Intune portal.
5. For **User Affinity**, choose whether devices with this profile enroll with or without user affinity.

 - **Enroll with user affinity** - The device must be affiliated with a user during initial setup and can then be permitted to access company data and email. Choose user affinity for ASM-managed devices that users log in to with their managed Apple ID.

 >[!NOTE]
 >Multifactor authentication (MFA) doesn't work during enrollment on ASM devices with user affinity. After enrollment, MFA works as expected on these devices.

  Apple School Manager's Shared iPad mode requires user enroll with user affinity.

 >[!NOTE]
	>ASM with user affinity requires [WS-Trust 1.3 Username/Mixed endpoint](https://technet.microsoft.com/library/adfs2-help-endpoints) to be enabled to request user token. [Learn more about WS-Trust 1.3](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

 - **Enroll without user affinity** - The device is not affiliated with a user. Use this affiliation for devices that perform tasks without accessing local user data. Apps requiring user affinity (including the Company Portal app used for installing line-of-business apps) won’t work.

6. Select **Device Management Settings**. These items are set during activation and require a factory reset to change. configure the following profile settings, and then select **Save**:

	- **Supervised** - a management mode that enables more management options and disabled Activation Lock by default. If you leave the check box blank, you have limited management capabilities.

	- **Locked enrollment** - (Requires Management Mode = Supervised) Disables iOS settings that could allow removal of the management profile. If you leave the check box blank, it allows the management profile to be removed from the Settings menu.

  - **Shared iPad** - (Requires **Enroll with User Affinity** and **Supervised** mode.) Allows multiple users to logon to enrolled iPads by using a managed Apple ID. Managed Apple IDs are created in the Apple School Manager portal.

  >[!NOTE]
  >If **Shared iPad** mode is enabled in a profile and either **User Affinity** or **Supervised** mode is then set to **Off**, Shared iPad mode is disabled for the enrollment profile.

  - **Maximum Cached Users** - (Requires **Shared iPad** = **Yes**) Creates a partition on the device for each user. The recommended value is the number of students likely to use the device over a period of time. For example, if six students use the device regularly during the week, set this number to six.  

	- **Allow Pairing** - specifies whether iOS devices can sync with computers. If you choose **Allow Apple Configurator by certificate**, you must choose a certificate under **Apple Configurator Certificates**.

	- **Apple Configurator Certificates** - If you chose **Allow Apple Configurator by certificate** under **Allow Pairing**, select an Apple Configurator Certificate to import.

7. Select **Setup Assistant Settings**, configure the following profile settings, and then select **Save**:

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

8. To save the profile settings, select **Create** on the **Create Enrollment Profile** blade.

## Connect School Data Sync
(Optional) ASM supports synching class roster data to Azure Active Directory (AD) using Microsoft School Data Sync (SDS). Complete the following steps to use SDS to sync school data.

1. On the **Enrollment Program Token** blade, select either the blue information banner or **Connect SDS**.
2. Select **Allow Microsoft School Data Sync to use this token**, setting to **Allow**. This setting allows Intune to connect with SDS in Office 365.
3. To enable a connection between ASM and Azure AD, select **Set up Microsoft School Data Sync**. Learn more about [how to set up School Data Sync](https://support.office.com/article/Install-the-School-Data-Sync-Toolkit-8e27426c-8c46-416e-b0df-c29b5f3f62e1).
4. Click **OK** to save and continue.

## Sync ASM-managed devices
Now that Intune has been assigned permission to manage your ASM devices, you can synchronize Intune with the ASM service to see your managed devices in the Intune portal.

1. In the Intune portal, choose **Device enrollment**, and then choose **Apple Enrollment**.
2. Under **Enrollment Program Devices**, select **Sync**. The progress bar shows the amount of time you must wait before requesting Sync again.

    To comply with Apple’s terms for acceptable ASM traffic, Intune imposes the following restrictions:
     -	A full ASM sync can run no more than once every seven days. During a full sync, Intune refreshes every serial number that Apple has assigned to Intune whether the serial has previously been synced or not. If a full sync is attempted within seven days of the previous full sync, Intune only refreshes serial numbers that are not already listed in Intune.
     -	Any sync request is given 15 minutes to finish. During this time or until the request succeeds, the **Sync** button is disabled.

>[!NOTE]
>You can also assign ASM serial numbers to profiles from the **Enrollment Program Devices** blade.

## Assign an ASM profile to devices
ASM devices managed by Intune must be assigned an ASM profile before they are enrolled.

1. In the Intune portal, choose **Device enrollment** > **Apple Enrollment**, and then select **Enrollment Program profiles**.
2. From the list of **Enrollment Program Profiles**, select the profile you want to assign to devices and then select **Device Assignments**
3. Select **Assign** and then select the ASM devices you want to assign this profile. You can filter to view ASM available devices:
  - **unassigned**
  - **any**
  - **&lt;ASM profile name&gt;**
4. Select the devices you want to assign. The checkbox above the column selects up to 1000 listed devices. Click **Assign**. To enroll more than 1000 devices, repeat the assignment steps until all devices are assigned an ASM profile.

## Distribute devices to users

You can now distribute corporate-owned devices to users. When an iOS ASM device is turned on, it is enrolled for management by Intune. If the device has been activated and is in use, the profile cannot be applied until the device is factory reset.

### How users install and use the Company Portal on their devices

Devices that are configured with user affinity can install and run the Company Portal app to download apps and manage devices. After users receive their devices, they must run Setup Assistant and install the Company Portal app.
