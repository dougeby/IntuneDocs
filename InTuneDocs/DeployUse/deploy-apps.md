---
# required metadata

title: Deploy apps | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: ad5ea85c-aa2e-4110-a184-172cd0b8f270

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Deploy apps with Microsoft Intune

This topic explains some of the concepts you'll need to understand before you start deploying apps with Microsoft Intune.

## The Intune software publisher
The **Microsoft Intune Software Publisher** starts when you add or modify apps from the Microsoft Intune administrator console. From the publisher, you select and configure a software installer type that will either upload apps (programs for computers or apps for mobile devices) to be stored in Intune cloud storage, or link to an online store or web application.

### Requirements
Before you begin to use the Microsoft Intune Software Publisher, you must install the full version of [Microsoft .NET Framework 4.0](https://www.microsoft.com/download/details.aspx?id=17851). After installation, you might have to restart your computer before the Software Publisher will open correctly.

## Cloud storage space
All apps that you deploy using the software installer installation type must be packaged and uploaded to Microsoft Intune cloud storage. A trial subscription of Intune includes 2 gigabytes (GB) of cloud-based storage that is used to store managed apps and updates. A paid subscription includes 20GB, with the option to purchase additional storage.

You can see how much space you are using and purchase more storage in the **Storage Use** node of the **Admin** workspace.

These rules apply to purchasing additional cloud-based storage for Intune:

-   You must have an active paid subscription in order to purchase additional storage.

-   Only billing administrators or global administrators for your Microsoft Online Service can purchase additional storage through the Intune account portal. To add, delete, or manage these administrators, you must be a global administrator and sign in to the Intune account portal.

-   If you are a volume licensing customer who has purchased Intune or the Microsoft Intune Add-on through the enterprise agreement, contact your Microsoft Account Manager or Microsoft Partner for pricing information and to purchase additional storage.

#### Requirements for cloud storage space

-   All files associated with an app must be in the same location and be accessible by Intune.

-   The maximum file size for any file you upload is 2GB.

-   To upload files, you must have a minimum Internet speed of 768kbps.

## App deployment actions
When you deploy apps, you can choose from one of the following deployment actions:

-   **Required install** – The app is installed onto the device, with no end-user intervention required.

    > [!TIP]
    > For iOS devices that are not in supervised mode, and for all Android devices, the user must accept the app offer before it is installed.
    >
    > You can no longer create new app deployments to iOS devices running an operating system earlier than iOS 7.1. Any existing app deployments to devices running an earlier operating system than iOS 7.1 will continue to work and be managed by Intune.

-   **Available install** – The app is displayed in the company portal, and end-users can install it on-demand.

-   **Uninstall** – The app is uninstalled from the device.

-   **Not applicable** – The app is not displayed in the company portal, and is not installed to any devices.

#### Understand which deployment actions are available for each installer type

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

## Deployment conflicts
When two deployments, with the same deployment action are received by a device, the following rules apply:

-   Deployments to a device group take precedence over deployments to a user group. However, if an app is deployed to a user group with a deployment action of **Available** and the same app is also deployed to a device group with a deployment action of **Not Applicable**, the app will be made available in the company portal for users to install.

-   The intent of the IT admin takes precedence over the user.

-   An install action takes precedence over an uninstall action.

-   If both a required and an available install are received by a device, the actions are combined (the app is both required and available).


## Next steps

Learn how to [deploy apps in Microsoft Intune](deploy-apps-in-microsoft-intune.md).