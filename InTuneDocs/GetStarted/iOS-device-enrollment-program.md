---
title: Apple DEP management for iOS devices with Microsoft Intune
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

## Apple DEP management for iOS devices with Microsoft Intune
To manage corporate-owned iOS devices with Apple’s Device Enrollment Program (DEP), your organization must join Apple DEP and acquire devices through that program. Details of that process are available at:  [https://deploy.apple.com](https://deploy.apple.com). Advantages of the program include hands-free set up of devices without USB-connecting each device to a computer.

Before you can enroll corporate-owned iOS devices with DEP, you need a DEP Token from Apple. This token allows Intune to sync information about DEP-participating devices owned by your corporation. It also permits Intune to perform Enrollment Profile uploads to Apple and to assign devices to those profiles.

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



### See also
[Get ready to enroll devices](get-ready-to-enroll-devices-in-microsoft-intune.md)
