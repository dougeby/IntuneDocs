---
# required metadata

title: Your device is missing a required certificate | Microsoft Intune
description:
keywords:
author: staciebarker
manager: angrobe
ms.date: 09/19/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 9081b1d8-50e8-4bc2-ba37-766421364213

# optional metadata

ROBOTS: NOINDEX,NOFOLLOW
#audience:
#ms.devlang:
ms.reviewer: arnab
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Your device is missing a required certificate


## Your device is missing a certificate that usually comes installed on your phone
If your Android device isn’t enrolled in Intune, and it’s missing a certificate that usually comes installed on your phone, you won’t be able to sign in to the Android Company Portal app. When you try to sign in, you’ll see the following message:

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

To fix this issue and get the required certificate:

1.  In a browser, go to this [Digicert certificate page](https://www.digicert.com/digicert-root-certificates.htm).

2.  Find and download the Baltimore CyberTrust Root certificate (https://www.digicert.com/CACerts/BaltimoreCyberTrustRoot.crt).

3.  Drag down from the top to open your notifications, and tap **BaltimoreCyberTrustRoot.crt** in the list of notifications.

4.  In the **Name the Certificate** dialog box, accept the default certificate name.

5. Ensure that **Credential Use** is set to **Used for VPN and apps**, and then tap **OK**.

	![screenshot-certificate-name-dialog-showing-baltimore-certificate-name](./media/andr-cert_install-2-add_cert_name.png)

6. Close the web browser and the Company Portal app.

7. Reopen the Company Portal app. You should now be able to sign in to the Company Portal app. If you need help, contact your IT admin.

## Your device is missing a certificate required by your IT admin
If your Android device isn’t enrolled in Intune, and it’s missing a certain certificate that is required by your IT admin, you won’t be able to sign in to the Android Company Portal app. When you try to sign in, you'll see the following message:

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

>[!NOTE]
> If you have already seen one "missing certificate" message, and followed the steps in [Your device is missing a certificate that usually comes installed on your phone](#your-device-is-missing-a-certificate-that-usually-comes-installed-on-your-phone), that's okay. That is a different message and certificate from this one, so go ahead and follow the steps in this section to get the missing certificate.

To fix this issue and get the required certificate, there are two main steps that you'll need to do:

- Identify the missing certificate by looking on a company or school PC.
- Use your device to download the missing certificate from the Internet.

### Identify the missing certificate by looking on a company or school PC

1. On a PC, open Internet Explorer. If you don't have a PC to use for this purpose, contact your IT admin. For your IT admin's contact information, check the [Company Portal website](http://portal.manage.microsoft.com).

2. Go to the [Company Portal website](http://portal.manage.microsoft.com), and sign in using your work or school credentials.

3. At the far right of the browser's address bar, choose the symbol that looks like a padlock, as shown in the following screenshot.

	![screenshot-internet-explorer-address-bar-padlock-symbol](./media/andr-missing-cert-ie-padlock-symbol.png)

	If you don't see the padlock symbol, stop and contact your IT admin. The lock means that you are securely signed in, so you should not proceed unless you see that symbol.

4. Choose **View certificates**.

	![screenshot-internet-explorer-view-certificates-button-on-website-identification-dialog](./media/andr-missg-cert-ie-view-cert-button.png)

5. In the **Certificate** dialog box, choose the **Certification path** tab, and then identify the certificate that you need to get from the Internet. The name of the certificate that you need will be in the same position as the one that is highlighted in the previous example screenshot.

### Download and install the missing certificate on your Android mobile device

1. Using a search engine like Bing or Google, search for the name of the missing certificate that you identified in the previous section. The certificate may end in different "extensions," like ".crt" or ".pem", etc.

2. Download the root certificate from the website.

3. After the certificate downloads, drag down from the top of your device to open your notifications, and then tap the name of the certificate in the list of notifications.

4. In the **Name the Certificate** dialog box shown in the following screenshot, accept the default certificate name.

5. Ensure that **Credential Use** is set to **Used for VPN and apps**, and then tap **OK**.

	![screenshot-certificate-name-dialog-showing-certificate-name](./media/andr-missing-cert-cert-name.png)

6. Close the Company Portal app.

7. Reopen the Company Portal app. You should now be able to sign in to the Company Portal app. If you need help, contact your IT admin.

If you see the same "missing certificate" message as the one shown previously, and you have already followed the procedure, there is probably still another certificate that your IT admin will need to help you install. Contact your IT admin and give that person this link to [Android certificate issues](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues), which has steps to help fix the issue.
