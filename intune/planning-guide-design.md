---
# required metadata

title: Create a design 
description: This article helps you to create a design for a Microsoft Intune cloud-only design and implementation.
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/13/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: a8e38e29-f5e3-4a71-a170-d3b1a06e37c6

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffbu, cgerth
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Create a design

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

The section of the guide should be used in parallel with other topics in Section 2. This design is based on the information you collect and decisions you make when completing previous sections of this guide. In this design section, we focus on Intune standalone, which is a Microsoft cloud-based service.

Although there’s minimal on-premises infrastructure requirements, work on a design plan to make sure you have the right mobile device management solution that meets your goals, objectives, and requirements.

Additionally, it’s common to have design changes during the implementation and testing phases, make sure to document these changes, and the rationale behind it as they occur. The design includes the following areas:

-   The current environment

-   Intune deployment options

-   Identity requirements for external dependencies

-   Device platform considerations

-   Requirements to be delivered  

Let’s review each of these areas in more detail. 

## Record your environment

The first step before you can create your design is to record your current environment. The current environment can influence design decisions and should be documented and referenced when making other Intune design decisions. Below are few examples of how to record the current environment:

-   **Identity in the cloud**

    -   Do you use DirSync or Azure Active Directory (Azure AD) Connect?

    -   Is your environment Federated?

    -   Is multi-factor authentication enabled?

-   **Email environment**

    -   Is Exchange being used, is it on-premises or in the cloud?

    -   Are you in the middle of a project to migrate Exchange to the cloud?

-   **Current MDM solution**

    -   Are you currently using other MDM solutions?

    -   What MDM solutions are you using for corporate and BYOD use case scenarios?

    -   What capabilities are you using (e.g. app device settings, Wi-Fi configurations, etc.)?

    -   What device platforms are supported?

    -   What groups and how many users are using the MDM solution?

-   **Certificate Solution**

    -   Have you implemented a certificate solution?

    -   What type of certificates do you use?

-   **Systems Management**

    -   How are you managing your PC and server environment?

    -   Is System Center Configuration Manager being used? Are you using a third-party system management platform?

-   **VPN Solution**

    -   What is your VPN solution?

    -   Is it used for both corporate and BYOD use case scenarios?

Make sure to note any projects or any other plans in place to could make changes to your environment when recording the current MDM environment. Below is an example of a way to record the current environment to assist when creating your Intune design:

| **Solution area** | **Current environment** | **Comments** |
|:---:|:---:|:---:|
| **Identity** | Azure AD, Azure AD Connect, not federated, no MFA | Project in place to enable MFA by end of year |                 
| **Email environment** | Exchange on-premises, Exchange online | Currently migrating from Exchange on-premises to Exchange online. 75% of mailboxes migrated. Last 25% will be migrated before Intune Pilot begins. |                
| **SharePoint** | SharePoint on-premises | No plans to move to SharePoint online |  
| **Current MDM** | Exchange ActiveSync |  |
| **Certificate solution** | Microsoft Server 2012 R2, AD Certificate Services | Only use PKI for Web Site Servers |
| **System Management** | System Center Configuration Manager CB 1606 | Would like to investigate Intune hybrid solution |
| **VPN solution** | Cisco AnyConnect |  |

## Choose an Intune deployment option

Intune offers two deployment options: standalone and hybrid. Decide which one fits your business requirements. Standalone refers to Intune service running in the cloud, hybrid refers to the integration of Intune with System Center Configuration Manager.

