---
# required metadata

title: Configure and deploy Lookout for Work app with Intune
titleSuffix: "Intune Azure preview"
description: Configure and deploy Lookout for Work apps for Android with Intune.
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/09/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 246a0a54-e394-4b85-84e2-ea5e69724ac2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Configure and deploy Lookout for Work app

This article explains how to configure and deploy the Lookout for Work app for Android and iOS devices.

## Android (Google Play Store app)

1.	In the [Microsoft Intune administrator console](https://manage.microsoft.com), go to **Apps** and choose **Add Apps**.
2.	On the **Software Setup** page of the publisher, choose **External link**, and specify the following URL:  https://play.google.com/store/apps/details?id=com.lookout.enterprise
  >[!NOTE]
  >Do not click the box for requiring a managed browser.

3.	On the **Software description** page fill in the following information:
  * **Publisher:** Lookout Mobile Security
  * **Name:**   Lookout for Work
  * **Description:**  Lookout offers the best protection against mobile threats to keep your device safe. When the Lookout app is installed on the device, the app protects your device from threats and will alert you, and your company administrator, if any are found.
  * **Category:** Computer Management

4. Upon successful completion you see a message **Upload of data to Microsoft Intune successfully completed**.

  In the Intune Console when you click on the **Apps** you will now see the **Lookout for Work** app in the list
  ![screenshot of Intune admin console apps page showing the Lookout for work apps in the list](./media/lookout-app-listed-intune-console.png)

5. Deploy the app to users by selecting the Lookout for Work app and choosing  **Manage Deployment**.

  You must select the same users added in to the Enrollment Management option in the Lookout MTD console.  See Step 3 in the [configure your subscription with Lookout MTD section](lookout-mtd-subscription-setup.md) for information about adding user groups to Lookout MTP.

  >[!IMPORTANT]
  > The Intune app deployment Wizard is not aware of the Azure AD user groups and uses the Intune user groups instead. So you must create an Intune user group based on the Azure AD user group that is enrolled in the Lookout MTD console.

6. Choose the **Required Install** option to require that the Lookout app be installed on the user’s device.

## iOS (Enterprise-signed version of Lookout app)

1. Make sure **iOS management** is set up on your device. For instructions on how to set up your device for iOS management, see [Set up iOS and Mac device management](https://docs.microsoft.com/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune).

2. **Re-sign** the Lookout for Work iOS app. Lookout distributes its Lookout for Work iOS app outside of the iOS App Store. **Before distributing the app**, you must re-sign the app with your iOS Enterprise Developer Certificate. For detailed instructions to re-sign the Lookout for Work iOS apps, see [Lookout for Work iOS app re-signing process](https://personal.support.lookout.com/hc/articles/114094038714) on the Lookout site.

3. Enable Azure Active Directory authentication for the iOS users by doing the following:
  1.  Login to the [Azure Active Directory management portal](https://manage.windowsazure.com), and navigate to the application page.
  2.  Add the **Lookout for Work iOS app** as a **native client application**.
  ![screenshot of the add apps dialog showing the native client app option](./media/aad-add-app.png)
  3. Replace the **com.lookout.enterprise.yourcompanyname** with the customer bundle ID you selected when you signed the IPA.
  4.  Add additional redirect URI: **&lt;companyportal://code/>** followed by a URLencoded version of your original redirect URI.
  5.  Add **Delegated Permissions** to your app.

  For more details, see [Configure a native client application](https://azure.microsoft.com/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application).

4. Upload the re-signed .ipa file as described in the [Add app for mobile devices in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune) topic. Set the minimum OS version to iOS 8.0 or later.

  ![screenshot of the apps page in the Intune administrator console with the Lookout for work app displayed in the list of apps](./media/ios-app-uploaded-intune.png)

5. Create the managed app configuration policy as described in the [Configure iOS apps with mobile app configuration policies in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune) topic.

  ![screenshot of hte create a new policy wizard with the iOS 8.0 or later app configuration policy highlighted](./media/ios-app-config.png)

6. **To deploy the app to users**, select the Lookout for Work app, and choose **Manage Deployment**.

  You must select the same users that were added to the Enrollment Management option in the Lookout  console.  See Step 3 in the [configure your Lookout subscription section](lookout-mtd-subscription-setup.md) for information about adding user groups to Lookout MTP.

  >[!IMPORTANT]
  > The Intune app deployment wizard is not aware of the Azure AD user groups and uses the Intune user groups instead, so you must create an Intune user group based on the Azure AD user group that is enrolled in the Lookout console.

  Choose the **Required Install** option to require that the Lookout app be installed on the user’s device.

## What happens when the deployed app is opened on the device

When the user opens the Lookout for Work on the device they are prompted to activate the app, and choose the Sign in with Azure Active Directory option. A detailed walk-through with the end-user flow can be found in the following topics:

* [You are prompted to install Lookout for Work on your Android device](https://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

* [You need to resolve a threat that Lookout for Work found on your Android device](https://docs.microsoft.com/intune/enduser/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)

## Next steps
* [Create Lookout device compliance policy in Intune](lookout-device-compliance-policy-create.md)
