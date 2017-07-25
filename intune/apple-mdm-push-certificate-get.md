---
# required metadata

title: Get an Apple MDM Push certificatetitleSuffix: "Intune on Azure"
description: Learn the steps for getting an Apple MDM Push certificate to manage iOS devices with Intune."
keywords:
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 04/14/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: dagerrit
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-azure

---

# Get an Apple MDM push certificate

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune enables mobile device management (MDM) of iPads, iPhones, and Mac computers and gives users access to company email and apps. An MDM Push certificate is required for Intune to manage iOS and Mac devices. After you add the certificate to Intune, your users can install the Company Portal app to enroll their devices. You can also set up corporate-owned iOS device management with Apple's Device Enrollment Program or enroll devices using Apple Configurator, for example. For more information about enrollment options, see [Choose how to enroll iOS devices](enrollment-method-choose-ios.md).

## Steps to get your certificate
In the Intune portal, choose **Device enrollment** > **Apple Enrollment** **Apple MDM Push Certificate**, and then follow the numbered steps in the Azure portal, which are shown below.

**Step 1. Download the Intune certificate signing request required to create an Apple MDM push certificate.**<br>
Select **Download your CSR** to download and save the .csr file locally. The .csr file is used to request a trust relationship certificate from the Apple Push Certificates Portal.
  ![Screenshot showing the Configure MDM Push Certificate screen with MDM Push not set up.](./media/create-mdm-push-certificate.png)
**Step 2. Create an Apple MDM push certificate.**<br>
Select **Create your MDM push Certificate** to go to the Apple Push Certificates Portal. Sign in with your company Apple ID to create the push certificate by using the .csr file. After choosing **Upload** on Apple's Push Certificate Portal, you will receive a .json file. Do use this file for the push certificate. Complete the download, return to the Apple Push Certificates Portal for Certificates for Third-Party Servers, and then choose **Download**. Download the push certificate (.pem file), and save the file locally.

> [!NOTE]
> The certificate is associated with the Apple ID used to create it. As a best practice, use a company Apple ID for management tasks. Never use a personal Apple ID.

**Step 3. Enter the Apple ID used to create your Apple MDM push certificate.**

**Step 4. Browse to your Apple MDM push certificate to upload.**<br>
Go to the certificate (.pem) file, choose **Open**, and then choose **Upload**. With the push certificate, Intune can enroll and manage iOS devices by pushing policy to enrolled mobile devices.

## Renew Apple MDM push certificate
The Apple MDM push certificate is valid for one year and must be renewed annually to maintain iOS and macOS device management. If your certificate expires, enrolled Apple devices cannot be contacted.

The certificate is associated with the Apple ID used to create it. Renew the MDM push certificate with the same Apple ID used to create it.

> [!NOTE]
> The certificate is associated with the Apple ID used to create it. As a best practice, use a company Apple ID for management tasks. Never use a personal Apple ID.

1. In the Intune portal, choose **Device enrollment** > **Apple Enrollment** and then select **Apple MDM Push Certificate**.
2. Select **Download your CSR** to download and save the .csr file locally. The .csr file is used to request a trust relationship certificate from the Apple Push Certificates Portal.
3. Find the certificate you want to renew and select **Renew**.
4. On the **Renew Push Certificate** screen, provide notes to help you identify the certificate in the future, select **Choose File** to browse to the new .csr file you downloaded, and choose **Upload**.
5. On the **Confirmation** screen, select **Download** and save the .pem file locally.
6. In the Azure Intune portal, select the **Apple MDM push certificate** browse icon, select the .pem file downloaded from Apple, and choose **Upload**.

Your Apple MDM push certificate appears **Active** and has 365 days until expiration.
