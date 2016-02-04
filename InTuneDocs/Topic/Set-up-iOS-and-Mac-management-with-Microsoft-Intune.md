---
title: Set up iOS and Mac management with Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: dc451224-1372-4b84-b641-cfa67cb3849b
author: NathBarn
---
# Set up iOS and Mac management with Microsoft Intune
With [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], you can enable BYOD ("bring your own device") iOS and Mac OS X device enrollment to give access to company email and apps to iPhone, iPad and Mac users. Once users install the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] company portal app, their devices can be targeted with policy using the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] administration console.  Before you can manage iOS and Mac devices, you must import an Apple Push Notification service (APNs) certificate from Apple. This certificate allows Intune to manage iOS and Mac devices and establishes an accredited and encrypted IP connection with the mobile device management authority services.

As an alternative to enrollment with the Company Portal app, you can also [enroll corporate-owned iOS devices](https://technet.microsoft.com/library/dn408185.aspx#BKMK_CODiOS) .

## Prepare to manage iOS and Mac devices with Microsoft Intune
The following steps allow [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] to manage iOS devices using the Company Portal.

#### Set up iOS and Mac enrollment with Intune

1.  **Set up Intune**
    If you haven’t already, prepare for mobile device management by  [setting the mobile device management authority](https://technet.microsoft.com/library/mt346013.aspx) as **Microsoft Intune** and setting up MDM.

2.  **Get a certificate signing request**
    As an administrative user, open the [Microsoft Intune administration console](http://manage.microsoft.com), go to **Administration** &gt; **Mobile Device Management** &gt; **iOS and Mac OS X** &gt; **Upload an APNs Certificate**, and click **Download the APNs certificate request**. Save the certificate signing request (.csr) file locally. The .csr file is used to request a trust relationship certificate from the Apple Push Certificates Portal.

    ![](../Image/Intune-iOS-enrollment-with-APNS.bmp)

3.  **Get an Apple Push Notification service certificate**
    Go to the [Apple Push Certificates Portal](http://go.microsoft.com/fwlink/?LinkId=269844) and sign in with your company Apple ID to create the APNs certificate using the .csr file. This Apple ID must be used in future to renew your APNs certificate. Download the APNs (.pem) certificate and save the file locally. This APNs certificate file is used to establish a trust relationship between the Apple Push Notification server and Intune’s mobile device management authority.

4.  **Add the APNs certificate to Intune**
    In the [Microsoft Intune administration console](http://manage.microsoft.com), go to **Administration** &gt; **Mobile Device Management** &gt; **iOS and Mac OS X** &gt; **Upload an APNs Certificate**, and click **Upload the APNs certificate**. **Browse** to the certificate (.pem) file and click **Open** and then enter your **Apple ID**. With the APNs certificate, Intune can enroll and manage iOS devices by pushing policy to enrolled mobile devices.

5.  **Tell users how to get access to company resources with the company portal**
    Your users will need to know how to enroll their devices and what to expect once they're brought into management. [What to tell your end users about using Microsoft Intune](../Topic/What-to-tell-your-end-users-about-using-Microsoft-Intune.md)

## <a name="BKMK_CODiOS"></a>Corporate-owned device (COD) management with Microsoft Intune
As an alternative to enrollment with the Company Portal app, you can enroll corporate-owned devices purchased from Apple. Intune supports the enrollment of corporate-owned iOS devices using the Apple Device Enrollment Program (DEP) or the [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) tool running on a Mac computer.

You can enroll corporate-enrolled iOS devices in three ways:

-   **Device Enrollment Program (DEP)** – Deploys an enrollment profile that enrolls the device “over the air” and can include setup assistant options for the device. Devices enrolled through DEP cannot be un-enrolled by users.

-   **Setup Assistant Enrollment** – Factory resets the device and prepares it for setup by the device’s new user. This method supports DEP or Apple Configurator enrollments.

-   **Direct Enrollment** – Creates an Apple Configurator-compliant file for use during device preparation. The enrolled device isn’t factory reset. This method cannot be used for DEP enrollment. This method only works if user affiliation is set to "No user affinity."

> [!CAUTION]
> Devices enrolled with these methods require the Intune Company Portal app to enable certain Intune capabilities such as [Conditional Access](https://technet.microsoft.com/library/dn818907.aspx) and [Mobile Application Management](https://technet.microsoft.com/library/dn878026.aspx). Additional steps may be necessary to properly configure the Company Portal app. [Learn more](https://blogs.technet.microsoft.com/intunesupport/2015/12/28/update-to-company-portal-brings-benefits-to-corporate-owned-ios-devices/)

### <a name="BKMK_DEP"></a>Apple DEP  management for iOS devices with Microsoft Intune
To manage corporate-owned iOS devices with Apple’s Device Enrollment Program (DEP), your organization must join Apple DEP and acquire devices through that program. Details of that process are available at:  [https://deploy.apple.com](https://deploy.apple.com). Advantages of the program include hands-free set up devices without USB-connecting each device to a computer.

Before you can enroll corporate-owned iOS devices with DEP, you need a DEP Token from Apple. This token allows Intune to sync information about DEP-participating devices owned by your corporation. It also permits Intune to perform Enrollment Profile uploads to Apple and to assign devices to those profiles.

#### <a name="BKMK_DEPtok"></a>Enable DEP management with Intune

1.  **Start managing iOS devices with Microsoft Intune**
    Before you can enroll iOS Device Enrollment Program (DEP) devices, you must complete enable iOS management for Intune.

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

7.  **Synchronize DEP-Managed Devices**
    As an administrative user, open the [Microsoft Intune administration console](http://manage.microsoft.com), go to **Admin** &gt; **Mobile Device Management** &gt; **iOS** &gt; **Device Enrollment Program**, and click **Sync now**. A sync request is sent to Apple. To see DEP-managed devices after synchronization, in the [Microsoft Intune administration console](http://manage.microsoft.com) go **Groups** &gt; **All Corporate-Owned Devices**. In the **Corporate-owned Devices** workspace, the **State** for managed devices reads “Not contacted” until the device is powered on and runs the Setup Assistant to enroll the device.

8.  **Distribute devices to users**
    Your corporate-owned devices can now be distributed to users. When an iOS device is turned on it will be enrolled for management by Intune.
    
### <a name="BKMK_SAE"></a>Setup Assistant  enrollment for iOS devices with Microsoft Intune
Using Apple Configurator you can factory reset iOS devices and prepares them for setup by the device’s new user.  This method requires you to USB-connect the iOS device to a Mac computer to setup corporate enrollment and assumes you are using Apple Configurator 2.0.

**Prerequisites**
* Physical access to iOS devices - Devices must be unconfigured (factory reset) without password protection
* Device serial numbers - [How to get an iOS serial number](https://support.apple.com/en-us/HT204308)
* USB connection cables 
* Mac computer with [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) 
 

#### <a name="BKMK_AC1"></a>Enable Setup Assistant enrollment with Intune

1.  **Create mobile device group** (Optional) 
    If your business requires mobile device groups to help manage devices, create those groups. [Use groups to manage users and devices with Microsoft Intune](../Topic/Use-groups-to-manage-users-and-devices-with-Microsoft-Intune.md). 

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

                -   **Device enrollment manager account** – The device is enrolled using a special Intune administrator account. It can be managed as a private account, but only a user who knows the enrollment manager credentials can install apps, wipe, reset, administer, and unenroll the device. For information about enrolling a device shared by many users through a common account, see [Enroll corporate-owned devices with the Device Enrollment Manager in Microsoft Intune](../Topic/Enroll-corporate-owned-devices-with-the-Device-Enrollment-Manager-in-Microsoft-Intune.md).

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

### <a name="BKMK_DE"></a>Direct enrollment for iOS devices with Microsoft Intune
Using Apple Configurator you can enroll iOS devices for management without resetting them to factory settings. This method is for devices with **No user affinity** and requires you to USB-connect the iOS device to a Mac computer to setup corporate enrollment. The Company Portal app is not supported for direct enrolled devices. This guidance assumes you are using Apple Configurator 2.0 on a Mac computer.

##### Enable direct enrollment with Intune

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

## See Also
[Get ready to enroll devices in Microsoft Intune](../Topic/Get-ready-to-enroll-devices-in-Microsoft-Intune.md)

