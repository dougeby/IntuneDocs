---
title: Manage access to Exchange Online test refactor
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic:
ms.assetid:
author: karthikaraman
---
# Manage access to Exchange Online test refactor
Use the Microsoft Intune conditional access policies for Exchange to manage access to
Exchange Online and Exchange Online dedicated email based on conditions you specify.


##  Mobile devices
You can control access to Exchange Online and Exchange Online Dedicated from the following mail apps:

- The built-in app for Android 4.0 and later, Samsung Knox 4.0 Standard and later

- The built-in app for iOS 7.1 and later

- The built-in app for Windows Phone 8.1 and later

- The mail application on Windows 8.1 and later

- The Microsoft Outlook app for Android and iOS (for Exchange Online only)
### Exchange Online:

Conditional access to Exchange Online is supported on devices that run:

- Windows Phone 8.1 and later
- iOS 7.1 and later
- Android 4.0 and later, Samsung Knox Standard 4.0 and later

Additionally:

- Devices must be registered with the Azure Active Directory Device Registration Service (AAD DRS).

  AAD DRS will be activated automatically for Intune and Office 365 customers. Customers who have already deployed the ADFS Device Registration Service will not see registered devices in their on-premises Active Directory.
- You must use an Office 365 subscription that includes Exchange Online (such as E3) and users must be licensed for Exchange Online.

- The optional Microsoft Intune service to service connector connects Intune to Microsoft Exchange Online and helps you manage device information through the Intune console (see Mobile device management with Exchange ActiveSync and Microsoft Intune). You do not need to use the connector to use compliance policies or conditional access policies, but is required to run reports that help evaluate the impact of conditional access.

If you configure the connector, some Exchange ActiveSync policies from Intune might be visible in the Office console but are not set as default policies and do not affect devices.

>[!NOTE]
>Do not configure the service to service connector if you intend to use conditional access for both Exchange Online and Exchange On-premises

### Exchange Online Dedicated (new)
Conditional access to Exchange Online Dedicated supports devices that run:

- Windows Phone 8 and later
- Any iOS device that uses an Exchange ActiveSync (EAS) email client
- Android 4 and later.

Additionally:

The optional Microsoft Intune service to service connector connects Intune to Microsoft Exchange Online and helps you manage device information through the Intune console (see Mobile device management with Exchange ActiveSync and Microsoft Intune). You do not need to use the connector to use compliance policies or conditional access policies, but is required to run reports that help evaluate the impact of conditional access.


#### Step-by-Step Walkthrough:
##### Step 1: Configure and deploy a compliance policy

Ensure that you have created and deployed a compliance policy to all devices that the Exchange conditional access policy will be targeted to.

For details about how to configure the compliance policy, see Manage device compliance policies for Microsoft Intune.
>[!IMPORTANT]
>If you have not deployed a compliance policy and then enable an Exchange conditional access policy, all targeted devices will be allowed access.

##### Step 2: Evaluate the effect of the conditional access policy

If you have configured a connection between Intune and Exchange by using the Microsoft Intune service to service connector or the on-premises Exchange connector, you can use the Mobile Device Inventory Reports to identify EAS mail clients that will be blocked from accessing Exchange after you configure the conditional access policy.

  1.  Navigate to Reports -> Mobile Device Inventory Reports.
  2.  In the report parameters, select the Intune group you want to evaluate and, if required, the device platforms to which the policy will apply.
  3.  Once you’ve selected the criteria that meets your organization’s needs, choose View Report.
 The Report Viewer opens in a new window.
 For more information about how to run reports, see Understand Microsoft Intune operations by using reports.

 After you run the report, examine these four columns to determine whether a user will be blocked:

 **Management Channel** – Indicates whether the device is managed by Intune, Exchange ActiveSync, or both.

 **AAD Registered** – Indicates whether the device is registered with Azure Active Directory (known as Workplace Join).

 **Compliant** – Indicates whether the device is compliant with any compliance policies you deployed.

 **Exchange ActiveSync ID** – iOS and Android devices are required to have their Exchange ActiveSync ID associated with the device registration record in Azure Active Directory. This happens when the user chooses the Activate Email link in the quarantine email.

>[!NOTE]
>Windows Phone devices always display a value in this column.
Devices that are part of a targeted group will be blocked from accessing Exchange unless the column values match those listed in the following table:





  3.Step3

  4.End result


##  Configure conditional access for PCs:
### Pre-requisites:
####  Exchange Online
Conditional access to Exchange Online supports devices that run:

- Windows 8.1 and later (when enrolled with Intune)


- Windows 7.0 or Windows 8.1 (when domain joined)




### Step-by-Step Walkthrough:
  1.Step1

  2.Step2

  3.Step3

  4.End result



##  Next steps
