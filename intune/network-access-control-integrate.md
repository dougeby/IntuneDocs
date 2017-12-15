---
# required metadata

title: Network access control integration with Intune
titlesuffix: "Azure portal"
description: Network access control (NAC) integration with Intune
keywords:
author: bruceperlerMS
ms.author: bruceper
manager: angrobe
ms.date: 12/15/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: aa7ecff7-8579-4009-8fd6-e17074df67de

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: davidra
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Network access control (NAC) integration with Intune

Intune integrates with network access control partners to help organizations secure corporate data when devices try to access on-premises resources.

## How do Intune and NAC solutions help protect your organization resources?

NAC solutions are responsible for checking the device enrollment and compliance state with Intune to make access control decisions. If the device is not enrolled or is enrolled and not compliant with Intune device compliance policies, the device should be redirected to Intune for enrollment and/or for a device compliance check.

### Example

If the device is enrolled and compliant with Intune, the NAC solution should allow the device access to corporate resources. For example, users can be allowed or denied access when trying to access corporate Wi-Fi or VPN resources.

## Feature behaviors

Devices which are actively syncing to Intune cannot move from **Compliant** / **Noncompliant** to **Not Sync’d** (or **Unknown**). The Unknown state is reserved for newly enrolled devices which have not yet been evaluated for compliance.  This means, for a customer, the devices have always been in this state due to some other problem with their enrollment.

For devices that are blocked from access to resources, the blocking service should redirect all users to https://portal.manage.microsoft.com to determine why the device is blocked.  If the users visit this page, their devices will be synchronously re-evaluated for compliance.

## NAC and conditional access

NAC works with conditional access to provide access control decisions.

- See [common ways to use conditional access with Intune](conditional-access-intune-common-ways-use.md) for more details.

## How the NAC integration works

Here’s an overview on how the NAC integration works when integrated with Intune. The first three steps, 1-3, explain the onboarding process. Once the NAC solution is integrated with Intune, steps 4-9 describe the on-going operation.

![How NAC works with Intune](./media/ca-intune-common-ways-2.png)

1. Register the NAC partner solution with Azure Active Directory (AAD), and grant delegated permissions to the Intune NAC API.

2. Configure the NAC partner solution with the appropriate settings including the Intune discovery URL.

3. Configure the NAC partner solution for certificate authentication.

4. User connects to corporate Wi-Fi access point or makes a VPN connection request.

5. NAC partner solution forwards the device information to Intune, and asks Intune about the device enrollment and compliance state.

6. If the device is not compliant or not enrolled, the NAC partner solution instructs the user to enroll or fix the device compliance.

7. The device attempts to re-verify its compliance and/or the enrollment state.

8. Once the device is enrolled and compliant, NAC partner solution gets the state from Intune.

9. Connection is successfully established which allows the device access to corporate resources.

## Integration specific notes

### Cisco ISE

 - ISE Api exposed by intune takes in MacAddress/IMEI/UDID/MEID (ie: No AAD lookups)
 - ISE reports compliance as true only if MDMStatus == 1 (Compliant)
 - ISE has a feature which requests from Intune the Url to redirect to in case the user device is non-compliant or is not enrolled (https://portal.manage.microsoft.com/networkaccesscontrol/index). The recommendation is for them to configure ISE in such a way that they allow users to redirect to this Url  automatically when they are non-compliant, so they can get compliant.

## Next steps

-   [Integrate Cisco ISE with Intune](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html)

-   [Integrate Citrix NetScaler with Intune](http://docs.citrix.com/en-us/netscaler-gateway/12/microsoft-intune-integration/configuring-network-access-control-device-check-for-netscaler-gateway-virtual-server-for-single-factor-authentication-deployment.html)

-   [Integrate HP Aruba Clear Pass with Intune](https://support.arubanetworks.com/Documentation/tabid/77/DMXModule/512/Command/Core_Download/Default.aspx?EntryId=23757)
