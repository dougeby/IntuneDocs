## March 2017

### New Capabilities

#### Support for Skycure

You can now control mobile device access to corporate resources using conditional access based on risk assessment conducted by Skycure, a mobile threat defense solution that integrates with Microsoft Intune. Risk is assessed based on telemetry collected from devices running Skycure, including:

- Physical defense
- Network defense
- Application defense
- Vulnerabilities defense

You can configure EMS conditional access policies based on Skycure risk assessment enabled through Intune device compliance policies. You can use these policies to allow or block non-compliant devices access to corporate resources based on detected threats. For more information, see [Skycure Mobile Threat Defense connector](/intune/deploy-use/skycure-mobile-threat-defense-connector).

#### New user experience for the Company Portal app for Android <!--621622-->

The Company Portal app for Android will be updating its user interface for a more modern look and feel, and better user experience. The notable updates are:

- Colors: Company Portal tab headers are colored in IT-defined branding.
- Apps: In the **Apps** tab, the **Featured Apps** and **All Apps** buttons are updated.
- Search: In the **Apps** tab, the **Search** button is a floating action button.
- Navigating Apps: **All Apps** view shows a tabbed view of **Featured**, **All**, and **Categories** for easier navigation.
- Support: **My Devices** and **Contact IT** tabs are updated to improve readability.

For more details about these changes, see [UI updates for Intune end user apps](whats-new-in-intune-app-ui.md).

#### Non-managed devices can access assigned apps <!--664691-->

As part of the design changes on the Company Portal website, iOS and Android users will be able to install apps assigned to them as "available without enrollment" on their non-managed devices. Using their Intune credentials, users will be able to log into the Company Portal website and see the list of apps assigned to them. The app packages of the "available without enrollment" apps are made available for download via the Company Portal website. Apps which require enrollment for installation are not affected by this change, as users will be prompted to enroll their device if they wish to install those apps.

#### Signing Script for Windows 10 Company Portal <!--941642-->

