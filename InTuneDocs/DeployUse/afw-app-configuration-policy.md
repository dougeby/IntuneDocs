---
# required metadata

title: Use Android for Work mobile app configuration policies | Microsoft Intune
description: Use mobile app configuration policies in Intune to supply settings that might be required when users run an Android for Work app.
keywords:
author: robstackmsft
manager: angrobe
ms.date: 09/19/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: fc6b645a-e837-4b2a-a10f-144065cbd8dd

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: chrisbal
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Configure Android for Work apps with mobile app configuration policies in Microsoft Intune
Use mobile app configuration policies in Microsoft Intune to supply settings that might be required when users run an app. For example, an app might require users to specify:

-   A custom port number.

-   Language settings.

-   Security settings.

-   Branding settings such as a company logo.

If users enter these settings incorrectly, this can increase the burden on your help desk and slow the adoption of new apps.

Mobile app configuration policies can help you eliminate these problems by letting you deploy these settings to users in a policy before they run the app. The settings are then supplied automatically, and users need to take no action.

To utilize app configuration policies, the developer of the app must have exposed enterprise app configurations when they created it. For example, Google Chrome exposes settings that let you set default bookmarks, and allowed and denied sites, and more. Contact the developer of the app to see if these settings are supported.

You do not deploy these policies directly to users and devices. Instead, you associate a policy with an app, and then deploy the app. The policy settings will be used whenever the app checks for them (typically, the first time it is run).

## Configure a mobile app configuration policy

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Policy** &gt; **Overview** &gt; **Add Policy**.

2.  In the list of policies, expand **Android for Work**, choose **Mobile App Configuration Policy (Android for Work)**, and then choose **Create Policy**.

    > [!TIP]
    > You can configure only custom settings for this policy type. Recommended settings are not available.

3.  In the **General** section of the **Create Policy** page, supply a name and an optional description for the mobile app configuration policy.

4. In the **Mobile App Configuration Policy** section of the page, specify the following information:
	- **Package ID for the application that this configuration applies to** - The package ID can be found in the 'id=' section of the app URL on it's Google Play page. For example, the package ID for the Microsoft Excel app is **com.microsoft.office.excel**.
	- In the text box, enter the data for the app settings you want to configure. You get these settings from the supplier of the app. Not all apps support these settings. The Google Chrome browser does.
5.  Click **Validate** to ensure that the data that you entered is in a valid property list format.

    > [!IMPORTANT]
    > When you click **Validate**, Intune checks that the configuration data you entered is in a valid format. It does not check that the data will work with the app that it is associated with.

6.  When you are done, click **Save Policy**.

The new policy is displayed in the **Configuration Policies** node.


## Associate a mobile app configuration policy with an app
After you have created a mobile app configuration policy, you must associate it with the iOS app to which you want the settings in the configuration policy to apply.

To do this, follow the steps to [synchronize a Google Play for Work app from the store](android-for-work-apps.md) and [Deploy apps with Microsoft Intune](deploy-apps-in-microsoft-intune.md). When you reach the **Mobile App Configuration** page of the wizard, select the policy that you want to associate with the app from the **App Configuration Policy** drop-down list.

Then, continue to deploy and monitor the app deployment as usual.

When the deployed app is run on a device, it will run with the settings that you configured in the mobile app configuration policy.

> [!TIP]
> If one or more mobile app configuration policies conflict, neither policy is enforced. The conflict will be reported in the Intune administration console **Dashboard**.




