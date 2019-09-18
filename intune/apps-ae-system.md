---
# required metadata

title: Add Android Enterprise system apps to Microsoft Intune
titleSuffix: 
description: Learn how to add Enterprise system apps to Microsoft Intune.
keywords:
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology:
ms.assetid: 

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: priyar
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure
ms.collection: M365-identity-device-management
---

# Add Android Enterprise system apps to Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Before you assign an app to a device or a group of users, you must first add the app to Microsoft Intune. System apps are supported on Android Enterprise devices. You can enable a system app for [Android Enterprise dedicated devices](android-kiosk-enroll.md) or [fully managed devices](android-fully-managed-enroll.md). 

## Add the app

You can add an Android Enterprise system app to Intune from the Azure portal by doing the following:

1. Sign in to [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. In the **Intune** pane, select **Client apps** > **Apps** > **Add**.
3. In the **Add App** pane, under the available **Other** types, select **Android Enterprise system app**.
4. To configure the app information, select **Configure**, and then provide the following information:
    - **App Name**: Enter the name of the app.
    - **Publisher**: Enter the name of the publisher of the app.  
    - **Package Name**: Enter a package name. Intune will validate that the package name is valid.
5. Select **OK**.
6. Select **Add**.

The app you've created is displayed in the apps list, where you can assign it to the groups that you select. 

Android Enterprise system apps will enable or disable apps that are already part of the platform. To enable an app, assign the system app as **Required**. To disable an app, assign the system app as **Uninstall**. System apps cannot be assigned as available for a user.

## Next steps

- [Assign apps to groups](apps-deploy.md)