If you need to download and sideload the Windows 10 Company Portal app, you can now use a script to simplify and streamline the app-signing process for your organization.   To download the script and the instructions for using it, see  [Microsoft Intune Signing Script for Windows 10 Company Portal](https://aka.ms/win10cpscript) on TechNet Gallery. For more details about this announcement, see [Updating your Windows 10 Company Portal app](https://blogs.technet.microsoft.com/intunesupport/2017/03/13/updating-your-windows-10-company-portal-app/) on the Intune Support Team Blog.


### Notices

#### Support for iOS 10.3

The iOS 10.3 release started rolling out on March 27, 2017 to iOS users. All existing Intune MDM and MAM scenarios are compatible with the latest version of Apple’s OS. We anticipate all existing Intune features currently available for managing iOS devices will continue to work as your users upgrade their devices and apps to iOS 10.3.

There are currently no known issues to share. If you run into any issues with iOS 10.3, please feel free to reach out to the [Intune support team](/intune/troubleshoot/contact-assisted-phone-support-for-microsoft-intune).

#### Improved support for Android users based in China <!--720444-->

Due to the absence of the Google Play Store in China, Android devices must obtain apps from Chinese marketplaces. The Company Portal will support this workflow by redirecting Android users in China to download the Company Portal and Outlook apps from local app stores. This will improve the user experience when Conditional Access policies are enabled, both for Mobile Device Management and for Mobile Application Management. The Company Portal and Outlook apps for Android are available on the following Chinese app stores:

- [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
- [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)
- [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
- [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
- [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)

#### Best practice: make sure your Company Portal apps are up-to-date <!--879465-->

In December 2016, we released an update that enabled enforcement for multi-factor authentication (MFA) on a group of users when they enroll an iOS, Android, Windows 8.1+, or Windows Phone 8.1+ device. This feature cannot work without certain baseline versions of the Company Portal app for Android (v5.0.3419.0+) and iOS (v2.1.17+).

Microsoft is continuously improving Intune by adding new functions to both the console and the Company Portal apps on all supported platforms. As a result, Microsoft only releases fixes for issues that we find in the current version of the Company Portal app. We therefore recommend to use the latest versions of the Company Portal apps for the best user experience.

>[!Tip]
> Have your users set their devices to automatically update apps from the appropriate app store. If you have made the Android Company Portal app available on a network share, you can download the latest version from [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=49140).

#### Microsoft Teams is now enabled for MAM on iOS and Android

Microsoft has announced the general availability of Microsoft Teams. The updated Microsoft Teams apps for iOS and Android are now enabled with Intune mobile app management (MAM) capabilities, so you can empower your teams to work freely across devices, while ensuring that conversations and corporate data is protected at every turn. For more details, see [the Microsoft Teams announcement](https://blogs.technet.microsoft.com/enterprisemobility/2017/03/14/microsoft-teams-is-now-generally-available-and-mam-enabled-on-ios-and-android/) on the Enterprise Mobility and Security blog.


## February 2017

### New Capabilities

#### Modernizing the Company Portal website <!--753980-->
The Company Portal website will support apps that are targeted to users who do not have managed devices. The website will align with other Microsoft products and services by using a new contrasting color scheme, dynamic illustrations, and a "hamburger menu," ![Small image of the hamburger menu that is now added at the top left corner of the Company Portal website](/intune/whats-new/media/CP_hamburger_menu.png) which will contain helpdesk contact details and information on existing managed devices. The landing page will be rearranged to emphasize apps that are available to users, with carousels for Featured and Recently Updated apps. You can find before and after images available on the [UI updates page](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui).

### Notices

#### Group migration will not require any updates to groups or policies for iOS devices <!--898837-->
For every Intune device group pre-assigned by a Corporate Device Enrollment profile, a corresponding dynamic device group will be created in AAD based on the Corporate Device Enrollment profile’s name, during the migration to Azure Active Directory device groups. This will ensure the as devices enroll, they will be automatically grouped and receive the same policies and apps as the original Intune group.

Once a tenant enters the migration process for grouping and targeting, Intune will automatically create a dynamic AAD group to correspond to an Intune group targeted by a Corporate Device Enrollment profile. If the Intune Admin deletes the targeted Intune group, the corresponding dynamic AAD group will not be deleted. The group's members and the dynamic query will be cleared, but the group itself will remain until the IT Admin removes it via the AAD portal.

Similarly, if the IT Admin changes which Intune group is targeted by a Corporate Device Enrollment profile, Intune will create new dynamic group reflecting the new profile assignment, but will not remove the dynamic group created for the old assignment.

#### Defaulting to managing Windows desktop devices through Windows settings <!--663050-->
The default behavior for enrolling Windows 10 desktops is changing. New enrollments will follow the typical MDM agent enrollment flow rather than through the PC agent. The Company Portal website will provide Windows 10 desktop users with enrollment instructions that guide them through the process of adding Windows 10 desktop computers as mobile devices. This will not impact currently enrolled PCs, and your organization can still manage Windows 10 desktops using the PC agent [if you prefer](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune).

#### Improving mobile app management support for selective wipe <!--581242-->
End users will be given additional guidance on how to regain access to work or school data if that data is automatically removed due to the "Offline interval before app data is wiped" policy.<!--, or the removal of the Intune Company Portal on Android.-->

#### Company Portal for iOS links open inside the app <!--665954-->
Links inside of the Company Portal app for iOS, including those to documentation and apps, will open directly in the Company Portal app using an in-app view of Safari. This update will ship separately from the service update in January.

#### New MDM server address for Windows devices <!--893007-->
Windows and Windows Phone users attempting to enroll a device will fail if they enter __manage.microsoft.com__ as the MDM server address (if prompted). The MDM server address is changing from __manage.microsoft.com__ to __enrollment.manage.microsoft.com__. Notify your user to use __enrollment.manage.microsoft.com__ as the MDM server address if prompted for it while enrolling a Windows or and Windows Phone device. No changes are needed to your CNAME setup. For additional information about this change, visit [aka.ms/intuneenrollsvrchange](https://aka.ms/intuneenrollsvrchange).

#### New user experience for the Company Portal app for Android <!--621622-->
Beginning in March, the Company Portal app for Android will follow [material design guidelines](https://material.io/guidelines/material-design/introduction.html) to create a more modern look and feel. This improved user experience includes:

* __Colors__: tab headers can be colored according to your custom color palette.
* __Interface__: Featured Apps and All Apps buttons have been updated in the Apps tab. The Search button is now a floating action button.
* __Navigation__: All Apps shows a tabbed view of Featured, All and Categories for easier navigation.
* __Service__: My Devices and Contact IT tabs have improved readability.

You can find before and after images on the [UI updates page](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui).

#### Associate multiple management tools with the Windows Store for Business <!--926135-->
If you are using more than one management tool to deploy Windows Store for Business apps, previously, you could only associate one of these with the Windows Store for Business. You can now associate multiple management tools with the store, for example, Intune and Configuration Manager. For details, see [Manage apps you purchased from the Windows Store for Business with Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune#associate-your-windows-store-for-business-account-with-intune).

## January 2017

### New Capabilities

#### In-console reports for MAM without enrollment <!--677961-->
New app protection reports have been added for both enrolled devices and devices that have not been enrolled. Find out more about how you can [monitor mobile app management policies with Intune here](https://docs.microsoft.com/intune/deploy-use/monitor-mobile-app-management-policies-with-microsoft-intune).

#### Android 7.1.1 support <!--694397-->
Intune now fully supports and manages Android 7.1.1.

#### Resolve issue where iOS devices are inactive, or the admin console cannot communicate with them <!--unknown-->
When users’ devices lose contact with Intune, you can give them new troubleshooting steps to help them regain access to company resources. See [Devices are inactive, or the admin console cannot communicate with them](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).

### Notices

#### Defaulting to managing Windows desktop devices through Windows settings <!--663050-->
The default behavior for enrolling Windows 10 desktops is changing. New enrollments will follow the typical MDM agent enrollment flow rather than through the PC agent.

The Company Portal website will provide Windows 10 desktop users with enrollment instructions that guide them through the process of adding Windows 10 desktop computers as mobile devices. This will not impact currently enrolled PCs, and your organization can still manage Windows 10 desktops using the PC agent [if you prefer](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune).

#### Improving mobile app management support for selective wipe <!--581242-->
End users will be given additional guidance on how to regain access to work or school data if that data is automatically removed due to the "Offline interval before app data is wiped" policy.<!--, or the removal of the Intune Company Portal on Android.-->

#### Company Portal for iOS links open inside the app <!--665954-->
Links inside of the Company Portal app for iOS, including those to documentation and apps, will open directly in the Company Portal app using an in-app view of Safari. This update will ship separately from the service update in January.

#### Modernizing the Company Portal website <!--753980-->
Beginning in February, the Company Portal website will support apps that are targeted to users who do not have managed devices. The website will align with other Microsoft products and services by using a new contrasting color scheme, dynamic illustrations, and a "hamburger menu," ![Company Portal website hamburger menu](/Intune/whats-new/media/CP_hamburger_menu.png) which will contain helpdesk contact details and information on existing managed devices. The landing page will be rearranged to emphasize apps that are available to users, with carousels for Featured and Recently Updated apps. You can find before and after images available on the [What's new in the Intune app UI page](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui).

#### New documentation for app protection policies <!--583398-->
We have updated our documentation for admins and app developers who want to enable app protection policies (known as MAM policies) in their iOS and Android apps using the Intune App Wrapping Tool or Intune App SDK.

The following articles have been updated:

* [Decide how to prepare apps for mobile application management with Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune)
* [Prepare iOS apps for mobile application management with the Intune App Wrapping Tool](https://docs.microsoft.com/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)
* [Get started with the Microsoft Intune App SDK](https://docs.microsoft.com/intune/develop/intune-app-sdk-get-started)
* [Intune App SDK for iOS developer guide](https://docs.microsoft.com/intune/develop/intune-app-sdk-ios)

The following articles are new additions to the docs library:

* [Intune App SDK Cordova Plugin](https://docs.microsoft.com/intune/develop/intune-app-sdk-cordova)
* [Intune App SDK Xamarin Component](https://docs.microsoft.com/intune/develop/intune-app-sdk-xamarin)

#### Progress bar when launching the Company Portal on iOS <!--665978-->
The Company Portal for iOS is introducing a progress bar on the launch screen to provide the user with information about the loading processes that occur. There will be a phased rollout of the progress bar to replace the spinner. This means that some of your users will see the new progress bar while others will continue to see the spinner.

## December 2016

### Public preview of the new Intune admin experience on Azure <!--736542-->
In early calendar year 2017, we will be migrating our full admin experience onto Azure, allowing for powerful and integrated management of core EMS workflows on a modern service platform that’s extensible using Graph APIs. In advance of the general availability of this portal for all Intune tenants, we're excited to announce that we will begin rolling out a preview of this new admin experience later this month to select tenants.

The admin experience in the Azure portal will use the already announced new grouping and targeting functionality; when your existing tenant is migrated to the new grouping experience you will also be migrated to preview the new admin experience on your tenant. In the meantime, find out more about what we have in store for Microsoft Intune in the Azure portal in our [new documentation](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune).

__Telecom expense management integration in public preview of Azure portal__ <!--747605-->
We are now beginning to preview integration with third-party telecom expense management (TEM) services within the Azure portal. You can use Intune to enforce limits on domestic and roaming data usage. We are beginning these integrations with [Saaswedo](http://www.saaswedo.com). To enable this feature in your trial tenant, please [contact Microsoft support](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

### New Capabilities

__Multi-factor authentication across all platforms__ <!--747590-->
You can now enforce multi-factor authentication (MFA) on a selected group of users when they enroll an iOS, Android, Windows 8.1+, or Windows Phone 8.1+ device from the Azure Management Portal by configuring MFA on the Microsoft Intune Enrollment application in Azure Active Directory.

__Ability to restrict mobile device enrollment__ <!--747596-->
Intune is adding new enrollment restrictions that control which mobile device platforms are allowed to enroll. Intune separates mobile device platforms as iOS, macOS, Android, Windows and Windows Mobile.
* Restricting mobile device enrollment does not restrict PC client enrollment.
* For iOS only, there is one additional option to block the enrollment of personally owned devices.

Intune marks all new devices as personal unless the IT admin takes action to mark them as corporate owned, as explained in [this article](https://docs.microsoft.com/intune/deploy-use/manage-corporate-owned-devices).

### Notices

__Multi-Factor Authentication on Enrollment moving to the Azure portal__ <!--VSO 750545-->
Previously, admins would go to either the Intune console or the Configuration Manager (earlier than release October 2016) console to set MFA for Intune enrollments. With this updated feature, you will now login to the [Microsoft Azure portal](https://manage.windowsazure.com) using your Intune credentials and configure MFA settings through Azure AD. Learn more about this [here](https://aka.ms/mfa_ad).

__Company Portal app for Android now available in China__ <!--VSO 658093-->
We are publishing the Company Portal app for Android for download in China. Due to the absence of Google Play Store in China, Android devices must obtain apps from Chinese app marketplaces. The Company Portal app for Android will be available for download on the following stores:
* [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
* [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
* [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
* [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)
* [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)

The Company Portal app for Android uses Google Play Services to communicate with the Microsoft Intune service. Since Google Play Services are not yet available in China, performing any of the following tasks can take up to 8 hours to complete. 

|Intune Admin Console| Intune Company Portal app for Android |Intune Company Portal Website|   
|---|---|---|
|Full wipe| Remove a remote device| Remove device (local and remote)|
|Selective wipe| Reset device| Reset device|
|New or updated app deployments| Install available line-of-business apps| Device passcode reset|
|Remote lock|||
|Passcode reset|||

### Deprecations

__Firefox to no longer support Silverlight__ <!--VSO TBA-->
Mozilla is removing support for Silverlight in version 52 of the [Firefox browser](https://www.mozilla.org/firefox), effective March 2017. As a result, you will no longer be able to log in to the existing Intune console using Firefox versions greater than 51. We recommend using Internet Explorer 10 or 11 to access the admin console, or a [version of Firefox prior to version 52](https://ftp.mozilla.org/pub/firefox/releases/). Intune's transition to the Azure portal will allow it to support a number of [modern browsers](https://docs.microsoft.com/azure/azure-preview-portal-supported-browsers-devices) without dependency on Silverlight.

__Removal of Exchange Online mobile inbox policies__ <!--770687-->
Beginning in December, admins will no longer be able to view or configure Exchange Online (EAS) mobile mailbox policies within the Intune console. This change will roll out to all Intune tenants over December and January. All existing policies will stay as configured; for configuring new policies, use the Exchange Management Shell. Find out more information [here](https://technet.microsoft.com/library/bb123783%28v=exchg.150%29.aspx).

__Intune AV Player, Image Viewer, and PDF Viewer apps are no longer supported on Android__ <!--747553-->
From mid-December 2016 on, users will no longer be able to use the Intune AV Player, Image Viewer, and PDF Viewer apps. These apps have been replaced with the Azure Information Protection app. Find out more about the Azure Information Protection app [here](https://docs.microsoft.com/information-protection/rms-client/mobile-app-faq).

## November 2016

### New capabilities

__New Microsoft Intune Company Portal available for Windows 10 devices__
Microsoft has released a new [Microsoft Intune Company Portal app for Windows 10 devices](https://www.microsoft.com/store/apps/9wzdncrfj3pz). This app, which leverages the new Windows 10 Universal format, will provide the user with an updated user experience within the app and identical experiences across all Windows 10 devices, PC and Mobile alike, while still enabling all the same functionality that they are using today.

The new app will also allow users to leverage additional platform features like single sign-on (SSO) and certificate-based authentication on Windows 10 devices. The app will be made available as an upgrade to the existing Windows 8.1 Company Portal and Windows Phone 8.1 Company Portal installs from the Windows Store. For more details, go to [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp).

> [!IMPORTANT]
> __An Update on Intune and Android for Work__
> While you can deploy Android for Work apps with an action of __Required__, you can only deploy apps as __Available__ if your Intune groups have been migrated to the new Azure AD groups experience.

__Intune App SDK for Cordova plugin now supports MAM without enrollment__
App developers can now use the Intune App SDK for Cordova plugin to enable MAM functionality without device enrollment in their Cordova-based apps for Android and iOS. The Intune App SDK for Cordova plugin can be found [here](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam).

__Intune App SDK Xamarin component now supports MAM without enrollment__
App developers can now use the Intune App SDK Xamarin component to enable MAM functionality without device enrollment in their Xamarin-based apps for Android and iOS. The Intune App SDK Xamarin component can be found [here](https://github.com/msintuneappsdk/intune-app-sdk-xamarin).

### Notices

__Symantec signing certificate no longer requires signed Windows Phone 8 Company Portal for upload__
Uploading the Symantec signing certificate will no longer require a signed Windows Phone 8 Company Portal app. The certificate can be uploaded independently.

###Deprecations

__Support for the Windows Phone 8 Company Portal__
Support for Windows Phone 8 Company Portal will now be deprecated. Support for the Windows Phone 8 and WinRT platforms was deprecated in October 2016. Support for the Windows 8 Company Portal was also deprecated in October 2016.

## October 2016

### Conditional access for mobile application management
You will be able to restrict access to Exchange Online so that access can come only from apps that support Intune mobile application management policies such as Outlook. [This new feature](/intune/deploy-use/allow-policy-managed-apps-access-to-o365) pairs up perfectly with Intune mobile app management (MAM) policies as you can block access to built-in mail clients or other apps that have not been configured with the Intune MAM policies. This ensures your users are accessing your organization’s data with apps that can be protected using Intune MAM. You can get started in Intune mobile app management via the Azure portal. Look for the new Conditional Access section in the “Settings” blade.

### Conditional access for Windows PCs
You can now create conditional access policies through the Intune admin console to block Windows PCs from accessing [Exchange Online](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune) and [SharePoint Online](/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune). You can also create conditional access policies to block access to Office desktop and universal applications.

### Android for Work support

> [!IMPORTANT]

> While you can deploy Android for Work apps with an action of __Required__, you can only deploy apps as __Available__ if your Intune groups have been migrated to the new Azure AD groups experience.

Intune is now part of the Android for Work (AfW) program. We will begin rolling out support for AfW features starting this month and continuing over the next few months. Note that  available app deployment of AfW leverages the new grouping and targeting experience. Newly provisioned Intune Service accounts will be able to use this feature once AfW is available to them.

[Read Microsoft’s announcement about Intune support for Android for Work](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/12/microsoft-intune-support-for-android-for-work/).

The following Intune topics are new, or updated with Android for Work information:

For IT professionals:
- [Set up Android for Work](/intune/deploy-use/set-up-android-for-work)
- [Restrict email access to Exchange Online and new Exchange Online Dedicated with Intune](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)
- [Restrict email access to Exchange on-premises and legacy Exchange Online Dedicated with Intune](/intune/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)
- [Android for Work compliance policy settings](/intune/deploy-use/afw-compliance-policy-settings-in-microsoft-intune)
- [How to deploy Android for Work apps](/intune/deploy-use/android-for-work-apps)
- [Configure Android for Work apps with mobile app configuration policies](/intune/deploy-use/afw-app-configuration-policy)
- [Android for Work policy settings](/intune/deploy-use/android-for-work-policy-settings-in-microsoft-intune)

For end users:
- [What happens when you create a work profile](/intune/enduser/what-happens-when-you-create-a-work-profile-android)
- [Create a work profile and enroll your device in Intune](/intune/enduser/create-a-work-profile-and-enroll-your-device-in-intune-android)

### Lookout integration to protect iOS devices
In October, Microsoft is integrating with Lookout’s mobile threat protection solution to protect iOS mobile devices by detecting malware, risky apps, and more, on devices. Lookout’s solution helps you determine the threat level, which is configurable. You can create a compliance policy rule in Intune to determine device compliance based on the risk assessment by Lookout. Using conditional access policies, you can allow or block access to company resources based on the device compliance status.

End users of noncompliant iOS devices will be prompted to enroll, and will be required to install the Lookout for Work app on their devices, activate the app, and remediate threats reported in the Lookout for Work application to gain access to company data. Learn how to [Configure and deploy Lookout for Work apps](/intune/deploy-use/configure-and-deploy-lookout-for-work-apps).
<!--TFS 1319493-->

### Intune App Wrapping Tool for Android
You can enable your apps to use Intune mobile application management (MAM) policies by using the Intune App Wrapping Tool. Support for Intune MAM policies without requiring device enrollment is now available.

### Manage printing from apps managed using MAM policies
You can now prevent printing company data from apps that have MAM policies. This setting is available on the [Azure portal](/Intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) and is supported on both [iOS](/Intune/deploy-use/ios-mam-policy-settings) and [Android](/Intune/deploy-use/android-mam-policy-settings) devices.
<!--TFS 1014328-->

### Support for fingerprints on Android devices
Android mobile app management (MAM) policies now allow users to access an app with their fingerprint instead of typing out their PIN. See this and other [mobile app management policy settings for Android here](/Intune/deploy-use/android-mam-policy-settings).

### Notices

__Android Samsung KNOX compatibility with Intune__
Certain models of the Samsung Galaxy Ace phone cannot be managed by Intune as Samsung KNOX devices. When you enroll these devices with Intune, they will instead be managed as standard Android devices.

The model numbers affected are:

* SM-G313HU
* SM-G313HY
* SM-G313M
* SM-G313MY
* SM-G313U

You and your end users need take no further action. For more information, visit the [Samsung KNOX](https://www.samsungknox.com) website.

__Company Portal app for Windows 8 is deprecated; support for Windows Phone 8 and Windows RT platforms are being deprecated__
Starting in October 2016, Microsoft Intune will deprecate support for the Windows 8 Company Portal. Microsoft Intune will also deprecate support for the Windows Phone 8 and Windows RT platforms. As a consequence, you will not be able to enroll or update any Windows Phone 8 or Windows RT devices.

You can continue to manage Windows Phone 8, Windows RT  and Windows 8 devices that are already enrolled. Update Windows Phone 8 and Windows 8 devices to Windows 8.1 and Windows Phone 8.1, and use the corresponding Windows 8.1 and Windows Phone 8.1 Company Portal apps to continue distributing apps to these devices without disruptions.

Starting in November 2016, we will deprecate support for the Windows Phone 8 Company Portal.
<!--TFS 1255391-->

### What's coming

__New Microsoft Intune Company Portal available for Windows 10 devices__
Microsoft is releasing a new Microsoft Intune Company Portal for Windows 10 devices. This app, which leverages the new Windows 10 Universal format, will provide the user with an updated user experience within the app and identical experiences across all Windows 10 devices, PC and Mobile alike, while still enabling all the same functionality that they are using today.

The new app will also allow users to leverage additional platform features like single sign-on (SSO) and certificate-based authentication on Windows 10 devices. The app will be made available as an upgrade to the existing Windows 8.1 Company Portal and Windows Phone 8.1 Company Portal installs from the Windows Store. For more details, go to [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp).
<!--TFS 1016502-->
