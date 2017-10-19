---
# required metadata

title: Android for Work app configuration policy 
description: Use mobile app configuration policies in Intune to supply settings that might be required when users run an Android for Work app.
keywords:
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 02/03/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: fc6b645a-e837-4b2a-a10f-144065cbd8dd
ROBOTS: NOINDEX,NOFOLLOW

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: chrisbal
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Configure Android for Work apps with mobile app configuration policies in Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Use mobile app configuration policies in Microsoft Intune to supply settings that might be required when users run an app. For example, an app might require users to specify:

-   A custom port number
-   Language settings
-   Branding settings such as a company logo

If users enter settings incorrectly, it can increase the burden on your help desk and slow the adoption of new apps.

Mobile app configuration policies let you deploy these settings to devices before users run the app. The settings are supplied automatically, and users need to take no action.

To utilize app configuration policies, the app developer must have exposed enterprise app configurations when they created it. For example, Google Chrome exposes settings that let you set default bookmarks, allowed and denied sites, and more. Contact the developer of the app to see if these settings are supported and how to specify them in the policy.

You deploy the app configuration policy to the same users to whom you have deployed the app you want to configure. App settings are applied when the app is run.

## Configure a mobile app configuration policy

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Policy** &gt; **Overview** &gt; **Add Policy**.

2.  In the list of policies, expand **Android for Work**, choose **Mobile App Configuration Policy (Android for Work)**, and then choose **Create Policy**.

    > [!TIP]
    > You can configure only custom settings for this policy type. Recommended settings are not available.

3.  In the **General** section of the **Create Policy** page, supply a name and an optional description for the mobile app configuration policy.

4. In the **Mobile App Configuration Policy** section of the page, specify the following information:
	- **Package ID for the application that this configuration applies to** - The package ID can be found in the 'id=' section of the app URL on it's Google Play page. For example, the package ID for the Microsoft Excel app is **com.microsoft.office.excel**.
	- In the text box, enter the data for the app settings you want to configure. You get these settings from the supplier of the app. Not all apps support these settings.
5.  Click **Validate** to ensure that the data that you entered is in a valid property list format.

    > [!IMPORTANT]
    > When you click **Validate**, Intune checks that the configuration data you entered is in a valid format. It does not check that the data will work with the app that it is associated with.

6.  When you are done, click **Save Policy**.

The new policy is displayed in the **Configuration Policies** node.


## Deploy the app configuration policy
After you have created a mobile app configuration policy, you must deploy it to the same users to whom you deploy the app to which the settings will apply.

For information about how to deploy policies, see [deploy a configuration policy](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#deploy-a-configuration-policy)

For information about how to deploy apps to Android for Work devices, see [How to deploy Android for Work apps with Intune](android-for-work-apps.md).

When the deployed app is run on a device, it will run with the settings that you configured in the mobile app configuration policy.

> [!TIP]
> Only deploy one app configuration policy for each app to a user.
