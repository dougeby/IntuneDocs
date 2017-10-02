---
# required metadata

title: Enroll your Android device in Intune | Microsoft Docs
description: Describes how to enroll an Android device in Intune
keywords:
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/02/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 0ed3a002-7533-4001-ae24-e10b64b66620
searchScope:
 - User help

# optional metadata

ROBOTS:  
#audience:
#ms.devlang:
ms.reviewer: arnab
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-enduser

---


# Enroll your Android device in Intune

If your company or school uses Microsoft Intune, you can enroll your Android device to get access to company email, files, and other resources. When you enroll your devices, your IT department can manage those work or school resources, keep them secure, and give you the freedom to use your preferred device to get your work done. To learn more about enrollment, see [What happens when I install and Company Portal app and enroll my device?](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-android.md)

> [!VIDEO https://channel9.msdn.com/Series/IntuneEnrollment/Android-Enrollment/player]

These enrollment instructions are for native and Samsung KNOX Android devices. Samsung KNOX is a type of security that certain Samsung devices use to provide additional protection outside of what native Android provides. To check if you have a Samsung KNOX device, go to **Settings** > **About device**. If you don't see "KNOX version" listed there, you have a native Android device.

Before or after enrolling, you may be asked to choose a category that best describes how you use your device. Your company support uses this category to help check the apps that you have access to.

**To enroll your Android device:**

1.  Install the free Intune Company Portal app from [Google Play](http://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal).

2.  Open the Company Portal app.

3.  On the Company Portal **Welcome** screen, tap **Sign in**, and then sign in with your work or school account.

    ![The Company Portal app for Android welcome screen, which asks the user to sign in with their required work or school account. It also cautions that Microsoft accounts and other personal accounts are not accepted.](./media/and-enroll-0-welcome-screen.png)   

4.  If your company support set up company terms and conditions, tap **ACCEPT** to accept the terms. This screen may differ slightly from the image below based on the version of Android you're currently using.

    ![android-company-portal-sign-in](./media/and-enroll-3-accept-terms.png)

5.  Sign in to the Company Portal app using your work or school account and password, and then tap **Sign in**.

    ![android-company-portal-sign-in](./media/and-enroll-2-cp-sign-in.png)

6.  On the **Company Access Setup** screen, tap **CONTINUE**.

    ![Company access setup screen](./media/android_cp_enroll_01_1709_new.png)

    > [!NOTE]
    > The yellow triangles don't mean you've already got an error. Those icons indicate that there are still steps to be completed in the enrollment process.

7.  Review a list of what your company support can and can't see on your device, and then tap **CONTINUE**.

	![Privacy settings](./media/android_cp_enroll_02_after_1710.png)

9.  On the **What's next?** screen, read about what happens during enrollment, and then tap **ENROLL**.

	![What comes next screen](./media/android_cp_enroll_03_after_1710.png)

10.  If you're using Android 6.0 or later, do this step. Otherwise, go to the next step.

	If your company support has set up certain policies, you may see the following messages:
	-	**Allow Company Portal to make and manage phone calls?**

		![android-company-portal-sign-in](./media/and-enroll-3a-allow-phone-access.png)

	If you see this message, tap **ALLOW**. It is safe to tap ALLOW because **Microsoft never makes or manages your phone calls**! Google controls the message text, and Microsoft cannot change it. When you allow access, all you're doing is letting your device send your device's international mobile station equipment identity (IMEI) number to Intune. The IMEI number is like a serial number that uniquely identifies a mobile device.

	If you deny access, the message will appear again the next time you sign in to the Company Portal, but you can turn off future messages by tapping the **Never ask again** box. If you later decide to allow access, go to **Settings** &gt; **Apps** &gt; **Company Portal** &gt; **Permissions** &gt; **Phone**, and then turn on the permission.

	-	**Allow Company Portal to access your contacts?**

        ![android-company-portal-sign-in](./media/and-enroll-3b-allow-contacts-access.png)

        If you see this message, tap **ALLOW**. It is safe to tap ALLOW because **Microsoft never accesses your contacts!** Google controls the message text, and Microsoft cannot change it. When you allow access, it only lets the Company Portal app create, use, and manage your work account.

        If you deny access, the message will appear again the next time you sign in to the Company Portal, but you can turn off future messages by tapping the **Never ask again** box. If you later decide to allow access, go to **Settings** &gt; **Apps** &gt; **Company Portal** &gt; **Permissions** &gt; **Phone**, and then turn on the permission.

11.  On the **Activate device administrator** screen, tap **Activate**.

    ![Activate device administrator screen](./media/and-enroll-5-activate.png)

    The device administrator role is one that the Company Portal needs to manage your device. It allows your admin to see certain things - like how many times you've attempted to unlock your screen - and to take some actions.

    The key to remember is that these are actions that are taken in the name of security. Your company support isn't trying to violate your privacy or erase your information for no reason, but wants to make sure that corporate data is kept safe.

    Microsoft does not control this message, and we understand that its phrasing can seem somewhat drastic. There's not a way for the Company Portal to display just the restrictions and access that are relevant to your organization. All of them are granted at once on this screen. Contact your company support for more information using the contact information in the [Company Portal website](https://portal.manage.microsoft.com) if you have questions specific to your individual organization's use.

12.  Follow the prompts to enter a PIN or password. If you already set up a PIN or password on this device, you won't see this screen or be required to enter a new PIN or password.

    ![Enter PIN or password](./media/and-enroll-6-PIN-native.png)

13.  If you are using a Samsung KNOX device, tap **Confirm**, and you’ll see a message that your device is being enrolled. If you are using a native Android device, just notice the following screen that shows that your device is being enrolled.

    ![Samsung KNOX privacy policy](./media/and-enroll-7-knox-privacy-policy.png)

    This screen shows that your device is being enrolled.

    ![Enrolling device screen](./media/and-enroll-8-device-enrolling.png)

14. When the **Company Access Setup** screen appears, tap **CONTINUE**. If a message indicates that your device is out of compliance, follow the instructions to fix the issue, and then tap **CONTINUE**.

    ![Device is not compliant but is enrolled](/intune/media/android_cp_enroll_05_post_1709.png)

    ![Device compliance issues appear that need resolution](/intune/media/android_cp_enroll_03_post_1709.png)

    You can find out more about the issues by tapping on them.

    ![Device compliance issues expanded](/intune/media/android_cp_enroll_04_post_1709.png)

    ![Company access setup screen](./media/and-enroll-9d-comp-access-setup.png)  

15. On the **Company Access Setup complete** screen, tap **DONE**. Your device is now enrolled.

    ![Company access setup complete screen](./media/and-enroll-10-comp-access-setup-complete.png)

Before you try to install company apps, go to **Settings** &gt; **Security**, and turn on **Unknown sources**. If you don't turn on this option before you try to install apps, you'll see the following message: "Install blocked. For security reasons, your device is set to block installations of apps obtained from unknown sources." You can tap **Settings** on the error dialog box to go to the **Unknown sources** option.

> [!Note]
> If your organization is using telecom expense management software, you will have an additional few steps to complete before your device is fully enrolled. Find out more [here](enroll-your-device-with-telecom-expense-management-android.md).

If you get an error while you try to enroll your device in Intune, you can [send enrollment errors to your company support](send-enrollment-errors-to-your-it-admin-android.md).

Still need help? Contact your company support (check the [Company Portal website](https://portal.manage.microsoft.com) for contact information), or write the <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with enrolling my Android device&body=Describe the issue you're experiencing here.">Microsoft Android team</a>.
