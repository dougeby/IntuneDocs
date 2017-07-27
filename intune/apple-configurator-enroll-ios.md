---
# required metadata

title: Enroll iOS devices- Apple Configurator-Setup Assistant
titleSuffix: "Intune on Azure"
description: Learn how to use the Apple Configurator to enroll corporate-owned iOS devices with Setup Assistant."
keywords:
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/28/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 6d384cd0-b662-41e7-94f5-0c96790ab20a

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: dagerrit
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Enroll iOS devices with Apple Configurator

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune supports the enrollment of iOS devices using [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) running on a Mac computer. Enrolling with Apple Configurator requires that you USB-connect each iOS device to a Mac computer to set up corporate enrollment. You can enroll devices into Intune with Apple Configurator in two ways:
- **Setup Assistant enrollment** - Factory resets the device, prepares it to enroll during Setup Assistant.
- **Direct enrollment** - Does not factory-reset the device and enrolls the device through iOS settings. This method only supports devices with **no user affinity**.

Apple Configurator enrollment methods can't be used with the [device enrollment manager](device-enrollment-manager-enroll.md).

## Prerequisites

- Physical access to iOS devices
- [Set MDM authority](mdm-authority-set.md)
- [An Apple MDM push certificate](apple-mdm-push-certificate-get.md)
- Device serial numbers (Setup Assistant enrollment only)
- USB connection cables
- Mac PC running [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)

## Create an Apple Configurator profile for devices

A device enrollment profile defines the settings applied during enrollment. These settings are applied only once. Follow these steps to create an enrollment profile to enroll iOS devices with Apple Configurator.

1. Sign in to the Azure portal.
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. Choose **Device enrollment** > **Apple Enrollment**.
4. In **Manage Apple Configurator Enrollment Settings**, select **AC Profiles**.
5. On the **Apple Configurator Enrollment Profiles** blade, select **Create**.
6. Type a **Name** and **Description** for the profile.
7. Specify **User Affinity**:
   - **Enroll with user affinity** - The device must be affiliated with a user with Setup Assistant and can then access company data and email. User affinity is required for managed devices that belong to users and that need to use the Company Portal for services like installing apps.
   - **Enroll without user affinity** - The device is not affiliated with a user. Use this affiliation for devices that perform tasks without accessing local user data. Apps requiring user affiliation (including the Company Portal app used for installing line-of-business apps) won’t work. Required for direct enrollment.

6. Select **Create** to save the profile.

## Setup Assistant enrollment

### Add Apple Configurator serial numbers

**To add Apple Configurator serial numbers to Intune**

