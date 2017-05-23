---
# required metadata

title: Conditional access with Intune
titleSuffix: "Intune Azure preview"
description: "Common ways to use conditional access with Intune"
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/23/2017
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: a0b8e55e-c3d8-4599-be25-dc10c1027b62

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Common ways to use conditional access with Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

You need to configure Intune mobile device compliance policy, and the Intune mobile application management (MAM) capabilities to drive conditional access compliance at your organization. Let’s talk about the common ways to use conditional access with Intune.

## Device-based conditional access

Intune and Azure Active Directory work together to make sure only managed and compliant devices are allowed access to email, Office 365 services, Software as a service (SaaS) apps, and [on-premises apps](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started). Additionally, you can set a policy in Azure Active Directory to only enable computers that are domain-joined, or mobile devices that are enrolled in Intune to access Office 365 services.

Intune provides device compliance policy capabilities that evaluate the compliance status of the devices. The compliance status is reported to Azure Active Directory that uses it to enforce the conditional access policy created in Azure Active Directory when the user tries to access company resources.

Starting at the [new Azure portal](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune), device-based conditional access policies for Exchange online and other Office 365 products are configured through the Azure portal.

-   Learn more about [Conditional Access in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal).

-   Learn more about [what is device compliance.](device-compliance.md)

### Conditional access for Exchange on-premises

Conditional access can be used to allow or block access to **Exchange on-premises** based on the device compliance policies and enrollment state. When conditional access is used in combination with a device compliance policy, only compliant devices are allowed access to Exchange on-premises.

You can configure advanced settings in conditional access for more granular control such as:

-   Allow or block certain platforms.

-   Immediately block devices that are not managed by Intune.

Any device used to access Exchange on-premises is checked for compliance when device compliance and conditional access policies are applied.

When devices do not meet the conditions set, the end user is guided through the process of enrolling the device to fix the issue that is making the device non-compliant.

#### How conditional access for Exchange on-premises work?

The Intune Exchange connector pulls in all the Exchange Active Sync (EAS) records that exist at the Exchange server so Intune can take these EAS records and map them to Intune device records. These records are devices enrolled and recognized by Intune. This process allows or blocks e-mail access.

If the EAS record is brand new, and Intune is not aware of it, Intune issues a command-let that blocks access to e-mail. Here are more details on how this process works:

![Exchange on-premises with CA flow-chart](../media/ca-intune-common-ways-1.png)

1.  User tries to access corporate e-mail, which is hosted on Exchange on-premises 2010 SP1 or later.

2.  If the device is not managed by Intune, it will be blocked access to e-mail. Intune sends block notification to the EAS client.

3.  EAS receives block notification, moves the device to quarantine, and sends the quarantine e-mail with remediation steps that contain links so the users can enroll their devices.

4.  The Workplace join process happens, which is the first step to have the device managed by Intune.

5.  The device gets enrolled into Intune.

6.  Intune maps the EAS record to a device record, and saves the device compliance state.

7.  The EAS client ID gets registered by the Azure AD Device Registration process, which creates a relationship between the Intune device record, and the EAS client ID.

8.  The Azure AD Device Registration saves the device state information.

9.  If the user meets the conditional access policies, Intune issues a command-let through the Intune Exchange connector that allows the mailbox to sync.

10. Exchange server sends the notification to EAS client so the user can access e-mail.

#### What’s the Intune role?

Intune evaluates and manage the device state.

#### What’s the Exchange server role?

Exchange server provides API and infrastructure to move devices to its quarantine.

> [!IMPORTANT] 
> Keep in mind that the user who’s using the device must have a compliance profile assigned to them so the device to be evaluated for compliance. If no compliance policy is deployed to the user, the device is treated as compliant and no access restrictions are applied.

### Conditional access based on network access control

Intune integrated with partners like Cisco ISE, Aruba Clear Pass, and Citrix NetScaler to provide access controls based on the Intune enrollment and the device compliance state.

Users can be allowed or denied access when trying to access corporate Wi-Fi or VPN resources based on whether the device is managed and compliant with Intune device compliance policies.

![CA with Network access controls](../media/ca-intune-common-ways-2.png)

