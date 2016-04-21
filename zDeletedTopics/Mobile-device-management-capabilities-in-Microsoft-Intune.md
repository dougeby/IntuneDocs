---
title: Mobile device management capabilities in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: f23b3ee7-78da-4e53-9fc2-78e58401bcf9
author: robstackmsft
---
# Mobile device management capabilities in Microsoft Intune
Intune supports mobile device management of iOS, Android, and Windows Phone devices. It also supports management of Windows RT, Window computers, and Mac OS X computers as mobile devices. Users use a *company portal* to install apps, enroll and remove devices, and helps them contact their IT department or helpdesk. To enroll mobile devices you must set [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] as your *mobile device authority* and then configure the infrastructure to support the platforms you want to managed. This requires establishing a trust relationship with the device.

## <a name="BKMK_MobileDeviceReqs"></a>Supported mobile devices
The requirements to manage a mobile device and the level of management you have depend on whether you manage the device directly or use Exchange ActiveSync:

-   **Direct management**: Different types of mobile devices have different requirements for direct management. For example, to manage iOS devices you need an Apple Push Notification service certificate, and to manage apps for a [!INCLUDE[winblue_winrt_2](../Token/winblue_winrt_2_md.md)] device, you need sideloading keys and a code-signing certificate. [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] can manage the following devices with mobile device management:

    -   Apple iOS 7.1 and later

        > [!NOTE]
        > iOS 6.0 devices that are already enrolled will remain enrolled, but new devices must be running iOS version 7.1 or later in order to enroll in Intune.

    -   Google Android 4.0 and later (including Samsung KNOX)

    -   Windows Phone 8.0 and later

    -   Windows RT and Windows 8.1 RT

    -   Windows 8.1 and later computers (managed as mobile devices; see [Windows PC management capabilities in Microsoft Intune](../Topic/Windows-PC-management-capabilities-in-Microsoft-Intune.md))

    -   Mac OS X 10.9 and later

    Before you can directly manage mobile devices you must [Set mobile device management authority and configure Microsoft Intune](../Topic/Set-mobile-device-management-authority-and-configure-Microsoft-Intune.md).

-   **Exchange ActiveSync**: To manage devices by using Exchange ActiveSync requires you to install the On-Premises Connector or use the built-in Service to Service Connector to connect to your Exchange Server.

    To learn about the hardware and software requirements to install the On-Premises Connector, see [Requirements for the On-Premises Connector](../Topic/Network-infrastructure-requirements-for-Microsoft-Intune.md#BKMK_ExchanceConnectorReqs).

    To learn about using the On-Premises Connector or Service to Service Connector with Exchange, see [Mobile device management with Exchange ActiveSync and Microsoft Intune](../Topic/Mobile-device-management-with-Exchange-ActiveSync-and-Microsoft-Intune.md).

## Mobile device management features
Intune supports mobile device management of iOS, Android, and Windows Phone devices. It also supports management of Windows RT and Window computers as mobile devices. [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] can manage users' devices, popularly known as "bring your own device" (BYOD). It can also manage company-owned devices including scenarios where the company provides a list of devices users may choose from, known as "choose your own device" (CYOD).

You can enroll devices to meet your organization's needs:

|Enrollment type|BYOD|CYOD|Shared device with manager account|Shared device without a user account|
|-------------------|--------|--------|--------------------------------------|----------------------------------------|
|**Description**|Personal device enrolled using Microsoft Intune|Corporate-owned device for single user|Corporate-owned device managed using a manager account shared by many users|Corporate-owned user-less device used by many users.|
|**Device’s user**|Owner|Assigned user|No user-specific account|No specific user|
|**Who enrolls**|Owner|Administrator|Device Manager|Anyone|
|**Who un-enrolls**|Owner or administrator|Administrator|Administrator|Administrator|
|**Who can reset**|Owner or administrator|Administrator|Administrator|Administrator|
To enroll mobile devices you must set [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] as your *mobile device authority* and then configure the infrastructure to support the platforms you want to managed. This requires establishing a trust relationship with the device.

Management, inventory, app deployment, provisioning, and retirement are all handled through the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] administration console. Users gain access to the company portal which allows them to install apps, enroll and remove devices, and helps them contact their IT department or helpdesk.

**Mobile device management (MDM) capabilities** differ across mobile device platforms but all platforms support the following:

-   **Certificate, email, VPN and Wifi profiles.** You can deploy certificate profiles to mobile devices, and also deploy e-mail, VPN and Wifi profiles. See [Enable access to company resources with Microsoft Intune - deleted](../Topic/Enable-access-to-company-resources-with-Microsoft-Intune---deleted.md).

