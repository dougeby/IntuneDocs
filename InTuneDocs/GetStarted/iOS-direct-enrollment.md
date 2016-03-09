---
title: Direct enrollment for iOS devices with Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid:
author: NathBarn
---
# Enroll corporate-owned devices
Organizations can use Intune to manage large numbers of mobile devices with a single user account called a [device enrollment manager account](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md). After creating a device enrollment manager account, that account can be used to enroll more than the standard five devices allowed by default to normal users. After creating a device enrollment manager account, you will be ready to enroll company owned devices on behalf of your end users.
elect from the following corporate device enrollment options to learn more:

> [!div class="op_single_selector"]
- [Apple device enrollment program (DEP) for iOS](iOS-device-enrollment-program.md)
- [Apple Configurator Setup Assistant for iOS](iOS-setup-assistant-enrollment.md)
- [Apple Configurator direct Enrollment for iOS](iOS-direct-enrollment.md)
- [Specify COD devices using IMEI numbers](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md)



## Direct enrollment for iOS devices with Microsoft Intune
Using Apple Configurator you can enroll iOS devices for management without resetting them to factory settings. This method is for devices with **No user affinity** and requires you to USB-connect the iOS device to a Mac computer to setup corporate enrollment. The Company Portal app is not supported for direct enrolled devices. This guidance assumes you are using Apple Configurator 2.0 on a Mac computer.

1.  **Create a profile for devices**
    A device enrollment profile defines the settings applied to devices. If you have not already, create a device enrollment profile for iOS devices enrolled using Apple Configurator.

    ###### To create a profile

    1.  In the [Microsoft Intune administration console](http://manage.microsoft.com) go **Policy** &gt; **Corporate Device Enrollment**, and then click **Add…**.

    2.  Enter details for the device profiles:

        -   **Name** – Name of the device enrollment profile. Not visible to users.

        -   **Description** - Description of the device enrollment profile. Not visible to users.

        -   **User affiliation** – Specifies how devices are enrolled. For Direct Enrollment, select **No user affinity**.

        -   **Device group pre-assignment** – All devices deployed this profile will initially belong to this group. You can reassign devices after enrollment.

    3.  Click **Save Profile** to add the profile.

2.  **Add iOS devices to enroll with Apple Configurator**
    In the [Microsoft Intune administration console](http://manage.microsoft.com) go **Groups** &gt; **All Devices** &gt; **Corporate pre-enrolled devices** &gt; **By iOS serial number**, and then click **Add devices…**. You can add devices in two ways:

    -   **Upload a CSV file containing serial numbers** – Create a comma-separated value (.csv) list of two columns without a header, limited to 5000 devices or 5MB per csv file.

        |||
        |-|-|
        |&lt;Serial #1&gt;|&lt;Device #1 Details&gt;|
        |&lt;Serial#2&gt;|&lt;Device #2 Details&gt;|
        This .csv file when viewed in a text editor appears as:

        ```
        0000000,PO 1234
        111111111,PO 1234
        ```

    -   **Manually add device details** - Enter the serial number and device details of up to five devices, and then click **Next**.

    > [!NOTE]
    > If you must later remove corporate-owned devices from Intune management, you must remove the device serial number from Intune in the **Corporate-owned devices** group to disable device enrollment.  If Intune performs a disaster recovery procedure on or around the time that serial numbers were removed, you will need to verify that only active devices’ serial numbers are present in that group.

3.  **Select devices to enroll**
    Confirm the devices to enroll. Serial numbers already enrolled or enrolled by other means cannot be imported. Click **Next** to continue.

4.  **Assign profile**
    Specify the profile to assign to added devices from the list of available profiles, review the **Enrollment profile details**, and then click **Finish**. Manually added devices can be assigned to any Enrollment profile.

5.  **Select a profile to deploy to iOS devices**
    In the [Microsoft Intune administration console](http://manage.microsoft.com) go **Policy** &gt; **Corporate Device Enrollment**, and then select the device profile to deploy to mobile devices. This profile should be the same profile that you assigned to deploy in the previous step. Click **Export…** in the taskbar. Click **Download profile** and save the downloaded .mobileconfig file.

6.  **Transfer the file**
    Copy the downloaded .mobileconfig file to a Mac computer.
    > [!NOTE]
    > The enrollment profile URL is valid for two weeks from when it is exported. After two, you must export a new enrollment profile URL to enroll iOS devices with Setup Assistant.
7.  **Prepare the device with Apple Configurator**
    iOS devices are connected to the Mac computer and enrolled for mobile device management.

    1.  On a Mac computer, launch **Apple Configurator 2.0**.

    2.  Connect the iOS device to the Mac computer with a USB cord. Close **Photos**, **iTunes**, and other apps that open for the device when the device is detected.

    3.  In Apple Configurator, single-click the connected iOS device, and then click the **Add** button. Options that can be added to the device appear in the drop-down list. Click **Profiles** .

    4.  Use the file picker to select the .mobileconfig file you exported from Intune, and then click **Add**. The profile is added to the device.  If the device is **Unsupervised**, the installation will require acceptance on the device.

8.  **Install the profile**
    You are ready to install the profile on the iOS device. The device must have already completed the Setup Assistant and be ready to use.  If enrollment entails app deployments, the device should have an Apple ID set up because the app deployments will require that you have an Apple ID signed in for the App Store.

    ###### Completing profile acceptance for unsupervised iOS devices

    1.  Unlock the iOS device.

    2.  In the **Install profile** dialog for **Management profile**,  tap **Install**.

    3.  Provide **Device Passcode** or **Apple ID**, if required.

    4.  Accept the **Warning**, and tap **Install**.

    5.  Accept the **Remote Warning**, and tap **Trust**.

    6.  When the **Profile Installed** box confirms the profile has **Installed**, click **Done**.

9. **Verify profile**
    On the iOS device, launch **Settings** and go **General** &gt; **Device Management** &gt; **Management Profile** &gt;  and confirm the profile installation is listed, check the iOS policy restrictions, and installed apps. Policy restrictions and apps may take up to 10 minutes to appear on the device.

10. **Distribute devices**
    The iOS device is now enrolled with Intune and managed.


### See also
[Get ready to enroll devices](get-ready-to-enroll-devices-in-microsoft-intune.md)
