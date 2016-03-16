---
title: Frequently asked questions about Intune | Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune 
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: a8126cca-9ec4-454b-a20b-dc1bb6797327
author: Nbigman
---
# Frequently asked questions about Intune
This article answers some frequently asked questions about Intune. If you don't see an answer to your question here, [let us know](https://microsoftintune.uservoice.com/).

## General issues

-   **How can I know when the Intune service has been updated?**

    Log on to your account at manage.microsoft.com. In Administration Overview, choose **View Service Status**. The location of your tenant and the maintenance schedule are listed there. Read about the service updates in the [What's new](../Topic/GetStarted/What-s-new-in-Microsoft-Intune.md) article.

-   **If a user renames a device within the Company Portal app will that name change in Intune or Configuration Manager?**

    No, that name change is only for the user’s convenience.

-   **Is there a remote assistance functionality in Intune for mobile devices?**

    No there isn’t. Third party apps such as [Lumia Beamer](https://www.lumiabeamer.com/), [Bomgar](http://www.bomgar.com/), and [TeamViewer](https://www.teamviewer.com/) could be helpful.

## Accounts

-   **If I start evaluating Intune and create a new tenant for the trial, can I add Office 365 to the evaluation using the same tenant?**

    Yes. Just sign in using a global admin from your existing Intune tenant/subscription, such as *globaladmin@&lt;company&gt;.onmicrosoft.com*.

-   **If I assign MDM authority to Intune during a trial subscription, does that make it difficult to switch to another company’s service if I change my mind about Intune?**

    Though it’s difficult to imagine you not sticking with Intune, the MDM authority choice does not affect your ability to move to another service. It’s specifically about choosing Intune or Intune with System Center Configuration Manager.

-   **Can I use my existing Office 365 domain name for my subsequent Intune account?**

    Yes, if you sign in with the organizational ID that is associated with your existing Office 365 tenant and verified domain when you either create your Intune trial or activate your licenses.

    Intune will then use the same domain/users/etc. as in your Office 365 account. Note that each Office 365 user would have to be enabled as an Intune user, using an Intune license. This would have to be done by the global administrator who manages the tenant.

## Enrollment

-   **Where can my users learn how to enroll their devices?**

    You can use or customize information from the  [End-user Intune enrollment instructions for IT administrators](https://gallery.technet.microsoft.com/End-user-Intune-enrollment-55dfd64a).

-   **How can I troubleshoot device enrollment?**

    Ways to troubleshoot common enrollment issues are  provided in [Troubleshoot device enrollment in Intune](../Topic/Troubleshoot/Troubleshoot-device-enrollment-in-Intune.md).

-   **How can I collect enrollment logs if a user has an enrollment problem?**

    Follow [these instructions](http://www.microsoft.com/en-us/download/46391).

## Mobile device management

-   **General MDM**

    -   **Can Intune detect whether a device is jailbroken?**

        Yes, for some operating systems. For information on how to manage jailbroken devices, see[Manage device compliance policies](../Topic/DeployUse/Manage-device-compliance-policies-for-Microsoft-Intune.md).

    -   **Can I selectively wipe corporate data from a device?**

        Yes. For information about selective wipe see [Help protect your data with remote wipe, remote lock, or passcode reset](../Topic/DeployUse/Help-protect-your-data-with-remote-wipe,-remote-lock,-or-passcode-reset-using-Microsoft-Intune.md).

    -   **Is there a way to block certain websites on the mobile device browser through Intune?**

        Not on the native browser of any platform. However, you can allow or block URLs when you have deployed the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] managed web browser on iOS and Android devices. For more information see [Manage Internet access using managed browser policies](../Topic/DeployUse/Manage-Internet-access-using-managed-browser-policies-with-Microsoft-Intune.md) .

    -   **Can we restrict a user from uninstalling an app?**

        Generally, no. However, on a supervised iOS device you can prevent a user from uninstalling an app that was distributed using the Apple Configurator. For information about using supervised mode in Intune, see [Manage access to apps using configuration policies - deleted](../Topic/DeployUse/Manage-access-to-apps-using-Microsoft-Intune-configuration-policies---deleted.md).

    -   **Is there a way to manage mobile data usage?**

        Not directly, but you can ensure that Wi-Fi is the preferred method for connecting by pushing Wi-Fi profiles to the devices, as described in [Help users connect to company networks using Wi-Fi profiles](../Topic/DeployUse/Help-users-connect-to-company-networks-using-Wi-Fi-profiles-with-Microsoft-Intune.md). Also, some platforms (for example,  iOS and Android KNOX) enable the ability to control settings such as voice and data roaming.

    -   **Is there a way to prevent a user from unenrolling a device? What if it’s a company-owned device?**

        In general, no. However, using custom Windows Phone settings, you can prevent user unenrollment on Windows Phone 8.1. Also, for iOS devices that are supervised and enrolled in Apple’s Device Enrollment Program (DEP), it is possible to prevent a user from unenrolling a device.

    -   **Can I switch my chosen MDM authority?**

        You can switch MDM authority in some situations. To do so, contact Support, as described in [How to get support for Microsoft Intune](../Topic/Troubleshoot/How-to-get-support-for-Microsoft-Intune.md). The table below describes what changes are possible. Changes in MDM authority require re-enrollment of devices.

        |||||
        |-|-|-|-|
        !**To:** Intune!**To:** O365!**To:** Configuration Manager with Intune
        |**From:** Intune|No|Yes&#42;|Yes|
        |**From:** O365|Yes&#42;|No|Yes|
        |**From:** Configuration Manager with Intune|Yes|Yes|No|
        &#42;O365 and Intune MDM authorities can coexist, so you won't have to re-enroll mobile devices.



-   **Windows**

    -   **Can I sideload a Windows Store app?**

        Publically available apps cannot be sideloaded. Even though you are able to download the XAP, you cannot upload it to Intune because it is a public XAP, encrypted and signed with the developer's code-signing certificate. Only apps you develop and sign with your own code-signing certificate can be sideloaded.

    -   **Do Windows Phone Store apps distributed through the Company Portal require that the end user have a Microsoft Account?**

        Yes, the end user will not be able to obtain the apps without a Microsoft Account. The exception is sideloaded, private LOB apps, which can be deployed to a device without a Microsoft Account.

    -   **Is a Microsoft Account needed on a Windows Phone 8.1 in order for it to be managed by Intune?**

        No. However, it will be needed to install most apps from the public store.

        **Why does Windows Phone require a Symantec certificate for management?**
        Windows Phone controls how you can install apps. Any user with a Microsoft account can install apps from the Windows Phone store, or companies can install or sideload their internally developed line of business (LOB) apps using a special process described in the Windows Phone documentation. When installing LOB apps, Windows Phones trust only one special type of certificate issued by Symantec. You cannot use any other commercially or privately generated certificate. This requirement is true for all mobile device management solutions, not just Intune.

        The Symantec certificate creates an application enrollment token (AET). The AET can be installed on a device when the device enrolls for mobile device management, or it can be installed out-of-band from a secure website or from an email attachment. Administrators must sign every LOB app with the Symantec certificate, using the tools provided in the [Windows Phone SDK](http://go.microsoft.com/fwlink/?LinkId=268439). When users attempt to install LOB apps, the Windows Phone operating system checks the signature in the AET against the signature on the app. If the signatures match, the installation is allowed to proceed. If the AET cannot be verified, installation fails. There are several reasons the AET might not be verified:

        -   The AET was never installed on the device

        -   The AET has expired

        -   The AET was not created using the same Symantec certificate used to sign the app

        Windows Phone does not require that the AET be present during MDM enrollment, but prior to the November 2014 release, Intune required the AET and a signed ssp.xap because there was no other way to install the AET and ssp.xap except during enrollment.

    **How is the AET created for Intune users?**
        When administrators upload the .pfx file for their Symantec certificate, Intune automatically creates the AET and deploys it to enrolled Windows Phones. It is not necessary for Intune admins to use the AET Generator tool in the Windows Phone SDK.

        > [!IMPORTANT]
        > Intune does not support manually creating the AET and deploying it out-of-band.

        **What changes happened to reduce the requirement for a Symantec certificate?**
        For the November 2014 release, Intune made changes to allow for scenarios where companies do not have a Symantec certificate.

        -   The Company Portal for Windows Phone 8.1 is available to install from the store, so it needn’t be signed with a Symantec certificate and validated against an AET. Instead, the app is validated as part of the store publishing process.

        -   Windows Phone 8.1 devices can enroll with or without an AET on the phone. If an AET is available, it will be installed the first time the device synchronizes with Intune. If there is no AET, the device can still be managed by Intune, and users can install the Company Portal from the store and use most features of the Company Portal without a Symantec certificate to sign apps.

        There are no changes to the Symantec requirement for Windows Phone 8 devices. Windows Phone 8 devices must have the signed ssp.xap and the AET present during enrollment or they will be blocked from enrolling.

        **What functionality is supported if a Windows Phone 8.1 device is enrolled but there is no Symantec certificate?**
        If a Windows Phone 8.1 device is enrolled but there’s no Symantec certificate, you can:

        -   Create policies and push them to the device

        -   Configure contact information for the IT department that will shows in the Company Portal

        -   Create deep links to the store and deploy them to the Company Portal

        -   Create links to web pages and deploy them to the Company Portal

        -   Create terms and conditions that must be accepted by users before they can use the Company Portal

        The one thing you cannot do without a Symantec certificate is deploy LOB apps.

        > [!IMPORTANT]
        > The Intune Software Publisher does not verify that apps are signed when you upload them. If you deploy unsigned apps, they will fail when users try to install them.

        **What can users do if they have the Company Portal but there is no Symantec certificate?**
        Windows Phone 8.1 devices don’t have to be enrolled before users install the Company Portal from the store. If the device is not enrolled, users are prompted to enroll. Touching the prompt in the Company Portal takes users directly to **Settings / Workplace** where they can enroll their devices.

        Even without enrolling the device, uses can perform the following actions with the Company Portal installed from the store:

        -   Accept or decline any terms and conditions configured by the admin. If users decline the terms and conditions, the Company Portal closes.

        -   View the contact information for the IT department

        -   View any enrolled devices including iOS, Android, and Windows devices

        -   Use deep links to apps in the store

        -   Use web links to open web pages

        With the device enrolled, users can view the device in the **My Devices** list. Once enrolled, the device is subject to any deployed Intune policies. Devices must be enrolled to get the AET and install LOB apps. An unenrolled device trying to install an LOB app will be directed to enroll.

        The only thing users cannot do if the company does not have a Symantec certificate is install LOB apps deployed by the admin.

        **Our company already has a certificate and has been enrolling Windows Phone 8.1 devices. Do I have to do anything different now that the Company Portal is available in the store?**
        The current ssp.xap from the Download Center still works on Windows Phone 8.1 devices. You can continue to direct users to enroll and get the company portal during installation.

        **What are the advantages and disadvantages of users getting the Company Portal from the store?**
        Advantages:

        -   Users get deep links and web links, even if the Windows Phone 8.1 device isn’t enrolled

        -   When Microsoft updates the Company Portal, the store app updates automatically without your downloading, signing, and redeploying the ssp.xap

        -   Documentation for Windows Phone 8.1, iOS, Android, and Windows users is consistent: “Go to the store and install the Company Portal.”

        -   Users see the app as it installs and get enrollment instructions when it opens

        Disadvantages:

        -   Users see a checkbox to install a “**company hub**” but nothing directs them to the Company Portal in the device’s app list

        -   Users aren’t required to accept custom terms and conditions until they open the Company Portal

        In the following circumstances, you can continue directing users to enroll and have the ssp.xap installed during enrollment:

        -   If the company blocks access to the store from Windows Phones, users must get the ssp.xap installed during enrollment.

        -   If users do not have Microsoft accounts configured on their Windows Phones, they will not be able to install the Company Portal from the store.

        -   If the existing documentation for Windows Phone enrollment tells them to go to Settings, Workplace first, it may take a while to update the docs and direct users to the store.

        **What’s the difference between the ssp.xap on the Download Center and the app in the store?**

        -   The Company Portal in the store does not have to be signed by a Symantec certificate to be installed

        -   The Company Portal in the store presents the terms and conditions to the user but the ssp.xap on the Download Center doesn’t

        -   The Company Portal in the store is an .appx instead of a .xap

        **Can I get the Company Portal file and push it to my users instead of sending them to the store?**
        Yes. The Company Portal app can be downloaded for the following operating systems from the Download Center:

        -   Windows Phone 8.1: [http://go.microsoft.com/fwlink/?LinkId=615799](http://go.microsoft.com/fwlink/?LinkId=615799)

        -   Windows Phone 8.0 : [http://go.microsoft.com/fwlink/?LinkId=268440](http://go.microsoft.com/fwlink/?LinkId=268440)

        -   Windows 8.1: [http://go.microsoft.com/fwlink/?LinkId=615800](http://go.microsoft.com/fwlink/?LinkId=615800)

        **Can companies still use the Support Tool for Windows Intune Trial Management of Windows Phone if they don’t have a Symantec certificate, and still have users install the Company Portal from the store?**
        Yes. If you need to do a proof of concept that includes installation of LOB apps, the trial management tool works with the store version of the company portal. Because the AET from the Symantec certificate is no longer required to enroll Windows Phone 8.1 devices, however, companies can test app installation using deep links to apps in the store.

        The Support Tool for Windows Intune Trial Management of Windows Phone is only for trial subscriptions of Intune.

        > [!IMPORTANT]
        > Only use the trial management tool testing. Devices enrolled with the AET from the trial management tool must unenroll and reenroll if the Symantec certificate for the trial management tool is no longer available, or if the company obtains its own Symantec certificate for signing apps.

        **Can companies start without any Symantec certificate and then add one later, even after Windows Phone 8.1 devices have enrolled?**
        Yes. Even if Windows Phone 8.1 devices have already enrolled, you can get a Symantec certificate, sign the ssp.xap, and upload it and the pfx file. Intune will then generate the AET. Windows Phone 8.1 devices will get the AET the next time they sync, up to eight hours. Allow at least eight hours before deploying line of business apps after uploading the xap and pfx.


-   **Android**

    -   **How long does it take to encrypt an Android device?**

        This depends primarily on the speed of the device’s processor and the amount of total and used memory, and is not a function of Intune.

-   **iOS**

    -   **When deploying iOS apps with Intune, if the application’s IPA and Manifest file have been uploaded; does the device need an AppleID specified to continue installing?**

        No. When Intune is providing the bits (IPA uploaded to Intune), the applications are sideloaded and don’t require an Apple ID.

    -   **Is there a way to enable the installation of apps on iOS without allowing access to the Apple Store?**

        No, but you can enable the App Store and use allowed and blocked apps on iOS to keep an eye on what users are doing. Sideloaded LOB apps don’t require access to the Apple App Store.

    -   **Do Apple Store apps distributed through the Company Portal require that the end user have an iTunes account?**

        Yes, the end user will not be able to obtain the apps without an iTunes account.

    -   **Can I block the App Store?**

        Yes you can, but this will block all app installs and updates from the App Store, not just ones initiated by the end user. This means any public app store apps that you deploy from Intune would also fail.

## App deployment

-   **How can I add a recommended app?**

    In Intune these are called "featured apps" and are documented in [Deploy apps to mobile devices in Microsoft Intune - deleted](../Topic/DeployUse/Deploy-apps-to-mobile-devices-in-Microsoft-Intune.md).

-   **Can I get additional cloud storage for apps I want to deploy?**

    Yes. You can read about this in [Plan for app deployment](../Topic/PlanDesign/Plan-for-app-deployment-in-Microsoft-Intune.md), in the section *Cloud storage requirements*.

## Security

-   **Can BitLocker be enforced by Intune?**

    The OMA-DM agent in Windows 8.1/RT allows you to read (get) the encryption status. You cannot set it. This is true for Intune and for other mobile device management services.

-   **If I encrypt a Windows 8 tablet using BitLocker, may I enforce full device wipe if a user consecutively fails logon several times?**

    There is no option for full wipe on Windows 8.1/RT devices for any mobile device management service, including Intune. Intune provides selective wipe for those devices. For more information on wipe/selective wipe in Intune, see [Help protect your data with remote wipe, remote lock, or passcode reset](../Topic/DeployUse/Help-protect-your-data-with-remote-wipe,-remote-lock,-or-passcode-reset-using-Microsoft-Intune.md).

## Company Portal

-   **Can I customize my Company Portal?**

    Yes. In the Intune admin console, go to **Admin&gt;Company Portal** for those settings.

## Microsoft Intune with Configuration Manager

-   **When I use Configuration Manager with Intune, where do I manage my devices?**

    Manage all of your devices from the Configuration Manager console, even though devices with the Intune agent installed on them will appear in the Intune console. Mobile devices will not appear in the Intune console.

-   **Can I do a selective wipe on devices?**

    If you are using System Center 2012 R2 Configuration Manager or later with Intune, you can do a selective wipe that removes company data. For more information see [Help protect your data with remote wipe, remote lock, or passcode reset](../Topic/DeployUse/Help-protect-your-data-with-remote-wipe,-remote-lock,-or-passcode-reset-using-Microsoft-Intune.md).

-   **If I’m using Configuration Manager with Intune, can I still use the Intune Admin Portal?**

    You can, but only PCs with the Intune agent installed on them will be manageable from that portal. There is also some other useful information in the portal regarding alerts about the service, service status, etc. but any device management settings there won’t apply to enrolled devices.

### See also
[Documentation for Microsoft Intune](../Topic/documentation-for-microsoft-intune.md)