- Learn more about [choosing between Microsoft Intune standalone and hybrid mobile device management with System Center Configuration Manager](https://docs.microsoft.com/sccm/mdm/understand/choose-between-standalone-intune-and-hybrid-mobile-device-management)

## Intune tenant location

If your organization has global presence, make sure to plan where your tenant resides when subscribing to the service. The country is defined when you sign up for an Intune subscription for the first time, and map to regions around the world which are listed below:

-   North America

-   Europe, Middle East, and Africa

-   Asia and Pacific

>[!IMPORTANT]
> It’s not possible to change the country and tenant location later.

## External dependencies

External dependencies are services and products that are separate from Intune, but are either a requirement of Intune, or might integrate with Intune. It’s important to identify requirements for any external dependencies and how it is to be configured. Some examples of common external dependencies are listed below.

-   Identity

-   User and device groups

-   PKI

Let’s explore in more detail these common external dependencies below

### Identity

Identity is how we identify the users who belong to your organization and are enrolling a device. Intune requires Azure Active Directory (Azure AD) as the user identity provider. If you already use this service, you’ll be able to leverage your existing identity already in the cloud. In addition, Azure AD Connect is the recommended tool to synchronize your on-premises user identities with Microsoft cloud services. If your organization is already using Office 365, it’s important that Intune uses the same Azure Active Directory environment.

You can find more information regarding Intune’s identity requirements below.

-   Learn more about [identity requirements](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview).

-   Learn more about [directory synchronization requirements](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements).

-   Learn more about [multi-factor authentication requirements](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements).

### User and device groups

User and device groups determines the target of a deployment. This could include deployment targeting for policies, applications, and profiles. Intune cloud-only supports user and device groups – you’ll need to determine what user and device groups will be required. It’s recommended that all groups are created in the on-premises Active Directory, then synchronized to Azure Active Directory. You can find more information about user and device group planning and creation below.

-   Learn more about [planning your user and device groups](/intune-classic/deploy-use/plan-your-user-and-device-groups).

-   Learn [how to create user and device groups](/intune-classic/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune).

### Public Key Infrastructure (PKI)

Public Key Infrastructure supplies certificates to devices or users to securely authenticate to a service. Intune supports a Microsoft PKI infrastructure. Device and user certificates can be issued to a mobile device to satisfy certificate based authentication requirements. Before implementing certificates, you need to determine if certificates are needed, whether the network infrastructure can support certificate based authentication, and whether certificates are currently used in the existing environment.

If you're planning to use certificates with VPN, Wi-Fi, or e-mail profiles with Intune, you need to make sure you have a supported [PKI infrastructure in place](/intune-classic/deploy-use/secure-resource-access-with-certificate-profiles), ready to create and deploy certificate profiles.

In addition, If SCEP certificates will be issued, you need to determine which server will host the Network Device Enrollment Service (NDES) feature, and how the communication will happen.

More information about configuring certificates in Intune:

-   [How to configure the certificate infrastructure for SCEP](/intune-classic/deploy-use/configure-certificate-infrastructure-for-scep).

-   [How to configure the certificate infrastructure for PFX](/intune-classic/deploy-use/configure-certificate-infrastructure-for-pfx).

-   [How to configure Intune certificate profiles](/intune-classic/deploy-use/configure-intune-certificate-profiles).

-   [How to configure resource access policies](/intune-classic/deploy-use/enable-access-to-company-resources-with-microsoft-intune).

## Device Platform Considerations

You need to take a closer look at your devices to understand how them correctly.

-   Determine supported device platforms

-   Devices

-   Device ownership

-   Bulk enrollment

Let’s review these areas in more detail.

### Determine supported device platforms

You need to know what devices will be in the environment and verify whether they are supported or not by Intune when creating your design. Intune supports iOS, Android, and Windows platforms.

-   Learn more about [Intune Supported Devices](/intune-classic/get-started/supported-mobile-devices-and-computers).

### Devices

Intune manages mobile devices to secure corporate data and allow end users to work from more locations. Intune supports multiple device platforms, so it’s recommended to document the devices and the OS platforms that will be supported in your organization’s design. This will expand on the devices and platforms created in section (use case requirements).

It’s also recommended to know the versions to reference the list when checking for device capabilities by OS platform and version. Here’s an example:

| **Device platform** | **OS Versions** |
|:---:|:---:|
| iOS - iPhone | 9.0+ |                
| iOS - iPad | 8.0+ |               
| Android – Samsung Knox Standard | 4.0+ |
| Windows 10 tablet | 10+ |

### Device ownership

Intune supports both corporate owned and BYOD ownership. A Device is considered corporate owned if enrolled by a device enrollment manager, or device enrollment program. As an example, a device could be enrolled via Apple DEP, marked as corporate, and placed in a device group that receives targeted corporate policies and apps.

Refer to [Section 3: Determine use case scenario requirements](planning-guide-requirements.md) for more information about Corporate and BYOD use cases.

### Bulk enrollment

There are multiple enrollment options available for enrolling a device in Intune to complement the self-service enrollment through the company portal. Bulk enrollment can be accomplished different ways depending on the platform. If bulk enrollment will be required, first determine the bulk enrollment method and incorporate in to your design. Find more information about different methods of bulk enrollment below.

-   Learn about more [bulk enrollment](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune).

## Feature requirements

In these sections, we’ll review the following features and capabilities that are aligned with your use case scenario requirements:

-   Terms and Conditions Policies

-   Configuration Policies

-   Resource Profiles

-   Apps

-   Compliance Policy

-   Conditional Access

Let’s review each of these areas in more detail.

### Terms and Conditions policies

Terms and Conditions can be used to explain policies or conditions that an end user must accept before enrollment. Intune supports the ability to add and deploy multiple terms and conditions policies to user groups. You need to determine if terms and condition policies are needed. If so, who will be responsible for providing this information in the organization.

-   Learn [how to create term and condition policies](/intune-classic/deploy-use/terms-and-condition-policy-settings-in-microsoft-intune) on Intune. An example of how to document the terms and conditions policy is below.

| **Terms and Conditions name** | **Use case** | **Targeted group** |
|:---:|:---:|:---:|
| Corporate T&C | Corporate | Corporate users |                 
| BYOD T&C | BYOD | BYOD users |                

### Configuration policies

Configuration policies are used to manage security settings and features on a device. When designing your configuration policies, refer to the use case requirements section to determine the configurations required for Intune devices. Document which settings, and how they should be configured, also document which user, or device groups they will be targeted to.

You should create at least one Configuration Policy per platform. You can create multiple Configuration Policies per platform if needed. Below is an example of designing four different configuration policies for different platforms and use case scenarios.

| **Policy name** | **Device platform** | **Settings** | **Target group** |   
|:---:|:---:|:---:|:---:|
| Corporate - iOS | iOS | PIN is required, Length: 6, Restrict Cloud Backup | Corporate Devices |                                                           
| Corporate - Android | Android | PIN is required, Length: 6, Restrict Cloud Backup | Corporate Devices |                                                           
| BYOD – iOS  | iOS | PIN is required, Length: 4 | BYOD devices |
| BYOD – Android  | Android | PIN is required, Length: 4 | BYOD devices |

### Profiles

Profiles are used to help the end user connect to company data. Intune supports many types of profiles. Refer to the use cases and requirements to determine when the [profiles](/intune-classic/deploy-use/enable-access-to-company-resources-with-microsoft-intune) will be configured. All device profiles are categorized per platform type, and should be included in the design documentation.

-   Certificate profiles

-   Wi-Fi profile

-   VPN profile

-   Email profile

Let’s review each type of profile in more detail.

##### Certificate profiles

Certificate profiles allow Intune to issue a certificate to a user or device. Intune supports the following:

-   Simple Certificate Enrollment Protocol (SCEP)

-   Trusted Root Certificate

-   PFX certificate.

It’s recommended to document which user group needs a certificate, how many certificate profiles will be needed, and which user groups to deploy them to.

>[!NOTE]
> Remember that the trusted root certificate is required for the SCEP certificate, so make sure all users targeted for the SCEP certificate also receive a trusted root certificate. If SCEP certificates are needed, design and document what SCEP certificate templates will be needed.

Here’s an example how you can document the certificates during the design:

| **Type** | **Profile name** | **Device platform** | **Use cases** |   
|:---:|:---:|:---:|:---:|
| Root CA | Corporate Root CA | Android, iOS, Windows mobile | Corporate, BYOD  |                                                           
| SCEP | User Certificate | Android, iOS, Windows mobile | Corporate, BYOD |                                                           

##### Wi-Fi profile

Wi-Fi Profiles are used to automatically connect a mobile device to a wireless network. Intune supports deploying Wi-Fi profiles to all supported platforms.

-   Learn more about [how Intune supports Wi-Fi profiles.](/intune-classic/deploy-use/wi-fi-connections-in-microsoft-intune)

Below is an example of a design for a Wi-Fi profile:

| **Type** | **Profile name** | **Device platform** | **Use cases** |   
|:---:|:---:|:---:|:---:|
| Wi-Fi | Asia Wi-Fi profile | Android | Corporate, BYOD Asia region|                                                           
| Wi-Fi | North America Wi-Fi profile | Android, iOS, Windows 10 Mobile | Corporate, BYOD North America region |                                                           

##### VPN profile

VPN profiles let users securely access your network from remote locations. Intune supports VPN profiles from native mobile VPN connections and third party vendors.

-   Learn more about [VPN profiles and vendors supported by Intune](/intune-classic/deploy-use/vpn-connections-in-microsoft-intune).

Below is an example of documenting the design of a VPN profile.

| **Type** | **Profile name** | **Device platform** | **Use cases** |   
|:---:|:---:|:---:|:---:|
| VPN | VPN Cisco any connect Profile | Android, iOS, Windows 10 Mobile | Corporate, BYOD North America and Germany|                                                           
| VPN | Pulse Secure | Android | Corporate, BYOD Asia region |                                                           

##### Email profile

Email profiles allow an email client to be automatically setup with connection information and setup email configuration. Intune supports email profiles on some devices.

-   Learn more about [email profiles](/intune-classic/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune) and what platforms are supported.

Below is an example of documenting the design of email profiles:

| **Type** | **Profile name** | **Device platform** | **Use cases** |   
|:---:|:---:|:---:|:---:|
| Email profile | iOS email profile | iOS | Corporate – Information worker BYOD |                                                           
| Email profile | Android Knox email profile | Android Knox | BYOD |

### Apps

Intune supports delivering apps to the users or devices in multiple ways. The type of application delivered could be software installer apps, apps from a public app store, external links, or managed iOS apps. In addition to individual app deployments, volume-purchased apps can be managed and deployed through the volume-purchase programs for iOS and Windows. Below is more information about how Intune supports apps and the volume purchase programs.

-   Learn more about [types of apps](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)

-   Learn more about [iOS Volume Purchase Program for Business (VPP)](/intune-classic/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune)).

