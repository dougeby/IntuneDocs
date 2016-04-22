---
title: MD Conversion - Mobile device security policy settings in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: cf3cc1ba-ffe9-4c9a-b005-f24e9afd1ee6
---
# MD Conversion - Mobile device security policy settings in Microsoft Intune
> [!IMPORTANT]
> [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] now features separate configuration policies for each device platform, and these policies contain the most up-to-date settings you can use. You can continue to use the mobile device security policy and any existing deployments will still work. However, you should plan to migrate to the new configuration policies as soon as possible as the mobile device security policy will be removed in the future.

Use [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] mobile device security policies to configure a wide range of settings that you can deploy to managed devices in your organization. These settings can be used to control the functionality and security of your devices.

You can create and deploy mobile device security policies for the following device types:

-   Windows RT 8.1 and enrolled Windows 8.1 devices

-   Windows RT

-   Windows Phone 8 and Windows Phone 8.1

-   iOS

-   Android and Samsung KNOX

> [!NOTE]
> Some settings are not applicable to some devices. See the table below for a full list of settings you can configure.

## Create a mobile device security policy

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Policy** &gt; **Add Policy**.

2.  Click **Common Mobile Device Settings** &gt; **Mobile Device Security**.

3.  Choose whether you want to create a policy that contains recommended settings, or whether you want to create a custom policy, and then click **Create Policy**.

    > [!TIP]
    > Click the information icon next to each setting to view the recommended value for the setting.

    For more information about how to create and deploy policies, see the [Use policies to manage computers and mobile devices with Microsoft Intune](../Topic/Use-policies-to-manage-computers-and-mobile-devices-with-Microsoft-Intune.md) topic.

4.  See the [Policy settings for mobile devices](../Topic/Mobile-device-security-policy-settings-in-Microsoft-Intune.md#BKMK_Settings) section in this topic for information about the settings you can configure.

5.  When you are finished, click **Save Policy**.

The new policy displays in the **Configuration Policies** node of the **Policy** workspace.

## Deploy a mobile device security policy

1.  Deploy the mobile device security policy to one or more groups of users or devices in your organization.

For more information about how to deploy policies, see [Use policies to manage computers and mobile devices with Microsoft Intune](../Topic/Use-policies-to-manage-computers-and-mobile-devices-with-Microsoft-Intune.md).

A status summary and alerts on the **Overview** page of the **Policy** workspace identify issues with the policy that require your attention. Additionally, a status summary appears in the **Dashboard** workspace.

> [!IMPORTANT]
> It might take up to 24 hours for status information to appear in the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] admin console.

## <a name="BKMK_Settings"></a>Policy settings for mobile devices

### <a name="BKMK_sec"></a>Security settings

|Setting name|Windows 8.1 and Windows RT 8.1|Windows RT|Windows Phone 8 and Windows Phone 8.1|iOS|Android and Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Require a password to unlock mobile devices**|No|No|Yes|Yes|Yes|
|**Required password type**<br /><br />(specifies the type of password that will be required, such as numeric only, or alphanumeric)|Yes|Yes|Yes|Yes|No|
|**Required password type – Minimum number of character sets**<br /><br />There are four character sets, lowercase letters, uppercase letters, numbers, and symbols. This setting specifies how many different character sets must be included in the password). However, for iOS devices, this specifies the number of symbol characters must be included in the password)|Yes|Yes|Yes|Yes|No|
|**Minimum password length**|Yes|Yes|Yes|Yes|Yes|
|**Allow simple passwords**<br /><br />Simple passwords include ‘0000’ and ‘1234’|No|No|Yes|Yes|No|
|**Number of repeated sign-in failures to allow before the device is wiped**|Yes|Yes|Yes|Yes|Yes|
|**Minutes of inactivity before screen turns off**<sup>1</sup>|Yes|Yes|Yes|Yes|Yes|
|**Password expiration (days)**|Yes|Yes|Yes|Yes|Yes|
|**Remember password history**|Yes|Yes|Yes|Yes|Yes|
|**Remember password history** – **Prevent reuse of previous passwords**|Yes|Yes|Yes|Yes|Yes|
|**Password quality**|No|No|No|No|Yes|
|**Allow picture password and PIN**|Yes|Yes|No|No|No|
|**Minutes of inactivity before password is required**|No|No|No|Yes|No|
|**Allow fingerprint unlock**|No|No|No|iOS 7 and later|No|
For iOS devices, when you configure the settings **Minutes of inactivity before screen turns off** and **Minutes of inactivity before password is required**, they are applied in sequence. For example, if you set the value for both settings to **5** minutes, the screen will turn off automatically after 5 minutes, and the device will be locked after an additional 5 minutes. However, if the user turns off the screen manually, the second setting is immediately applied. In the same example, after the user turns off the screen, the device will lock 5 minutes later.

