---
# required metadata

title: Troubleshoot Conditional Access
titleSuffix: Microsoft Intune
description: What to do when your users fail to get access to resources through Intune Conditional Access.
keywords:
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 09/25/2018
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology:
ms.assetid: 5fa59501-5f33-46b7-a5f5-75eeae9f1209

# optional metadata

#audience:
#ms.devlang:
ms.reviewer:
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure
ms.collection: M365-identity-device-management
---

# Troubleshoot Conditional Access

You can protect access to Office 365 services like Exchange Online, SharePoint Online, Skype for Business Online, Exchange on-premises, and other services by using Intune and Conditional Access. This capability allows you to make sure that access to company resources is restricted to devices that are enrolled with Intune and compliant with the Conditional Access rules that you set either in the Intune admin console or Azure Active Directory. This article describes what to do when your users fail to get access to resources protected with Conditional Access, or when users can access protected resources but should be blocked.

## Requirements for Conditional Access


The following requirements must be met for Conditional Access to work:


- The device must be enrolled into MDM and managed by Intune.
- Both the user and the device must be compliant with the assigned Intune compliance policies.
- By default, the user must be assigned a device compliance policy. This can depend on the how the setting **Mark devices with no compliance policy assigned as** is configured under **Device Compliance** > **Compliance Policy Settings** in the Intune admin portal.
-	Exchange ActiveSync must be activated on the device if the user is using the device's native mail client rather than Outlook. This happens automatically for iOS, Windows Phone, and Android Knox devices.
-	For on-premise Exchange, your Intune Exchange Connector must be properly configured. See [Troubleshooting the Exchange Connector in Microsoft Intune](troubleshoot-exchange-connector.md) for more information.
- For on-premise Skype, you must configure Hybrid Modern Authentication. See [Hybrid Modern Auth Overview](https://docs.microsoft.com/en-us/office365/enterprise/hybrid-modern-auth-overview)


You can view these conditions for each device in the Azure portal and in the device inventory report.

## Devices appear compliant but users are still blocked

- Ensure that the user has an Intune license assigned for proper compliance evaluation.
- Non-Knox Android devices will not be granted access until the user clicks the **Get Started Now** link in the quarantine email they receive. This applies even if the user is already enrolled in Intune. If the user does not get the email with the link on their phone, they can use a PC to access their email and forward it to an email account on their device.
- When a device is first enrolled, it might take some time for compliance information to be registered for a device. Wait a few minutes and try again.
- For iOS devices, an existing email profile might block the deployment of an Intune admin-created email profile assigned to that user, thus making the device noncompliant. In this scenario, the Company Portal app will notify the user that they are not compliant because of their manually-configured email profile, and it will prompt the user to remove that profile. Once the user removes the existing email profile, the Intune email profile will then be successfully deployed. To prevent this problem, instruct your users to remove any existing email profiles on their device before enrolling.
- A device might get stuck in a checking-compliance state, preventing the user from initiating another check-in. If you have a device in this state, try the following:
  - Make sure the device is using the latest version of the Company Portal app.
  - Restart the device.
  - See if the problem persists on different networks (e.g. cellular, Wi-Fi, etc.).

  If the problem remains, contact Microsoft Support as described in [get support for Microsoft Intune](get-support.md).
- Certain Android devices might appear to be encrypted, however the Company Portal app recognizes these devices as not encrypted, thus marking them as noncompliant. In this scenario, the user will see a notification in the Company Portal app asking them to set a start-up passcode for the device. After tapping the notification and confirming the existing PIN or password, choose the **Require PIN to start device** option on the **Secure start-up** screen, then tap the **Check Compliance** button for the device from the Company Portal app. The device should now be detected as encrypted. 

  > [!NOTE]
  > Some device manufacturers encrypt their devices using a default PIN instead of a PIN set by the user. Intune views encryption using the default PIN as insecure and will mark those devices as noncompliant until the user creates a new, nondefault PIN.

- An Android device that is enrolled and compliant might still be blocked and receive a quarantine notice when first trying to access corporate resources. If this occurs, make sure the Company Portal app is not running, then click the **Get Started Now** link in the quarantine email to trigger evaluation. This should only need to be done when conditional access is first enabled.
- An Android device that is enrolled might prompt the user "No certificates found" and not be granted access to O365 resources. The user must enable the Enable Browser Access option on the enrolled device as follows:
  1. Open the Company Portal app.
  2. Go to the Settings page from the triple dots (...) or the hardware menu button.
  3. Select the Enable Browser Access button.
  4. In the Chrome browser, sign out of Office 365 and restart Chrome.  


## Devices are blocked and no quarantine email is received

- Verify that the device is present in the Intune admin console as an Exchange ActiveSync device. If it’s not, it's likely that device discovery is failing, probably because of an Exchange Connector issue. See [Troubleshoot the Intune on-premises Exchange connector](troubleshoot-exchange-connector.md) for more information.
- Before the Exchange Connector blocks a device, it sends an activation (quarantine) email. If the device is offline, it might not receive the activation email. 
- Check if the email client on the device is configured to retrieve email using **Push** instead of **Poll**. If so, this could cause the user to miss the email. Switch to **Poll** and see if the device receives the email.

## Devices are noncompliant but users are not blocked

- For Windows PCs, Conditional Access only blocks the native email app, Office 2013 with Modern Authentication, or Office 2016. Blocking earlier versions of Outlook or all mail apps on Windows PCs require AAD Device Registration and Active Directory Federation Services (AD FS) configurations as per [Set up SharePoint Online and Exchange Online for Azure Active Directory Conditional Access](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-no-modern-authentication). 
- If the device is selectively wiped or retired from Intune, it might continue to have access for several hours after retirement. This is because Exchange caches access rights for 6 hours. Consider other means of protecting data on retired devices in this scenario.
- Surface Hub, Bulk-Enrolled, and DEM enrolled Windows devices can support conditional access when a user who has been assigned a license for Intune is signed in; however, you must deploy the compliance policy to device groups (not user groups) for correct evaluation.
- Check the assignments for your compliance policies and your conditional access policies. If a user isn't in the group that is assigned the policies, or is in a group being excluded, the user will not be blocked. Only devices for users in an assigned group are checked for compliance.

## Noncompliant device is not blocked

If you encounter a device that is not compliant but continues to have access, take the following steps.
- Review your Target and Exclusion groups. If a user isn't in the right target group or is in the exclusion group, they won’t be blocked. Only devices of users in a Target group are checked for compliance.
- Ensure the device is being discovered. Is the Exchange Connector pointing to an Exchange 2010 CAS while the user is on an Exchange 2013 server? In this case, if the default Exchange rule is Allow, even if the user is in the Target group, Intune can't be aware of the device's connection to Exchange.
- Check Device Existence/Access State in Exchange:
  - Use this PowerShell cmdlet to get a list of all mobile devices for a mailbox: "Get-ActiveSyncDeviceStatistics -mailbox mbx'. If the device isn’t listed, it isn’t accessing Exchange.
  - If the device is listed, use the Get-CASmailbox -identity:’upn’ | fl cmdlet to get detailed information about its access state, and provide that information to Microsoft Support.

## Next steps
If this information doesn't help you, you can also [get support for Microsoft Intune](get-support.md).
