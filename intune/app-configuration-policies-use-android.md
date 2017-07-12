---
# required metadata

title: Use Intune app configuration policies for Android for Work 
titleSuffix: "Intune on Azure"
description: Learn how to use app configuration policies to provide configuration data to an Android for Work app when it is run."
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/12/2017
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

# How to use Microsoft Intune app configuration policies for Android for Work

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Use app configuration policies in Microsoft Intune to supply settings that might be available when users run an Android for Work app. Not all apps support app configuration. Check with the app’s developer to see whether or not they have built their app to support app configuration policies.

App configuration policies can help you pre-configure available app settings for your users before they run the app. Some Android apps support managed configurations options that you can configure in the Intune console with the [configuration designer](#use-configuration-designer). Some configuration settings on apps (such as those with Bundle types) cannot be configured with the configuration designer.  You will need to use the [JSON editor](#use-json-editor) for those values.   Settings are supplied to apps automatically when the app is installed.

You do not assign these policies directly to users and devices. Instead, you associate a policy with an app, and then assign the app. The policy settings is used when the app checks for them, typically the first time it is run).

## Use configuration designer

1. In the Intune portal, choose **Mobile apps**. Under **Manage**, choose **App configuration policies** and then click **Add**.
2. Set the following details:
    - **Name** - The name of the profile that will appear in the Intune console
    - **Description** - The  description of the profile that will appear in the Intune console
    - **Platform** - Select **Android**
    - **Device enrollment type** - **Enrolled with Intune** is pre-selected for you.
3. Select **Associated App** to choose the app for which you want to define a configuration policy.  Select from the list of Android for Work apps that you have approved and synchronized with Intune
4. Select **Configuration settings**.
5. For **Configuration settings format**, select **Use configuration designer**.
6. Choose **Add**. A list of  available configuration settings is displayed. The list includes:
    - **Configuration keys** - Name of the setting.
    - **Value type** - The setting that can be configured, for example **Boolean** or **String**.
    - **Description** - A description of the configuration setting.
7. Select the checkboxes of settings you want to configure with this profile, and then click **OK**.
8. A list of your selected settings is displayed with the available **Configuration value**. Specify a value for each setting, and then click **OK**.

## Use JSON editor

1. In the Intune portal, choose **Mobile apps**. Under **Manage**, choose **App configuration policies** and then click **Add**.
2. Set the following details:
    - **Name** - The name of the profile that will appear in the Intune console
    - **Description** - The  description of the profile that will appear in the Intune console
    - **Platform** - Select **Android**
    - **Device enrollment type** - **Enrolled with Intune** is pre-selected for you.
3. Select **Associated App** to choose the app for which you want to define a configuration policy.  Select from the list of Android for Work apps that you have approved and synchronized with Intune.
5. Select **Configuration Settings**.
6. For **Configuration settings format**, select **Enter JSON editor**.
7. In the editor you can define JSON values for configuration settings. You can choose **Download JSON template** to download a sample file that you can then configure.
8. When you're done, choose **OK** and then click **Add**.

The policy will be created and appears on the policies list blade.



When the assigned app is run on a device, it will run with the settings that you configured in the app configuration policy.

## Preconfigure permissions grant state for apps

You can also preconfigure permission for apps to access Android device features. By default, Android apps that require device permissions such as access to location or the device camera prompt users to accept or deny permissions. For example, if an app uses the device's microphone then the end user is prompted to grant the app permission to use the microphone.

1. In the Intune portal, choose **Mobile apps**. Under **Manage**, choose **App configuration policies** and then click **Add**.
2. Set the following details:
    - **Name** - The name of the profile that will appear in the Intune console
    - **Description** - The  description of the profile that will appear in the Intune console
    - **Platform** - Select **Android**
    - **Device enrollment type** - **Enrolled with Intune** is pre-selected for you.
3. Select **Associated App** to choose the app for which you want to define a configuration policy.  Select from the list of Android for Work apps that you have approved and synchronized with Intune.
5. Select **Permissions** and then choose **Add**.
6. Select from the list of available app permissions and then choose **OK**.
7. Select an option for each permission to grant with this policy:
    - **Prompt** - Prompt the user to accept or deny.
    - **Auto grant** - Automatically approve without notifying the user.
    - **Auto deny** - Automatically deny without notifying the user.
8. To assign the app configuration policy, select the app configuration policy, select **Assignment**, and then select **Select groups**.
9. Select the user groups to assign, and then choose **Select**.
10. Choose **Save** to assign the policy.

## Next steps

Continue to [assign](apps-deploy.md) and [monitor](apps-monitor.md) the app as usual.

