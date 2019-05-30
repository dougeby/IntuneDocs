---
title: include file
description: include file
author: ErikjeMS  
ms.service: microsoft-intune
ms.topic: include
ms.date: 03/28/2019
ms.author: erikje
ms.custom: include file
---

These notices provide important information that can help you prepare for future Intune changes and features. 

### Update your Android Company Portal app to the latest version <!--4536963-->
Intune periodically releases updates to the Android Company Portal App. In November 2018 we released a company portal update, which included a back-end switch to prepare for Google’s change from their existing notification platform to Google’s Firebase Cloud Messaging (FCM). When Google retires their existing notification platform and moves to FCM, end users will need to have updated their company portal app to at least November 2018 release to continue communicating with the Google play store.

#### How does this affect me?
Our telemetry indicates you have devices with a Company Portal version earlier than 5.0.4269.0. If this version or later of the company portal app is not installed, IT pro initiated device actions like wipe, reset password, available and required app installs, and certificate enrollment may not work as expected. If your devices are MDM enrolled in Intune, then you can see the company portal versions and users by going to Client apps – Discovered apps. Selecting earlier versions of the Company Portal will allow you to see what end users have the devices that haven’t updated the company portal.

#### What do I need to do to prepare for this change?
Ask end users of Android devices that have not updated to update the company portal through Google play. Notify your help desk in case a user has not kept auto-updating of the company portal app. See the link in Additional Information for more on Google’s FCM platform and change.

#### Additional Information
https://firebase.google.com/docs/cloud-messaging/
