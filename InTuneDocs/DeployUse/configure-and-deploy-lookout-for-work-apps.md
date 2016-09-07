---
# required metadata

title: Deploy Lookout for Work app | Microsoft Intune
description: Configure and deploy Lookout for Work apps for Android.
author: karthikaraman
manager: angrobe
ms.date: 09/08/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 524c4209-ad57-4d35-955e-a00d796bf858

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: sandera
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Configure and deploy Lookout for Work apps
In this release, Lookout for work app on Android devices running 4.1 and later is supported.
## Android
This section discusses how to configure and deploy the Lookout for Work application for Android devices enrolled in Intune.  
* Step 1:	In the [Microsoft Intune administrator console](https://manage.microsoft.com), go to **Apps** and choose **Add Apps**.   
* Step 2:	On the **Software Setup** page of the publisher, choose **External link**, and specify the following URL:  https://play.google.com/store/apps/details?id=com.lookout.enterprise
>[!NOTE]
>Do not click the box for requiring a managed browser.

* Step 4:	On the **Software description** page fill in the following information:
  * **Publisher:** Lookout Mobile Security
  * **Name:**   Lookout for Work
  * **Description:**  Lookout offers the best protection against mobile threats to keep your device safe. When the Lookout app is installed on the device, the app protects your device from threats and will alert you, and your company administrator, if any are found.
  * **Category:** Computer Management
* Step 5:  Upon successful completion you see a message **Upload of data to Microsoft Intune successfully completed**.

On the Intune Console when you click on the **Apps** you will now see the Lookout for Work app in the list
![screenshot of Intune admin console apps page showing the Lookout for work apps in the list](../media/mtp/lookout-app-listed-intune-console.png)

Step 6: At this point Intune knows how to deploy the Lookout for work android app.   You can deploy the app to users, by selecting the Lookout for Work app shown in the screen above and selecting **Manage Deployment**.

Step 7: You must select the same group of users   that was used during the Lookout MTP Enrollment to deploy the  apps .
Step 8: Choose the **Required Install** option to require that the Lookout app be installed on the user’s device.

### Device activation
With the **Required Install** option selected for deployment, Intune will push the Lookout for work application to the device.   
When the user opens the Lookout for Work on the device they will need to Activate, and choose the Sign in with Azure Active Directory option. A detailed walkthrough with the end-user flow can be found in the following topics:

* [Installing Lookout for work app on Android](http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

* [Your device does not meet the mobile risk policy](http://docs.microsoft.com/intune/enduser/your-device-does-not-meet-the-mobile-risk-policy-android)

## Next steps
* [Enable device threat protection rule in the compliance policy](enable-device-threat-protection-rule-in-compliance-policy.md)
