---
# required metadata

title: Add app configuration policies for managed Android devices | Microsoft Docs
titlesuffix: "Azure portal"
description: Learn how to use app configuration policies to provide configuration data to an Android for Work app when it is run."
keywords:
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/23/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: d0b6f3fe-2bd4-4518-a6fe-b9fd115ed5e0


# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: chrisbal
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure
---

# Add app configuration policies for managed Android devices

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Use app configuration policies in Microsoft Intune to supply settings that might be available when users run an Android for Work app. App configuration policies can help you pre-configure available app settings for your users before they run the app. 
You do not assign these policies directly to users and devices. Instead, you associate a policy with an app, and then assign the app. The policy settings is used when the app checks for them, typically the first time it is run).

> [!Note]  
> Not all apps support app configuration. Check with the app’s developer to see whether or not they have built their app to support app configuration policies.

1. Sign in to the Azure portal.
2. Choose **More Services** > **Monitoring + Management** + **Intune**.
3. Choose **Mobile apps**. Under **Manage**, choose **App configuration policies** and then click **Add**.
4. Set the following details:
    - **Name** - The name of the profile that will appear in the Azure portal.
    - **Description** - The  description of the profile that will appear in the Azure portal.
    - **Device enrollment type** - Choose **Managed devices**
5. Select **Android** for the **Platform.
6. Select **Associated App** to choose the app for which you want to define an  app configuration policy.  Select from the list of Android for Work apps that you have approved and synchronized with Intune.
7. Select **Configuration settings**. You can set configurations using:
    - [The configuration designer](#Use-the-configuration-designer)
    - [The JSON editor](#Use-the-JSON-editor)

## Use the configuration designer

Some Android apps support managed configurations options that you can configure in the Azure portal using the configuration designer. Settings are supplied to apps automatically when the app is installed.

1. For **Configuration settings format**, select **Use configuration designer**.
2. Choose **Add**. A list of  available configuration settings is displayed. The list includes:
    - **Configuration keys** - Name of the setting.
    - **Value type** - The setting that can be configured, for example **Boolean** or **String**.
    - **Description** - A description of the configuration setting.
3. Select the checkboxes of settings you want to configure with this profile, and then click **OK**.
4. A list of your selected settings is displayed with the available **Configuration value**. Specify a value for each setting, and then click **OK**.

## Use the JSON editor

Some configuration settings on apps (such as those with Bundle types) cannot be configured with the configuration designer.  You will need to use JSON editor for those values. Settings are supplied to apps automatically when the app is installed.

1. For **Configuration settings format**, select **Enter JSON editor**.
2. In the editor you can define JSON values for configuration settings. You can choose **Download JSON template** to download a sample file that you can then configure.
3. When you're done, choose **OK** and then click **Add**.

The policy will be created and appears on the policies list blade.

When the assigned app is run on a device, it will run with the settings that you configured in the app configuration policy.

## Preconfigure permissions grant state for apps

You can also preconfigure permission for apps to access Android device features. By default, Android apps that require device permissions such as access to location or the device camera prompt users to accept or deny permissions. For example, if an app uses the device's microphone then the end user is prompted to grant the app permission to use the microphone.

1. Sign in to the Azure portal.
2. Choose **More Services** > **Monitoring + Management** + **Intune**.
3. Choose **Mobile apps**. Under **Manage**, choose **App configuration policies** and then click **Add**.
4. Set the following details:
    - **Name** - The name of the profile that will appear in the Azure portal
    - **Description** - The  description of the profile that will appear in the Azure portal
    - **Platform** - Select **Android**
    - **Device enrollment type** - **Enrolled with Intune** is pre-selected for you.
5. Select **Associated App** to choose the app for which you want to define a configuration policy.  Select from the list of Android for Work apps that you have approved and synchronized with Intune.
6. Select **Permissions** and then choose **Add**.
7. Select from the list of available app permissions and then choose **OK**.
8. Select an option for each permission to grant with this policy:
    - **Prompt** - Prompt the user to accept or deny.
    - **Auto grant** - Automatically approve without notifying the user.
    - **Auto deny** - Automatically deny without notifying the user.
9. To assign the app configuration policy, select the app configuration policy, select **Assignment**, and then select **Select groups**.
10. Select the user groups to assign, and then choose **Select**.
11. Choose **Save** to assign the policy.

## Next steps

Continue to [assign](apps-deploy.md) and [monitor](apps-monitor.md) the app as usual.

