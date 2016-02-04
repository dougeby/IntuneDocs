---
title: Exchange ActiveSync policy settings in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: e9cbb826-b155-4df6-abf3-60c6f05b2783
author: robstackmsft
---
# Exchange ActiveSync policy settings in Microsoft Intune
Use the [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] **Exchange ActiveSync** policy to configure settings that let you control a range of features and functionality on devices that are managed by Exchange ActiveSync.

## Create an Exchange ActiveSync policy

#### To provide basic settings for the policy

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Policy** &gt; **Overview** &gt; **Add Policy**.

2.  Click **Common Mobile Device Settings** &gt; **Exchange ActiveSync** and then click **Create Policy**.

    > [!NOTE]
    > You cannot create a configuration policy using recommended settings. You must create a custom policy.

3.  In the **General** section of the **Create Policy** page, specify a name and a description for the new policy.

4.  Use the information in the following sections to help you supply settings for the policy.

5.  When you are finished, click **Save Policy**.

The new policy displays in the **Configuration Policies** node of the **Policy** workspace.

## <a name="BKMK_Settings"></a>Policy settings for devices managed by Exchange ActiveSync

### <a name="BKMK_sec"></a>Security settings

|Setting name|
|----------------|
|**Require a password to unlock mobile devices**|
|**Required password type**<br /><br />(specifies the type of password that will be required, such as numeric only, or alphanumeric)|
|**Minimum password length**|
|**Allow simple passwords**<br /><br />Simple passwords include ‘0000’ and ‘1234’|
|**Number of repeated sign-in failures to allow before the device is wiped**|
|**Password expiration (days)**|
|**Remember password history**|
|**Remember password history** – **Prevent reuse of previous passwords**|
|**Minutes of inactivity before password is required**|

### Encryption settings

|Setting name|
|----------------|
|**Require encryption on mobile device**<sup>1</sup><br /><br />For Windows Phone 8 devices, you must set this to **Yes**.<br /><br />To enable encryption on iOS devices, enable the setting **Require a password to unlock mobile devices**.|
|**Require encryption on storage cards**|
<sup>1</sup> Additional information for devices that run Windows 8.1

-   To enforce encryption on devices that run Windows 8.1, you must install the [December 2014 MDM client update for Windows](http://support.microsoft.com/kb/3013816) on each device.

-   If you enable this setting for Windows 8.1 devices, all users of the device must have a Microsoft Account.

-   For encryption to work, the device must meet the Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) hardware certification requirements.

-   When you enforce encryption on a device, the recovery key is only accessible from the users Microsoft Account, accessed from their OneDrive account. You cannot recover this key on behalf of a user.

### <a name="BKMK_email"></a>Email settings

|Setting name|
|----------------|
|**Allow users to download email attachments**|
|**Email synchronization period**|
|**Allow mobile devices that don’t fully support Exchange ActiveSync settings to synchronize with Exchange**|

### <a name="BKMK_browser"></a>Applications - Browser

|Setting name|
|----------------|
|**Allow web browser**|

### <a name="BKMK_hard"></a>Device capabilities - hardware

|Setting name|
|----------------|
|**Allow camera**|

## Deploy the Configuration Policy

1.  Deploy the configuration policy to one or more groups of users or devices in your organization.

For more information about how to deploy policies, see [Use policies to manage computers and mobile devices with Microsoft Intune](../Topic/Use-policies-to-manage-computers-and-mobile-devices-with-Microsoft-Intune.md).

A status summary and alerts In the **Policy** workspace identify issues with the policy that require your attention. Additionally, a status summary appears in the **Dashboard** workspace.

## See Also
[Use policies to manage computers and mobile devices with Microsoft Intune](../Topic/Use-policies-to-manage-computers-and-mobile-devices-with-Microsoft-Intune.md)

