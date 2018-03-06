---
# required metadata

title: Configure Intune education settings for Windows 10
titleSuffix: "Azure portal"
description: Learn how to use Intune to configure Windows 10 education settings on devices you manage."
keywords:
author: barlanmsft
ms.author: barlan
manager: dougeby
ms.date: 02/23/2018
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 6f4de4bd-3dde-4a8d-8e22-46c5d06c3eea

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# How to configure Windows 10 education settings in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Education profiles let you specify details that configure the Windows Take a Test app including account details, and the test URL. When you configure this, the Take a Test app opens with the test you specify, and no other apps can be run on the device until the test is complete.

For details about the Take a Test app, see [Take tests in Windows 10](https://docs.microsoft.com/education/windows/take-tests-in-windows-10).

## Create a device profile containing education profile settings

1. Sign into the [Azure portal](https://portal.azure.com).
2. Choose **All services** > **Intune**. Intune is located in the **Monitoring + Management** section.
3. On the **Intune** pane, choose **Device configuration**.
2. On the **Device configuration** pane under the **Manage** section, choose **Profiles**.
3. On the profiles pane, choose **Create profile**.
4. On the **Create Profile** pane, enter a **Name** and **Description** for the device restriction profile.
5. From the **Platform** drop-down list, select **Windows 10 and later**.
6. From the **Profile type** type drop-down list, choose **Education profile**. 
7. Choose **Settings > Configure**, then, on the **Take a Test** pane, configure the following:
	- **Account type** - Select an account type from the drop-down field.
	- **Account user name** - Enter the user name of the account used with Take a Test. This can be a domain account, an Azure Active Directory (AAD) account, or a local computer account.
	- **Assessment URL** - Provide the URL of the test you want users to take. For more information, see the Take a Test documentation.
	- **Screen monitoring** - Specify whether you want to be able to monitor screen activity while users are taking a test.
	- **Text suggestion** - Allow or block text suggestions while users are taking a test.
8. When you're done, go back to the **Create profile** pane, and hit **Create**.

The profile will be created and appears on the profiles list pane.

## Next steps

If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).



