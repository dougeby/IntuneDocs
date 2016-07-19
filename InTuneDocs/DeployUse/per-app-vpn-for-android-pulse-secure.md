---
# required metadata

title: Per-app VPN for Android using Pulse Secure | Microsoft Intune
description: You can create a per-app VPN profile for Android devices managed by Intune. 
keywords:
author: nbigman
manager: jeffgilb
ms.date: 05/08/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: ac65e906-3922-429f-8d9c-d313d3126645

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: chrisbal
#ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Use a custom policy to create a per-app VPN profile for Android devices

You can create a per-app VPN profile for Android devices managed by Intune. First you'll create a VPN profile  that uses the Pulse Secure connection type, and then a custom configuration policy that associates that profile with specific apps. After you deploy those policies to your Android device or user groups, opening one of the specified apps on those devices will open a VPN connection for that app. 

### Step 1:  Create a VPN profile

1. In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Policy** > **Add Policy**.
2. Select a template for the new policy by expanding **Android**, then choose **VPN Profile (Android 4 and later)**.

3. In the template, for **Connection type**, choose **Pulse Secure**.
4. Complete and save the VPN profile. For more details about VPN profiles see [VPN connections](vpn-connections-in-microsoft-intune.md).

> [!NOTE]
Take note of the VPN profile name for use in the next step.	For example, **MyAppVpnProfile**.
   
### Step 2:  Create a custom configuration policy
	
   1. In the Intune admin console **Policy** -> **Add Policy** -> **Android** -> **Custom configuration** -> **Create Policy**.
   2. Provide a name for the policy.
   3. Under **OMA-URI settings**, click **Add**.
   4. Provide a setting name.
   5. For **Data type** specify **String**.
   6. for **OMA-URI** specify this string: **./Vendor/MSFT/VPN/Profile/*Name*/PackageList**, where *Name* is the VPN profile name you noted in Step 1. In our example, the string would be **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/PackageList**.
   7.	In **Value**, provide a semicolon-separated list of packages that should be associated with the profile.  For example, if you want Excel and the Google Chrome browser to use the VPN connection, then you would enter: **com.microsoft.office.excel;com.android.chrome**.
  

   ![Example Android per-app VPN custom policy](..\media\android_per_app_vpn_oma_uri.png) 
#### Set your app list as Blacklist or Whitelist (optional)
You can specify that your list of apps will *not* be allowed to use the VPN connection, by using the **BLACKLIST** value.  All other apps will connect through VPN.

Alternatively, you can specify that *only* the specified apps will be able to use the VPN connection, by using the **WHITELIST** value.
 

1.	Under OMA-URI settings, click **Add**.
2.	Provide a setting name.
3.	For **Data type** specify **String**.
4.	For **OMA-URI** specify this string: **./Vendor/MSFT/VPN/Profile/*Name*/Mode**, where *Name* is the VPN profile name you noted in Step 1. In our example, the string would be **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/Mode**.
5.	In **Value**, enter **BLACKLIST** or **WHITELIST**. 


   
### Step 3: Deploy both policies

You must deploy *both* policies to the *same* Intune groups.

   1.  In the **Policy** workspace, select the policy you want to deploy, then click **Manage Deployment**.

2.  In the **Manage Deployment** dialog box:

    -   **To deploy the policy** - Select one or more groups to which you want to deploy the policy, then click **Add** &gt; **OK**.

    -   **To close the dialog box without deploying it** - Click **Cancel**.

A status summary and alerts on the **Overview** page of the **Policy** workspace identify issues with the policy that require your attention. Additionally, a status summary appears in the Dashboard workspace.

