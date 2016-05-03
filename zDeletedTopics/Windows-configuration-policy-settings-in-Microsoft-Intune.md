---
title: Windows configuration policy settings in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 6982a2bc-aafa-475a-9236-4840b709e5a1
author: robstackmsft
---
# Windows configuration policy settings in Microsoft Intune
Use the [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] **Windows general configuration policy** to configure settings for enrolled Windows 8, and Windows 8.1 devices:

## Create a Windows general configuration policy

#### To provide basic settings for the configuration policy

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Policy** &gt; **Overview** &gt; **Add Policy**.

2.  Click **Windows** &gt; **General Configuration (Windows 8.1 and later)** and then click **Create Policy**.

    > [!NOTE]
    > You cannot create a configuration policy using recommended settings. You must create a custom policy.

3.  In the **General** section of the **Create Policy** page, specify a name and a description for the new policy.

4.  Use the information in the following sections to help you supply settings for the policy.

5.  When you are finished, click **Save Policy**.

The new policy displays in the **Configuration Policies** node of the **Policy** workspace.

## <a name="BKMK_Settings"></a>Settings for enrolled Windows devices

### <a name="BKMK_sec"></a>Security settings

|Setting name|Windows 8.1 and Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Required password type**<br /><br />(specifies the type of password that will be required, such as numeric only, or alphanumeric)|Yes|Yes|
|**Required password type – Minimum number of character sets**<br /><br />There are four character sets, lowercase letters, uppercase letters, numbers, and symbols. This setting specifies how many different character sets must be included in the password). However, for iOS devices, this specifies the number of symbol characters must be included in the password)|Yes|Yes|
|**Minimum password length**<sup>1</sup>|Yes|Yes|
|**Number of repeated sign-in failures to allow before the device is wiped**|Yes|Yes|
|**Minutes of inactivity before screen turns off**|Yes|Yes|
|**Password expiration (days)**|Yes|Yes|
|**Remember password history**|Yes|Yes|
|**Remember password history** – **Prevent reuse of previous passwords**|Yes|Yes|
|**Allow picture password and PIN**|Yes|Yes|
<sup>1</sup> When you set deploy a password length policy to devices that run Windows RT, users will be forced to reset their password, even if their current password complies with the policy requirements.

### Encryption settings

|Setting name|Windows 8.1 and Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Require encryption on mobile device**<sup>1</sup><br /><br />For Windows Phone 8 devices, you must set this to **Yes**.|Yes|No|
<sup>1</sup> Additional information for devices that run Windows 8.1

-   To enforce encryption on devices that run Windows 8.1, you must install the [December 2014 MDM client update for Windows](http://support.microsoft.com/kb/3013816) on each device.

-   If you enable this setting for Windows 8.1 devices, all users of the device must have a Microsoft Account.

-   For encryption to work, the device must meet the Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) hardware certification requirements.

-   When you enforce encryption on a device, the recovery key is only accessible from the users Microsoft Account, accessed from their OneDrive account. You cannot recover this key on behalf of a user.

### Malware settings

|Setting name|Windows 8.1 and Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Require network firewall**|Yes|No|
|**Enable SmartScreen**|Yes|No|

### System settings

|Setting name|Windows 8.1 and Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Require automatic updates**|Yes|No|
|**Require automatic updates – Minimum classification of updates to install automatically** <sup>1</sup><br /><br />Choose the classification of updates that will be installed automatically:<br /><br />-   **Important** – Installs all updates classified as important.<br />-   **Recommended** – Installs all updates classified as important or recommended.|Yes|No|
|**User Account Control**|Yes|No|
|**Allow diagnostic data submission**|Yes|No|
<sup>1</sup> To enforce encryption on devices that run Windows 8.1, you must install the [December 2014 MDM client update for Windows](http://support.microsoft.com/kb/3013816) on each device.

### <a name="BKMK_cloud"></a>Cloud settings – documents and data

|Setting name|Windows 8.1 and Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Work Folders URL**<br /><br />(sets the URL of the work folder to allow documents to be synchronized across devices)|Yes|No|

### <a name="BKMK_email"></a>Email settings

|Setting name|Windows 8.1 and Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Make Microsoft account optional in Windows Mail application**|Yes|No|

### <a name="BKMK_browser"></a>Application settings - browser

|Setting name|Windows 8.1 and Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Allow autofill**|Yes|No|
|**Allow pop-up blocker**|Yes|No|
|**Allow plug-ins**|Yes|No|
|**Allow active scripting**|Yes|No|
|**Allow fraud warning**|Yes|No|
|**Allow intranet site for single word entry**<br /><br />(allows use of a single word to direct Internet Explorer to a web site, such as ‘Bing’)|Yes|No|
|**Allow automatic detection of intranet network**|Yes|No|
|**Security level for Internet**|Yes|No|
|**Security level for intranet**|Yes|No|
|**Security level for trusted sites**|Yes|No|
|**Security level for restricted sites**|Yes|No|
|**Send Do Not Track header**|Yes|No|
|**Allow Enterprise Mode menu access**|Yes|No|
|**Enterprise Mode site list location**|Yes|No|

### Device capabilities settings - cellular

|Setting name|Windows 8.1 and Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Allow data roaming**|Yes|No|

## Deploy the Configuration Policy

1.  Deploy the configuration policy to one or more groups of users or devices in your organization.

For more information about how to deploy policies, see [Use policies to manage computers and mobile devices with Microsoft Intune](../Topic/Use-policies-to-manage-computers-and-mobile-devices-with-Microsoft-Intune.md).

A status summary and alerts in the **Policy** workspace identify issues with the policy that require your attention. Additionally, a status summary appears in the **Dashboard** workspace.

## See Also
[Use policies to manage computers and mobile devices with Microsoft Intune](../Topic/Use-policies-to-manage-computers-and-mobile-devices-with-Microsoft-Intune.md)

