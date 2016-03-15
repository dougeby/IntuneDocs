---
title: MD Conversion - Use policies to manage computers and mobile devices with Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: b7dbb479-d3c8-4ac0-8140-a7a68120e598
---
# MD Conversion - Use policies to manage computers and mobile devices with Microsoft Intune
[!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)]**Policies** are groups of settings that control features on mobile devices and computers. You create policies using templates that contain recommended or customized settings, and then deploy them to device or user groups.

## How to create configuration policies
The way you create policies differs depending on the policy type you are creating.

These procedures cover creating configuration policies.

-   To help choose the right policy for your needs, see [Manage settings and features on your devices with Microsoft Intune policies](../Topic/Manage-settings-and-features-on-your-devices-with-Microsoft-Intune-policies.md).

-   For information about creating compliance policies, see [Manage device compliance policies for Microsoft Intune](../Topic/Manage-device-compliance-policies-for-Microsoft-Intune.md).

-   For information about creating conditional access policies, see [Manage access to email and SharePoint with Microsoft Intune](../Topic/Manage-access-to-email-and-SharePoint-with-Microsoft-Intune.md).

-   For information about corporate device enrollment policies, see [Set up iOS and Mac management with Microsoft Intune](../Topic/Set-up-iOS-and-Mac-management-with-Microsoft-Intune.md).

#### To create a policy

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com/), click **Policy** &gt; **Configuration Policies** &gt; **Add**.

2.  Choose the policy you want, choose to use the recommended settings for the policy (when available; you can change these settings later), or to create a custom policy with your own settings.

    > [!TIP]
    > For help choosing the right policy, see [Manage settings and features on your devices with Microsoft Intune policies](../Topic/Manage-settings-and-features-on-your-devices-with-Microsoft-Intune-policies.md).

3.  When you are ready, click **Create Policy**.

4.  On the **Create Policy** screen, configure a name and optional description for the policy.

5.  Configure the required policy settings, then click **Save Policy**.

6.  In the confirmation dialog box, click **Yes** to deploy the policy now, or click **No** to create the policy without deploying it.

You can view and edit the new policy by browsing the sections for each policy type in **Policy** workspace.

When you create a policy that uses the recommended settings, the name of the new policy is a combination of the template name, date, and time. When you edit the policy, the name updates with the time and date of the edit.

Now that you have created a policy, you will typically want to deploy it to one or more groups of users or devices.

> [!TIP]
> You don't deploy all policy types. For example, the mobile application management policy is not deployed. This policy type is instead associated with an app, which you then deploy.

#### To deploy a policy

1.  In the **Policy** workspace, select the policy you want to deploy, then click **Manage Deployment**.

2.  In the **Manage Deployment** dialog box:

    -   **To deploy the policy** - Select one or more groups to which you want to deploy the policy, then click **Add** &gt; **OK**.

    -   **To close the dialog box without deploying it** - Click **Cancel**.

When you select a deployed policy, you can view further information about the deployment in the lower part of the policies list.

#### To manage policies you have already created

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com/), click **Policy**, then browse to and select the policy you want to manage.

2.  Select one of the actions in the following table:

    |Action|More information|
    |----------|--------------------|
    |**Edit**|Opens the properties for the selected policy to allow you to make changes.|
    |**Delete**|Deletes the selected policy.<br /><br />When you delete a policy, it is removed from all groups to which it was deployed.<br /><br />[What happens when a policy is deleted, or no longer applicable](../Topic/Use-policies-to-manage-computers-and-mobile-devices-with-Microsoft-Intune.md#BKMK_What)|
    |**Manage Deployment**|In the **Manage Deployment** dialog box, select the group you want to deploy the policy to and click **Add**.|

## Tasks for Intune policies

### <a name="BKMK_Refresh"></a>To refresh the policies on a device to ensure they are current (applies to computers only)

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com/), click **Groups**, and then select a device group.

2.  Select the devices on which you want to refresh the policies, and then click **Remote Tasks** &gt; **Refresh Policies**.

3.  Click **Remote Tasks** in the bottom-right corner of the [!INCLUDE[wit_adminconsole](../Token/wit_adminconsole_md.md)] window to check the task status.

## More information about Intune policies

### How long does it take for mobile devices to get policy or apps after they have been deployed?
When a policy or app is deployed, **[!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] immediately begins attempting to notify the device that it should check-in with the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] service.** This typically takes less than 5 minutes.

If a device doesn't check in to get policy after the first notification is sent, 3 more attempts are made.  If the device is offline (for example, it is turned off, or not connected to a network) then it might not receive the notifications.

In this case, the device will get policy on its next scheduled check-in with the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] service as follows:

|Platform|Check-in frequency after initial notification|
|------------|-------------------------------------------------|
|iOS|Every 6 hours|
|Android|Every 8 hours|
|Windows Phone|Every 8 hours|
|Windows PCs enrolled as devices|Every 24 hours|
If the device has just enrolled the check-in frequency will be more frequent as follows:

|Platform|Frequency|
|------------|-------------|
|iOS|Every 15 minutes for 6 hours and then every 6 hours|
|Android|Every 3 minutes for 15 minutes then every 15 minutes for 2 hours, and then every 8 hours|
|Windows Phone|Every 5 minutes for 15 minutes then every 15 minutes for 2 hours, and then every 8 hours|
|Windows PCs enrolled as devices|Every 3 minutes for 30 minutes, and then every 24 hours|
Users can also launch the Company Portal app and sync the device to immediately check for policy anytime.

