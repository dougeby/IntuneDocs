---
# required metadata

title: How to configure certificates with IntunetitleSuffix: "Intune Azure preview"
description: "Intune Azure preview: Learn how to use Intune to create and assign certificates that help you secure Wi-Fi, VPN, and other connections."
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 03/16/2017
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
ms.custom: intune-azure

---

# How to configure certificates in Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

When you give users access to corporate resources through VPN, Wi-Fi, or email profiles, you can secure the access by using a certificate that is installed on each users device. The high-level workflow is as follows:

1. Ensure you have the right certificate infrastructure in place. You can use [SCEP certificates](configure-certificate-infrastructure-for-scep.md), and [PKCS certificates](configure-certificate-infrastructure-for-pfx.md).
2. Install a root certificate or an intermediate Certification Authority (CA) certificate on each device so that the device recognizes the legitimacy of your CA. To do this, create and assign a **trusted certificate profile**. When you assign this profile, the devices that you manage with Intune will request and receive the root certificate. You have to create a separate profile for each platform. Trusted certificate profiles are available for these platforms:
	- iOS 8.0 and later
	- macOS 10.9 and later
	- Android 4.0 and later
	<!--Android for Work --->
	- Windows 8.1 and later
	- Windows Phone 8.1 and later
	- Windows 10 and later
3. Create certificate profiles so that devices request a certificate to be used for authentication of VPN, Wi-Fi, and email access. You can create and deploy a **PKCS** or a **SCEP** certificate profile for devices running these platforms:
	- iOS 8.0 and later
	- Android 4.0 and later
	- Android for Work
	- Windows 10 (desktop and mobile) and later

	You can only use a SCEP certificate profile with these platforms:

- 	macOS 10.9 and later
- 	Windows Phone 8.1 and later

You must create a separate profile for each device platform. When you create the profile, associate it with the trusted root certificate profile that you've already created.

### Further considerations

- If you don't have an Enterprise Certification Authority, you must create one.
- If you decide, based on your device platforms, to use the Simplified Certificate Enrollment Protocol (SCEP) profile, you'll also need to configure a Network Device Enrollment Service (NDES) server.
- Whether you plan to use SCEP or PKCS profiles, you must download and configure the Microsoft Intune Certificate Connector.

## Before you start


### If you want to use SCEP certificates

Complete the necessary prerequisites in [Certificate infrastructure for SCEP](/intune-azure/configure-devices/configure-certificate-infrastructure-for-scep).

### If you want to use PKCS certificates

Complete the necessary prerequisites in [Certificate infrastructure for PKCS](/intune-azure/configure-devices/configure-certificate-infrastructure-for-pfx).

## Task 1: Export the Trusted Root CA certificate
Export the Trusted Root Certification Authorities (CA) certificate as a **.cer** file from the issuing CA, or from any device that trusts your issuing CA. Do not export the private key.

You'll import this certificate when you set up a trusted certificate profile.

## Task 2: Create Trusted certificate profiles
You must create a trusted certificate profile before you can create a SCEP or PKCS certificate profile. You need a trusted certificate profile and a SCEP or PKCS profile for each device platform.

### To create a Trusted certificate profile

1. Sign into the Azure portal.
2. Choose **More Services** > **Other** > **Intune**.
3. On the **Intune** blade, choose **Device configuration**.
2. On the **Device Configuration** blade, choose **Manage** > **Profiles**.
3. On the profiles blade, choose **Create Profile**.
4. On the **Create Profile** blade, enter a **Name** and **Description** for the trusted certificate profile.
5. From the **Platform** drop-down list, select the device platform for this trusted certificate. Currently, you can choose one of the following platforms for certificate settings:
	- **Android**
	- **iOS**
	- **macOS**
	- **Windows Phone 8.1**
	- **Windows 8.1 and later**
	- **Windows 10 and later**
6. From the **Profile type** type drop-down list, choose **Trusted certificate**.
7. Browse to the certificate you saved in task 1, then click **OK**.
8. For Windows 8.1 and Windows 10 devices only, select the **Destination Store** for the trusted certificate from:
	- **Computer certificate store - Root**
	- **Computer certificate store - Intermediate**
	- **User certificate store - Intermediate**
