---
# required metadata

title: How to configure certificates with Microsoft Intune | Microsoft Docs
description: Description.
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/03/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 5eccfa11-52ab-49eb-afef-a185b4dccde1

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# How to configure certificates with Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

When you give users access to corporate resources through VPN, Wi-Fi, or email profiles, you can secure the access by using a certificate that is installed on each user device. The high-level workflow is as follows:

1. Ensure you have the right certificate infrastructure in place.
2. Install a root certificate or an intermediate Certification Authority (CA) certificate on each device so that the device recognizes the legitimacy of your CA. To do this, create and deploy a **trusted certificate profile**. When you deploy this profile, the devices that you manage with Intune will request and receive the root certificate. You have to create a separate profile for each platform. Trusted certificate profiles are available for these platforms:
	- iOS 8.0 and later
	- Mac OS X 10.9 and later
	- Android 4.0 and later
	<!--Android for Work --->
	- Windows 8.1 and later
	- Windows Phone 8.1 and later
3. Create certificate profiles so that devices request a certificate to be used for authentication of VPN, Wi-Fi, and email access. You can create and deploy a **PKCS** or a **SCEP** certificate profile for devices running these platforms:
	- iOS 8.0 and later
	- Android 4.0 and later
	- Android for Work
	- Windows 10 (desktop and mobile) and later

	You can only use a SCEP certificate profile with these platforms:
	- Mac OS X 10.9 and later
	- Windows Phone 8.1 and later

You must create a separate profile for each platform. When you create the profile, associate it with the trusted root certificate profile that you've already created.

### Notes

- If you don't have an Enterprise Certification Authority, you must create one.
- If you decide, based on your device platforms, to use the Simplified Certificate Enrollment Protocol (SCEP) profile, you'll also need to configure a Network Device Enrollment Service (NDES) server.
- Whether you plan to use SCEP or .PFX profiles, you must download and configure the Microsoft Intune Certificate Connector.

## Before you start


### If you will use SCEP certificates

Complete the necessary prerequisites in [Certificate infrastructure for SCEP](/intune-azure/configure-devices/configure-certificate-infrastructure-for-scep).

### If you will use PFX certificates

Complete the necessary prerequisites in [Certificate infrastructure for PFX](/intune-azure/configure-devices/configure-certificate-infrastructure-for-pfx).

## Task 1: Export the Trusted Root CA certificate
Export the Trusted Root Certification Authorities (CA) certificate as a **.cer** file from the issuing CA, or from any device that trusts your issuing CA. Do not export the private key.

You'll import this certificate when you set up a trusted certificate profile.

## Task 2: Create Trusted certificate profiles
You must create a Trusted certificate profile before you can create a Simple Certificate Enrollment Protocol (SCEP) or a PKCS certificate profile. You need a Trusted certificate profile and an SCEP or .PFX profile for each device platform.

### To create a Trusted certificate profile

1. In the Azure Portal, select the **Device Configurations** workload.
2. On the **Device configuration** blade, select **Manage** > **Profiles**.
3. On the profiles blade, click **Create Profile**.
4. On the **Create Profile** blade, enter a **Name** and **Description** for the trusted certificate profile.
5. From the **Platform** drop-down list, select the device platform for this trusted certificate. Currently, you can choose one of the following platforms for device restriction settings:
	- **Android**
	- **iOS**
	- **macOS**
	- **Windows Phone 8.1**
	- **Windows 8.1 and later**
	- **Windows 10 and later**
6. From the **Profile** type drop-down list, choose **Trusted certificate**.
7. Browse to the certificate you saved in task 1, then click **OK**.
8. For Windows 8.1 and Windows 10 devices only, select the **Destination Store** for the trusted certificate.
8. When you're done, go back to the **Create Profile** blade, and hit **Create**.

The profile will be created and appears on the profiles list blade.

> [!Note]
> Android devices will display a notice that a third party has installed a trusted certificate.

## Task 3: Create SCEP or .PFX certificate profiles
After you create a Trusted CA certificate profile, create SCEP or .PFX certificate profiles for each platform you want to use. When you create an SCEP certificate profile, you must specify a Trusted certificate profile for that same platform. This links the two certificate profiles, but you still must assign each profile separately.

