---
title: MD Conversion - Help users connect to company networks using Wi-Fi profiles with Microsoft
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: c70c5549-07ef-4d79-8270-dc7c7b8979a6
---
# MD Conversion - Help users connect to company networks using Wi-Fi profiles with Microsoft
Use [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] Wi-Fi profiles to deploy wireless network settings to users and devices in your organization. These settings simplify connecting to wireless networks for end-users.

For example:

-   You install a new Wi-Fi network named **Contoso Wi-Fi** and want to provision all devices that run the iOS operating system with the settings required to connect to this network.

-   You create a Wi-Fi profile containing the settings necessary to connect to the **Contoso Wi-Fi** wireless network.

-   You then deploy this profile to all users with iOS devices.

-   Users find the new **Contoso Wi-Fi** network in the list of wireless networks and can easily connect to this network.

You can deploy Wi-Fi profiles to the following platforms:

-   Android 4.0 and later

-   iOS 7.1 and later

-   Mac OS X 10.9 and later

Additionally, for devices that run Windows 8.1 and later, you can import a Wi-Fi configuration profile that was previously exported to a file. For details, see [Import a Wi-Fi configuration profile (Windows 8.1 and later only)](../Topic/Help-users-connect-to-company-networks-using-Wi-Fi-profiles-with-Microsoft-Intune.md#BKMK_Import).

## Steps to create and deploy a Wi-Fi profile

### Step 1: Create a Wi-Fi profile and supply general information

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Policy** &gt; **Add Policy**.

2.  Select one of the following policy types, and then click **Create Policy**:

    -   **Wi-Fi Profile (Android 4 and later)**

    -   **Wi-Fi Profile (iOS 7.1 and later)**

    -   **Wi-Fi Profile (Mac OS X 10.9 and later)**

    There are no recommended settings for this policy type. You must create a custom policy.

3.  Specify the following general values:

    |Setting|More information|
    |-----------|--------------------|
    |**Name**|Enter a unique name for the Wi-Fi profile to help identify it in the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] console.|
    |**Description**|Provide a description of the Wi-Fi profile that helps you to locate it.|

### Step 2: Configure network connection settings
Specify the **Network Connections** values:

|Setting|More information|
|-----------|--------------------|
|**Network name**|Specify a descriptive name for the wireless network. This is the name that displays on a user’s device when they choose a wireless network.|
|**SSID (Service Set Identifier)**|Specify the (SSID) of the wireless network that you want devices to connect to. The SSID is case-sensitive and is not displayed to users.|
|**Connect automatically when this network is in range**|Select this option to automatically connect devices to the wireless network when it is in range.|
|**Connect when the network is not broadcasting its name (SSID)**|Select this option to allow devices to connect to the network when it is not visible in the list of networks (because it is hidden and not broadcasting its name).|

### Step 3: Configure security settings
Configure the **Security Settings** for the selected platform. The available settings depend on the security types you select.

#### For Android devices