-   **Manage corporate-owned iOS devices.** You can set up devices for enrollment and then distribute them to specific users, or you can enroll devices so that they can be shared by multiple users. See [Set up iOS and Mac management with Microsoft Intune](../Topic/Set-up-iOS-and-Mac-management-with-Microsoft-Intune.md).

-   **Mobile application management.** Managed mobile apps can be configured to restrict certain app operations, such as copy and paste, to help protect your organization’s data. You can also use the managed browser to control the sites that users are allowed to visit. See [Configure and deploy mobile application management policies in the Microsoft Intune console](../Topic/Configure-and-deploy-mobile-application-management-policies-in-the-Microsoft-Intune-console.md) and [Manage Internet access using managed browser policies with Microsoft Intune](../Topic/Manage-Internet-access-using-managed-browser-policies-with-Microsoft-Intune.md).

-   **Conditional access.** Use [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] conditional access policies to control access to on-premises Microsoft Exchange email from mobile devices, even when the device is not managed by Intune. See [Manage access to email and SharePoint with Microsoft Intune](../Topic/Manage-access-to-email-and-SharePoint-with-Microsoft-Intune.md).

-   **Passwords management** differs across mobile device platforms, but all platforms let you require a password, limit the number of failed attempts, limit the minutes before the screen locks, set password expiration, and prevent previously-used passwords.

-   **Application settings.** You can control browser settings, and also such application settings as whether app stores can be used on mobile devices.

-   **Device capabilities, cellular and voice.** You can allow or deny the use of a camera, control roaming settings, and enable or disable iOS voice assistant and voice dialing features.

-   **Reset passcodes, lock, selectively wipe or retire devices.** You can reset passcodes if users lose access to their device, lock missing or stolen devices, or even wipe data off of missing or stolen devices.

## Device security and configuration

|Capability|Details|More information|
|--------------|-----------|--------------------|
|Configuration policies|Mobile device configuration policies let you manage many settings and features on mobile devices in your organization.|[iOS configuration policy settings in Microsoft Intune](../Topic/iOS-configuration-policy-settings-in-Microsoft-Intune.md)<br /><br />[Android configuration policy settings in Microsoft Intune](../Topic/Android-configuration-policy-settings-in-Microsoft-Intune.md)<br /><br />[Windows configuration policy settings in Microsoft Intune](../Topic/Windows-configuration-policy-settings-in-Microsoft-Intune.md)<br /><br />[Windows Phone configuration policy settings in Microsoft Intune](../Topic/Windows-Phone-configuration-policy-settings-in-Microsoft-Intune.md)<br /><br />[Exchange ActiveSync policy settings in Microsoft Intune](../Topic/Exchange-ActiveSync-policy-settings-in-Microsoft-Intune.md)<br /><br />[Mobile device security policy settings in Microsoft Intune](../Topic/Mobile-device-security-policy-settings-in-Microsoft-Intune.md)|
|Custom policies|Use custom polices when configuration policies do not contain the setting you require. For iOS devices, you can import settings you exported from the Apple Configurator Tool. For other devices, you can use OMA-URI settings to configure settings and features on the device.|[iOS custom policy settings in Microsoft Intune](../Topic/iOS-custom-policy-settings-in-Microsoft-Intune.md)<br /><br />[Android custom policy settings in Microsoft Intune](../Topic/Android-custom-policy-settings-in-Microsoft-Intune.md)<br /><br />[Windows Phone custom policy settings in Microsoft Intune](../Topic/Windows-Phone-custom-policy-settings-in-Microsoft-Intune.md)<br /><br />[Windows 10 custom policy settings in Microsoft Intune](../Topic/Windows-10-custom-policy-settings-in-Microsoft-Intune.md)|
|Remote Wipe, Remote Lock, and Passcode Reset|Erase sensitive data when a device is lost or stolen. For example, you can remotely lock the device, restore it to factory settings, or wipe only corporate data.|[Help protect your data with remote wipe, remote lock, or passcode reset using Microsoft Intune](../Topic/Help-protect-your-data-with-remote-wipe,-remote-lock,-or-passcode-reset-using-Microsoft-Intune.md)|
|Kiosk mode|Lets you lock down certain features of mobile devices such as screen capture and the power switch. Also lets you restrict devices to run a single app that you specify.|[iOS configuration policy settings in Microsoft Intune](../Topic/iOS-configuration-policy-settings-in-Microsoft-Intune.md)|

## App management

