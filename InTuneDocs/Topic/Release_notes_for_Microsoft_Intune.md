---
title: Release notes for Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: db9479b2-582d-4a1a-9fbc-fbfc6c680e6f
author: Staciebarker
---
# Release notes for Microsoft Intune
[!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] is an integrated, cloud-based client management solution that provides tools, reports, and upgrade licenses to the latest version of Windows, and helps keep your computers up-to-date and secure. In addition, [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] lets you manage mobile devices on the network either through Exchange ActiveSync or directly through [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]. The following release notes describe important information and known issues in [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)].

-   [Installation, Deployment, and Enrollment](../Topic/Release_notes_for_Microsoft_Intune.md#BKMK_WitRelnoteInstall)

-   [Alerts](../Topic/Release_notes_for_Microsoft_Intune.md#BKMK_WitRelnoteAlerts)

## <a name="BKMK_WitRelnoteInstall"></a>Installation, Deployment, and Enrollment
The following issues can occur during client software deployment, client device preparation for [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)], or device enrollment.

### When you enroll a Windows 8.1 device that must authenticate to a proxy server, the enrollment process fails with no visible indication as to the cause of the failure
**Issue:** When you enroll a [!INCLUDE[winblue_client_2](../Token/winblue_client_2_md.md)] device and the device must authenticate to a proxy server during the enrollment process, the enrollment fails if the device has not cached the proxy server credentials. When the credentials for the proxy server are not cached on the device, the enrolment process must wait for the user to enter the credentials. However, the prompt to provide the proxy server credentials does not display during the enrollment process. The result is that the enrollment process cannot authenticate to the proxy server and there is no visible indication of this failure presented to the user.

**Workaround:** For [!INCLUDE[winblue_client_2](../Token/winblue_client_2_md.md)] devices that must enroll on a network that requires use of an authenticated proxy server, configure and save the credentials for the proxy server prior to enrollment of the device. To configure and save the credentials on a [!INCLUDE[winblue_client_2](../Token/winblue_client_2_md.md)] device:

1.  On the [!INCLUDE[winblue_client_2](../Token/winblue_client_2_md.md)] device, open **Internet Explorer**.

2.  When prompted for the proxy server credentials, enter the credentials and then select the option **Remember my credentials**.

3.  Enroll the device.

### Windows Phone 8.1 devices fail to enroll with Microsoft Intune when device authentication is enabled in AD FS
**Issue:** When you enroll a Windows Phone 8.1 device, enrollment fails if the optional setting for device authentication is enabled as part of global authentication policy in Active Directory Federated Services (AD FS).

**Workaround:** Disable device authentication on the AD FS server by unchecking **Enable device authentication** in **Edit Global Authentication Policy**. For more information, see [Configuring Authentication Policies](http://technet.microsoft.com/library/dn486781.aspx)

### Configuring the “Allow adult content in media store” setting may affect how device settings display
**Issue:** If a mobile device policy has the **Allow adult content in media store** setting configured, and is applied to an iOS 5 or iOS 6 device, the status of all settings for that device may display as **Conforms**.

**Workaround:** To see the correct status of the device settings, remove the **Allow adult content in media store** setting from the policy, and reapply.

### Microsoft Intune App Wrapping Tool for Android has no built-in uninstall capability
**Issue:** The **Microsoft App Wrapping Tool for Android** does not have built-in functionality for uninstalling the tool.

**Workaround:** Browse to the location where you installed the tool, and delete the directory. The default installation location is: **C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool**. For more information about the app wrapping tool, see [Prepare Android apps for mobile application management](http://technet.microsoft.com/library/mt147413.aspx).

## Language support in the Azure preview portal
The Azure preview portal is built on a new platform and supports the following languages - Chinese (Simplified), Chinese (Traditional), Czech, Dutch, English, German, Hungarian, Italian, Japanese, Portuguese (Brazil), Portuguese (Portugal), Russian, Spanish  
English, French, Korean, Polish, Swedish, Turkish.

The Intune Admin Console and the end user facing mobile experiences support Danish, Greek, Finish, Norwegian and Romanian
in addition to all the languages supported by the Azure preview portal.

## <a name="BKMK_WitRelnoteAlerts"></a>Alerts
The following are known issues with alerts in this release of [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].

### Remote assistance is not available on computers that run Windows 8 or Windows 8.1
**Issue:** In this release, the remote assistance feature is not available on computers that run Windows 8 or Windows 8.1.

**Workaround:** None.

### Alert notifications for recipients that are automatically added may not work
**Issue:** If a recipient is automatically added to an alert notification, they may not always receive a notification.

**Workaround:** To make sure that recipients will receive message notification, you should manually add recipients to alert notifications.

## See Also
[Technical reference for Microsoft Intune](../Topic/Technical_reference_for_Microsoft_Intune.md)