1. Create a two-column, comma-separated value (.csv) list without a header. Add the serial number in the left column, and the details in the right column. The current maximum for the list is 500 rows. In a text editor, the .csv list looks something like this:

	F7TLWCLBX196,device details</br>
	DLXQPCWVGHMJ,device details

   Learn [how to find an iOS device serial number](https://support.apple.com/HT204073).
2. In Intune in the Azure portal, choose **Device enrollment**, and then choose **Apple Enrollment**.
3. Under **Manage Apple Configurator Enrollment Settings**, select **Apple Configurator Devices**.
4. Select **Add**.
5. Select an **Enrollment profile** to apply to the serial numbers you're importing. If you import a file with new details that overwrites existing details, select **Overwrite details for existing identifiers**.
6. Navigate to the csv file of serial numbers, and select **Add**.

### Reassign a profile to device serial numbers

You assign an enrollment profile when you import iOS serial numbers for Apple Configurator enrollment. Intune also lets you assign profiles from two places in the Azure portal:
- Assign from **Apple Configurator devices**
- Assign from **AC profiles**

#### Assign from Apple Configurator devices
1. In Intune in the Azure portal, choose **Device enrollment**, and then choose **Apple Enrollment**.
3. On the **Apple Configurator Devices** blade, select the serial numbers you want to assign a profile to, and then select **Assign Profile**.
4. On the **Assign Profile** blade, select the **New profile** you want to assign, and then select **Assign**.

#### Assign from profiles
1. In Intune in the Azure portal, choose **Device enrollment**, and then choose **Apple Enrollment**.
2. Choose **AC Profiles**, and select the profile that you want to assign to serial numbers.
3. In the profile blade, choose **Assigned devices**, and then choose **Assign**.
4. Filter to find device serial numbers you want to assign to the profile, select the devices, and then choose **Assign**.

### Export the profile
After you create the profile and assign serial numbers, you must export the profile from Intune as a URL. You then import it into Apple Configurator on a Mac for deployment to devices.

1. In Intune in the Azure portal, choose **Device enrollment** > Apple enrollment** > **AC Profiles**, and then choose the profile to export.
2. On the blade for the profile, select **Export Profile**.
3. Copy the profile URL. You can then add it in Apple Configurator later to define the Intune profile used by iOS devices.

  Next you import this profile to Apple Configurator in the following procedure to define the Intune profile used by iOS devices.

### Enroll devices with Setup Assistant

1.  On a Mac computer, open **Apple Configurator 2**. In the menu bar, choose **Apple Configurator 2**, and then choose **Preferences**.
  > [!WARNING]
  > Devices reset to factory configurations during the enrollment process. As a best practice, reset the device and turn it on. Devices should be at the **Hello** screen when you connect the device.

2. In the **preferences** pane, select **Servers** and choose the plus symbol (+) to launch the MDM Server wizard. Choose **Next**.
3. Enter the **Host name or URL** and **enrollment URL** for the MDM server under Setup Assistant enrollment for iOS devices with Microsoft Intune. For the Enrollment URL, enter the enrollment profile URL exported from Intune. Choose **Next**.  

  You can safely disregard a warning stating "server URL is not verified." To continue, choose **Next** until the wizard is finished.
4.  Connect the iOS mobile devices to the Mac computer with a USB adapter.
5.  Choose **Prepare**. On the **Prepare iOS Device** pane, select **Manual** and then choose **Next**.
6. On the **Enroll in MDM Server** pane, select the server name you created, and then choose **Next**.
7. On the **Supervise Devices** pane, select the level of supervision, and then choose **Next**.
8. On the **Create an Organization** pane, choose the **Organization** or create a new organization, and then choose **Next**.
9. On the **Configure iOS Setup Assistant** pane, choose the steps to be presented to the user, and then choose **Prepare**. If prompted, authenticate to update trust settings.  
10. When the iOS device finishes preparing, disconnect the USB cable.  

### Distribute devices
The devices are now ready for corporate enrollment. Turn off the devices and distribute them to users. When users turn on their devices, Setup Assistant starts.

After users receive their devices, they must complete Setup Assistant. Devices configured with user affinity can install and run the Company Portal app to download apps and manage devices.

## Direct enrollment
When you directly enroll iOS devices with Apple Configurator, you can enroll a device without acquiring the device's serial number. You can also name the device for identification purposes before Intune captures the device name during enrollment. The Company Portal app is not supported for directly enrolled devices. This method does not do a factory reset of the device.

Apps requiring user affiliation, including the Company Portal app used for installing line-of-business apps, cannot be installed.

### Export the profile as .mobileconfig to iOS devices
1. Sign in to the Azure portal.
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Export Profile** blade, download the enrollment profile to [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) to push directly as a management profile to iOS devices.
4. Prepare the device with Apple Configurator by using the following steps.
  1. On a Mac computer, open Apple Configurator 2.0.
  2. Connect the iOS device to the Mac computer with a USB cord. Close Photos, iTunes, and other apps that open for the device when the device is detected.
  3. In Apple Configurator, choose the connected iOS device, and then choose the **Add** button. Options that can be added to the device appear in the drop-down list. Choose **Profiles**.
  4. Use the file picker to select the .mobileconfig file that you exported from Intune, and then choose **Add**. The profile is added to the device. If the device is Unsupervised, the installation requires acceptance on the device.
5. Use the following steps to install the profile on the iOS device. The device must have already completed the Setup Assistant and be ready to use. If enrollment entails app deployments, the device should have an Apple ID set up because the app deployments requires that you have an Apple ID signed in for the App Store.
   1. Unlock the iOS device.
   2. In the **Install profile** dialog box for **Management profile**, choose **Install**.
   3. Provide the Device Passcode or Apple ID, if necessary.
   4. Accept the **Warning**, and choose **Install**.
   5. Accept the **Remote Warning**, and choose **Trust**.
   6. When the **Profile Installed** box confirms the profile as Installed, choose **Done**.

6. On the iOS device, open **Settings** and go to **General** > **Device Management** > **Management Profile**. Confirm that the profile installation is listed, and check the iOS policy restrictions and installed apps. Policy restrictions and apps might take up to 10 minutes to appear on the device.

7. Distribute devices. The iOS device is now enrolled in Intune and managed.