When you set deploy a password length policy to devices that run Windows RT, users will be forced to reset their password, even if their current password complies with the policy requirements.

### Encryption settings

|Setting name|Windows 8.1 and Windows RT 8.1|Windows RT|Windows Phone 8 and Windows Phone 8.1|iOS|Android and Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Require encryption on mobile device**<sup>1</sup><br /><br />For Windows Phone 8 devices, you must set this to **Yes**.<br /><br />To enable encryption on iOS devices, enable the setting **Require a password to unlock mobile devices**.|Yes|No|Yes|No|Yes|
|**Require encryption on storage cards**<br /><br />Applies to devices that are managed by Exchange ActiveSync also.|n/a|n/a|n/a (apps and associated data are automatically encrypted)|n/a|Yes|
Additional information for devices that run Windows 8.1

-   To enforce encryption on devices that run Windows 8.1, you must install the [December 2014 MDM client update for Windows](http://support.microsoft.com/kb/3013816) on each device.

-   If you enable this setting for Windows 8.1 devices, all users of the device must have a Microsoft Account.

-   For encryption to work, the device must meet the Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) hardware certification requirements.

-   When you enforce encryption on a device, the recovery key is only accessible from the users Microsoft Account, accessed from their OneDrive account. You cannot recover this key on behalf of a user.

### Malware settings

|Setting name|Windows 8.1 and Windows RT 8.1|Windows RT|Windows Phone 8 and Windows Phone 8.1|iOS|Android and Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Require network firewall**|Yes|No|No|No|No|
|**Enable SmartScreen**|Yes|No|No|No|No|

### System settings