### To create an SCEP certificate profile



1. In the Azure Portal, select the **Device Configurations** workload.
2. On the **Device configuration** blade, select **Manage** > **Profiles**.
3. On the profiles blade, click **Create Profile**.
4. On the **Create Profile** blade, enter a **Name** and **Description** for the SCEP certificate profile.
5. From the **Platform** drop-down list, select the device platform for this SCEP certificate. Currently, you can choose one of the following platforms for device restriction settings:
	- **Android**
	- **iOS**
	- **macOS**
	- **Windows Phone 8.1**
	- **Windows 8.1 and later**
	- **Windows 10 and later**
6. From the **Profile** type drop-down list, choose **SCEP certificate**.
7. On the **SCEP Certificate** blade, configure the following settings:
	- **Certificate validity period** - 
	- **Key storage provider (KSP)** (Windows Phone 8.1, Windows 8.1, Windows 10) - 
	- **Subject name format** - 
	- **Subject alternative name** - 
	- **Key usage** - 
	- **Key size (bits)** - 
	- **Hash algorithm** (Android, Windows Phone 8.1, Windows 8.1, Windows 10) - 
	- **Root Certificate** - 
	- **Extended key usage** - 
	- **Enrollment Settings** - 
	- **Renewal threshold (%)** - 
	- **SCEP Server URLs** - 
8. When you're done, go back to the **Create Profile** blade, and hit **Create**.

The profile will be created and appears on the profiles list blade.

Follow the instructions on the profile configuration page to configure the SCEP certificate profile settings.
>[!Note]
> For iOS devices only: Under Subject name format, select Custom to enter a custom subject name format.
> The two variables currently supported for the custom format are **Common Name (CN)** and **Email (E)**. By using a combination of these variables and static strings, you can create a custom subject name format, like this one:
> **CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US**
In this example, you created a subject name format that, in addition to the CN and E variables, uses strings for Organizational Unit, Organization, Location, State, and Country values. [This topic](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx) show the **CertStrToName** function and its supported strings.


### To create a .PFX certificate profile

In the Azure Portal, select the **Device Configurations** workload.
2. On the **Device configuration** blade, select **Manage** > **Profiles**.
3. On the profiles blade, click **Create Profile**.
4. On the **Create Profile** blade, enter a **Name** and **Description** for the PKCS certificate profile.
5. From the **Platform** drop-down list, select the device platform for this PKCS certificate. Currently, you can choose one of the following platforms for device restriction settings:
	- **Android**
	- **iOS**
	- **Windows 10 and later**
6. From the **Profile** type drop-down list, choose **PKCS certificate**.
7. On the **PKCS Certificate** blade, configure the following settings:
	- **Renewal threshold (%)** - 
	- **Certificate validity period** - 
	- **Key storage provider (KSP)** (Windows 10) - 
	- **Certificate authority** - 
	- **Certificate authority name** - 
	- **Certificate template name** - 
	- **Subject name format** - 
	- **Subject alternative name** - 
	- **Extended key usage** (Android) - 
	- **Root Certificate** (Android) - 
8. When you're done, go back to the **Create Profile** blade, and hit **Create**.

The profile will be created and appears on the profiles list blade.

## Task 4: Assign certificate profiles

Consider the following before you assign certificate profiles to groups:

- When you assign certificate profiles to groups, the certificate file from the Trusted CA certificate profile is installed on the device. The device uses the SCEP or .PFX certificate profile to create a certificate request by the device.
- Certificate profiles install only on devices running the platform you use when you created the profile.
- You can deploy certificate profiles to user collections or to device collections.
- To publish a certificate to a device quickly after the device enrolls, deploy the certificate profile to a user group rather than to a device group. If you deploy to a device group, a full device registration is required before the device receives policies.
- Although you deploy each profile separately, you also need to deploy the Trusted Root CA and the SCEP or .PFX profile. Otherwise, the SCEP or .PFX certificate policy will fail.

See [How to assign device profiles](how-to-assign-device-profiles.md) for general information about how to assign device profiles.
