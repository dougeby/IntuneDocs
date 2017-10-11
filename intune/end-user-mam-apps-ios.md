---
# required metadata

title: iOS apps with app protection policies
description: This topic describes what to expect when your iOS app is managed by app protection policies.
keywords:
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 05/05/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: b57e6525-b57c-4cb4-a84c-9f70ba1e8e19

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: andcerat
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# What to expect when your iOS app is managed by app protection policies

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

 This topic describes the user experience when using apps with app protection policies applied to. App protection policies are applied only when apps are used in the work context; for example, when the user is accessing apps with a work account or accessing files that are stored in a company OneDrive for business location.

##  Access apps

If the device is **not enrolled in Intune**, the user is asked to restart the app when they first use it. A restart is required so that app protection polices can be applied to the app.

<!--- The following screenshot from the Skype app illustrates this restart request: --->


<!---  ![Screenshot of the iOS device showing PIN prompt](../media/appmanagement/iOS_AppPINPrompt.png) --->

For devices that are **enrolled for management in Intune**, the user sees a message that their app is now managed.

##  Use apps with multi-identity support

Apps that support multi-identity let you use different accounts (work and personal) to access the same apps, while app protection policies are applied only when the apps are used in the work context.  

For example, the user gets a PIN prompt when accessing work data. For the **Outlook app**, the user is prompted for a PIN when they launch the app. For the **OneDrive app**, the user is prompted for a pin when they type in the work account.  For Microsoft **Word**, **PowerPoint**, and **Excel**, the user is prompted for a pin when they access documents that are stored in the company OneDrive for Business location.

- Learn more about the apps that support [app protection and multi-identity](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) with Intune.

App protection polices are only applied in the work context. Therefore, the app might behave differently depending on whether the context is work or personal.

##  Manage user accounts on the device

Intune supports the deployment of app protection policies to  one user account per device only.

* Depending on the app that you are using, the second user might be blocked on the device. However, in all cases, only the first user who gets the app protection policies is affected by the policy.
  * **Microsoft Word**, **Excel**, and **PowerPoint** don't block a second user account, but the second user account is not affected by the app protection policies.  

  * For **OneDrive** and **Outlook apps**, you can only use one work account. You can't add multiple work accounts for these apps. You can however, remove a user and add a different user on the device.

* If a device has existing multiple user accounts before the app protection policies are deployed, the account that the app protection policies are deployed to first is managed by Intune app protection policies.


Read the following example scenario to get a deeper understanding of how multiple user accounts are treated.

User A works for two companies—**Company X** and **Company Y**. User A has a work account for each company, and both use Intune to deploy app protection policies. **Company X** deploys app protection policies **before** **Company Y**. The account that's associated with **Company X** gets the app protection policy, but not the account that's associated with Company Y. If you want the user account that's associated with Company Y to be managed by the app protection policies, you must remove the user account that's associated with Company X.

### Add a second account

If you are using an iOS device, when you try to add a second work account on that device, you might see a blocking message. The accounts will be displayed, and then you can choose the account you want to remove.

## Next steps
[What to expect when your Android app is managed by app protection policies](end-user-mam-apps-android.md)