-   Learn more about [Windows Store for Business](/intune-classic/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune).

#### App type requirements

Since apps can be deployed to users and devices, it’s recommended to decide which applications will be managed by Intune. While gathering the list, try to answer the following questions:

-   Do the apps require integration with cloud services?

-   Will all apps be available to BYOD users?

-   What are the deployment options available for these apps?

-   Does your company need to provide access to Software as a service (SaaS) apps data for their partners?

-   Do the apps require internet access from user’s devices?

-   Are the apps publicly available in an app store, or are they custom Line of Business Apps?


>[!TIP]
> Check out the [different types of applications that Intune support](/intune-classic/deploy-use/add-apps).

#### App protection policies

App protection policies minimize data loss by defining how the application manages the corporate data. Intune supports app protection policies for any application built to function with mobile app management. When designing the app protection policy, you need to determine what restrictions you will place on corporate data in a given app. It’s recommended to review how [app protection policies](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) work. Below is an example of how to document the existing applications and what protection is needed.

| **Application** | **Purpose** | **Platforms** | **Use case** | **App protection policy** |
|:---:|:---:|:---:|:---:|:---:|
| Outlook mobile  | Available | iOS | Corporate - Executives | Cannot be jail broken, encrypt files |                                                         
| Word | Available | iOS, Android - Samsung Knox, non-Knox, Windows 10 mobile | Corporate, BYOD | Cannot be jail broken, encrypt files |                                                         

