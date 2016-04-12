---
title: Overview of device and app lifecycles|Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid:
author: robstack
---
# Overview of device and app lifecycles

Although the needs of individual organization might differ, there are certain common steps that all organizations will need to take on an ongoing basis, whatever their other operational needs. These can be grouped into two main categories, termed as **lifecycles**.:

1. **The device management lifecyle** - For management purposes, all devices have a lifecycle, from initially enrolling the device, through to retiring it when it is no longer required.
2. **The app lifecycle** - Similarly, apps you work with have their own lifecycle which works *within* the device management lifecycle, from adding an app to Intune, all the way through to uninstalling it when it is no longer required.

This diagram is a high-level view of how the MDM and app lifecyles work together to satisfy enterprise mobility requirements. The individual steps are covered in detail below.

![The MDM and app lifecycle](./media/mdmapplifecycle_v8.gif "mobile device and app lifecycle")

Microsoft Intune has a range of capabilities that help you manage these lifecycles through each stage. Read the following sections to find more information about these capabilities, and how you can use them.


## The Mobile device management (MDM) lifecycle

### Enroll

Today's mobile device management (MDM) strategies deal with variety of phones, tablets, and PCs (iOS, Android, Windows, Mac OS X). Whether users are bringing their own devices (BYOD) into management to get company mail and data or you're distributing company-owned devices (COD), the first step is to [set up device enrollment](enroll-devices-in-microsoft-intune.md). You can also manage Windows PCs either by enrolling them with Intune (MDM) or by [installing the Intune client software](manage-windows-pcs-with-microsoft-intune.md).

### Configure

Getting your devices managed is just the first step. To take advantage of all that Intune offers and to ensure your devices are secure and compliant with company standards, you can choose from a wide range of **policies** which let you configure almost every aspect of how managed devices operate.
For example, should users have passwords on devices that have company data? You can require one. Are there apps you don't want them to use? You can block them. Try these polices out before you enroll your test clients, and then keep tweaking and tuning as you roll out to all your users.
- [**Configuration policies**](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) - These policies let you configure how the features and capabilities of device you manage work. For example, you could require the use of a password on Windows Phone's, or disable the use of the camera on iPhones.
- [**Company resource access policies**](enable-access-to-company-resources-with-microsoft-intune.md) - To let your users access their work on their personal device can present you with challenges. For example, how do you ensure that all devices that need to access company email are configured correctly? How can you ensure that users can access the company network with a VPN connection without having to know the often complex settings required? Intune can help to reduce this burden by automatically configuring devices you manage to access common company resources.
- [**Windows PC management policies (with the Intune client software)**](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md) - While enrolling Windows PCs with Intune gives you the most device management capabilities, Intune continues to support managing Windows PCs with the Intune client software. If you need information about some of the tasks you can perform with PCs, start here.


### Protect

In the modern IT world, protecting devices from unauthorized access is one of the most important tasks you'll perform. In addition to the items in the **Configure** step of the device lifecycle, Intune provides further capabilities that help protect devices that you manage from unauthorized access, or malicious attacks:

- [**Multi-factor authentication**](protect-windows-devices-with-multi-factor-authentication.md) - Adding an extra layer of authentication to user logons can help make devices even more secure. Windows, Windows Phone, and Windows Mobile devices offer multi-factor authentication which requires a second level of authentication such as a phone call or text message before users can gain access.
- [**Microsoft Passport settings**](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md) - Microsoft Passport is an alternative sign-on method that lets users use a *gesture*, such as a fingerprint, or Windows Hello to sign on without needing a password.
- [**Policies to protect Windows PCs (with the Intune client software)**](policies-to-protect-windows-pcs-in-microsoft-intune.md) - When you manage Windows PCs using the Intune client software, policies are available that let you control settings for Endpoint Protection, software updates, and Windows Firewall on PCs you manage.

### Retire

When device get lost or stolen, need to be replaced, or when users move to another position, it's usually time to [retire or wipe](help-protect-your-data-with-remote-wipe-remote-lock-or-passcode-reset-using-microsoft-intune.md) the device. There are a number of ways you can do this ranging from resetting the device, removing it from management, or wiping the corporate data on it.

## The App lifecycle

### Add

The first step in app deployment is to add the apps you want to manage and deploy into Intune. While there are many different app types you can work with, the basic procedures are the same. Intune lets you add apps for both [devices you've enrolled](add-apps-for-mobile-devices-in-microsoft-intune.md), and [Windows PCs you manage with the Intune client software](create-apps-for-windows-pcs-in-microsoft-intune.md). 

### Deploy

Once you've added the app to Intune, you can then [deploy it to devices that you manage](deploy-apps-in-microsoft-intune.md). Intune makes this process easy, and once the app is deployed, you can [monitor the success](monitor-apps-in-microsoft-intune.md) of the deployment from the Intune administration console.
Additionally, some app stores, like [Apple](manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune.md) and [Windows](manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune.md) allow you to purchase app licenses in bulk for your company. Intune can synchronize data with these stores to let you deploy and track license usage for these types of app right from the Intune administration console.

### Configure

As part of the app lifecycle, new versions of apps are regularly released. Intune provides tools to easily [update apps](update-apps-using-microsoft-intune.md) you have deployed to a newer version.
Additionally, some apps let you configure extra functionality, for example:
- [iOS app configuration policies](configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune.md) let you supply settings for compatible iOS apps that are used when the app is run. For example, an app might require specific branding settings, or the name of a server to connect to.
- [Managed browser policies](manage-internet-access-using-managed-browser-policies.md) help you to configure settings for the Intune managed browser, an app that replaces the default device browser and lets you restrict the websites that your users can visit.

### Protect

Intune gives you many ways to help protect the data in your apps. The main methods are:
- [**Conditional access**](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) lets you control access to email and other services based on conditions you specify like device types, or compliance with a [device compliance policy](introduction-to-device-compliance-policies-in-microsoft-intune.md) you deployed.
- [**Mobile application management (MAM)**](introduction-to-mobile-app-management-policies-with-microsoft-intune.md) works with individual apps to help protect the company data they use. For example, you can restrict copying data between unmanaged apps and apps you manage, or you can prevent apps from running on devices that have been jailbroken or rooted.

### Retire

Eventually, it's likely that apps you deployed become outdated, and need to be removed. Intune makes it easy to [retire apps from service](retire-apps-using-microsoft-intune.md).