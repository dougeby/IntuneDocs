---
# required metadata

title: Enroll iOS corporate-owned Device Enrollment Program devices | Intune Azure preview | Microsoft Docs
description: "Intune Azure preview: "
keywords:
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Enroll iOS corporate-owned Device Enrollment Program devices

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Microsoft Intune can deploy an enrollment profile that enrolls iOS devices that were bought through the Device Enrollment Program (DEP) “over the air.” The enrollment package can include setup assistant options for the device. Devices enrolled through DEP cannot be unenrolled by users.

To manage corporate-owned iOS devices with Apple’s Device Enrollment Program (DEP), your organization must join Apple DEP and get devices through that program. Details of that process are available at:  [https://deploy.apple.com](https://deploy.apple.com). Advantages of the program include hands-free setup of devices without using a USB cable to connect each device to a computer.

Before you can enroll corporate-owned iOS devices with DEP, you need a DEP token from Apple. This token lets Intune sync information about DEP-participating devices that your corporation owns. It also permits Intune to perform Enrollment Profile uploads to Apple and to assign devices to those profiles.

## Prerequisites

Before you follow the steps in this topic, complete the following prerequisites:

- [Get an Apple MDM Push certificate](get-an-apple-mdm-push-certificate.md)
- [Get an Apple DEP token](get-apple-dep-token.md)
- 
## Create an Apple DEP profile for devices

A device enrollment profile defines the settings applied to a group of devices. The following steps show how to create a device enrollment profile for iOS devices enrolled by using DEP.

1. In the **Enrollment** workload, choose **Apple Enrollment**.

2. Under **Manage Apple Device Enrollment Program (DEP) Settings**, select **DEP Profiles**.

3. On the **Apple DEP Profiles** blade, select **Create**.

4. On the **Create Enrollment Profile** blade, enter a name and description for the profile.

5. For **User Affinity** choose whether devices with this profile will enroll with or without user affinity.

 - **Enroll with user affinity** - The device must be affiliated with a user during initial setup and can then be permitted to access company data and email. Choose user affinity for DEP-managed devices that belong to users and that need to use the company portal for services like installing apps. Note that Multifactor authentication (MFA) doesn't work during enrollment on DEP devices with user affinity. After enrollment, MFA works as expected on these devices. 

	>[!NOTE]
	>DEP with user affinity requires WS-Trust 1.3 Username/Mixed endpoint to be enabled to request user token.

 - **Enroll without user affinity** - The device is not affiliated with a user. Use this affiliation for devices that perform tasks without accessing local user data. Apps requiring user affiliation (including the Company Portal app used for installing line-of-business apps) won’t work.

6. Select **Device Management Settings**, configure the following profile settings, and then select **Save**:

	- **Supervised** - a management mode that enables more management options and disabled Activation Lock by default. If you leave the check box blank, you have limited management capabilities.

	- **Locked enrollment** - (Requires Management Mode = Supervised) Disables iOS settings that could allow removal of the management profile. If you leave the check box blank, it allows the management profile to be removed from the Settings menu. This item is set during activation and cannot be changed without a factory reset. 

	- **Allow Pairing** - specifies whether iOS devices can sync with computers. If you choose **Allow Apple Configurator by certificate**, you must choose a certificate under **Apple Configurator Certificates**. 

	- **Apple Configurator Certificates** - If you chose **Allow Apple Configurator by certificate** under **Allow Pairing**, select an Apple Configurator Certificate to import. 

7. Select **Setup Assistant Settings**, configure the following profile settings, and then select **Save**:

	- **Department Name** - Appears when users tap **About Configuration** during activation.

	- **Department Phone** - Appears when the user clicks the Need Help button during activation. 
    - **Setup Assistant Options** - These optional settings can be set up later in the iOS **Settings** menu.
        - **Passcode** - Prompt for passcode during activation. Always require a passcode unless the device will be secured or have access controlled in some other manner (that is, kiosk mode that restricts the device to one app).
        - **Location Services** - If enabled, Setup Assistant prompts for the service during activation
        - **Restore** - If enabled, Setup Assistant prompts for iCloud backup during activation
        - **Apple ID** - If enabled, iOS will prompt users for an Apple ID when Intune attempts to install an app without an ID. An Apple ID is required to download iOS App Store apps, including those installed by Intune.
        - **Terms and Conditions** - If enabled, Setup Assistant prompts users to accept Apple's terms and conditions during activation
        - **Touch ID** - If enabled, Setup Assistant prompts for this service during activation
        - **Apple Pay** - If enabled, Setup Assistant prompts for this service during activation
        - **Zoom** - If enabled, Setup Assistant prompts for this service during activation
        - **Siri** - If enabled, Setup Assistant prompts for this service during activation
        - **Diagnostic Data** - If enabled, Setup Assistant prompts for this service during activation

8. To save the profile settings, select **Create** on the **Create Enrollment Profile** blade.

## Assign Apple DEP serial numbers to profiles

Go to the [Device Enrollment Program Portal](https://deploy.apple.com) (https://deploy.apple.com) and sign in with your company Apple ID. Go to  **Deployment Program** &gt; **Device Enrollment Program** &gt; **Manage Devices**. Specify how you will **Choose Devices**, provide device information and specify details by device **Serial Number**, **Order Number**, or **Upload CSV File**. Next, choose **Assign to Server** and choose the &lt;ServerName&gt; specified for Microsoft Intune, and then choose **OK**.

## Synchronize DEP-managed devices

1. In the Azure portal **Enrollment** workload, choose **Apple Enrollment**.

2. Under **Manage Apple Device Enrollment Program (DEP) Settings**, select **DEP Serial Numbers**.

4. On the **Apple DEP Serial Numbers** blade, select **Sync**.

5. On the **Sync** blade, select **Request Sync**. The progress bar shows the amount of time you must wait before requesting Sync again.

    To comply with Apple’s terms for acceptable DEP traffic, Intune imposes the following restrictions:
     -	A full DEP sync can run no more than once every seven days. During a full sync, Intune refreshes every serial number that Apple has assigned to Intune whether the serial has previously been synced or not. If a full sync is attempted within seven days of the previous full sync, Intune only refreshes serial numbers that are not already listed in Intune.
     -	Any sync request is given 10 minutes to finish. During this time or until the request succeeds, the **Sync** button is disabled.

>[!NOTE]
>You can also assign DEP serial numbers to profiles from the **Apple DEP Serial Numbers** blade.

## Distribute devices to users

You can now distribute corporate-owned devices to users. When an iOS device is turned on, it will be enrolled for management by Intune.