-   Learn more about [conditional access based on network access controls](https://docs.microsoft.com/intune-classic/deploy-use/restrict-access-to-networks).

### Conditional access based on device risk

Intune partnered with Mobile Threat Defense vendors that provides a security solution to detect malwares, Trojans, and other threats on mobile devices.

#### How the Intune and mobile threat defense integration works?

When mobile devices have the mobile threat defense agent installed, the agent can send compliance state messages back to Intune reporting if a threat has been found in the mobile device itself.

The Intune and mobile threat defense integration plays a factor at the conditional access decisions based on device risk.

-   Learn more about [Intune mobile threat defense](https://docs.microsoft.com/intune-classic/deploy-use/mobile-threat-defense).

### Conditional access for Windows PCs

Conditional access for PCs provide similar capabilities available for mobile devices. Let’s talk about the ways you can use conditional access when managing PCs with Intune.

#### Corporate-owned

-   **On premises AD domain joined:** This has been the most common conditional access deployment option for organizations, whose are reasonable comfortable with the fact they’re already managing their PCs through AD group policies and/or with System Center Configuration Manager.

-   **Azure AD domain joined and Intune management:** This scenario is typically geared to Choose Your Own Device (CYOD), and roaming laptop scenarios where these devices are rarely connected to corporate-network. The device joins to the Azure AD and gets enrolled to Intune, which removes any dependency on on-premises AD, and domain controllers. This can be used as a conditional access criteria when accessing corporate resources.

-   **AD domain joined and System Center Configuration Manager:** As of current branch, System Center Configuration Manager provides conditional access capabilities that can evaluate specific compliance criteria, in addition to be a domain-joined PC:

    -   Is the PC encrypted?

    -   Is Malware installed? Is it up-to-date?

    -   Is the device jailbroken or rooted?

#### Bring your own device (BYOD)

-   **Workplace join and Intune management:** Here the user can join their personal devices to access corporate resources and services. You can use Workplace join and enroll devices into Intune to receive device-level policies, which is also another option to evaluate conditional access criteria.

## App-based conditional access

Intune and Azure Active Directory work together to make sure only managed apps can access corporate e-mail or other Office 365 services.

A managed app is an app that has app protection policies applied to, and can be managed by Intune.

App-based conditional access and mobile application management add a security layer by making sure only mobile apps that support Intune app protection policies can access Exchange online, and other Office 365 services. App-based conditional access can be configured in the Azure portal.

> [!NOTE] 
> App-based conditional access [also supports LOB apps](https://docs.microsoft.com/intune-classic/deploy-use/block-apps-with-no-modern-authentication), but these apps need to use [Office 365 modern authentication](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a).

### How App-based conditional access works?

In this example, the admin has app protection policies applied to the Outlook app followed by a conditional access rule that adds the Outlook app to an approved list of apps that can be used when accessing corporate e-mail.

> [!NOTE] 
> The flowchart structure below can be used for other managed apps.

![App-based ca with Intune flow-chart](../media/ca-intune-common-ways-3.png)

1.  The user tries to authenticate to Azure AD from the Outlook app.

2.  The user gets redirected to the app store to install a broker app when trying to authenticate for the first time. The broker app can be either the Microsoft Authenticator for iOS, or the Microsoft Company portal for Android devices.

	> NOTE: In this scenario, if users try to use a native e-mail app, they’ll be redirected to the app store to then install the Outlook app.

3.  The broker app gets installed on the device.

4.  The broker app starts the Azure AD registration process which creates a device record in Azure AD. This is not the same as the mobile device management (MDM) enrollment process, but this record is necessary so the conditional access policies can be enforced on the device.

5.  The broker app verifies the identity of the app. There’s a security layer so the broker app can validate if the app is authorized to be used by the user.

6.  The broker app requests the App Client ID to check if it’s in the policy approved list.

7.  Azure AD allows the user to authenticate and use the app. If the app is not in the policy approved list, Azure AD denies access to the app.

8.  Outlook app communicates with Outlook Cloud Service to initiate communication with Exchange Online.

9.  Outlook Cloud Service communicates with Azure AD to retrieve Exchange Online service access token for the user.

10.  Exchange Online allows user to get corporate e-mail.

## Next steps

[How to configure conditional access in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)

[How to create a conditional access policy for Exchange on-premises](conditional-access-exchange-create.md)
