---
# required metadata

title: Use Intune app configuration policies for Android for Work | Microsoft Docs
titleSuffix: "Intune Azure preview"
description: "Intune Azure preview: Learn how to use app configuration policies to provide configuration data to an Android for Work app when it is run."
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/24/2017
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

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Use app configuration policies in Microsoft Intune to supply settings that might be required when users run an Android for Work app.

If users enter these settings incorrectly, this can increase the burden on your help desk and slow the adoption of new apps.

App configuration policies can help you eliminate these problems by letting you assign these settings to users in a policy before they run the app. Some Android apps support managed configurations options that you can configure in the Intune console with the [configuration designer](#use-configuration-designer). Others can be set by defining  values in the [JSON editor](#use-json-editor). Settings are supplied to apps automatically, and users need to take no action.

You do not assign these policies directly to users and devices. Instead, you associate a policy with an app, and then assign the app. The policy settings will be used whenever the app checks for them (typically, the first time it is run).

## Use configuration designer

1. In the Intune portal, choose **Mobile apps**. Under **Manage**, choose **App configuration policies** and then click **Add**.
2. Set the following details:
    - **Name** - The name of the profile that will appear in the Intune console
    - **Description** - The  description of the profile that will appear in the Intune console
    - **Platform** - Select **Android for Work**
    - **Enrollment type** - Select **Devices with enrollment**
3. Select **Configuration settings**.
4. For **Configuration settings format**, select **Use configuration designer**.
5. Choose **Add**. A list of  available configuration settings is displayed.  The list includes:
    - **Configuration keys** - Name of the setting.
    - **Value type** - The setting that can be configured, for example **Boolean** or **String**.
    - **Description** - A description of the configuration setting.
6. Select the checkboxes of settings you want to configure with this profile, and then click **OK**.
7. A list of your selected settings is displayed with the available **Configuration value**. Specify a value for each setting, and then click **OK**.

## Use JSON editor

1. In the Intune portal, choose **Mobile apps**. Under **Manage**, choose **App configuration policies** and then click **Add**.
2. Set the following details:
    - **Name** - The name of the profile that will appear in the Intune console
    - **Description** - The  description of the profile that will appear in the Intune console
    - **Platform** - Select **Android for Work**
    - **Enrollment type** - Select **Devices with enrollment**
2.  In the list of policies blade, choose **Add**.
3. Select **Configuration settings**.
4. For **Configuration settings format**, select **Enter JSON editor**.
5. In the editor you can define JSON values for configuration settings. You can choose **Download JSON template** to download a sample file that you can then configure.
8. When you're done, choose **OK** and then click **Add**.

The policy will be created and appears on the policies list blade.

Then, continue to [assign](apps-deploy.md) and [monitor](apps-monitor.md) the app as usual.

When the assigned app is run on a device, it will run with the settings that you configured in the app configuration policy.

> [!TIP]
> If one or more app configuration policies conflict, neither policy is enforced.


## Preconfigure permissions for apps

You can also preconfigure permission for apps to access Android device features. By default, Android apps that require device permissions such as access to location or the device camera prompt users to accept or deny permissions. For example, if an app uses the device's microphone then the end user is prompted to grant the app permission to use the microphone.

1. Sign into the Azure portal.
2. On the **Intune** blade, choose **Mobile apps**.
3. In the **Mobile apps** workload, choose **App configuration Policies** > **Android for Work**.
4. Set the following details:
    - **Name** - The name of the profile that will appear in the Intune console
    - **Description** - The  description of the profile that will appear in the Intune console
    - **Platform** - Select **Android for Work**
    - **Enrollment type** - Select **Devices with enrollment**
5. Select **Permissions** and then choose **Add**.
6. Select from the list of available device permissions adn then choose **OK**.
7. Select an option for each permission to grant with this policy:
    - **Prompt** - Prompt the user to accept or deny.
    - **Auto grant** - Automatically approve without notifying the user.
    - **Auto deny** - Automatically deny without notifying the user.
8. To assign the app configuration policy, select the app configuratiopn policy, select **Assignment**, and then select **Select groups**.
9. Select the user groups to assign, and then choose **Select**.
10. Choose **Save** to assign the policy.
