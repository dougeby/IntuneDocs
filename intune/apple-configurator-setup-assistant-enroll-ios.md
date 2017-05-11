---
# required metadata

title: Enroll iOS devices- Apple Configurator-Setup AssistanttitleSuffix: "Intune Azure preview"
description: "Intune Azure preview: Learn how to use the Apple Configurator to enroll corporate-owned iOS devices with Setup Assistant."
keywords:
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 04/15/2017
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

# Enroll iOS devices with Apple Configurator and Setup Assistant

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Intune supports the enrollment of corporate-owned iOS devices using [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) running on a Mac computer. This process resets the device to factory settings, prepares it to run Setup Assistant, and installs the company's policies for the device’s new user.

>[!NOTE]
>This enrollment method can't be used with the [device enrollment manager](device-enrollment-manager-enroll.md) method.

Using Apple Configurator, you can reset an iOS device to factory settings and prepare it to be set up for the device’s new user. This method requires you to connect the iOS device to a Mac computer via USB to set up corporate enrollment, and it assumes you are using Apple Configurator 2.0. Most scenarios require that the policy applied to the iOS device include user affinity to enable the Intune Company Portal app.

Other methods of enrolling iOS devices are described in [Choose how to enroll iOS devices in Intune](enrollment-method-choose-ios.md).

## Prerequisites

Complete the following prerequisites before setting up iOS device enrollment:

- [Get an Apple MDM push certificate](apple-mdm-push-certificate-get.md)
- Ensure that you have physical access to iOS devices
- Have the device serial numbers (see [How to get an iOS serial number](https://support.apple.com//HT204308))
- Have USB connection cables on hand
- Ensure that you have a Mac PC with [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) installed
- [Add Apple Configurator serial numbers](apple-configurator-serial-numbers-add.md)


## Create an Apple Configurator profile for devices

A device enrollment profile defines the settings applied to a group of devices. The following steps show how to create a device enrollment profile for iOS devices enrolled by using Apple Configurator.

1. In the Azure portal, choose **More Services** > **Monitoring + Management** > **Intune**.

2. On the Intune blade, choose **Enroll devices**, and then choose **Apple Enrollment**.

3. Under **Manage Apple Configurator Enrollment Settings**, select **AC Profiles**.

4. On the **Apple Configurator Enrollment Profiles** blade, select **Create**.

5. On the **Create Enrollment Profile** blade, enter a name and description for the profile.

6. For **User Affinity**, choose whether devices with this profile will enroll with or without user affinity.

   - **Enroll with user affinity** - The device must be affiliated with a user during initial setup and can then be permitted to access company data and email. User affinity should be set up for managed devices that belong to users and that need to use the company portal for services like installing apps.

   - **Enroll without user affinity** - The device is not affiliated with a user. Use this affiliation for devices that perform tasks without accessing local user data. Apps requiring user affiliation (including the Company Portal app used for installing line-of-business apps) won’t work.

7. Select **Create** to save the profile.

## Assign serial numbers to an Apple Configurator profile

After you create Apple Configurator profiles, you can assign device serial numbers to the profiles. To be able to assign serial numbers, you must first add them to Intune by following the steps in [Add Apple Configurator serial numbers](apple-configurator-serial-numbers-add.md).

### Assign serial numbers to Apple Configurator profiles

1. In the Azure portal, choose **More Services** > **Monitoring + Management** > **Intune**.

2. From the **Apple Configurator Enrollment Profiles** blade, select the profile that you want to assign serial numbers to.

3. In the blade named for the profile, select **Serial Numbers** > **Assign**.

4. Select the serial numbers that you want to assign to the profile, and then select the **Assign** button.

## Export the profile to iOS devices

After you create the profile and assign serial numbers, you have to export the profile from Intune, either as a URL or as a file in the format described below. You then manually import it to the Apple Configurator program on a Mac, after which the Apple Configurator program deploys it to the devices.

### Export a profile using Setup Assistant enrollment

1. In the Azure portal, choose **More Services** > **Monitoring + Management** > **Intune**.

2. On the **Apple Configurator Enrollment Profiles** blade, choose the profile to export.

3. On the blade for the profile, select **Export Profile**.

4. Copy the profile URL into [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12), with the iOs device attached. You will upload it in Apple Configurator later to define the Intune profile used by iOS devices.

  You will upload this profile URL to the Apple service using Apple Configurator in the following procedure to define the Intune profile used by iOS devices.

5. Upload this profile URL to the Apple service using Apple Configurator to define the Intune profile used by iOS devices.
 1.  On a Mac computer, open **Apple Configurator 2**. In the menu bar, choose **Apple Configurator 2**, and then choose **Preferences**.
  > [!WARNING]
  > The devices will be reset to factory configurations during the enrollment process. As a best practice, reset the device and turn it on. Devices should be at the **Hello** screen when you connect the device.

  2. In the **preferences** pane, select **Servers** and choose the plus symbol (+) to launch the MDM Server wizard. Choose **Next**.

  3. Enter the **Name** and **Enrollment URL** for the MDM server from Step #6 under Setup Assistant enrollment for iOS devices with Microsoft Intune. For the Enrollment URL, enter the enrollment profile URL exported from Intune. Choose **Next**.  

    You can safely disregard a warning stating "server URL is not verified." To continue, choose **Next** until the wizard is finished.

  4.  Connect the iOS mobile devices to the Mac computer with a USB adapter.
  > [!WARNING]
  > The devices will be reset to factory configurations during the enrollment process. As a best practice, reset the device and turn it on. Devices should be at the **Hello** screen when you start Setup Assistant.

  5.  Choose **Prepare**. On the **Prepare iOS Device** pane, select **Manual** and then choose **Next**.
  6. On the **Enroll in MDM Server** pane, select the server name you created, and then choose **Next**.
  7. On the **Supervise Devices** pane, select the level of supervision, and then choose **Next**.
  8. On the **Create an Organization** pane, choose the **Organization** or create a new organization, and then choose **Next**.
  9. On the **Configure iOS Setup Assistant** pane, choose the steps to be presented to the user, and then choose **Prepare**. If prompted, authenticate to update trust settings.  
  10. When the iOS device finishes preparing, disconnect the USB cable.  
6.  **Distribute devices**.
    The devices are now ready for corporate enrollment. Turn off the devices and distribute them to users. When users turn on their devices, Setup Assistant will start.

    See [How to educate your end users about Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune). You can also direct your end users to[Using your iOS or macOS device with Intune](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune)

## How users install and use the Company Portal on their devices

Devices that are configured with user affinity can install and run the Company Portal app to download apps and manage devices. After users receive their devices, they must complete the additional steps described below to complete the Setup Assistant and install the Company Portal app.
