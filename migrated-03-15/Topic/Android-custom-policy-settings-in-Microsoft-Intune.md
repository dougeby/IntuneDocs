---
title: Android custom policy settings in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 15904440-5a05-47c9-818e-48073b4090e7
author: robstackmsft
---
# Android custom policy settings in Microsoft Intune
Use the [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] **Android custom configuration policy** to deploy OMA-URI (Open Mobile Alliance Uniform Resource Identifier) settings that can be used to control features on Android devices. These are standard settings that many mobile device manufacturers use to control device features.

This capability is intended to allow you to deploy Android settings that are not configurable with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] policies. For information about the settings you can configure with these policies, see [Manage settings and features on your devices with Microsoft Intune policies](../Topic/Manage-settings-and-features-on-your-devices-with-Microsoft-Intune-policies.md).

> [!NOTE]
> Currently, Android custom policies only support configuring Wi-Fi settings for Android devices that include a pre-shared key. See [Example: Configure a custom Wi-Fi profile with a pre-shared key](../Topic/Android-custom-policy-settings-in-Microsoft-Intune.md#BKMK_Example) to learn how to do this.

## How to create an Android custom policy

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Policy** &gt; **Overview** &gt; **Add Policy**.

2.  Configure a policy of the type **Android** &gt; **Custom Configuration**.

    For help creating and deploying policies, see [Use policies to manage computers and mobile devices with Microsoft Intune](../Topic/Use-policies-to-manage-computers-and-mobile-devices-with-Microsoft-Intune.md).

    You can only create and deploy a custom policy of this type. Recommended settings are not available.

3.  Use the following table to help you configure the general policy settings:

    |Setting name|More information|
    |----------------|--------------------|
    |**Name**|Enter a unique name for the Android custom policy to help you identify it in the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] console.|
    |**Description**|Provide a description that gives an overview of the Android custom policy and other relevant information that helps you to locate it.|

4.  In the **OMA-URI Settings** section, click **Add** to add a setting. You can also edit or delete an existing setting.

5.  In the **Add or Edit OMA-URI Setting** dialog box, specify the following information:

    |Item|More information|
    |--------|--------------------|
    |**Setting name**|Enter a unique name for the OMA-URI setting to help you identify it in the list of settings.|
    |**Setting description**|Provide a description that gives an overview of the setting and other relevant information to help you locate it.|
    |**Data type**|Select the date type in which you will specify this OMA-URI setting. Choose from  **String, String (XML), Date and time, Integer, Floating point**, or **Boolean**.|
    |**OMA-URI (case sensitive)**|Specify the OMA-URI you want to supply a setting for.|
    |**Value**|Specify the value to associate with the OMA-URI you specified previously.|

6.  Click **OK** to save the setting and return to the **Create Policy** page.

7.  Continue to add as many settings as you require. When you are done, click **Save Policy**.

8.  The new policy displays in the **Configuration Policies** node of the **Policy** workspace.

## Deploy an Android custom policy

-   Deploy the Android custom policy to one or more groups of users or devices in your organization.

For help deploying policies, see [Use policies to manage computers and mobile devices with Microsoft Intune](../Topic/Use-policies-to-manage-computers-and-mobile-devices-with-Microsoft-Intune.md).

A status summary and alerts on the **Overview** page of the **Policy** workspace identify issues with the policy that require your attention. Additionally, a status summary appears in the **Dashboard** workspace.

## <a name="BKMK_Example"></a>Example: Configure a custom Wi-Fi profile with a pre-shared key
Although [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] supports Wi-Fi profiles for Android devices, this feature does not currently support the inclusion of a pre-shared key in the configuration. In this example, you’ll learn how to create an Android custom policy that creates a Wi-Fi profile with a pre-shared key on the Android device.

#### To create a Wi-Fi profile with a pre-shared key

1.  Ensure that your users are using the latest version of the [Intune Company Portal](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) app for Android.

2.  Create an Android custom policy and add the following settings:

    |Setting name|More information|
    |----------------|--------------------|
    |**Setting name**|Specify a name of your choice for the setting.|
    |**Setting description**|Specify a description for the setting.|
    |**Data type**|Select **String (XML)**.|
    |**OMA-URI**|Enter the following: ./Vendor/MSFT/WiFi/Profile/*&lt;your Wi-Fi profile&gt;*/Settings|

3.  For **Value**, copy and paste the following XML code:

    ```
    <!--
    WEP Wifi Profile
                    <Name of wifi profile> = Name of profile 
                    <SSID of wifi profile> = Plain text of SSID. Does not need to be escaped, could be <name>Your Company's Network</name>
                    <WEP password> = Password to connect to the network
    -->
    <WLANProfile 
    xmlns="http://www.microsoft.com/networking/WLAN/profile/v1">
      <name><Name of wifi profile></name>
      <SSIDConfig>
        <SSID>
          <name><SSID of wifi profile></name>
        </SSID>
      </SSIDConfig>
      <connectionType>ESS</connectionType>
      <MSM>
        <security>
          <authEncryption>
            <authentication>open</authentication>
            <encryption>WEP</encryption>
            <useOneX>false</useOneX>
          </authEncryption>
          <sharedKey>
            <keyType>networkKey</keyType>
            <protected>false</protected>
            <keyMaterial><WEP password></keyMaterial>
          </sharedKey>
          <keyIndex>0</keyIndex>
        </security>
      </MSM>
    </WLANProfile>
    ```

4.  When you are done, save the policy and deploy it to the required Android devices. The new Wi-Fi profile will appear in the list of connections on the device.

## See Also
[Use policies to manage computers and mobile devices with Microsoft Intune](../Topic/Use-policies-to-manage-computers-and-mobile-devices-with-Microsoft-Intune.md)

