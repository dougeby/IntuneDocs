---
title: Configure Intune certificate profiles
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 679a20a1-e66f-4b6b-bd8f-896daf1f8175
author: Lizap
---
# Configure Intune certificate profiles
After your infrastructure and certificates are configured as described in [Configure certificate infrastructure](Configure-certificate-infrastructure.md), you can configure certificate profiles:

**Task 1** - Export the Trusted Root CA certificate 
**Task 2** - Create Trusted CA certificate profiles 
**Task 3** - Either:

Create SCEP certificate profiles

Create .PFX certificate profiles

### <a name="BKMK_ConfigExportRootCA"></a>Task 1 - Export the Trusted Root certificate
Export the Trusted Root CA certificate as a **.cer** file from the issuing CA, or any device that trusts your issuing CA. You do not export the private key.

You will import this certificate when you configure a Trusted  certificate profile.

### <a name="BKMK_ConfigRootCA"></a>Task 2 - Create Trusted certificate profiles
You must create a **Trusted certificate profile** before you can create a SCEP or .PFX certificate profile. You need a Trusted certificate profile and a SCEP or.PFS profile for each mobile device platform.

##### To create a trusted certificate profile

1.  Open the [Intune administration console](https://manage.microsoft.com), and click **Policy** &gt; **Add Policy**.

2.  Configure one of the following policy types:

    **Android &gt; Trusted Certificate Profile (Android 4 and later)**

    **iOS &gt; Trusted Certificate Profile (iOS 7.1 and later)**

    **Mac OS X &gt; Trusted Certificate Profile (Mac OS X 10.9 and later)**

    **Windows &gt; Trusted Certificate Profile (Windows 8.1 and later)**

    **Windows &gt; Trusted Certificate Profile (Windows Phone 8.1 and later)**

    Learn more: [Use policies to manage computers and mobile devices with Microsoft Intune](../Topic/Use-policies-to-manage-computers-and-mobile-devices-with-Microsoft-Intune.md).

3.  Provide the requested information to configure the trusted certificate profile settings for Android, iOS, Mac OS X, Windows 8.1, or Windows Phone 8.1. In the  **Certificate file** setting,  import the Trusted Root CA certificate (**.cer**) that you exported from your issuing CA. The **Destination store** setting applies only to devices running Windows 8.1 and later, and only if the device has more than one certificate store.


4.  When you are finished, click **Save Policy**.

The new policy displays in the **Policy** workspace, and can now be deployed.

### <a name="BKMK_ConfigSCEP"></a>Task 3 – Create SCEP or .PFX certificate profiles
After you have created a Trusted CA certificate profile, create SCEP or .PFX certificate profiles for each platform you want to use. When you create a SCEP certificate profile, you must specify a Trusted certificate profile for that same platform. This links the two certificate profiles, although you must still deploy each profile separately.

##### To create a SCEP certificate profile

1.  Open the [Intune administration console](https://manage.microsoft.com), click **Policy** &gt; **Add Policy**.

2.  Configure one of the following policy types:

    **Android &gt; SCEP Certificate Profile (Android 4 and later)**

    **iOS &gt; SCEP Certificate Profile (iOS 7.1 and later)**

    **Mac OS X &gt; SCEP Certificate Profile (Mac OS X 10.9 and later)**

    **Windows &gt; SCEP Certificate Profile (Windows 8.1 and later)**

    **Windows &gt; SCEP Certificate Profile (Windows Phone 8.1 and later)**

    Learn more: [Use policies to manage computers and mobile devices with Microsoft Intune](../Topic/Use-policies-to-manage-computers-and-mobile-devices-with-Microsoft-Intune.md).

3.  Follow the instructions on the profile configuration page to configure the SCEP certificate profile settings.

4.  When you are finished, click **Save Policy**.

The new policy displays in the **Policy** workspace, and can now be deployed.

##### To create a .PFX certificate profile

1.  Open the [Intune administration console](https://manage.microsoft.com), click **Policy** &gt; **Add Policy**.

2.  Configure one of the following policy types:



-   **Android &gt;.PFX Certificate Profile (Android 4 and later)**

    -   **Windows &gt; PKCS #12 (.PFX)  Certificate Profile (Windows 10 and later)**

    -   **Windows &gt; PKCS #12 (.PFX)  Certificate Profile (Windows Phone 10 and later)**
    
    -    **iOS > PKCS #12 (.PFX) Certificate Profile (iOS 7.1 and later)**    

    Learn more: [Use policies to manage computers and mobile devices with Microsoft Intune](../Topic/Use-policies-to-manage-computers-and-mobile-devices-with-Microsoft-Intune.md).

3.  Provide the information requested on the policy form. 

4.  When you are finished, click **Save Policy**.

The new policy displays in the **Policy** workspace, and can now be deployed.

## <a name="BKMK_Deploy"></a>Deploy certificate profiles
When you deploy certificate profiles, the certificate file from the Trusted CA certificate profile is installed on devices, and the SCEP or .PFX certificate profile is used by the device to create a certificate request by the device.

Certificate profiles install only on applicable devices based on the platform you use when creating the profile.

-   You can deploy certificate profiles to user collections or device collections.

    > [!TIP]
    > To allow certificates to be published to devices quickly after the device enrolls, deploy the certificate profile to a user group (not a device group). If you deploy to a device group, a full device registration must take place before the device receives policy.

-   Although each profile is deployed separately, both the Trusted Root and the SCEP/.PFX profile must be deployed or else the SCEP/.PFX certificate policy will fail.

You deploy certificate profiles the same way you deploy other policy for [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]. For information about how to deploy and manage policies, see [Use policies to manage computers and mobile devices with Microsoft Intune](../Topic/Use-policies-to-manage-computers-and-mobile-devices-with-Microsoft-Intune.md).

##  Next steps

You can now use certificates to help secure email, Wi-Fi, and VPN profiles:

-  [Configure access to corporate email using email profiles](Configure-access-to-corporate-email-using-email-profiles-with-Microsoft-Intune.md)
-  [Help users connect to company networks using Wi-Fi profiles](Help-users-connect-to-company-networks-using-Wi-Fi-profiles-with-Microsoft-Intune.md)
-  [Help users connect to their work using VPN profiles](Help-users-connect-to-their-work-using-VPN-profiles-with-Microsoft-Intune.md)
