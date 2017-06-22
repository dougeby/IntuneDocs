---
# required metadata

title: Add Skycure apps into Intune
titleSuffix: Intune on Azure
description: "Add Skycure apps, Microsoft Authenticator app and iOS configuration policy into the Intune Azure portal."
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/21/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 00356258-76a8-4a84-9cf5-64ceedb58e72

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Add and assign Skycure apps, Microsoft Authenticator app and iOS configuration policy

You can use Intune to add and deploy the Skycure apps so end-users can receive notifications when a threat is identified in their mobile devices, and to receive guidance to remediate the threats.

For iOS devices, you need the [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) so users can have their identities checked by Azure AD. Additionally, you need the iOS app configuration policy which signals the Skycure iOS app to use Intune and Azure AD Single Sign On (SSO) so users don’t need to type username and password every time they log in the Skycure app.

> [!TIP]
> The Intune company portal works as the broker on Android devices so users can have their identities checked by Azure AD.

## Before you begin

-   The below steps need to be completed in the [Azure portal](https://portal.azure.com/).

-   Make sure you’re familiar with the process of:

    -   [Adding an app into Intune](apps-add.md).

    -   [Adding an iOS app configuration policy into Intune](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

    -   [Assigning an app with Intune](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune).

    -   [ Adding an iOS app configuration policy](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

## To add apps

### Skycure app for Android

- See the instructions for [adding Android store apps to Microsoft Intune](store-apps-android.md). Use this [Skycure app store URL](https://play.google.com/store/apps/details?id=com.skycure.skycure) on **step 7**.

### Skycure app for iOS

- See the instructions for [adding iOS store apps to Microsoft Intune](store-apps-ios.md). Use this [Skycure app store URL](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) on **step 5** under the **Configure app information** section.

### Microsoft Authenticator app for iOS

- See the instructions for [adding iOS store apps to Microsoft Intune](store-apps-ios.md). Use this [Microsoft Authenticator app store URL](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) on **step 5** under the **Configure app information** section.

### Lookout for work Android app

- See the instructions for [adding Android store apps to Microsoft Intune](store-apps-android.md). Use this [Lookout for work Google app store URL](https://play.google.com/store/apps/details?id=com.lookout.enterprise) on **step 7**.

### Lookout for Work iOS app

- See the instructions for [adding iOS store apps to Microsoft Intune](store-apps-ios.md). Use this [Lookout for Work iOS app store URL](https://itunes.apple.com/us/app/lookout-for-work/id997193468?mt=8) on **step 5** under the **Configure app information** section.

### Lookout for Work app outside the Apple store

You need to re-sign the Lookout for Work iOS app. Lookout distributes its Lookout for Work iOS app outside of the iOS App Store. Before distributing the app, you must re-sign the app with your iOS Enterprise Developer Certificate.

For detailed instructions to re-sign the Lookout for Work iOS apps, see [Lookout for Work iOS app re-signing process](https://personal.support.lookout.com/hc/articles/114094038714) on the Lookout website.

#### Enable Azure AD authentication for Lookout for Work iOS app

Enable Azure Active Directory authentication for the iOS users by doing the following:

1. Go to the [Azure portal](https://portal.sazure.com), sign in with your credentials, then navigate to the application page.
  
2. Add the **Lookout for Work iOS app** as a **native client application**.

3. Replace the **com.lookout.enterprise.yourcompanyname** with the customer bundle ID you selected when you signed the IPA.

4.  Add additional redirect URI: **&lt;companyportal://code/>** followed by a URL encoded version of your original redirect URI.

5.  Add **Delegated Permissions** to your app.

	> [!NOTE] 
	> See [configure a native client application with Azure AD](https://azure.microsoft.com/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application) for more details.

#### Add the Lookout for Work ipa file

- Upload the re-signed .ipa file as described in the [Add iOS LOB apps with Intune](lob-apps-ios.md) topic. You also need to set the minimum OS version to iOS 8.0 or later.

## To associate the MTD app with an iOS app configuration policy

### For Skycure

-   Use the same Azure AD account previously configured in the Skycure Management console, which should be the same account used to log in into the Intune classic console.

-   You need to have the Skycure integration file ready to use. This is the .zip file previously downloaded from the Skycure Management console, which contains the file **skycure\_configuration.plist** with the iOS app configuration policy parameters.

- See the instructions for [using Microsoft Intune app configuration policies for iOS](app-configuration-policies-use-ios.md) to add the Skycure iOS app configuration policy.
	- On step 8, use the option **Enter XML data**, copy the content from the **skycure_configuration.plist** file and paste its content into the configuration policy body.

You can also copy the **skycure_configuration.plist** content from here:

```
<dict>
	<key>MdmType</key>
	<string>Intune</string>
	<key>UserEmail</key>
	<string>{{userprincipalname}}</string>
</dict>

```
### For Lookout

- Create the iOS app configuration policy as described in the [using iOS app configuration policy](app-configuration-policies-use-ios.md) topic.

## To assign MTD apps

- See the instructions for [assigning apps to groups with Intune](apps-deploy.md).

## Next steps

[Set up the Skycure integration with Intune](skycure-mtd-connector-integration.md)
[Set up the Lookout integration with Intune](lookout-mtd-connector-integration.md)