### What actions cause Intune to immediately send notification  to a device?
Devices check in with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] either when they receive a notification telling them to check-in, or during their regularly scheduled check-in as shown in the tables above.  When you target a device or user specifically with an action such as a wipe, lock, passcode reset, app deployment, profile deployment (WiFi, VPN, e-mail, etc.), or policy deployment, [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] will immediately begin trying to notify the device that it should check-in with the Intune service to receive these updates.

Other changes such as revising the contact information in the company portal do not cause an immediate notification to devices.

### If multiple policies are deployed to the same user or device how do I know which settings will get applied?
It’s important to know that when two or more policies are deployed to the same user or device the evaluation for which setting is applied is done at the individual setting level.

-   Compliance policy settings always have precedence over configuration policy settings

-   The most restrictive compliance policy setting is applied if evaluated against the same setting in a different compliance policy

-   The most restrictive configuration policy setting is applied if evaluated against the same setting in a different configuration policy

### What happens when mobile application management (MAM) policies conflict with each other? Which one will be applied to the app?
Conflict values are the most restrictive settings available in a mobile application management policy, except for the number entry fields (like PIN attempts before reset).  The number entry fields will be set to the same as the values as if you create a MAM policy in the console using the recommended settings option.

Conflicts occur when two policy settings are the same.  For example, you configured two MAM policies that are identical except for the copy/paste setting.  In this scenario, the copy/paste setting will be set to the most restrictive value, but the rest of the settings will be applied as configured.

If one policy is deployed to the app and takes effect, and then a second one is deployed, the first one deployed will take precedence and stay applied, while the second shows in conflict. However, if they are both applied at the same time, meaning that there is no preceding policy, then they will both be in conflict, and any conflicting settings will be set to the most restrictive values.

### What happens when iOS custom policies conflict?
Intune does not evaluate the payload of Apple Configuration files or custom OMA-URI policy, it merely serves as the delivery mechanism.

Therefore, when you deploy a custom policy, ensure the settings configured do not conflict with compliance, configuration or other custom policies. In the case of a custom policy with settings conflicts, the order in which are settings are applied is random.

### <a name="BKMK_What"></a>What happens when a policy is deleted, or no longer applicable
When you delete a policy, or remove a device from a group to which a policy was deployed, the policy and settings will be removed from the device according to the following tables:

#### Mobile devices

|Policy type|Windows|Android|Windows Phone (8.1 only)|iOS|
|---------------|-----------|-----------|----------------------------|-------|
|Wi-Fi, VPN, certificate and email profiles|Removed|Removed|Removed|Removed|
|All other policy types|Not removed|Not removed|The following settings are removed:<br /><br />Require a password to unlock mobile devices<br /><br />Allow simple passwords<br /><br />Minimum password length<br /><br />Required password type<br /><br />Password expiration (days)<br /><br />Remember password history<br /><br />Number of repeated sign-in failures to allow before the device is wiped<br /><br />Minutes of inactivity before password is required<br /><br />Required password type – minimum number of character sets<br /><br />Allow camera<br /><br />Require encryption on mobile device<br /><br />Allow removable storage<br /><br />Allow web browser<br /><br />Allow application store<br /><br />Allow screen capture<br /><br />Allow geolocation<br /><br />Allow Microsoft Account<br /><br />Allow copy and paste<br /><br />Allow Wi-Fi tethering<br /><br />Allow automatic connection to free Wi-Fi hotspots<br /><br />Allow Wi-Fi hotspot reporting<br /><br />Allow factory reset<br /><br />Allow Bluetooth<br /><br />Allow NFC<br /><br />Allow Wi-Fi|Removed, **except** for:<br /><br />Allow voice roaming<br /><br />Allow data roaming<br /><br />Allow automatic synchronization while roaming|

#### Computers

|Policy type|Action|
|---------------|----------|
|**Endpoint Protection settings**|Settings are restored to their recommended values. The only exception is the setting **Join Microsoft Active Protection Service** for which the default value is **No**. For details, see [Help secure Windows PCs with Endpoint Protection for Microsoft Intune](../Topic/Help-secure-Windows-PCs-with-Endpoint-Protection-for-Microsoft-Intune.md).|
|**Software updates settings**|Settings are reset to the default state for the operating system. For details, see [Keep Windows PCs up to date with software updates in Microsoft Intune](../Topic/Keep-Windows-PCs-up-to-date-with-software-updates-in-Microsoft-Intune.md).|
|**[!INCLUDE[wit_tools](../Token/wit_tools_md.md)] settings**|Any support contact information that was configured by the policy is deleted from computers.|
|**Windows Firewall settings**|Settings are reset to the default for the computer operating system. For details, see [Help secure Windows PCs with Endpoint Protection for Microsoft Intune](../Topic/Help-secure-Windows-PCs-with-Endpoint-Protection-for-Microsoft-Intune.md).|

## See Also
[Technical reference for Microsoft Intune](../Topic/Technical-reference-for-Microsoft-Intune.md)
[Manage settings and features on your devices with Microsoft Intune policies](../Topic/Manage-settings-and-features-on-your-devices-with-Microsoft-Intune-policies.md)

