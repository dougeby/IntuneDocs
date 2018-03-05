---
# required metadata

title: iOS apps with app protection policies
titlesuffix: Microsoft Intune
description: Learn what to expect from an iOS app that has protection policies.
keywords:
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 12/07/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 586d9440-3813-4dec-b865-8bd319befde0

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: andcerat
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# What to expect when your iOS app is managed by app protection policies

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Learn about the user experience for iOS apps with app protection policies. App protection polices are applied only when apps are used in the work context. For example, when you access an app with a work account, or when you access files stored in your company OneDrive location.
##  Accessing apps

If the device is **not enrolled in Intune**, the user will be asked to restart the app when they first use the app.  A restart is required so app protection polices can be applied to the app. The following screenshot illustrates this using the Skype app:


![screenshot of the iOS device showing PIN prompt](./media/ios-pin-prompt.png)

For devices that are **enrolled for management in Intune**, the user will see a message that their app is now managed:

![screenshot of the iOS device showing the managed by your company message with PIN prompt](./media/ios-managed-devices-pin-prompt.png)

##  Using apps with multi-identity support

App protection policies only take effect when a user tries to access work-related data.  You may see different behaviors if the user accesses the app for personal use. 

For apps that support multi-identity, Intune only applies app protection policies if a user accesses work data.  For example, a user may get a PIN prompt.  In the **Outlook app**, a prompt occurs when a user launches the app. In the **OneDrive app**, a prompt occurs when a user types in the work account.  In Microsoft **Word**, **PowerPoint**, and **Excel**, a prompt occurs when a user accesses company OneDrive documents.
##  Managing user accounts on the device

Intune only supports deploying app protection policies to only one user account per device.

* Depending on the app that you are using, the second user may or may not be blocked on the device. However, in all cases, only the first user who gets the app protection policies are affected by the policy.
  * **Microsoft Word**, **Excel**, and **PowerPoint** won't block access to an additional user account. However, the user account will not be affected by the app protection policies.

  * For **OneDrive and Outlook apps**, you can only use one work account.  Adding multiple work accounts are blocked on these apps.  However, you can remove a user from a device, and then add a different user to the device.

* A device may have multiple existing user accounts before the app protection policies are deployed. In this case, the first account that the app protection policies are deployed to is managed by Intune app protection policies.


Read the following example scenario to learn how Intune handles multiple user accounts.

User A works for two companies: **Company X**, and **Company Y**. User A has a work account for each company, and both use Intune to deploy app protection policies. **Company X** deploys app protection policies **before** **Company Y**. The account associated with **Company X** will get the app protection policy, but not the account associated with Company Y. To have the Company Y user account managed by the app protection policies, User A must remove the Company X user account.
### Adding a second account

If you are using an iOS device, when you try to add a second work account on the same device, you may see a blocking message.  The accounts will be displayed and you can choose the account you want to remove.

![Screenshot of the dialog box with the blocking message and Yes and No options](./media/ios-switch-user.PNG)

## Next steps
[What to expect when your Android app is managed by app protection policies](app-protection-enabled-apps-android.md)
### See also
[Create and deploy app protection policies with Microsoft Intune](app-protection-policies.md)
