---
# required metadata

title: Specify IMEI numbers | Microsoft Intune
description: Microsoft Intune lets admins import IMEI numbers for mobile device platforms to help identify corporate-owned mobile devices
keywords:
author: NathBarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 1712bd39-562b-4409-9cec-155d5f4d8a39

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: dagerrit
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Specify corporate-owned devices with international mobile equipment identity (IMEI) numbers
Microsoft Intune lets admins import international mobile equipment identity (IMEI) numbers for mobile device platforms by using IMEI numbers to help identify corporate-owned mobile devices. After devices are enrolled in Intune, you can see devices that have imported IMEI numbers under **Groups** > **Overview** > **All Devices**. **Device group** lists devices that have imported IMEI numbers as **Corporate** in the **Ownership** column.

1. In the [Microsoft Intune administration console](http://manage.microsoft.com), choose **Groups** &gt; **All Devices** &gt; **All Corporate Pre-enrolled Devices** &gt; **By IMEI (All platforms)**, and then choose **Add devices…**. You can add devices in two ways:

    -   **Upload a .csv file that has serial numbers** – Create a two-column, comma-separated value (.csv) list without a header, and limit the list to 5,000 devices or 5 MB per .csv file.

        |||
        |-|-|
        |&lt;IMEI #1&gt;|&lt;Device #1 Details&gt;|
        |&lt;IMEI #2&gt;|&lt;Device #2 Details&gt;|
        This .csv file when viewed in a text editor appears as:

        ```
        AABBBBBBCCCCCCD,PO 1234
        AABBBBBBCCCCCCE,PO 1234
        ```

    -   **Manually add device details** - Enter the IMEI number and device details of up to five devices.

   *Details* are for administrative use so you can identify the IMEI number that's associated with a device. This information is not sent to the device, but it will appear in the Intune console.

2.   Choose **Next**.
3.  On the **Review Devices** pane, you can confirm the imported device IMEI numbers. You can also decide whether to overwrite the **Details** for IMEI numbers that are being imported again. You can uncheck the **Overwrite** box to preserve the Current details. Choose **Finish** to import the IMEI numbers.
4.  The imported IMEI numbers and descriptions are added to the **By IMEI (All platforms)** list.

When a device that has IMEI number enrolls in Intune, usually when a user installs the Company Portal app and completes the enrollment process, the device will be tagged as corporate-owned and appear as enrolled in the **IMEI Devices** group.
