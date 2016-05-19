---
# required metadata

title: Remotely lock a device from the Company Portal website | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: adc6af23-b22f-42e5-955a-4dffbdb8b42b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Remotely lock a device from the Company Portal website

If your device has been lost or stolen, you can lock the device by using the Remote Lock option on the [Company Portal website](http://portal.manage.microsoft.com). Remote Lock works for the following types of devices:

Platform  |Support details  
---------|---------
Android | Supported       
iOS | Supported
Windows 10 Mobile | Supported only if the phone has a passcode set     
Windows 10 Desktop | Not supported  
Windows Phone 8.1 | Supported only if the phone has a passcode set
Windows Phone 8.0 | Not supported
PC (Windows 8.0 and earlier) | Not supported       
PC (Windows 8.1) | Not supported

</br>
To use Remote Lock to lock your device:

1.	On the [Company Portal website](http://portal.manage.microsoft.com), tap the name of the device you want to lock.

2.	Tap **Remote Lock**.

	Once you tap **Remote Lock**, a “Remote lock pending” status appears.  When Remote Lock succeeds, the status changes to “Remote lock successful.”

	The Remote Lock status displays in three places:

	* The notifications area of the website. 
	* The Details page for the device.
	* The tile that shows the device name on the My Devices section of the page.

	If you see a “Remote Lock failed” notification, wait a few minutes, and then try again to lock your device. Once you tap to retry, the status changes back to “Remote lock pending.” 

	If a retry doesn’t work, contact your IT administrator for help. If you find your device and want to unlock it after using Remote Lock, just enter your passcode.


### See also
[Using the Intune Company Portal website](using-the-intune-company-portal-website.md)