|Capability|Details|More information|
|--------------|-----------|--------------------|
|App deployment and management|Provides a range of tools to help you manage mobile apps through their lifecycle, including app deployment from installation files and app stores, detailed monitoring of app status, and app removal.|[Deploy apps to mobile devices in Microsoft Intune - deleted](../Topic/Deploy-apps-to-mobile-devices-in-Microsoft-Intune---deleted.md)|
|Compliant and noncompliant apps|Lets you specify lists of compliant apps (that users are allowed to install) and noncompliant apps (which must not be installed by users).|[iOS configuration policy settings in Microsoft Intune](../Topic/iOS-configuration-policy-settings-in-Microsoft-Intune.md)|
|Mobile application management|Configure restrictions for apps by using a mobile application management policy. This helps you to increase the security of your company data by restricting operations such as copy and paste, external backup of data and the transfer of data between apps.|[Configure and deploy mobile application management policies in the Microsoft Intune console](../Topic/Configure-and-deploy-mobile-application-management-policies-in-the-Microsoft-Intune-console.md)<br /><br />[Prepare iOS apps for mobile application management with the Microsoft Intune App Wrapping Tool](../Topic/Prepare-iOS-apps-for-mobile-application-management-with-the-Microsoft-Intune-App-Wrapping-Tool.md)<br /><br />[Prepare Android apps for mobile application management with the Microsoft Intune App Wrapping Tool](../Topic/Prepare-Android-apps-for-mobile-application-management-with-the-Microsoft-Intune-App-Wrapping-Tool.md)<br /><br />[Microsoft apps you can use with Microsoft Intune mobile application management policies](../Topic/Microsoft-apps-you-can-use-with-Microsoft-Intune-mobile-application-management-policies.md)|
|Managed browser|After you deploy the managed browser to your users, you can configure a managed browser policy to control the websites that they can visit. In addition, you can also apply mobile application management policies to the managed browser.|[Manage Internet access using managed browser policies with Microsoft Intune](../Topic/Manage-Internet-access-using-managed-browser-policies-with-Microsoft-Intune.md)|

## Company resource access

|Capability|Details|More information|
|--------------|-----------|--------------------|
|Certificate profiles|Create and deploy trusted certificate profiles and Simple Certificate Enrollment Protocol (SCEP) certificates which can be used to help secure and authenticate Wi-Fi, VPN, and email profiles.|[Enable access to company resources using certificate profiles with Microsoft Intune](../Topic/Enable-access-to-company-resources-using-certificate-profiles-with-Microsoft-Intune.md)|
|Wi-Fi profiles|Deploy wireless network settings to your users. By deploying these settings, you minimize the end-user effort required to connect to the corporate network.|[Help users connect to company networks using Wi-Fi profiles with Microsoft Intune](../Topic/Help-users-connect-to-company-networks-using-Wi-Fi-profiles-with-Microsoft-Intune.md)|
|Email profiles|Create and deploy email settings to devices. This lets users access corporate email on their personal devices without any required setup on their part.|[Configure access to corporate email using email profiles with Microsoft Intune](../Topic/Configure-access-to-corporate-email-using-email-profiles-with-Microsoft-Intune.md)|
|VPN profiles|Deploy VPN settings to users and devices in your organization. By deploying these settings, you minimize the end-user effort required to connect to resources on the company network.|[Help users connect to their work using VPN profiles with Microsoft Intune](../Topic/Help-users-connect-to-their-work-using-VPN-profiles-with-Microsoft-Intune.md)|
|Conditional access policies|Manage access to Microsoft Exchange email and SharePoint Online from devices that are not managed by [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].|[Manage access to email and SharePoint with Microsoft Intune](../Topic/Manage-access-to-email-and-SharePoint-with-Microsoft-Intune.md)|

## Inventory and reporting

|Capability|Details|More information|
|--------------|-----------|--------------------|
|Inventory and reporting|Find information about the devices you manage and the software they are using.<br /><br />You can filter these reports in a number of ways, such as the device platform, and whether the device is compliant with corporate standards.|[Understand Microsoft Intune operations by using reports](../Topic/Understand-Microsoft-Intune-operations-by-using-reports.md)|

## See Also
[Introduction to Microsoft Intune](../Topic/Introduction-to-Microsoft-Intune.md)
[Get ready to enroll devices in Microsoft Intune](../Topic/Get-ready-to-enroll-devices-in-Microsoft-Intune.md)
[Manage mobile devices and PCs from the cloud](http://technet.microsoft.com/library/dn715906.aspx)
[Bring your own device (BYOD) design considerations guide](http://technet.microsoft.com/library/dn656905.aspx)
[Sign up for a free trial](https://account.manage.microsoft.com/Signup/MainSignUp.aspx?OfferId=A77BE827-FC8B-4EF2-A0F5-7CD6C813AA65&ali=1)
[How to buy Intune](http://technet.microsoft.com/library/dn646949.aspx)
[Start using Microsoft Intune](../Topic/Start-using-Microsoft-Intune.md)
[Microsoft Intune Service Description](../Topic/Microsoft-Intune-Service-Description.md)
[Get started with a 30-day trial of Microsoft Intune](../Topic/Get-started-with-a-30-day-trial-of-Microsoft-Intune.md)