8. When you're done, choose **OK**, go back to the **Create Profile** blade, and hit **Create**.

The profile will be created and appears on the profiles list blade.
If you want to go ahead and assign this profile to groups, see [How to assign device profiles](how-to-assign-device-profiles.md).


> [!Note]
> Android devices will display a notice that a third party has installed a trusted certificate.

## Task 3: Create SCEP or PKCS certificate profiles
After you create a trusted certificate profile, create SCEP or PKCS certificate profiles for each platform you want to use. When you create a SCEP certificate profile, you must specify a trusted certificate profile for that same platform. This links the two certificate profiles, but you still must assign each profile separately.

### To create an SCEP certificate profile

1. In the Azure Portal, select the **Configure devices** workload.
2. On the **Device Configuration** blade, choose **Manage** > **Profiles**.
3. On the profiles blade, choose **Create Profile**.
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
	- **Certificate validity period** - If you have run the **certutil - setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE** command on the issuing CA, which allows a custom validity period, you can specify the amount of remaining time before the certificate expires.<br>You can specify a value that is lower than the validity period in the specified certificate template, but not higher. For example, if the certificate validity period in the certificate template is two years, you can specify a value of one year but not a value of five years. The value must also be lower than the remaining validity period of the issuing CA's certificate. 
	- **Key storage provider (KSP)** (Windows Phone 8.1, Windows 8.1, Windows 10) - Specify where the key to the certificate will be stored. Choose from one of the following values:
		- **Enroll to Trusted Platform Module (TPM) KSP if present, otherwise Software KSP**
		- **Enroll to Trusted Platform Module (TPM) KSP, otherwise fail**
		- **Enroll to Passport, otherwise fail (Windows 10 and later)**
		- **Enroll to Software KSP**
	- **Subject name format** - From the list, select how Intune automatically creates the subject name in the certificate request. If the certificate is for a user, you can also include the user's email address in the subject name. Choose from:
		- **Not configured**
		- **Common name**
		- **Common name including email**
		- **Common name as email**
	- **Subject alternative name** - Specify how Intune automatically creates the values for the subject alternative name (SAN) in the certificate request. For example, if you selected a user certificate type, you can include the user principal name (UPN) in the subject alternative name. If the client certificate will be used to authenticate to a Network Policy Server, you must set the subject alternative name to the UPN. 
	- **Key usage** - Specify key usage options for the certificate. You can choose from the following options: 
		- **Key encipherment:** Allow key exchange only when the key is encrypted. 
		- **Digital signature:** Allow key exchange only when a digital signature helps protect the key. 
	- **Key size (bits)** - Select the number of bits that will be contained in the key. 
	- **Hash algorithm** (Android, Windows Phone 8.1, Windows 8.1, Windows 10) - Select one of the available hash algorithm types to use with this certificate. Select the strongest level of security that the connecting devices support. 
	- **Root Certificate** - Choose a root CA certificate profile that you have previously configured and assigned to the user or device. This CA certificate must be the root certificate for the CA that will issue the certificate that you are configuring in this certificate profile. 
	- **Extended key usage** - Choose **Add** to add values for the certificate's intended purpose. In most cases, the certificate will require **Client Authentication** so that the user or device can authenticate to a server. However, you can add any other key usages as required. 
	- **Enrollment Settings**
		- **Renewal threshold (%)** - Specify the percentage of the certificate lifetime that remains before the device requests renewal of the certificate.
		- **SCEP Server URLs** - Specify one or more URLs for the NDES Servers that will issue certificates via SCEP. 
8. When you're done, go back to the **Create Profile** blade, and hit **Create**.

The profile will be created and appears on the profiles list blade.

Follow the instructions on the profile configuration page to configure the SCEP certificate profile settings.
>[!Note]
> For iOS devices only: Under Subject name format, select Custom to enter a custom subject name format.
> The two variables currently supported for the custom format are **Common Name (CN)** and **Email (E)**. By using a combination of these variables and static strings, you can create a custom subject name format, like this one:
> **CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US**
In this example, you created a subject name format that, in addition to the CN and E variables, uses strings for Organizational Unit, Organization, Location, State, and Country values. [This topic](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx) show the **CertStrToName** function and its supported strings.


