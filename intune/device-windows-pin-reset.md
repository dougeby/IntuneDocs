---
# required metadata

title: Reset passcode on Windows devices with Intune 
titleSuffix: "Intune on Azure"
description: Learn how to use Intune to reset the passcode on Windows devices integrated with the Microsoft PIN Reset Service."
keywords:
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/05/2017
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 5027d012-d6c2-4971-a9ac-217f91d67d87

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: ilwu
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Reset the passcode on Windows devices integrated with the Microsoft PIN Reset Service using Intune

The reset passcode capability for Windows devices integrates with the Microsoft Pin Reset Service to let you generate a new passcode for devices that run Windows 10 Mobile. The devices must be running the Windows 10 Creators Update, or later.


## Before you start

Before you can remotely reset the passcode on Windows devices you can manage, you must onboard the PIN reset service to your Intune tenant, and configure devices you manage. Follow these instructions to get that set up:

### Connect Intune with the PIN reset service

1. Visit [Microsoft PIN Reset Service Integration website](https://login.windows.net/common/oauth2/authorize?response_type=code&client_id=b8456c59-1230-44c7-a4a2-99b085333e84&resource=https%3A%2F%2Fgraph.windows.net&redirect_uri=https%3A%2F%2Fcred.microsoft.com&state=e9191523-6c2f-4f1d-a4f9-c36f26f89df0&prompt=admin_consent), and sign in using the tenant administrator account you use to manage your Intune tenant.
2. After you log in, click **Accept** to give consent for the PIN reset service to access your account.
![PIN reset service permissions page](./media/pin-reset-service-application.png)
3. In the Azure portal, you can verify that Intune and the PIN reset service were integrated from the Enterprise applications - All applications blade as shown in the following screenshot:
![PIN reset service application in Azure](./media/pin-reset-service-home-screen.png)
4. Log in to [this website](https://login.windows.net/common/oauth2/authorize?response_type=code&client_id=9115dd05-fad5-4f9c-acc7-305d08b1b04e&resource=https%3A%2F%2Fcred.microsoft.com%2F&redirect_uri=ms-appx-web%3A%2F%2FMicrosoft.AAD.BrokerPlugin%2F9115dd05-fad5-4f9c-acc7-305d08b1b04e&state=6765f8c5-f4a7-4029-b667-46a6776ad611&prompt=admin_consent) using your Intune tenant admin credentials and, again, choose **Accept** to give consent for the service to access your account.

### Configure Windows devices to use PIN reset

To configure PIN reset on Windows devices you manage, use an [Intune Windows 10 custom device policy](custom-settings-windows-10.md) to enable the feature. Configure the policy using the following Windows policy configuration service providers (CSPs):


- **For users** - **./User/Vendor/MSFT/PassportForWork/<tenant ID>/Policies/EnablePinRecovery**
- **For devices** - **./Device/Vendor/MSFT/PassportForWork/<tenant ID>/Policies/EnablePinRecovery**

The values for these CSPs must both be set to **True**.

## Steps to reset the passcode

1. Sign into the Azure portal.
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Devices**.
4. On the **Devices** blade, choose **Manage** > **All devices**.
5. Select the device for which you want to reset the passcode, and then, on the device properties blade, choose **New passcode**.
6. From the confirmation that appears, choose **Yes**. The passcode is generated, and is displayed in the portal for the next seven days.

## Next steps

If the passcode reset fails, a link is provided in the portal to get more information.


