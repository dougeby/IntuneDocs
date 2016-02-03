---
title: robstack - V2 of Get started with app deployment
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: c16a4fea-d3b9-4f97-b587-6123863dddf0
author: robstackmsft
---
# robstack - V2 of Get started with app deployment
Before you start deploying [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] apps, take some time to familiarize yourself with the concepts introduced in this topic. This will give you an overview of the deployment process, and act as a reference to which device types and app types are supported.

## App types you can deploy with Intune
You can deploy apps to all device types that are supported by [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]. Depending on the type of app you want to deploy, the process and supported devices will differ. Use the following table to help you understand what you can, and cannot deploy:

|Installer type|Details|
|------------------|-----------|
|**Windows Installer (&#42;.exe, &#42;.msi)**|-   Windows Installer files must support silent installation with no user input. Your app documentation should include the relevant command-line options to silently install the app (for example, **/q**).<br />-   Any additional files and folders that are required by the app’s setup program must be available from the location that you specify for the app setup files.<br />-   In most cases, Windows Installer (.msi) and Windows Installer Patch (.msp) files do not require any command-line arguments to be installed by Intune. Check your app documentation. If command-line arguments are required, they must be entered as Name=Value pairs (such as TRANSFORMS=custom_transform.mst).<br /><br />This type of app is uploaded to your cloud storage space.|
|**App Package for Android (&#42;.apk file)**|This type of app is uploaded to your cloud storage space.|
|**App Package for iOS (&#42;.ipa file)**|-   To deploy iOS apps, you must have a valid .ipa package.<br />-   The .ipa package must be signed by Apple, and the expiration date indicated in the provisioning profile must be valid. Intune can distribute enterprise certificate iOS applications. Not all Apple developer certificate apps are supported.<br />-   Your company must be registered for the iOS Developer Enterprise Program.<br />-   Make sure that your organization’s firewall allows access to the iOS provisioning and certification web sites.<br />-   A manifest  file (.plist) is not required to be deployed with the app.<br /><br />This type of app is uploaded to your cloud storage space. **Note:** Currently, end users cannot install corporate apps from the Intune Company Portal app for iOS. This is due to restrictions placed on apps that are published in the iOS App Store (see [App Store Review Guidelines](https://developer.apple.com/app-store/review/guidelines/)). Users can access corporate apps (including managed App Store apps and line-of-business app packages) by launching the Company Portal app on their device and tapping the Company Apps tile, which will open the browser and redirect them to the Intune Web Portal. For more information about the mobile management capabilities enabled by the Intune Company Portal app, see [Mobile device management capabilities in Microsoft Intune](../Topic/Mobile_device_management_capabilities_in_Microsoft_Intune.md).|
|**Windows Phone app package (&#42;.xap, .appx, .appxbundle)**|-   To deploy apps, you'll need an enterprise mobile code-signing certificate. For details, see [Set up Windows Phone management with Microsoft Intune](../Topic/Set_up_Windows_Phone_management_with_Microsoft_Intune.md).<br /><br />This type of app is uploaded to your cloud storage space.<br /><br />See below for information about installing line of business Universal Windows Platform (UWP) apps with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].|
|**Windows app package (.appx, .appxbundle)**|-   To deploy apps, you'll need an enterprise mobile code-signing certificate. For details, see [Set up Windows device management with Microsoft Intune](../Topic/Set_up_Windows_device_management_with_Microsoft_Intune.md).<br /><br />This type of app is uploaded to your cloud storage space.|
|**Windows Installer through MDM (&#42;.msi)**|This installer type lets you create and deploy Windows Installer-based apps to enrolled PCs that run Windows 10.<br /><br />The following considerations apply when you use this installer type:<br /><br />-   You can only upload a single file with the extension .msi.<br />-   The file's product code and product version are used for app detection.<br />-   The default restart behavior of the app will be used. [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] does not control this.<br />-   Per user MSI packages will be installed for a single user.<br />-   Per machine MSI packages will be installed for all users on the device.<br />-   Dual mode MSI packages currently only install for all users on the device.<br />-   App updates are supported when the MSI product code of each version is the same.<br /><br />This type of app is uploaded to your cloud storage space.|
|**External Link**|Used when you have a:<br /><br />-   **URL** that lets users download an app from an app store.<br />-   **Link** to a web-based app that runs from the web browser.<br /><br />Apps based on external links are not stored in your [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] cloud storage space.|
|**Managed iOS app from the app store**|Lets you manage and deploy iOS apps that are free of charge from the app store. Also lets you associate [mobile application management policies](https://technet.microsoft.com/library/dn878026.aspx) with [compatible apps](https://technet.microsoft.com/library/dn708489.aspx) and review their status in the administrator console.<br /><br />Managed iOS apps are not stored in your Intune cloud storage space.|
> [!TIP]
> Options for mobile devices are not available until you [set the Mobile Device Management Authority](https://technet.microsoft.com/library/mt346013.aspx) to [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].

## Support for Universal Windows Platform (UWP) apps
Windows 10 devices do not require a sideloading key to install line of business apps. However, the registry key **HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Appx\AllowAllTrustedApps** must have a value of to **1** to enable sideloading.

If this registry key is not configured, [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] will automatically set this value to **1** the first time you deploy an app to the device. If you have set this value to **0**, then [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] cannot automatically change the value, and the deployment of line of business apps will fail.

Universal Windows Platform line of business apps must be signed with a code-signing certificate that is trusted on each device to which the app is deployed. You can use certificates from an in-house PKI infrastructure, or a certificate from a third-party public root certificate installed on the device.

On Windows 10 Mobile devices, you can use a non-Symantec code signing certificate to sign universal **.appx** apps. For **.xap** apps, and also **.appx** packages built for Windows Phone 8.1 that you want to install on Windows 10 Mobile devices, you must use a Symantec code-signing certificate.

## More concepts

### Intune software publisher
The **Microsoft Intune Software Publisher** starts when you add or modify apps from the Microsoft Intune administrator console. From the publisher, you select and configure a software installer type that will either upload apps (programs for computers or apps for mobile devices) to be stored in [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] cloud storage, or link to an online store or web application.

#### Requirements
Before you begin to use the Microsoft Intune Software Publisher, you must install the full version of [Microsoft .NET Framework 4.0](https://www.microsoft.com/download/details.aspx?id=17851). After installation, you might have to restart your computer before the Software Publisher will open correctly.

### Cloud storage space
All apps that you deploy using the software installer installation type must be packaged and uploaded to Microsoft Intune cloud storage. A trial subscription of Intune includes 2 gigabytes (GB) of cloud-based storage that is used to store managed apps and updates. A paid subscription includes 20GB, with the option to purchase additional storage.

You can see how much space you are using and purchase more storage in the **Storage Use** node of the **Admin** workspace.

These rules apply to purchasing additional cloud-based storage for [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]:

-   You must have an active paid subscription in order to purchase additional storage.

-   Only billing administrators or global administrators for your Microsoft Online Service can purchase additional storage through the Intune account portal. To add, delete, or manage these administrators, you must be a global administrator and sign in to the Intune account portal.

-   If you are a volume licensing customer who has purchased Intune or the Microsoft Intune Add-on through the enterprise agreement, contact your Microsoft Account Manager or Microsoft Partner for pricing information and to purchase additional storage.

#### Requirements for cloud storage space

-   All files associated with an app must be in the same location and be accessible by [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].

-   The maximum file size for any file you upload is 2GB.

-   To upload files, you must have a minimum Internet speed of 768kbps.

### App deployment actions
When you deploy apps, you can choose from one of the following deployment actions:

-   **Required install** – The app is installed onto the device, with no end-user intervention required.

    > [!TIP]
    > For iOS devices that are not in supervised mode, and for all Android devices, the user must accept the app offer before it is installed.
    > 
    > You can no longer create new app deployments to iOS devices running an operating system earlier than iOS 7.1. Any existing app deployments to devices running an earlier operating system than iOS 7.1 will continue to work and be managed by [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].

-   **Available install** – The app is displayed in the company portal, and end-users can install it on-demand.

-   **Uninstall** – The app is uninstalled from the device.

-   **Not applicable** – The app is not displayed in the company portal, and is not installed to any devices.

#### <a name="BKMK_Actions"></a>Understand which deployment actions are available for each installer type

|Installer type|Required install|Available install|Uninstall|Not applicable|
|------------------|--------------------|---------------------|-------------|------------------|
|Windows app package (deployed to a user group)|Yes|Yes|Yes|Yes|
|Windows app package (deployed to a device group)|Yes|No|Yes|Yes|
|App package for mobile devices (deployed to a user group)|Yes|Yes|Yes|Yes|
|App package for mobile devices (deployed to a device group)|Yes|No|Yes|Yes|
|Windows Installer (deployed to a user group)|No|Yes|No|Yes|
|Windows Installer (deployed to a device group)|Yes|No|Yes|Yes|
|External link (deployed to a user group)|No|Yes|No|Yes|
|External link (deployed to a device group)|No|No|No|No|
|Managed iOS app from the app store (deployed to a user group)|Yes|Yes|Yes|Yes|
|Managed iOS app from the app store (deployed to a device group)|Yes|No|Yes|Yes|
> [!TIP]
> When you deploy apps, if you select both user and device groups, you can only deploy the app as an **Available install**.

### Deployment conflicts
When two deployments, with the same deployment action are received by a device, the following rules apply:

-   Deployments to a device group take precedence over deployments to a user group. However, if an app is deployed to a user group with a deployment action of **Available** and the same app is also deployed to a device group with a deployment action of **Not Applicable**, the app will be made available in the company portal for users to install.

-   The intent of the IT admin takes precedence over the user.

-   An install action takes precedence over an uninstall action.

-   If both a required install and an available install are received by a device, the actions are combined (the app is both required and available).

## See Also
[Deploy and configure apps with Microsoft Intune](../Topic/Deploy_and_configure_apps_with_Microsoft_Intune.md)

