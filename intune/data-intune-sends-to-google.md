---
# required metadata

title: Data Intune sends to Google
titlesuffix: "Azure portal"
description: List of data that Intune sends to Google.
keywords:
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/26/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: a5c3bec4-18ed-11e8-accf-0ed5f89f718b


# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---

# Data Intune sends to Google

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

When Android device management is enabled on a device, Microsoft Intune establishes a connection with Google and shares user and device information with Google. Before Microsoft Intune can establish a connection, you must create an Google account.

The following table lists the data that Microsoft Intune sends to Google when device management is enabled on a device:


| Data sent to Google | Details | Used for | Example |
|:---:|:---:|:---:|:---:|
| EnterpriseId | Originated in Google upon binding your Gmail account to Intune. | Primary identifier used to communicate between Intune and Google.  This includes setting policies, managing devices, and binding/unbinding of Android enterprise with Intune. | Unique identifier, Example format: LC04eik8a6 |
| Policy Body | Originated in Intune when saving a new app or configuration policy. | Applying policies to devices. | This is a collection of all configured settings for an application or configuration policy. This can contain customer information if provided as part of a policy, such as network names, application names and app specific settings. |
| Device Data | Devices for Work Profile scenarios begin with enrollment in Intune. Devices for Managed device scenarios begin with enrollment into Google. | Device Data information is sent between Intune and Google for various actions such as applying policies, managing the device and general reporting. | **Unique identifier to represent Device Name.** Example: enterprises/LC04ebru7b/devices/3592d971168f9ae4<br>**Unique Identifier to represent User Name.** Example: Enterprises/LC04ebru7b/users/116838519924207449711<br>**Device state.** Examples: Active, Disabled, Provisioning.<br>**Compliance states.** Examples: Setting not supported, missing required apps<br>**Software Info.** Examples: software versions & patch level.<br>**Network Info.** Examples: IMEI, MEID, WifiMacAddress<br>**Device Settings.** Examples: Information on encryption levels & whether device allows unknown apps.<br> See below for an example of a JSON message. |
| newPassword | Originated in Intune. | Resetting device passcode. | String representing new password. |
| Google User | Google | Managing the work profile for Work Profile (BYOD) scenarios. | Unique identifier to represent the linked Gmail account. Example: 114223373813435875042 |
| Application Data | Originated in Intune when saving application policy. |  | Application Name string. Example: app:com.microsoft.windowsintune.companyportal |
| Enterprise Service Account | Originated in Google upon Intune request. | Used for authentication between Intune and Google for transactions involving this customer. | There are several parts:<br> **Enterprise Id**: already documented above.<br>**UPN**: generated UPN used in authentication on behalf of customer.<br>Example: w49d77900526190e26708c31c9e8a0@pfwp-commicrosoftonedfmdm2.google.com.iam.gserviceaccount.com<br>**Key**: Base64 encoded blob used in auth requests, we store it encrypted in the service, but this is what it looks like:<br> Unique Identifier to represent the customer’s key<br>Example: a70d4d53eefbd781ce7ad6a6495c65eb15e74f1f |

**Device Data example**

Here’s an example JSON device message we get from Google:



```
'{
  "name": "enterprises/LC02dhxx1r/devices/3195483be017acdc",
  "userId": "114223373813435875042",
  "adminType": "DEVICE_OWNER",
  "state": "ACTIVE",
  "appliedState": "ACTIVE",
  "policyCompliant": true,
  "enrollmentTime": "2017-10-06T15:17:41.702Z",
  "lastStatusReportTime": "2017-10-06T15:18:10.325Z",
  "lastPolicyComplianceReportTime": "2017-10-06T15:18:11.665Z",
  "lastPolicySyncTime": "2017-10-06T15:18:07.852Z",
  "appliedPolicyVersion": "2",
  "apiLevel": 26,
  "enrollmentTokenData": "brew 30 day token",
  "enrollmentTokenId": "yXdtW0_0L7c7Yo9DtRhEfPi3PcMqTorF3V1bTAw_eRs",
  "softwareInfo": {
    "androidVersion": "8.0.0",
    "cloudDpcVersionCode": 55314,
    "cloudDpcVersionName": "bv00553-rc14",
    "androidBuildNumber": "OPR4.170623.009",
    "deviceKernelVersion": "3.10.73-ga51b1600b7f8",
    "bootloaderVersion": "BHZ21c",
    "androidBuildTime": "2017-08-28T18:57:48Z",
    "securityPatchLevel": "2017-10-05",
    "androidBuildType": "user",
    "buildUser": "android-build"
  },
  "hardwareInfo": {
    "brand": "google",
    "hardware": "bullhead",
    "deviceBasebandVersion": "M8994F-2.6.39.3.03",
    "manufacturer": "LGE",
    "serialNumber": "01ed07873b3c20cd",
    "model": "Nexus 5X",
    "batteryShutdownTemperatures": [60.0],
    "batteryThrottlingTemperatures": [-3.4028235E38],
    "cpuShutdownTemperatures": [115.0, 115.0, 115.0, 115.0, 115.0, 115.0],
    "cpuThrottlingTemperatures": [60.0, 60.0, 60.0, 60.0, 60.0, 60.0],
    "gpuShutdownTemperatures": [-3.4028235E38],
    "gpuThrottlingTemperatures": [-3.4028235E38],
    "skinShutdownTemperatures": [-3.4028235E38],
    "skinThrottlingTemperatures": [37.0]
  },
  "displays": [{
    "name": "Built-in Screen",
    "refreshRate": 60,
    "state": "ON",
    "width": 1080,
    "height": 1920,
    "density": 420
  }],
  "appliedPolicyName": "enterprises/LC02dhxx1r/policies/default",
  "networkInfo": {
    "imei": "353626070676775",
    "wifiMacAddress": "02:00:00:00:00:00"
  },
  "memoryInfo": {
    "totalRam": "1902936064",
    "totalInternalStorage": "3169611776"
  },
  "memoryEvents": [{
    "eventType": "EXTERNAL_STORAGE_DETECTED",
    "createTime": "2017-10-06T15:18:09.959Z",
    "byteCount": "26720919552"
  }],
  "powerManagementEvents": [{
    "eventType": "BATTERY_LEVEL_COLLECTED",
    "createTime": "2017-10-06T15:18:09.939Z",
    "batteryLevel": 95.0
  }],
  "userName": "enterprises/LC02dhxx1r/users/114223373813435875042",
  "enrollmentTokenName": "enterprises/LC02dhxx1r/enrollmentTokens/yXdtW0_0L7c7Yo9DtRhEfPi3PcMqTorF3V1bTAw_eRs"
}'
```

To stop using Android device management with Microsoft Intune and delete the data, you must both disable the Microsoft Intune Android device management and also delete your Google account. Refer to Google account how to perform account management.