#### Compliance policies

Compliance policies determine whether a device conforms to certain requirements. Intune uses compliance policies to determine if a device is considered compliant or non-compliant. The compliance status can then be used to restrict access to company resources. If conditional access is required, it is recommended to design a [device compliance policy](/intune-classic/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune). Refer to requirements and use cases to determine how many device compliance policies are needed and which user groups are the target user groups. Additionally, you need to determine how long a device can be offline without checking in before it’s considered non-compliant.

Below is an example of how to design a compliance policy:

| **Policy name** | **Device platform** | **Settings** | **Target group** |   
|:---:|:---:|:---:|:---:|
| Compliance policy | iOS, Android - Samsung Knox, non-Knox, Windows 10 mobile | PIN - required, cannot be jail broken | Corporate, BYOD |

#### Conditional access policies

Conditional Access is used to allow only compliant devices to access company resources. Intune works with the entire Enterprise Mobility + Security (EMS) to control access to company resources. You’ll need to determine if conditional access is required, and what must be secured.

-   Learn more about [Conditional Access](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).

For online access, determine what platforms, and user groups will be targeted by conditional access policies.

Additionally, you need to determine whether you need to install/configure the Intune service-to-service connector for Exchange Online or Exchange on-premises.

Learn more how to install and configure the Intune service-to-service connectors:

-   [Exchange Online](/intune-classic/deploy-use/intune-service-to-service-exchange-connector)

-   [Exchange On-premises](/intune-classic/deploy-use/intune-on-premises-exchange-connector)

Here’s an example of how to document conditional access policies:

| **Service** | **Platforms for Modern Authentication** | **Basic Authentication** | **Use cases** |   
|:---:|:---:|:---:|:---:|
| Exchange online | iOS, Android | Block non-compliant devices on platforms supported by Intune | Corporate, BYOD |
| SharePoint online | iOS, Android |  | Corporate, BYOD |

## Next Section

The next section provides guidance on the [Intune implementation process](planning-guide-onboarding.md).
