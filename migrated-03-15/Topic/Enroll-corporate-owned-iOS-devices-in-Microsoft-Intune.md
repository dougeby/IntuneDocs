---
title: Enroll corporate-owned iOS devices in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 2d3ca4ab-f20c-4d56-9413-f8ef19cf0722
author: NathBarn
robots: noindex,nofollow
---
# Enroll corporate-owned iOS devices in Microsoft Intune
Intune supports the enrollment of corporate-owned iOS devices using the Apple Device Enrollment Program (DEP) or the [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) tool running on a Mac computer.

You can enroll corporate-enrolled iOS devices in three ways:

-   **Setup Assistant Enrollment** – Factory resets the device and prepares it for setup by the device’s new user. This method supports DEP or Apple Configurator enrollments.

-   **Direct Enrollment** – Creates an Apple Configurator-compliant file for use during device preparation. The enrolled device isn’t factory reset but has no user affiliation. This method cannot be used for DEP enrollment.

-   **Device Enrollment Program (DEP)** – Deploys an enrollment profile that enrolls the device “over the air” and can include setup assistant options for the device. Devices enrolled through DEP cannot be un-enrolled by users.

## Setup Assistant Instructions

1.  **Create mobile device group** (Optional) 
    If your business requires mobile device groups to help manage devices, create those groups. [Use groups to manage users and devices with Microsoft Intune](../Topic/Use-groups-to-manage-users-and-devices-with-Microsoft-Intune.md).

