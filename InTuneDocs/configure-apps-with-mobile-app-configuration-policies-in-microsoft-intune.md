---
title: Configure apps with mobile app configuration policies in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: fc6b645a-e837-4b2a-a10f-144065cbd8dd
author: robstackmsft
---
# Configure apps with mobile app configuration policies in Microsoft Intune
Use mobile app configuration policies in [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] to supply settings that might be required when the user runs an app. For example, an app might require the user to specify:

-   A custom port number when it is run

-   Language settings

-   Security settings

-   Branding settings such as a company logo

If these settings are incorrectly entered by the user, this can increase the burden on your help desk, and also slow the adoption of new apps.

Mobile app configuration policies can help you eliminate these problems by letting you deploy these settings to users in a policy before they run the app. The settings are then supplied automatically, and the user needs to take no action.

You do not deploy these policies directly to users and devices. Instead, you associate the policy with an app, then deploy the app. The policy settings will be used whenever the app checks for them (typically, the first time it is run).

> [!TIP]
> This policy type is currently available only devices running iOS 7.1 and later and supports the following app installation types:
> 
> -   **Managed iOS app from the app store**
> -   **App package for iOS**
> 
> For more information about app installation types, see [Plan for app deployment in Microsoft Intune](../Topic/Plan-for-app-deployment-in-Microsoft-Intune.md).

## Configure a mobile app configuration policy

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Policy** &gt; **Overview** &gt; **Add Policy**.

2.  In the list of policies, expand **iOS**, click **Mobile App Configuration**, and then click **Create Policy**.

    > [!TIP]
    > You can only configure custom settings for this policy type. Recommended settings are not available.

3.  In the **General** section of the **Create Policy** page, supply a name, and an optional description for the mobile app configuration policy.

4.  In the **Mobile App Configuration Policy** section of the page, enter or paste an  XML property list containing the app configuration settings you want into the box.

    > [!TIP]
    > To find out more about XML property lists, see [Understanding XML Property Lists](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html)in the iOS Developer Library.
    > 
    > The format of the XML property list will vary depending on the app you are configuring. Contact the supplier of the app for details about the exact format to use.
    > 
    > [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] supports the following data types in a property list:
    > 
    > -   &lt;integer&gt;
    > -   &lt;real&gt;
    > -   &lt;string&gt;
    > -   &lt;array&gt;
    > -   &lt;dict&gt;
    > -   &lt;true /&gt; or &lt;false /&gt;
    > 
    > For more information about data types, see [About Property Lists](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/AboutPropertyLists/AboutPropertyLists.html) in the iOS Developer Library.

5.  Click **Validate** to ensure that the XML you entered is in a valid property list format.

    > [!IMPORTANT]
    > When you click **Validate**, [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] checks that the XML you entered is in a valid format. It does not check that the XML property list will work with the app it is associated with.

6.  When you are done, click **Save Policy**.

The new policy is displayed in the **Configuration Policies** node.

## Associate a mobile app configuration policy with an app
After you have created a mobile app configuration policy, you must associate it with the iOS app to which you want the settings in the configuration policy to apply.

To do this, follow the steps to create an app deployment in [Deploy apps to mobile devices in Microsoft Intune - deleted](../Topic/Deploy-apps-to-mobile-devices-in-Microsoft-Intune---deleted.md). When you reach the **Mobile App Configuration** page of the wizard, select the policy you want to associate with the app from the **App Configuration Policy** drop-down list.

Then, continue to deploy and monitor the app deployment as usual.

When the deployed app is run on a device, it will run with the settings you configured in the mobile app configuration policy.

> [!TIP]
> If one or more mobile app configuration policies conflict, neither policy is enforced, and the conflict will be reported in the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] admin console **Dashboard**.

## See Also
[Deploy and configure apps with Microsoft Intune](../Topic/Deploy-and-configure-apps-with-Microsoft-Intune.md)
[Deploy apps to mobile devices in Microsoft Intune - deleted](../Topic/Deploy-apps-to-mobile-devices-in-Microsoft-Intune---deleted.md)