|Setting name|Windows 8.1 and Windows RT 8.1|Windows RT|Windows Phone 8 and Windows Phone 8.1|iOS|Android and Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Require automatic updates**|Yes|No|No|No|No|
|**Require automatic updates – Minimum classification of updates to install automatically**<br /><br />Choose the classification of updates that will be installed automatically:<br /><br />**Important** – Installs all updates classified as important.<br /><br />**Recommended** – Installs all updates classified as important or recommended.|Yes|No|No|No|No|
|**Allow screen capture**|No|No|Windows Phone 8.1 only|Yes|Yes (Samsung KNOX only)|
|**Allow control center in lock screen**|No|No|No|iOS 7 and later|No|
|**Allow notification view in lock screen**|No|No|No|iOS 7 and later|No|
|**Allow today view in lock screen**|No|No|No|iOS 7 and later|No|
|**User Account Control**|Yes|No|No|No|No|
|**Allow diagnostic data submission**|Yes|No|Windows Phone 8.1 only|Yes|Yes (Samsung KNOX only)|
|**Allow untrusted TLS certificates**|No|No|No|Yes|No|
|**Allow personal wallet software while locked**|No|No|No|Yes|No|
|**Allow factory reset**|No|No|No|No|Yes (Samsung KNOX only)|
To enforce encryption on devices that run Windows 8.1, you must install the [December 2014 MDM client update for Windows](http://support.microsoft.com/kb/3013816) on each device.

### <a name="BKMK_cloud"></a>Cloud settings – documents and data

|Setting name|Windows 8.1 and Windows RT 8.1|Windows RT|Windows Phone 8 and Windows Phone 8.1|iOS|Android and Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Allow backup to iCloud**|No|No|No|Yes|No|
|**Allow document sync to iCloud**|No|No|No|Yes|No|
|**Allow Photo Stream sync to iCloud**|No|No|No|Yes|No|
|**Require encrypted backup**|No|No|No|Yes|No|
|**Work Folders URL**<br /><br />(sets the URL of the work folder to allow documents to be synchronized across devices)|Yes|No|No|No|No|
|**Allow Google backup**|No|No|No|No|Yes (Samsung KNOX only)|

### Cloud settings – accounts and synchronization

|Setting name|Windows 8.1 and Windows RT 8.1|Windows RT|Windows Phone 8 and Windows Phone 8.1|iOS|Android and Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Allow Microsoft account**|No|No|Windows Phone 8.1 only|No|No|
|**Allow Google account auto sync**|No|No|No|No|Yes (Samsung KNOX only)|

### <a name="BKMK_email"></a>Email settings

|Setting name|Windows 8.1 and Windows RT 8.1|Windows RT|Windows Phone 8 and Windows Phone 8.1|iOS|Android and Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Allow users to download email attachments**<sup>1</sup>|n/a|n/a|n/a|n/a|n/a|
|**Email synchronization period** Applies to devices that are managed by Exchange ActiveSync also.|n/a|n/a|n/a|n/a|n/a|
|**Allow mobile devices that don’t fully support these settings to synchronize with Exchange (Exchange ActiveSync)** Applies to devices that are managed by Exchange ActiveSync also.|n/a|n/a|n/a|n/a|n/a|
|**Make Microsoft account optional in Windows Mail application**|Yes|No|No|No|No|
|**Allow custom email accounts**|No|No|Windows Phone 8.1 only|No|No|

### <a name="BKMK_browser"></a>Application settings - browser

|Setting name|Windows 8.1 and Windows RT 8.1|Windows RT|Windows Phone 8 and Windows Phone 8.1|iOS|Android and Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Allow web browser**|No|No|Windows Phone 8.1 only|Yes|Yes (Samsung KNOX only)|
|**Allow autofill**|Yes|No|No|Yes|Yes (Samsung KNOX only)|
|**Allow pop-up blocker**|Yes|No|No|Yes|Yes (Samsung KNOX only)|
|**Allow cookies**|No|No|No|Yes|Yes (Samsung KNOX only)|
|**Allow plug-ins**|Yes|No|No|No|No|
|**Allow active scripting**|Yes|No|No|Yes|Yes (Samsung KNOX only)|
|**Allow fraud warning**|Yes|No|No|Yes|No|
|**Allow intranet site for single word entry**<br /><br />(allows use of a single word to direct Internet Explorer to a web site, such as ‘Bing’)|Yes|No|No|No|No|
|**Allow automatic detection of intranet network**|Yes|No|No|No|No|
|**Security level for Internet**|Yes|No|No|No|No|
|**Security level for intranet**|Yes|No|No|No|No|
|**Security level for trusted sites**|Yes|No|No|No|No|
|**Security level for restricted sites**|Yes|No|No|No|No|
|**Send Do Not Track header**|Yes|No|No|No|No|
|**Allow Enterprise Mode menu access**|Yes|No|No|No|No|
|**Enterprise Mode site list location**|Yes|No|No|No|No|

### <a name="BKMK_apps"></a>Application settings - apps

|Setting name|Windows 8.1 and Windows RT 8.1|Windows RT|Windows Phone 8 and Windows Phone 8.1|iOS|Android and Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Allow application store**|No|No|Windows Phone 8.1 only|Yes|Yes (Samsung KNOX only)|
|**Require a password to access application store**|No|No|No|Yes|No|
|**Allow in-app purchases**|No|No|No|Yes|No|
|**Allow managed documents in other unmanaged apps**|No|No|No|iOS 7 and later|No|
|**Allow unmanaged documents in other managed apps**|No|No|No|iOS 7 and later|No|
|**Allow video conferencing**|No|No|No|Yes|No|
|**Allow adult content in media store**|No|No|No|Yes|No|
|**Allow app installation**|No|No|No|iOS 6 and later|No|

### Application settings - gaming

|Setting name|Windows 8.1 and Windows RT 8.1|Windows RT|Windows Phone 8 and Windows Phone 8.1|iOS|Android and Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Allow Game Center friends**|No|No|No|Yes|No|
|**Allow multiplayer gaming**|No|No|No|Yes|No|

### <a name="BKMK_hard"></a>Device capabilities settings - hardware

|Setting name|Windows 8.1 and Windows RT 8.1|Windows RT|Windows Phone 8 and Windows Phone 8.1|iOS|Android and Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Allow camera**|No|No|Windows Phone 8.1 only|Yes|Yes|
|**Allow removable storage**|No|No|Yes|No|Yes (Samsung KNOX only)|
|**Allow Wi-Fi**|No|No|Windows Phone 8.1 only|No|Yes (Samsung KNOX only)|
|**Allow Wi-Fi tethering**|No|No|Windows Phone 8.1 only|No|Yes (Samsung KNOX only)|
|**Allow automatic connection to free Wi-Fi hotspots**|No|No|Windows Phone 8.1 only|No|No|
|**Allow Wi-Fi hotspot reporting**<br /><br />(send information about Wi-Fi connections to help discover nearby connections)|No|No|Windows Phone 8.1 only|No|No|
|**Allow geolocation**<br /><br />(allows the device to utilize location information)|No|No|Windows Phone 8.1 only|No|Yes (Samsung KNOX only)|
|**Allow NFC**<br /><br />(allows operations that use near field communication)|No|No|Windows Phone 8.1 only|No|Yes (Samsung KNOX only)|
|**Allow Bluetooth**|No|No|Windows Phone 8.1 only|No|Yes (Samsung KNOX only)|
|**Allow power off** If disabled, the setting **Number of repeated sign in failures to allow before the device is wiped** for Samsung KNOX devices does not function.|No|No|No|No|Yes (Samsung KNOX only)|

### Device capabilities settings - cellular

|Setting name|Windows 8.1 and Windows RT 8.1|Windows RT|Windows Phone 8 and Windows Phone 8.1|iOS|Android and Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Allow voice roaming**|No|No|No|Yes|Yes (Samsung KNOX only)|
|**Allow data roaming**|Yes|No|No|Yes|Yes (Samsung KNOX only)|
|**Allow automatic synchronization while roaming**|No|No|No|Yes|No|
|**Allow SMS/MMS messaging**|No|No|No|No|Yes (Samsung KNOX only)|

### Device capabilities settings - features

|Setting name|Windows 8.1 and Windows RT 8.1|Windows RT|Windows Phone 8 and Windows Phone 8.1|iOS|Android and Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Allow voice assistant**|No|No|No|Yes|Yes (Samsung KNOX only)|
|**Allow voice assistant while device is locked**|No|No|No|Yes|No|
|**Allow voice dialing**|No|No|No|Yes|Yes (Samsung KNOX only)|
|**Allow copy and paste**|No|No|Windows Phone 8.1 only|No|Yes (Samsung KNOX only)|
|**Allow clipboard share between applications**|No|No|No|No|Yes (Samsung KNOX only)|
|**Allow YouTube**|No|No|No|No|Yes (Samsung KNOX only)|

## See Also
[Use policies to manage computers and mobile devices with Microsoft Intune](../Topic/Use-policies-to-manage-computers-and-mobile-devices-with-Microsoft-Intune.md)

