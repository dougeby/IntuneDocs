---
# required metadata

title: Direct enrollment for iOS devices 
description: Use the Apple Configurator tool to directly enroll corporate-owned iOS devices with a predefined policy by USB-connecting them to a Mac computer.
keywords:
author: nathbarn
ms.author: nathbarn
manager: dougeby
ms.date: 01/29/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: a692b90c-72ae-47d1-ba9c-67a2e2576cc2
ROBOTS: NOINDEX,NOFOLLOW

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: dagerrit
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Directly enroll iOS devices by using Apple Configurator

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune supports the enrollment of corporate-owned iOS devices by using the [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) tool running on a Mac computer. This process does not factory-reset the device and enrolls the device with a predefined policy. This method is for devices with **No user affinity** and requires you to USB-connect the iOS device to a Mac computer to set up corporate enrollment.

When you're directly enrolling iOS devices, you can enroll a device without acquiring the device's serial number. You can also name the device for identification purposes before Intune captures the device name during enrollment. The Company Portal app is not supported for directly enrolled devices. This guidance assumes you are using Apple Configurator 2.0 on a Mac computer.

>[!NOTE]
>This enrollment method can't be used with the [device enrollment manager](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) method.

1.  If you haven't already, create a device enrollment profile for iOS devices enrolled through Apple Configurator. A device enrollment profile defines the settings applied to devices.

    1.  In the [Microsoft Intune administration console](https://manage.microsoft.com) go to **Policy** &gt; **Corporate Device Enrollment**, and then choose **Add**.

        ![Create device enrollment profile page](../media/pol-sa-corp-enroll.png)

    2.  Enter details for the device profiles:

        -   **Name**: Name of the device enrollment profile. Not visible to users.

        -   **Description**: Description of the device enrollment profile. Not visible to users.

        -   **User affiliation**: Specifies how devices are enrolled. For Direct Enrollment, choose **No user affinity**.

        -   **Device group pre-assignment**: All devices that have this profile will initially belong to this group. You can reassign devices after enrollment.

            [!INCLUDE[groups deprecated](../includes/group-deprecation.md)]

    3.  Choose **Save Profile** to add the profile.

5.  Export a profile as .mobileconfig to deploy to iOS devices:

	1.   Select the device profile that you created.

    2.   Choose **Export** in the taskbar.

    3.   Choose **Download profile** and save the downloaded .mobileconfig file.

6.  Transfer the file by copying the downloaded .mobileconfig file to a Mac computer.
    > [!NOTE]
    > The enrollment profile URL is valid for two weeks from when it is exported. After two weeks, you must export a new enrollment profile URL to enroll iOS devices with Setup Assistant.

7.  Prepare the device with Apple Configurator. iOS devices are connected to the Mac computer and enrolled for mobile device management.

    1.  On a Mac computer, open **Apple Configurator 2.0**.

    2.  Connect the iOS device to the Mac computer with a USB cord. Close **Photos**, **iTunes**, and other apps that open for the device when the device is detected.

    3.  In Apple Configurator, choose the connected iOS device, and then choose the **Add** button. Options that can be added to the device appear in the drop-down list. Choose **Profiles**.

    4.  Use the file picker to select the .mobileconfig file that you exported from Intune, and then choose **Add**. The profile is added to the device.  If the device is **Unsupervised**, the installation will require acceptance on the device.

8.  You are ready to install the profile on the iOS device. The device must have already completed the Setup Assistant and be ready to use. If enrollment entails app deployments, the device should have an Apple ID set up because the app deployments will require that you have an Apple ID signed in for the App Store.

    1.  Unlock the iOS device.

    2.  In the **Install profile** dialog box for **Management profile**,  choose **Install**.

    3.  Provide **Device Passcode** or **Apple ID**, if required.

    4.  Accept the **Warning**, and choose **Install**.

    5.  Accept the **Remote Warning**, and choose **Trust**.

    6.  When the **Profile Installed** box confirms the profile as **Installed**, choose **Done**.

9.  On the iOS device, open **Settings** and go to **General** &gt; **Device Management** &gt; **Management Profile**. Confirm that the profile installation is listed, and check the iOS policy restrictions and installed apps. Policy restrictions and apps might take up to 10 minutes to appear on the device.

10.  Distribute devices. The iOS device is now enrolled with Intune and managed.
