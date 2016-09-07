---
# required metadata

title: Troubleshoot Lookout Integration | Microsoft Intune
description: This topic describes troubleshooting issues that commonly occur with Lookout Integration
keywords:
author: karthikaraman
manager: angrobe
ms.date: 09/08/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: bbe0b5f4-b8bc-49f3-85a9-51fb2f226fca

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: sandera
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Troubleshoot Lookout Integration with Intune
This topic describes some common issues you may encounter when with your Lookout mobile threat protection setup.
## Troubleshoot login errors
### 403 errors
You may see a 403 error: *you are not authorized to access the service*  when you login. This issue can happen when the username you provided during your login to https://aad.lookout.com  is not a member of the Azure Active Directory (Azure AD) group configured to access Lookout MTP.

Lookout MTP is configured to only allows users from a configured Azure AD group to have access.  This group access should be setup when the Enterprise account is created by Lookout support. If you are unsure which group is configured with access to Lookout MTP, contact Lookout support.

You can contact Lookout support through on the following methods:

* email to enterprisesupport@lookout.com
* Login to the  [MTP  Console](http://aad.lookout.com), and navigate to the Support page.
* Go to:  https://enterprise.support.lookout.com/hc/en-us/requests and make a support request.

### Unable to sign in
You may see the following error when the Azure AD global admin user has not accepted the initial Lookout setup.

![screenshot of the Lookout login screen showing sign in error](../media/mtp/lookout-mtp-consent-not-accepted-error.png)

To resolve this issue, the global admin user must login to  https://aad.lookout.com/les?action=consent
and accept to initiate the setup. More detailed information can be found in  [Setup your subscription with Lookout MTP](set-up-your-subscription-with-lookout-mtp.md) topic

## Troubleshoot device status issues

### Device not showing up in the Lookout MTP console device list.

This could happen in the following one of two scenarios:
* When the user that owns this device is not in the **Enrollment Group** specified in the **Lookout MTP Console**.   On the Lookout MTP Console, from the **System** module go to **Intune Connector** tab and then look at the **Enrollment Management**  settings.  The administrator should have configured a set of Azure AD groups for enrollment.  Verify that the user that owns the missing device is part of one of the specified Azure AD groups.  Once a new user is added to the enrollment group it will take up to the configured polling interval (5 minutes is the default) to see the device show up in the **Devices** module of the Lookout MTP Console.

* If the device is unsupported by Lookout MTP.  Devices found that are unsupported will appear in the **Managed Devices** section of the connector settings on the Lookout MTP Console.

### Device continues to be reported as **pending**

A device that is showing  **Pending**  means the end user has not opened the Lookout for work application and selected the  **Activate** button. For more details on the device activation with Lookout for work app, read the following topic:

* [Installing Lookout for work app on Android](http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

### In the Lookout MTP Console, a device is showing as active, but does not have a device ID.  
This means that the user that owns this device is not in the enrollment group specified in the Lookout MTP Console.   A device can get into this state is if the user who owns the device has been removed from the enrollment group or the enrollment group that the user belongs to has been removed.

On the Lookout MTP Console, from the **System** module, go to **Intune Connector** tab review the **Enrollment** settings.  The administrator should have configured a set of Azure AD groups for enrollment.  Verify that the user that owns the device is part of one of the AAD groups specified.  

While a device is in this state, Lookout will continue to notify the user of any threats detected, but will not send any threat information to Intune.

### Device shows disconnected state

Disconnected means that Lookout MTP has not heard from the device for over a preconfigured time interval (default is 24 hours).This means that either the company portal app or the Lookout for Work app are not installed on the device or have been uninstalled. Reinstalling the apps should resolve this issue. When the user opens the Lookout for Work and activates the app, a full device resync with Lookout MTP and Intune will occur.    

### Forcing a resync on the device
From the **Devices** module of the Lookout MTP console, the administrator can select the device and choose to delete the device.   The next time the device owner opens the Lookout for work app and selects **activate**, the device state will do a full resync.

### The owner of the device is no longer using device
You must wipe the device and ask the new user to enroll.  From the [Intune administrator console](https://manage.microsoft.com), select the device, right click, and choose retire/wipe to remove the device from management. After retiring the device can be deleted.

![screenshot of the device page in the Intune admin console with the retire/wipe option displayed](../media/mtp/mtp-retire-device-intune-console.png)

You can also, go to the Devices page of the Lookout MTP Console and choose **Delete**.  

As long as the new user is in one of the  enrollment groups specified in the Lookout MTP console, the device will appear once Azure AD associates the device to the new user.

## Compliance remediation workflows
[You are prompted to install Lookout for work app on your device]( http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

[Your device does not meet the mobile risk policy](http://docs.microsoft.com/intune/enduser/your-device-does-not-meet-the-mobile-risk-policy-android)


### See also
[Set up you subscription with Lookout MTP](set-up-your-subscription-with-lookout-mtp.md)
