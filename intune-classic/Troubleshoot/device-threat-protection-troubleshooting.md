---
# required metadata

title: Troubleshoot Lookout Integration 
description: This topic describes troubleshooting issues that commonly occur with Lookout Integration
keywords:
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: bbe0b5f4-b8bc-49f3-85a9-51fb2f226fca

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: sandera
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Troubleshoot Lookout Integration with Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

This topic describes some common issues you may encounter with your Lookout mobile threat protection (MTP) setup.

**Login errors**

## 403 errors
When you log in to the [Lookout MTP console](https://aad.lookout.com) you see a 403 error:  **you are not authorized to access the service**  This can happen when the specified username is not a member of the Azure Active Directory (AD) group configured to access Lookout MTP.

Lookout MTP only allows users from a configured Azure AD group to access the service. To determine which group is configured with access to Lookout MTP, contact Lookout Support:

* Email: enterprisesupport@lookout.com
* Login to the  [MTP  Console](http://aad.lookout.com), and navigate to the **Support** module.
* Go to: https://enterprise.support.lookout.com/hc/requests and make a support request.

## Unable to sign in
You see the following error when the Azure AD global admin user has not accepted the initial Lookout setup.

![screenshot of the Lookout login screen showing sign in error](../media/mtp/lookout-mtp-consent-not-accepted-error.png)

To resolve this issue, the global admin user must login to  https://aad.lookout.com/les?action=consent
and accept the prompt to initiate the set up. More detailed information can be found in  [Set up your subscription with Lookout MTP](../deploy-use/setup-your-lookout-mtd-subscription.md) topic

**Device status issues**

## Device missing from Lookout device list

This could happen in either of the following scenarios:
* The device user is not in the **Enrollment Group** specified in the **Lookout MTP Console**.  In the [Lookout console](http://aad.lookout.com), go **System** > **Intune Connector** > **Enrollment Management**.  Review the Azure AD groups configured for enrollment and verify that the device user is part of one of the Azure AD groups.  Once a user is added to the enrollment group, it can take up to the configured polling interval, 5 minutes by default, for the device to appear in the **Devices** module of the Lookout MTP console.
* If the device is unsupported by Lookout MTP.  Devices that are unsupported will appear in the **Managed Devices** section of the connector settings on the Lookout MTP Console.

### Device reported as **pending**

A device is shown as  **Pending** if the end user has not opened the Lookout for work app and tapped the  **Activate** button. For more details on the device activation with Lookout for work app, see [You are prompted to install Lookout for Work on your Android device](http://docs.microsoft.com/intune-user-help/you-are-prompted-to-install-lookout-for-work-android) or
[You are prompted to install Lookout for Work on your iOS device](https://docs.microsoft.com/intune-user-help/you-are-prompted-to-install-lookout-for-work-ios)

## Device whos active, but has no device ID
In the Lookout MTP console, if an active device has no device ID then the device user is not in the enrollment group. A device can get into this state is if the device user has been removed from the enrollment group or the enrollment group has been removed.

In the [Lookout console](http://aad.lookout.com), go **System** > **Intune Connector** > **Enrollment** and review the settings.  Review the Azure AD groups and verify that the device useris part of one of the Azure AD groups.

While a device is in this state, Lookout will continue to notify the user of any threats detected, but will not send any threat information to Intune.

## Device reported as **disconnected**

**Disconnected** means the device hasn't synced with Lookout MTP in the configured interval, 30 days by default with a minimum of 7 days. Either the Company Portal app or the Lookout for Work app is missing from the device. Reinstalling the apps should resolve this issue. When the user opens Lookout for Work and activates the app, the device resyncs with Lookout MTP and Intune.

### Forcing a device sync
From the **Devices** module of the Lookout MTP console, the administrator can select the device and choose to delete it.   The next time the device owner opens the Lookout for Work app and taps **Activate**, the device state will do a full resync.

## Device has a new user
You should wipe the device and ask the new user to enroll.  From the [Intune administrator console](https://manage.microsoft.com), select the device, right click, and choose **Retire/Wipe** to remove the device from management. After retiring the device you can delete it.

![screenshot of the device module in the Intune admin console with the retire/wipe option displayed](../media/mtp/mtp-retire-device-intune-console.png)

You can also go to the **Devices** module of the [Lookout console](http://aad.lookout.com) and choose **Delete**.

If the new user is in an  Lookout MTP enrollment group, the device will appear once Azure AD associates the device with the new user.

## Compliance remediation workflows
- [You are prompted to install Lookout for Work on your Android device]( http://docs.microsoft.com/intune-user-help/you-are-prompted-to-install-lookout-for-work-android)
- [You need to resolve a threat that Lookout for Work found on your Android device](http://docs.microsoft.com/intune-user-help/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)
- [You need to resolve a threat that Lookout for Work found on your iOS device](https://docs.microsoft.com/intune-user-help/you-need-to-resolve-a-threat-found-by-lookout-for-work-ios)


### See also
[Set up you subscription with Lookout MTP](/intune-classic/deploy-use/set-up-your-subscription-with-lookout-mtp)
