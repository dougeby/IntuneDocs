---
# required metadata

title: Configure certificate profiles | Microsoft Intune
description: Learn how to create an Intune certificate profile.
keywords:
author: nbigman
manager: Arob98
ms.date: 07/21/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 679a20a1-e66f-4b6b-bd8f-896daf1f8175

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: kmyrup
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Configure Intune certificate profiles
After your infrastructure and certificates are configured as described in [Configure certificate infrastructure for SCEP](configure-certificate-infrastructure-for-scep.md) or [Configure certificate infrastructure for PFX](configure-certificate-infrastructure-for-pfx.md), you can configure certificate profiles:

**Task 1** - Export the Trusted Root CA certificate
**Task 2** - Create Trusted CA certificate profiles
**Task 3** - Either:

Create SCEP certificate profiles

Create .PFX certificate profiles

### Task 1 - Export the Trusted Root certificate
Export the Trusted Root CA certificate as a **.cer** file from the issuing CA, or any device that trusts your issuing CA. You do not export the private key.

You will import this certificate when you configure a Trusted  certificate profile.

### Task 2 - Create Trusted certificate profiles
You must create a **Trusted certificate profile** before you can create a SCEP or .PFX certificate profile. You need a Trusted certificate profile and a SCEP or .PFS profile for each mobile device platform.

##### To create a trusted certificate profile

1.  Open the [Intune administration console](https://manage.microsoft.com), and click **Policy** &gt; **Add Policy**.

2.  Configure one of the following policy types:

    **Android &gt; Trusted Certificate Profile (Android 4 and later)**

    **iOS &gt; Trusted Certificate Profile (iOS 7.1 and later)**

    **Mac OS X &gt; Trusted Certificate Profile (Mac OS X 10.9 and later)**

    **Windows &gt; Trusted Certificate Profile (Windows 8.1 and later)**

    **Windows &gt; Trusted Certificate Profile (Windows Phone 8.1 and later)**

    Learn more: [Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  Provide the requested information to configure the trusted certificate profile settings for Android, iOS, Mac OS X, Windows 8.1, or Windows Phone 8.1. In the  **Certificate file** setting,  import the Trusted Root CA certificate (**.cer**) that you exported from your issuing CA. The **Destination store** setting applies only to devices running Windows 8.1 and later, and only if the device has more than one certificate store.


4.  When you are finished, click **Save Policy**.

The new policy displays in the **Policy** workspace, and can now be deployed.

### Task 3 – Create SCEP or .PFX certificate profiles
After you have created a Trusted CA certificate profile, create SCEP or .PFX certificate profiles for each platform you want to use. When you create a SCEP certificate profile, you must specify a Trusted certificate profile for that same platform. This links the two certificate profiles, although you must still deploy each profile separately.

##### To create a SCEP certificate profile

1.  Open the [Intune administration console](https://manage.microsoft.com), click **Policy** &gt; **Add Policy**.

2.  Configure one of the following policy types:

    **Android &gt; SCEP Certificate Profile (Android 4 and later)**

    **iOS &gt; SCEP Certificate Profile (iOS 7.1 and later)**

    **Mac OS X &gt; SCEP Certificate Profile (Mac OS X 10.9 and later)**

    **Windows &gt; SCEP Certificate Profile (Windows 8.1 and later)**

    **Windows &gt; SCEP Certificate Profile (Windows Phone 8.1 and later)**

    Learn more: [Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

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

    Learn more: [Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  Provide the information requested on the policy form.

4.  When you are finished, click **Save Policy**.

The new policy displays in the **Policy** workspace, and can now be deployed.

## Deploy certificate profiles
When you deploy certificate profiles, the certificate file from the Trusted CA certificate profile is installed on devices, and the SCEP or .PFX certificate profile is used by the device to create a certificate request by the device.

Certificate profiles install only on applicable devices based on the platform you use when creating the profile.

-   You can deploy certificate profiles to user collections or device collections.

    > [!TIP]
    > To allow certificates to be published to devices quickly after the device enrolls, deploy the certificate profile to a user group (not a device group). If you deploy to a device group, a full device registration must take place before the device receives policy.

-   Although each profile is deployed separately, both the Trusted Root and the SCEP/.PFX profile must be deployed or else the SCEP/.PFX certificate policy will fail.

You deploy certificate profiles the same way you deploy other policy for Intune:

1.  In the **Policy** workspace, select the policy you want to deploy, then click **Manage Deployment**.

2.  In the **Manage Deployment** dialog box:

    -   **To deploy the policy** - Select one or more groups to which you want to deploy the policy, then click **Add** &gt; **OK**.

    -   **To close the dialog box without deploying it** - Click **Cancel**.

When you select a deployed policy, you can view further information about the deployment in the lower part of the policies list.
###  Next steps

You can now use certificates to help secure email, Wi-Fi, and VPN profiles:

-  [Configure access to corporate email using email profiles](configure-access-to-corporate-email-using-email-profiles-with-Microsoft-Intune.md)
-  [Wi-Fi connections in Microsoft Intune](wi-fi-connections-in-microsoft-intune.md)
-  [VPN connections in Microsoft Intune](vpn-connections-in-microsoft-intune.md)