### To create a PKCS certificate profile

In the Azure Portal, select the **Configure devices** workload.
2. On the **Device configuration** blade, choose **Manage** > **Profiles**.
3. On the profiles blade, click **Create Profile**.
4. On the **Create Profile** blade, enter a **Name** and **Description** for the PKCS certificate profile.
5. From the **Platform** drop-down list, select the device platform for this PKCS certificate from:
	- **Android**
	- **iOS**
	- **Windows 10 and later**
6. From the **Profile** type drop-down list, choose **PKCS certificate**.
7. On the **PKCS Certificate** blade, configure the following settings:
	- **Renewal threshold (%)** - Specify the percentage of the certificate lifetime that remains before the device requests renewal of the certificate.
	- **Certificate validity period** - If you have run the **certutil - setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE** command on the issuing CA, which allows a custom validity period, you can specify the amount of remaining time before the certificate expires.<br>You can specify a value that is lower than the validity period in the specified certificate template, but not higher. For example, if the certificate validity period in the certificate template is two years, you can specify a value of one year but not a value of five years. The value must also be lower than the remaining validity period of the issuing CA's certificate.
	- **Key storage provider (KSP)** (Windows 10) -
	- **Certification authority** -
	- **Certification authority name** -
	- **Certificate template name** - Enter the name of a certificate template that the Network Device Enrollment Service is configured to use and that has been added to an issuing CA.
	Make sure that the name exactly matches one of the certificate templates that are listed in the registry of the server that is running the Network Device Enrollment Service. Make sure that you specify the name of the certificate template and not the display name of the certificate template. 
	To find the names of certificate templates, browse to the following key: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP. You will see the certificate templates listed as the values for **EncryptionTemplate**, **GeneralPurposeTemplate**, and **SignatureTemplate**. By default, the value for all three certificate templates is IPSECIntermediateOffline, which maps to the template display name of **IPSec (Offline request)**. 
	- **Subject name format** - From the list, select how Intune automatically creates the subject name in the certificate request. If the certificate is for a user, you can also include the user's email address in the subject name. Choose from:
		- **Not configured**
		- **Common name**
		- **Common name including email**
		- **Common name as email**
	- **Subject alternative name** - Specify how Intune automatically creates the values for the subject alternative name (SAN) in the certificate request. For example, if you selected a user certificate type, you can include the user principal name (UPN) in the subject alternative name. If the client certificate will be used to authenticate to a Network Policy Server, you must set the subject alternative name to the UPN.
	- **Extended key usage** (Android) - Choose **Add** to add values for the certificate's intended purpose. In most cases, the certificate will require **Client Authentication** so that the user or device can authenticate to a server. However, you can add any other key usages as required. 
	- **Root Certificate** (Android) - Choose a root CA certificate profile that you have previously configured and assigned to the user or device. This CA certificate must be the root certificate for the CA that will issue the certificate that you are configuring in this certificate profile.
8. When you're done, go back to the **Create Profile** blade, and hit **Create**.

The profile will be created and appears on the profiles list blade.

## Task 4: Assign certificate profiles

Consider the following before you assign certificate profiles to groups:

- When you assign certificate profiles to groups, the certificate file from the Trusted CA certificate profile is installed on the device. The device uses the SCEP or PKCS certificate profile to create a certificate request by the device.
- Certificate profiles install only on devices running the platform you use when you created the profile.
- You can deploy certificate profiles to user collections or to device collections.
- To publish a certificate to a device quickly after the device enrolls, deploy the certificate profile to a user group rather than to a device group. If you deploy to a device group, a full device registration is required before the device receives policies.
- Although you deploy each profile separately, you also need to deploy the Trusted Root CA and the SCEP or PKCS profile. Otherwise, the SCEP or PKCS certificate policy will fail.

## Next steps
See [How to assign device profiles](how-to-assign-device-profiles.md) for general information about how to assign device profiles.
