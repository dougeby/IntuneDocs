---
title: MD Mac OS X configuration policy settings in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 818798ce-b718-435f-897e-3e36a7053b82
---
# MD Mac OS X configuration policy settings in Microsoft Intune
Use the [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)]**Mac OS X general configuration policy** to configure settings for:

-   **Device security settings** - Choose from a list of predefined settings that let you control a range of features and functionality on the device.

-   **Compliant and noncompliant apps** - Specify a list of apps that are compliant, or not compliant in your company. The Noncompliant Apps Report can be used to view the compliance of apps you specified in the list against the apps that users have installed (but cannot actually block the installation of the app).

## Create an Mac OS X general configuration policy

#### To provide basic settings for the configuration policy

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Policy** &gt; **Overview** &gt; **Add Policy**.

2.  Click **Mac OS X** &gt; **General Configuration** and then click **Create Policy**.

    > [!NOTE]
    > You cannot create a configuration policy using recommended settings. You must create a custom policy.

3.  In the **General** section of the **Create Policy** page, specify a name and a description for the new policy.

4.  Use the information in the following sections to help you supply settings for the policy.

5.  When you are finished, click **Save Policy**.

The new policy displays in the **Configuration Policies** node of the **Policy** workspace.

## Settings for Mac OS X devices
If the setting you are looking for does not appear in this list, you might be able to create it using a Mac OS X custom policy that lets you import settings you created using the Apple Configurator Tool. For more information, see [Mac OS X custom policy settings in Microsoft Intune](../Topic/Mac-OS-X-custom-policy-settings-in-Microsoft-Intune.md).

### Password settings

|Setting name|Description|
|----------------|---------------|
|**Require a password to unlock devices**|Specifies whether the use must use a password to access their Mac computer.<br /><br />Unlike iOS devices, on Mac OS X devices, the user is not immediately notified to update their password to comply with this setting.|
|**Required password type**|Specifies whether the password used can be Numeric only, or whether it must be **Alphanumeric** (contain letters and numbers).<br /><br />This setting is only supported on Mac OS X version 10.10.3 and later.|
|**Number of complex characters required in password**|Specifies the number of complex characters required in the password (from **0** - **4**).<br /><br />A complex character is a symbol, such as '**?**'|
|**Minimum password length**|Specifies the minimum length for the password (between **4** and **14** characters).|
|**Allow simple passwords**|Allows the use of simple passwords such as '**0000**' or '**1234**'.|
|**Minutes of inactivity before password is required**|Specifies how long the computer must be inactive before a password is required to unlock it.|
|**Password expiration (days)**|Specifies how many days elapse before the user must change the password (from **1** - **255** days).|
|**Remember password history**|This setting is used to prevent the user from using a previously used password. When it is set, you can also set **Prevent reuse of previous passwords** to specify the number of previously used passwords that cannot be reused (from **1** - **24**).|
|**Minutes of inactivity before screensaver activates**|Specifies the length of time the computer must be idle before the screensaver activates.|

## Settings for compliant and noncompliant apps
In the **Compliant &amp; Noncompliant Apps list for Mac OS X**, enable **Managed settings for devices**, and then specify a list of compliant or noncompliant apps using the following information:

> [!NOTE]
> A single policy can only contain a list of compliant, or a list of noncompliant apps. You cannot specify both in the same policy.
> 
> [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] lets you report devices with noncompliant apps. It does not block installation, or remove noncompliant apps.

|Setting name|Description|
|----------------|---------------|
|**Report noncompliance when users install the listed apps**|Lists the Mac OS X apps that users are not allowed to install. If users install any of these apps, they will be reported in the **Noncompliant Apps Reports**.|
|**Report noncompliance when users install apps which are not listed**|Lists the Mac OS X apps that users are allowed to install. If users install any other apps, they will be reported in the **Noncompliant Apps Reports**.|
|**Add**|Adds an app to the selected list. Specify a name of your choice, optionally the app publisher, and the  bundle ID of the app.|
|**Import Apps**|Imports a list of apps you have specified in a comma-separated values file. Use the format, app name, publisher, app bundle ID in the file.|
|**Edit**|Let’s you edit the name, publisher and app bundle ID of the selected app.|
|**Delete**|Deletes the selected app from the list.|
> [!TIP]
> To find the bundle ID of an app, use the following steps on a Mac computer that has the app installed:
> 
> 1.  Open the folder in which the app is installed (for example, **/Applications**)
> 2.  Select the *&lt;App Name&gt;***.app** bundle, and choose **Show Package Contents**
> 3.  Open the **Info.plist** file
> 4.  Check the value associated with the key **CFBundleIdentifier**
> 
> The format for Bundle ID is **com.contoso.appname**

> [!TIP]
> For more information about [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] reports, see [Understand Microsoft Intune operations by using reports](../Topic/Understand-Microsoft-Intune-operations-by-using-reports.md).

## Deploy the configuration policy
Deploy the configuration policy to one or more groups of users or devices in your organization.

For more information about how to deploy policies, see U[Use policies to manage computers and mobile devices with Microsoft Intune](../Topic/Use-policies-to-manage-computers-and-mobile-devices-with-Microsoft-Intune.md).

A status summary and alerts In the **Policy** workspace identify issues with the policy that require your attention. Additionally, a status summary appears in the **Dashboard** workspace.

> [!IMPORTANT]
> When a Mac OS X device is in Sleep mode, policies and profiles cannot be delivered or inventoried. As a result, the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] console might temporarily display the status **Policy settings in error** until the next time the device wakes from Sleep mode.

## Monitor compliant and noncompliant apps
Use the **Noncompliant Apps Reports** to view the compliance of apps you specified.

#### To run the report

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Reports** &gt; **Noncompliant Apps Reports**.

2.  Select the device groups that you would like to check, whether you want to check for compliant apps, noncompliant apps, or both, then click **View Report**.

## See Also
[Use policies to manage computers and mobile devices with Microsoft Intune](../Topic/Use-policies-to-manage-computers-and-mobile-devices-with-Microsoft-Intune.md)