|Setting name|More information|Use when:|
|----------------|--------------------|-------------|
|**Security type**|Select the security protocol for the wireless network:<br /><br />**WPA-Enterprise/WPA2-Enterprise**<br /><br />**No authentication (Open)** if the network is unsecured.|Always|
|**EAP Type**|Choose the Extensible Authentication Protocol (EAP) type used to authenticate secured wireless connections:<br /><br />**EAP-TLS**<br /><br />**PEAP**<br /><br />**EAP-TTLS**|You selected the **WPA-Enterprise/WPA2-Enterprise** security type.|
|**Select root certificates for server validation**|Click **Select**, then choose the trusted root certificate profile used to authenticate the connection.<br /><br />To create the trusted root certificate profile, see [Enable access to company resources using certificate profiles with Microsoft Intune](../Topic/Enable-access-to-company-resources-using-certificate-profiles-with-Microsoft-Intune.md).|Any **EAP Type** is selected.|
|**Authentication method**|Select the authentication method for the connection:<br /><br />**Certificates** to specify the client certificate<br /><br />**Username and Password** to specify a different method for authentication|The **EAP type** is **PEAP** or **EAP-TTLS**.|
|**Select a non-EAP method for authentication (Inner identity)**|Select how you will authenticate the connection:<br /><br />**None**<br /><br />**Unencrypted password (PAP)**<br /><br />**Challenge Handshake Authentication Protocol (CHAP)**<br /><br />**Microsoft CHAP (MS-CHAP)**<br /><br />**Microsoft CHAP Version 2 (MS-CHAP v2)**<br /><br />The available options depend on the EAP type you selected.|The **Authentication method** is **Username and Password**.|
|**Enable identity privacy (Outer Identity)**|Specify the text sent in response to an EAP identity request. This text can be any value. During authentication, this anonymous identity is initially sent, and then followed by the real identification sent in a secure tunnel.|The **EAP type** is **PEAP** or **EAP-TTLS**.|
|**Select a client certificate for client authentication (Identity Certificate)**|Click **Select**, then choose the SCEP certificate profile used to authenticate the connection.<br /><br />To create a SCEP certificate profile, see [Enable access to company resources using certificate profiles with Microsoft Intune](../Topic/Enable-access-to-company-resources-using-certificate-profiles-with-Microsoft-Intune.md).|The security type is **WPA-Enterprise/WPA2-Enterprise**, and any **EAP type** is selected.|

#### For iOS and Mac OS X devices

|Setting name|More information|Use when:|
|----------------|--------------------|-------------|
|**Security type**|Select the wireless network security protocol:<br /><br />**WPA-Personal/WPA2-Personal**<br /><br />**WPA-Enterprise/WPA2-Enterprise**<br /><br />**WEP**<br /><br />**No authentication (Open)** if the network is unsecured.|Always|
|**EAP Type**|Choose the Extensible Authentication Protocol (EAP) type used to authenticate secured wireless connections:<br /><br />**EAP-TLS**<br /><br />**PEAP**<br /><br />**EAP-TLS**<br /><br />**EAP-AST**<br /><br />**LEAP**<br /><br />**EAP-SIM**|You selected a security type of **WPA-Enterprise/WPA2-Enterprise**.|
|**Trusted server certificate names**|Select the trusted root certificate profile used to authenticate the connection.<br /><br />To create the trusted root certificate profile, see [Enable access to company resources using certificate profiles with Microsoft Intune](../Topic/Enable-access-to-company-resources-using-certificate-profiles-with-Microsoft-Intune.md).|You selected an EAP type of **EAP-TLS**, **PEAP**, **EAP-TTLS** or **EAP-FAST**.|
|**Use Protected Access Credential (PAC)**|Select to use protected access credentials to establish an authenticated tunnel between the client and the authentication server. An existing PAC file is used if present.|The **EAP-type** is **EAP-FAST**.|
|**Provision PAC**|Provisions the PAC file to your devices.<br /><br />When used, you can also select **Provision PAC Anonymously** to ensure that the PAC file is provisioned without authenticating the server.|**Use Protected Access Credential (PAC)** is selected.|
|**Authentication method**|Select the authentication method used for the connection:<br /><br />**Certificates** to specify the client certificate<br /><br />**Username and Password** to specify one of the following non-EAP methods for authentication (also known as Inner identity):<br /><br />**None**<br /><br />**Unencrypted password (PAP)**<br /><br />**Challenge Handshake Authentication Protocol (CHAP)**<br /><br />**Microsoft CHAP (MS-CHAP)**<br /><br />**Microsoft CHAP Version 2 (MS-CHAP v2)**<br /><br />**EAP-TLS**|The **EAP type** is **PEAP**, or **EAP-TTLS**.|
|**Select a client certificate for client authentication (Identity Certificate)**|Select the SCEP certificate profile used to authenticate the connection.<br /><br />To create a SCEP certificate profile, see [Enable access to company resources using certificate profiles with Microsoft Intune](../Topic/Enable-access-to-company-resources-using-certificate-profiles-with-Microsoft-Intune.md).|When the security type is **WPA-Enterprise/WPA2-Enterprise** and the **EAP type** is **EAP-TLS**, **PEAP** or **EAP-TTLS**.|
|**Enable identity privacy (Outer Identity)**|Specify text that sent in response to an EAP identity request. This text can be any value.<br /><br />During authentication, this anonymous identity is initially sent, followed by the real identification sent in a secure tunnel.|When the **EAP type** is set to **PEAP**, **EAP-TTLS** or **EAP-FAST**.|

