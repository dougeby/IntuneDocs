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

### Change in enrollment workflow with Intune Company Portal on corporate iOS devices authenticating with Setup Assistant <!-- 1927359 -->
There's an upcoming change in workflow for enrollment of iOS devices through one of Apple’s corporate device enrollment methods - Apple Configurator, Apple Business Manager, Apple School Manager, or the Apple Device Enrollment Program (DEP), when using Setup Assistant for authentication. This change applies only to devices enrolled with user affinity.

#### How does this affect me?
When this change is rolled out, enrollment profiles in Intune in the Azure portal will be updated so that you can specify how devices authenticate and if they receive the Company Portal app. There will be an improved workflow to enroll iOS devices through the methods listed above. 

- When enrolling new devices and authenticating with Setup Assistant, you’ll be able to choose whether or not to deploy the Company Portal app automatically. End users will no longer see the “Identify your device” screen and the “Confirm your device” screen in the enrollment flow.  
- On devices already enrolled via Setup Assistant through one of Apple’s corporate device enrollment methods, you must take action if you want to enable Conditional Access. You’ll have to configure an app configuration policy with a specific xml to push the Company Portal down to these devices. Directions to do this are in the blog post at the Additional Information link. If you choose to push the Company Portal in this manner, end users will no longer see the “Identify your device” screen and the “Confirm your device” screen in the enrollment flow. 
- After this change is rolled out, if you haven't deployed the Company Portal with the app configuration profile mentioned above and if end users download the Company Portal app from the App store, they can sign in, but they'll get an error message. They won't be able to use the app for Conditional Access. 

#### What do I need to do to prepare for this change?
If you plan on using the modified workflow, you'll want to update your end user guidance to indicate that:

- End users will no longer see the two screens mentioned above in the enrollment flow. 
- They'll need to sign in to the Company Portal when it's automatically deployed and not download it from the app store. 

You can choose to create an app configuration policy now if needed, in preparation for this change. When this new workflow rolls out, you’ll see updated enrollment profiles in the console. We’ll also inform you of this rollout through the Message Center. After this, you’ll need to take the action so your end users can enroll through DEP by authenticating with Setup Assistant and you can use Company Portal for Conditional Access.

See our support blog post at the Additional Information link for more details about this change.

#### Additional Information 
[https://aka.ms/enrollment_setup_assistant](https://aka.ms/enrollment_setup_assistant)


### Update your Android Company Portal app to the latest version <!--4536963-->
Intune periodically releases updates to the Android Company Portal App. In November, 2018 we released a company portal update which included a back-end switch to prepare for Google’s change from their existing notification platform to Google’s Firebase Cloud Messaging (FCM). When Google retires their existing notification platform and moves to FCM, end users will need to have updated their company portal app to at least November, 2018 release to continue communicating with the Google play store.

#### How does this affect me?
Our telemetry indicates you have devices with a Company Portal version earlier than 5.0.4269.0. If this version or later of the company portal app is not installed, IT pro initiated device actions like wipe, reset password, available and required app installs, and certificate enrollment may not work as expected. If your devices are MDM enrolled in Intune, then you can see the company portal versions and users by going to Client apps – Discovered apps. Selecting earlier versions of the Company Portal will allow you to see what end users have the devices that haven’t updated the company portal.

#### What do I need to do to prepare for this change?
Ask end users of Android devices that have not updated to update the company portal through Google play. Notify your help desk in case a user has not kept auto-updating of the company portal app. See the link in Additional Information for more on Google’s FCM platform and change.

#### Additional Information
https://firebase.google.com/docs/cloud-messaging/