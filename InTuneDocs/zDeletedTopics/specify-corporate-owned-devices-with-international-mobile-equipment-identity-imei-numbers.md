---
title: Specify corporate-owned devices with international mobile equipment identity (IMEI) numbers
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 1712bd39-562b-4409-9cec-155d5f4d8a39
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



## Specify corporate-owned devices with international mobile equipment identity (IMEI) numbers
Microsoft Intune enables administrators to import international mobile equipment identity (IMEI) numbers for mobile device platforms with an IMEI numbers to help identify corporate-owned mobile devices. Once enrolled in Intune, devices with imported IMEI numbers are tagged as Corporate which can be used for applying policies that are different than those applied to personally owned devices.

1. In the [Microsoft Intune administration console](http://manage.microsoft.com) go **Groups** &gt; **All Devices** &gt; **All Corporate Pre-enrolled Devices** &gt; **By IMEI (All platforms)**, and then click **Add devices…**. You can add devices in two ways:

    -   **Upload a CSV file containing serial numbers** – Create a comma-separated value (.csv) list of two columns without a header, limited to 5000 devices or 5MB per csv file.

        |||
        |-|-|
        |&lt;IMEI #1&gt;|&lt;Device #1 Details&gt;|
        |&lt;IMEI #2&gt;|&lt;Device #2 Details&gt;|
        This .csv file when viewed in a text editor appears as:

        ```
        AA-BBBBBB-CCCCCC-D,PO 1234
        AA-BBBBBB-CCCCCC-E,PO 1234
        ```

    -   **Manually add device details** - Enter the IMEI number and device details of up to five devices

   *Details* are for administrative use so you can identify which IMEI number is associated with a device. This information is not sent to the device but will appear in the Intune console.

2.   Click **Next**.
3.  On the **Review Devices** pane you can confirm which device IMEI numbers are imported. You can also decide whether to overwrite the **Details** for IMEI numbers being re-imported. You can uncheck the **Overwrite** checkbox to preserve the Current details. Click **Finish** to import the IMEI numbers.
4.  The added IMEI numbers and descriptions are added to the **By IMEI (All platforms)** list.

When the device with that IMEI number enrolls, usually when a user installs the Company Portal app and completes the enrollment process, the device will be tagged as Corporate owned and appear as enrolled in the **IMEI Devices** group.

### See also
[Get ready to enroll devices](get-ready-to-enroll-devices-in-microsoft-intune.md)