### Step 4: Configure proxy settings (iOS and MAC OS X only)

1.  For iOS and Mac OS X Wi-Fi profiles, configure the following settings (if you are using a proxy server to help secure your network) under **Proxy Settings**:

    |Setting name|Moe information|Use when:|
    |----------------|-------------------|-------------|
    |**Proxy settings for this Wi-Fi connection**|Choose the proxy settings type:<br /><br />**None** (default)<br /><br />**Manual** -   Manually specify the URL and port number of the proxy server.<br /><br />**Automatic** – Use a configuration file to configure the proxy server.|Always|
    |**Proxy server address** and **Port number**|Specify the URL and port number of the proxy server.|**Proxy settings for this Wi-Fi connection** is set to **Manual**|
    |**Proxy Server URL**|Specify the URL of the file containing the proxy server settings.|**Proxy settings for this Wi-Fi connection** is set to **Automatic**|

### Step 5: Save the Wi-Fi profile

1.  When you are finished, click **Save Policy**.

The new policy displays in the **Configuration Policies** node of the **Policy** workspace.

### Step 6: Deploy the Wi-Fi profile

1.  Deploy the Wi-Fi profile to one or more groups of users or devices in your organization.

For more information about how to deploy policies, see [Use policies to manage computers and mobile devices with Microsoft Intune](../Topic/Use-policies-to-manage-computers-and-mobile-devices-with-Microsoft-Intune.md).

A status summary and alerts in the **Policy** workspace identify issues with the policy that require your attention. Additionally, a status summary appears in the **Dashboard** workspace.

After successful deployment, users devices can automatically connect to the corporate wireless network you configured.

## <a name="BKMK_Import"></a>Import a Wi-Fi configuration profile (Windows 8.1 and later only)
Use the **Windows Wi-Fi Import Policy** to import a set of Wi-Fi settings that you can then deploy to the required user or device groups.

> [!TIP]
> In Windows, you can use the **netsh wlan** utility to export an existing Wi-Fi profile to an XML file readable by [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].
> 
> For example, to export a Wi-Fi connection named **MyConnection** to an XML file, type the following from a Windows command prompt:
> 
> **netsh wlan export profile MyConnection**

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Policy** &gt; **Add Policy**.

2.  Configure a policy of the type **Windows** &gt; **Windows Wi-Fi Import Policy**.

    You can only create and deploy a custom Windows Wi-Fi import policy. Recommended settings are not available.

    For more information about how to create and deploy policies, see the [Use policies to manage computers and mobile devices with Microsoft Intune](../Topic/Use-policies-to-manage-computers-and-mobile-devices-with-Microsoft-Intune.md) topic.

3.  Specify the following general values for the Windows Wi-Fi Import Policy:

    |Setting name|More information|
    |----------------|--------------------|
    |**Name**|Enter a unique name for the Wi-Fi profile to identify it in the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] console.|
    |**Description**|Provide a description w of the Wi-Fi profile and other relevant information that helps you to locate it.|

4.  Specify the following values under the **Custom Wi-Fi Profile** heading:

    |Setting name|More information|
    |----------------|--------------------|
    |**Configuration profile file**|Click **Import** to select the XML file containing the Wi-Fi profile settings that you want to import into [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].|
    |**Custom configuration profile name (displayed to users)**|Displays the name of the Wi-Fi configuration profile as it will be shown to users on their device.|
    |**Configuration profile details**|Displays the XML code for the configuration profile you selected.|

5.  When you are finished, click **Save Policy**.

6.  The new policy displays in the **Configuration Policies** node of the **Policy** workspace.

You can now use the information in **Step 6** above to help you deploy the custom Wi-Fi profile.

## See Also
[Enable access to company resources with Microsoft Intune - deleted](../Topic/Enable-access-to-company-resources-with-Microsoft-Intune---deleted.md)

