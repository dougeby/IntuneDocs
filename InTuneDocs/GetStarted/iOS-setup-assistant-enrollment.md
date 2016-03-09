---
title: Setup Assistant enrollment for iOS devices with Microsoft Intune
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



## Setup Assistant enrollment for iOS devices with Microsoft Intune
Using Apple Configurator you can factory reset iOS devices and prepares them for setup by the device’s new user.  This method requires you to USB-connect the iOS device to a Mac computer to setup corporate enrollment and assumes you are using Apple Configurator 2.0.

**Prerequisites**
* Physical access to iOS devices - Devices must be unconfigured (factory reset) without password protection
* Device serial numbers - [How to get an iOS serial number](https://support.apple.com/en-us/HT204308)
* USB connection cables
* Mac computer with [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)


1.  **Create mobile device group** (Optional)
    If your business requires mobile device groups to help manage devices, create those groups. [Use groups to manage users and devices with Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).

2.  **Create a profile for devices**
    A device enrollment profile defines the settings applied to a group of devices. If you have not already, create a device enrollment profile for iOS devices enrolled using Apple Configurator.

    ###### To create a profile

    1.  In the [Microsoft Intune administration console](http://manage.microsoft.com) go **Policy** &gt; **Corporate Owned Devices**, and then click **Add…**.

    2.  Enter details for the device profiles:

        -   **Name** – Name of the device enrollment profile. (Not visible to users)

        -   **Description** - Description of the device enrollment profile. (Not visible to users)

        -   **Enrollment Details** – Specifies how devices are enrolled.

            -   **Prompt for user affinity** – The iOS device can be affiliated with a user during initial setup and could then be permitted to access company data and email as that user. For most Setup Assistant scenarios, use **Prompt for user affinity**.
            This mode supports a number of scenarios:

                -   **Corporate-owned personal device** – “Choose Your Own Device” (CYOD) Similar to privately owned or personal devices but the administrator has certain privileges including permission to wipe, reset, administer, and unenroll the device. The device’s user can install apps and has most other permissions for device use where not blocked by management policy.

                -   **Device enrollment manager account** – The device is enrolled using a special Intune administrator account. It can be managed as a private account, but only a user who knows the enrollment manager credentials can install apps, wipe, reset, administer, and unenroll the device. For information about enrolling a device shared by many users through a common account, see [Enroll corporate-owned devices with the Device Enrollment Manager in Microsoft Intune](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md).

            -   **No user affinity** – The device is user-less. Use this affiliation for devices that perform tasks without accessing local user data. Apps requiring user affiliation are disabled or won’t work.

        -   **Device group pre-assignment** – All devices deployed this profile will initially belong to this group. You can reassign devices after enrollment.

          -  **Device Enrollment Program** - The Apple Device Enrollment Program (DEP) cannot be used with Setup Assistant enrollment. Ensure the toggle is set to **off**.

    3.  Click **Save Profile** to add the profile.

3.  **Add iOS devices to enroll with Setup Assistant**
    In the [Microsoft Intune administration console](http://manage.microsoft.com) go **Groups** &gt; **All Devices** &gt; **All Corporate-owned Devices** &gt; **All Devices**, and then click **Add devices…**. You can add devices in two ways:

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

    -   **Manually add device details** - Enter the serial number and device details of up to five devices

    > [!NOTE]
    > If you must later remove corporate-owned devices from Intune management, you might need to remove the device serial number from Intune in the **Corporate-owned devices** group to disable device enrollment.  If Intune performs a disaster recovery procedure on or around the time that serial numbers were removed, you will need to verify that only active devices’ serial numbers are present in that group.

    And then click **Next**.

4.  **Select devices to enroll**
    Confirm the devices to enroll. Serial numbers already enrolled or enrolled by other means cannot be imported. Click **Next** to continue.

5.  **Assign profile**
    Specify the profile to assign to added devices from the list of available profiles, review the **Enrollment profile details**, and then click **Finish**. Manually added devices can be assigned to any Enrollment profile.

6.  **Export a profile to deploy to iOS devices**
    In the [Microsoft Intune administration console](http://manage.microsoft.com) go **Policy** &gt; **Corporate Device Enrollment**, and then select the device profile to deploy to mobile devices. Click **Export…** in the taskbar. Copy and save the **Profile URL**. You will upload it in Apple Configurator later to define the Intune profile used by iOS devices.

    > [!NOTE]
    > The enrollment profile URL is valid for two weeks from when it is exported. After two, you must export a new enrollment profile URL to enroll iOS devices with Setup Assistant.

7.  **Prepare the device with Apple Configurator**
    iOS devices are connected to the Mac computer and enrolled for mobile device management.

    1.  On a Mac computer, open **Apple Configurator 2**. In the menu bar, click **Apple Configurator 2**, and click **Preferences**.

    2. In the preferences pane, select **Servers** and click the “+” symbol below the left pane to launch the MDM Server wizard. Click **Next**.

    3. Enter the **Name** and **Enrollment URL** for the MDM server from Step #6 above. For the Enrollment URL enter the enrollment profile URL exported from Intune. Click **Next**.  

       If you receive a warning about trust profile requirements for Apple TV, you may safely cancel the **Trust Profile** option by clicking the grey "X". You can also safely disregard any Anchor certificate warning. To continue, click **Next** until the wizard is complete.

    4.  On the **Servers**  pane, click “Edit” beside the new server’s profile. Ensure that the Enrollment URL exactly matches the URL exported from Intune. Reenter the original URL if it is different and **Save** the enrollment profile exported from Intune.

    5.  Connect the iOS mobile devices to the Apple computer with a USB adapter.

        > [!WARNING]
        > The devices will be reset to factory configurations during the enrollment process. As a best practice, reset the device and power it on. As a best practice, devices should be at the **Hello** screen when you start Setup Assistant.

    6.  Click **Prepare**. On the **Prepare iOS Device** pane, select **Manual** and then click **Next**.

    7. On the **Enroll in MDM Server** pane, select the server name you created and then click **Next**.

    8. On the **Supervise Devices** pane, select the level of supervision, and then click **Next**.

    9. On the **Create an Organization** pane, choose the **Organization** or create a new organization,  and then click **Next**.

    10. On the **Configure iOS Setup Assistant** pane, choose the steps presented to the user, and then click **Prepare**. If prompted, authenticate to update trust settings.  

    11. When the iOS device finishes preparing, you can disconnect the USB cable.  

8.  **Distribute devices**
    The devices are now ready for corporate enrollment. Power down the devices and distribute them to users. When the device is turned on, the Setup Assistant will start.



### See also
[Get ready to enroll devices](get-ready-to-enroll-devices-in-microsoft-intune.md)