2.  **Create a profile for devices**
    A device enrollment profile defines the settings applied to a group of devices. If you have not already, create a device enrollment profile for iOS devices enrolled using Apple Configurator. **Prompt for User Affiliation** should be enabled for **Setup Assistant** enrollment

    ###### Instructions

    1.  In the [Microsoft Intune administration console](http://manage.microsoft.com) go **Policy** &gt; **Corporate Owned Devices**, and then click **Add…**.

    2.  Enter details for the device profiles:

        -   **Name** – Name of the device enrollment profile. (Not visible to users)

        -   **Description** - Description of the device enrollment profile. (Not visible to users)

        -   **User affiliation** – Specifies how devices are enrolled.

            -   **Prompt for user affinity** – The device can be affiliated with a user during initial setup and could then be permitted to access company data and email as that user. This mode supports a number of scenarios:

                -   **Corporate-owned personal device** – “Choose Your Own Device” (CYOD) Similar to privately owned or personal devices but the administrator has certain privileges including permission to wipe, reset, administer, and unenroll the device. The device’s user can install apps and has most other permissions for device use where not blocked by management policy.

                -   **Device enrollment manager account** – The device is enrolled using a special Intune administrator account. It can be managed as a private account, but only a user who knows the enrollment manager credentials can install apps, wipe, reset, administer, and unenroll the device. For information about enrolling a device shared by many users through a common account, see [Enroll corporate-owned devices with the Device Enrollment Manager in Microsoft Intune](../Topic/Enroll-corporate-owned-devices-with-the-Device-Enrollment-Manager-in-Microsoft-Intune.md).

            -   **No user affinity** – The device is user-less. Use this affiliation for devices that perform tasks without accessing local user data. Apps requiring user affiliation are disabled or won’t work.

        -   **Device group pre-assignment** – All devices deployed this profile will initially belong to this group. You can reassign devices after enrollment.

    3.  Click **Save Profile** to add the profile.

3.  **Add iOS devices to enroll with Setup assistant**
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
    > If you must later remove corporate-owned devices from Intune management, you must remove the device serial number from Intune in the **Corporate-owned devices** group to disable device enrollment.  If Intune performs a disaster recovery procedure on or around the time that serial numbers were removed, you will need to verify that only active devices’ serial numbers are present in that group.

    And then click **Next**.

4.  **Select devices to enroll**
    Confirm the devices to enroll. Serial numbers already enrolled or enrolled by other means cannot be imported. Click **Next** to continue.

5.  **Assign profile**
    Specify the profile to assign to added devices from the list of available profiles, review the **Enrollment profile details**, and then click **Finish**. Manually added devices can be assigned to any Enrollment profile, but DEP-synced devices must be assigned to a DEP-enabled profile.

6.  **Select a profile to deploy to iOS devices**
    In the [Microsoft Intune administration console](http://manage.microsoft.com) go **Policy** &gt; **Corporate Device Enrollment**, and then select the device profile to deploy to mobile devices. Click **Export…** in the taskbar. Copy and save the **Profile URL**. You will upload it in Apple Configurator later to define the Intune profile used by iOS devices. For DEP devices, simply run Setup Assistant from a factory image or factory reset on the device.

7.  **Prepare the device with Apple Configurator**
    iOS devices are connected to the Mac computer and enrolled for mobile device management.

    > [!WARNING]
    > The devices will be reset to factory configurations during the enrollment process.

    1.  On a Mac computer, open **Apple Configurator**.

    2.  Select **Setup** and then **Device Enrollment**. Enter the enrollment URL from Intune in the **MDM Server URL**, and then click **Save**.

    3.  Connect the iOS mobile devices to the Apple computer with a USB adapter.

    4.  Click **Prepare**. Progress is displayed in Apple Configurator.

8.  **Distribute devices**
    The devices are now ready for corporate enrollment. Power down the devices and distribute them to users. When the device is turned on, the setup assistant will start and prompt the user for their work or school account.

## Direct Enrollment Instructions

1.  **Create mobile device group** (Optional) 
    If your business or organization requires mobile device groups to help manage devices, create those groups. [Use groups to manage users and devices with Microsoft Intune](../Topic/Use-groups-to-manage-users-and-devices-with-Microsoft-Intune.md).

2.  **Create a profile for devices**
    A device enrollment profile defines the settings applied to devices. If you have not already, create a device enrollment profile for iOS devices enrolled using Apple Configurator.

    ###### Instructions

    1.  In the [Microsoft Intune administration console](http://manage.microsoft.com) go **Policy** &gt; **Corporate Device Enrollment**, and then click **Add…**.

    2.  Enter details for the device profiles:

        -   **Name** – Name of the device enrollment profile. Not visible to users.

        -   **Description** - Description of the device enrollment profile. Not visible to users.

        -   **User affiliation** – Specifies how devices are enrolled. For Direct Enrollment, select **Do not prompt**.

        -   **Device group pre-assignment** – All devices deployed this profile will initially belong to this group. You can reassign devices after enrollment.

    3.  Click **Save Profile** to add the profile.

3.  **Select and export an enrollment profile file**
    In the [Microsoft Intune administration console](http://manage.microsoft.com) go **Policy** &gt; **Corporate Device Enrollment**, and then select the device profile to deploy to your iOS devices. Click **Export…** in the taskbar. The **Apple Configuration Method** window opens.

    Under **Apple configurator Method**, select **Direct enrollment**. Download and save the direct enrollment profile file (.mobileconfig). You must import this file into Apple Configurator to define the Intune profile used by iOS devices. An enrollment profile file is valid for 2 weeks.

4.  **Import the profile file and prepare the device**
    Copy the Intune enrollment profile file (.mobileconfig) to a Mac computer and import the file into Apple Configurator. You can then USB-connect iOS devices to enroll them using Apple Configurator. Devices configured with this file must already have completed Setup Assistant and must have an internet connection when the file is applied.

## Enroll corporate-owned iOS devices in Microsoft Intune using Apple Device Enrollment Program
To manage corporate-owned iOS devices with Apple’s Device Enrollment Program (DEP), companies must join Apple DEP and acquire devices through that program. Details of that process are available at:  [https://deploy.apple.com](https://deploy.apple.com)

Before you can enroll corporate-owned iOS devices with DEP, you need a DEP Token from Apple. This token allows Intune to sync information about DEP-participating devices owned by your corporation. It also permits Intune to perform Enrollment Profile uploads to Apple and to assign devices to those profiles.

### <a name="BKMK_DEPtok"></a>

1.  **Start managing iOS devices with Microsoft Intune**
    Before you can enroll iOS Device Enrollment Program (DEP) devices, you must complete steps to [Set up iOS and Mac management with Microsoft Intune](../Topic/Set-up-iOS-and-Mac-management-with-Microsoft-Intune.md).

2.  **Get an Encryption Key**
    As an administrative user, open the [Microsoft Intune administration console](http://manage.microsoft.com), go to **Admin** &gt; **Mobile Device Management** &gt; **iOS** &gt; **Device Enrollment Program**, and click **Download Encryption Key**. Save the encryption key (.pem) file locally. The .pem file is used to request a trust-relationship certificate from the Apple Device Enrollment Program portal.

3.  **Get a Device Enrollment Program token**
    Go to the [Device Enrollment Program Portal](https://deploy.apple.com) (https://deploy.apple.com) and sign in with your company Apple ID. This Apple ID must be used in future to renew your DEP token.

    1.  In the [Device Enrollment Program Portal](https://deploy.apple.com) portal, go **Device Enrollment Program** &gt; **Manage Servers**, and then click **Add MDM Server**.

    2.  Enter the **MDM Server Name** and then click **Next**. The server name is for your reference to identify the MDM server. It is not name or URL of the Microsoft Intune server.

    3.  The **Add &lt;ServerName&gt;** dialog box opens. Click **Choose File…** to upload the .pem file and then click **Next**.

    4.  The **Add &lt;ServerName&gt;** dialog box displays a **Your Server Token** link. Download the server token (.p7m) file to your computer, and then click **Done**.

    This certificate (.p7m) file is used to establish a trust relationship between Intune and Apple’s Device Enrollment Program servers.

4.  **Add the DEP token to Intune**
    In the [Microsoft Intune administration console](http://manage.microsoft.com), go to **Admin** &gt; **Mobile Device Management** &gt; **iOS** &gt; **Device Enrollment Program**, and click **Upload the DEP Token**. **Browse** to the certificate (.p7m) file, enter your **Apple ID**, and click **Upload**.

5.  **Add the Corporate Device Enrollment Policy**
    In the [Microsoft Intune administration console](http://manage.microsoft.com), go to **Policy** &gt; **Corporate Device Enrollment** and then click **Add**. Provide **General** details including **Name** and **Description**, specify whether devices assigned to the profile have user affinity or belong to a group, and then enable **Configure Device Enrollment Program settings for this policy** to support DEP. The **Setup assistant panes** define the iOS device settings configured during setup.

6.  **Assign DEP Devices for Management**
    Go to the [Device Enrollment Program Portal](https://deploy.apple.com) (https://deploy.apple.com) and sign in with your company Apple ID. Go **Deployment Program** &gt; **Device Enrollment Program** &gt; **Manage Devices**. Specify how you will **Choose Devices**, provide device information and specify details by device **Serial Number**, **Order Number**, or **Upload CSV File**. Next, select **Assign to Server** and select the &lt;ServerName&gt; specified for Microsoft Intune, and then click **OK**.

7.  **Distribute devices to users**
    Your corporate-owned devices can now be distributed to users. When an iOS device is turned on it will be enrolled for management by Intune.

8.  **Synchronize DEP-Managed Devices**
    As an administrative user, open the [Microsoft Intune administration console](http://manage.microsoft.com), go to **Admin** &gt; **Mobile Device Management** &gt; **iOS** &gt; **Device Enrollment Program**, and click **Sync now**. A sync request is sent to Apple. To see DEP-managed devices after synchronization, in the [Microsoft Intune administration console](http://manage.microsoft.com) go **Groups** &gt; **All Corporate-Owned Devices**. In the **Corporate-owned Devices** workspace, the **State** for managed devices reads “Not contacted” until the device is powered on and runs the Setup Assistant to enroll the device.

## Next steps
**Once devices are enrolled you can:**

-   [Understand your devices with inventory in Microsoft Intune](../Topic/Understand-your-devices-with-inventory-in-Microsoft-Intune.md)

-   [Enable access to company resources with Microsoft Intune - deleted](../Topic/Enable-access-to-company-resources-with-Microsoft-Intune---deleted.md)

-   [Deploy apps to mobile devices in Microsoft Intune - deleted](../Topic/Deploy-apps-to-mobile-devices-in-Microsoft-Intune---deleted.md)

-   [Manage settings and features on your devices with Microsoft Intune policies](../Topic/Manage-settings-and-features-on-your-devices-with-Microsoft-Intune-policies.md)

-   [Help protect your data with remote wipe, remote lock, or passcode reset using Microsoft Intune](../Topic/Help-protect-your-data-with-remote-wipe,-remote-lock,-or-passcode-reset-using-Microsoft-Intune.md)

## See Also
[Get ready to enroll devices in Microsoft Intune](../Topic/Get-ready-to-enroll-devices-in-Microsoft-Intune.md)

