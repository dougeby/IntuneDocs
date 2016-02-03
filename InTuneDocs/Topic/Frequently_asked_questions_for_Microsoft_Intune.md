---
title: Frequently asked questions for Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: a8126cca-9ec4-454b-a20b-dc1bb6797327
author: Nbigman
---
# Frequently asked questions for Microsoft Intune
This topic provides answers to frequently asked questions about Microsoft Intune. If you have suggestions for other questions you'd like to see answered, [let us know](https://microsoftintune.uservoice.com/).

## About this FAQ
This FAQ is divided into the following categories:

-   [General](#BKMK_General)

-   [Accounts](#BKMK_Accounts)

-   [Enrollment](#BKMK_Enrollment)

-   [Mobile Device Management](#BKMK_MDM)

-   [App Deployment](#BKMK_App_Deploy)

-   [Security](#BKMK_Security)

-   [Company portal](#BKMK_Company_Portal)

-   [Microsoft Intune with Configuration Manager](#BKMK_hybrid)

### <a name="BKMK_General"></a>General

-   **How can I know when the Microsoft Intune service has been updated?**

    Log on to your account at manage.microsoft.com. In Administration Overview select View Service Status. The location of your tenant and the maintenance schedule are listed there. For details of the service updates see [What's new in Microsoft Intune](../Topic/What_s_new_in_Microsoft_Intune.md).

-   **If a user renames a device within the Company Portal app will that name change in Intune or Configuration Manager?**

    No, that name change is only for the user’s convenience.

-   **Is there a remote assistance functionality in Intune for mobile devices?**

    No there isn’t. Third party apps such as [Lumia Beamer](https://www.lumiabeamer.com/) , [Bomgar](http://www.bomgar.com/) , and [TeamViewer](https://www.teamviewer.com/) could be helpful.

### <a name="BKMK_Accounts"></a>Accounts

-   **If I start evaluating Intune and create a new tenant for the trial, can I add O365 to the evaluation using the same tenant?**

    Yes. Just sign in using a global admin from your existing Intune tenant/subscription, such as *globaladmin@&lt;company&gt;.onmicrosoft.com*.

-   **If I assign MDM authority to Intune during a trial subscription, does that make it difficult to switch to another company’s service if I change my mind about Intune?**

    Though it’s difficult to imagine you not sticking with Intune, the MDM authority choice does not affect your ability to move to another service. It’s specifically about choosing Intune or Intune with System Center Configuration Manager, of O365 MDM.

-   **Can I use my existing Office 365 domain name for my subsequent Intune account?**

    Yes, if you sign in with the organizational ID which is associated with your existing O365 tenant and verified domain when your either create their Intune trial or activate your licenses. Intune will then use the same domain/users/etc. as in your O365 account. Note that each O365 user would have to be enabled as an Intune user, using an Intune license. This would have to be done by the global administrator who manages the tenant.

### <a name="BKMK_Enrollment"></a>Enrollment

-   **Where can my  users learn how to enroll their devices?**

    You can use or customize information from the  [Microsoft Intune Enrollment Instructions](http://www.microsoft.com/en-us/download/46398).

-   **How can I troubleshoot device enrollment?**

    Ways to troubleshoot common enrollment issues are  provided in [Troubleshoot device enrollment in Intune](../Topic/Troubleshoot_device_enrollment_in_Intune.md).

-   **How can I collect enrollment logs if a user has an enrollment problem?**

    Follow [these instructions](http://www.microsoft.com/en-us/download/46391).

### <a name="BKMK_MDM"></a>Mobile Device Management

-   **General MDM**

    -   **Can Intune detect whether a device is jailbroken?**

        Yes, for some operating systems. For information on how to manage jailbroken devices, see[Manage device compliance policies for Microsoft Intune](../Topic/Manage_device_compliance_policies_for_Microsoft_Intune.md).

    -   **Can I selectively wipe corporate data from a device?**

        Yes. For information about selective wipe see [Help protect your data with remote wipe, remote lock, or passcode reset using Microsoft Intune](../Topic/Help_protect_your_data_with_remote_wipe,_remote_lock,_or_passcode_reset_using_Microsoft_Intune.md).

    -   **Is there a way to block certain websites on the mobile device browser through Intune?**

        Not on the native browser of any platform. However, you can allow or block URL's when you have deployed the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] managed web browser on iOS and Android devices. For more information see [Manage Internet access using managed browser policies with Microsoft Intune](../Topic/Manage_Internet_access_using_managed_browser_policies_with_Microsoft_Intune.md) .

    -   **Can we restrict a user from uninstalling an app?**

        Generally, no. However, on a supervised iOS device you can prevent a user from uninstalling an app that was distributed using the Apple Configurator. For information about using supervised mode   in Microsoft Intune, see [Manage access to apps using Microsoft Intune configuration policies - deleted](../Topic/Manage_access_to_apps_using_Microsoft_Intune_configuration_policies_-_deleted.md).

    -   **Is there a way to manage mobile data usage?**

        Not directly, but you can ensure that Wi-Fi is the preferred method for connecting by pushing Wi-Fi profiles to the devices, as described in [Help users connect to company networks using Wi-Fi profiles with Microsoft Intune](../Topic/Help_users_connect_to_company_networks_using_Wi-Fi_profiles_with_Microsoft_Intune.md). Also, some platforms (for example,  iOS and Android KNOX) enable the ability to control settings such as voice and data roaming.

    -   **Is there a way to prevent a user from unenrolling a device? What if it’s a company-owned device?**

        In general, no. However, using custom Windows Phone settings, you can enforce this on Windows Phone 8.1. Also, for iOS devices that are supervised and enrolled in Apple’s Device Enrollment Program (DEP), it is possible to prevent a user from unenrolling a device.

    -   **Can I switch my chosen MDM authority?**

        You can switch MDM authority in some situations. To do so, contact Support, as described in [How to get support for Microsoft Intune](../Topic/How_to_get_support_for_Microsoft_Intune.md). The table below describes what changes are possible. Changes in MDM authority require re-enrollment of devices.

        |||||
        |-|-|-|-|
        ||**To:** Intune|**To:** O365|**To:** Configuration Manager with Intune|
        |**From:** Intune||Yes&#42;|Yes|
        |**From:** O365|Yes&#42;||Yes|
        |**From:** Configuration Manager with Intune|Yes|Yes||
        &#42;O365 and Intune MDM authorities can coexist, so you won't have to re-enroll mobile devices.

-   **Windows**

    -   **Can I sideload a Windows Store app?**

        Publically available apps cannot be sideloaded. Even though you are able to download the XAP, you cannot upload it to Intune because it is a public XAP, encrypted and signed with the developer's code-signing certificate. Only apps you develop and sign with your own code-signing certificate can be sideloaded.

    -   **Do Windows Phone Store apps distributed through the Company Portal require that the end user have a Microsoft Account?**

        Yes, the end user will not be able to obtain the apps without a Microsoft Account. The exception is sideloaded, private LOB apps, which can be deployed to a device without a Microsoft Account.

    -   **Is a Microsoft Account needed on a Windows Phone 8.1 in order for it to be managed by Intune?**

        No. However, it will be needed to install most apps from the public store.

-   **Android**

    -   **How long does it take to encrypt an Android device?**

        This depends primarily on the speed of the device’s processor and the amount of total and used memory, and is not a function of Intune.

-   **iOS**

    -   **When deploying iOS apps with Intune, if the application’s IPA and Manifest file have been uploaded; does the device need an AppleID specified to continue installing?**

        No. When Intune is providing the bits (IPA uploaded to Intune), the applications are sideloaded and don’t require an Apple ID.

    -   **Is there a way to enable the installation of apps on iOS without allowing access to the Apple Store?**

        No, but you can enable the App Store and use allowed and blocked apps on iOS to keep an eye on what users are doing. Sideloaded LOB apps don’t require access to the Apple App Store.

    -   **Do Apple Store apps distributed through the Company Portal require that the end user have an iTunes account?**

        Yes, the end user will not be able to obtain the apps without an Itunes account.

    -   **Can I block the App Store?**

        Yes you can, but this will block all app installs and updates from the App Store, not just ones initiated by the end user. This means any public app store apps that you deploy from Intune  would also fail.

### <a name="BKMK_App_Deploy"></a>App Deployment

-   **How can I add a recommended app?**

    In Intune these are called "featured apps" and are documented in [Deploy apps to mobile devices in Microsoft Intune - deleted](../Topic/Deploy_apps_to_mobile_devices_in_Microsoft_Intune_-_deleted.md).

-   **Can I get additional cloud storage for apps I want to deploy?**

    Yes. You can read about this in [Plan for app deployment in Microsoft Intune](../Topic/Plan_for_app_deployment_in_Microsoft_Intune.md), in the section *Cloud storage requirements*.

### <a name="BKMK_Security"></a>Security

-   **Can BitLocker be enforced by Intune?**

    The OMA-DM agent in Windows 8.1/RT allows you to read (get) the encryption status. You cannot set it. This is true for Microsoft Intune and for other mobile device management services.

-   **If I encrypt a Windows 8 tablet using BitLocker, may I enforce full device wipe if a user consecutively fails logon several times?**

    There is no option for full wipe on Windows 8.1/RT devices for any mobile device management service, including Intune. Intune provides selective wipe for those devices. For more information on wipe/selective wipe in Intune, see [Help protect your data with remote wipe, remote lock, or passcode reset using Microsoft Intune](../Topic/Help_protect_your_data_with_remote_wipe,_remote_lock,_or_passcode_reset_using_Microsoft_Intune.md).

### <a name="BKMK_Company_Portal"></a>Company portal

-   **Can I customize my Company Portal?**

    Yes. In the Intune admin console, go to **Admin&gt;Company Portal** for those settings

### <a name="BKMK_hybrid"></a>Microsoft Intune with Configuration Manager

-   **When I use Configuration Manager with Intune, where do I manage my devices?**

    Manage all of your devices from the Configuration Manager console, even though devices with the Intune agent installed on them will appear in the Intune console. Mobile devices will not appear in the Intune console.

-   **Can I do a selective wipe on devices?**

    If you are using System Center 2012 R2 Configuration Manager or later with Intune, you can do a selective wipe that removes company data. For more information see [Help protect your data with remote wipe, remote lock, or passcode reset using Microsoft Intune](../Topic/Help_protect_your_data_with_remote_wipe,_remote_lock,_or_passcode_reset_using_Microsoft_Intune.md).

-   **If I’m using Configuration Manager together with Intune, can I still use the Intune Admin Portal?**

    You can, but only PCs with the Intune agent installed will be manageable from that portal. There is also some other useful information in the portal regarding alerts about the service, service status, etc. but any device management settings there won’t apply to enrolled devices.

## See Also
[Technical reference for Microsoft Intune](../Topic/Technical_reference_for_Microsoft_Intune.md)

