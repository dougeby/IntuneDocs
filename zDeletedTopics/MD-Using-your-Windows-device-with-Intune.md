---
title: MD Using your Windows device with Intune
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: fb557a13-cc0f-4d78-901d-cac6c793b085
---
# MD Using your Windows device with Intune
Use these steps  for tasks that you need to do on your Windows device or computer when your company is using Microsoft Intune:

|Task category|Tasks you can do|
|-----------------|--------------------|
|Company Portal app installation and Intune enrollment|[Enroll your Windows device in Intune](#BKMK_windows_enroll_instrucs)<br /><br />[What happens when I install the Company Portal app and enroll my device in Intune?](#BKMK_what_happns_enroll_all)<br /><br />[What can my IT admin see when I enroll my device in Intune?](#BKMK_win_what_IT_can_see)|
|Things you can do when your device is enrolled in Intune|[What is the Company Portal website?](#BKMK_win_whatis_cp_website)<br /><br />[Encrypt your device](#BKMK_win_encrypt_device)<br /><br />[Reset (erase) your lost or stolen device](#BKMK_win_erase_lost_device)<br /><br />[What happens if I reset my Windows device using the Company Portal?](#BKMK_win_what_happs_reset_devc)<br /><br />[Unenroll your device from Intune](#BKMK_win_unenroll_device)<br /><br />[What happens when I remove my device from the Company Portal?](#BKMK_what_happs_unenroll_win)<br /><br />[Turn off Microsoft usage data collection](#BKMK_windows_pc_data_collect)|
|Fix Intune issues with your device|[Device doesn't have the required minimum operating system version](#BKMK_win_no_min_os)<br /><br />[Device doesn't comply with the maximum operating system version](#BKMK_win_no_max_os)|

## <a name="BKMK_windows_enroll_instrucs"></a>Enroll your Windows device in Intune
To enroll, use the link that corresponds to the device you are using:

-   [Windows 10](#BKMK_enrollment_w10)

-   [Windows 8.1 or Windows RT 8.1](#BKMK_enrollment_w81orwrt81)

-   [Windows RT](#BKMK_enrollment_rt)

-   [Windows Phone 8.1](#BKMK_enrollment_81)

-   [Windows Phone 8](#BKMK_enrollment_wp8)

### <a name="BKMK_enrollment_w10"></a>Windows 10
To enroll your device:

1.  Go to Windows  **Settings** and tap **Accounts**.

    ![](../Image/IW-Help-pics/W10-enroll-1-settings-accounts.png)

2.  Tap **Your account**.

    ![](../Image/IW-Help-pics/W10-enroll-2-accounts-your-account.png)

3.  Tap **Add a work or school account**.

    ![](../Image/IW-Help-pics/W10-enroll-3-add-work-school-acct.png)

4.  Sign in with your work or school credentials.

    ![](../Image/IW-Help-pics/W10-enroll-4-sign-in.png)

If you followed the steps above, but still can't access your work or school email, files, and other data, go back to **Accounts** and tap **Work access**.

-   If you see your work or school account, congratulations. You’re connected.

-   If you don’t see your work or school account, tap **Connect**, and then sign in with your work or school credentials.

We also recommend that you install the Company Portal app, which lets you easily identify and get the company apps that are relevant to you and your role. Depending on how your company  configured Intune, the Company Portal app may have been installed as part of your enrollment process. To check if you have the app, look for **Company Portal** in your apps list. If you don't see the Company Portal in your list of apps, follow these steps to install it.

1.  Tap **Start** &gt; **Store**.

2.  Tap **Search** and type **company portal**.

3.  In the list of results, tap **Company Portal** &gt; **Install**.

4.  Tap  either **Install** or **Free**. The option shown depends on how your company configured the app.

### <a name="BKMK_enrollment_w81orwrt81"></a>Windows 8.1 or Windows RT 8.1
To enroll your device:

1.  On the device, tap **Settings** &gt; **PC Settings** &gt; **Network** &gt; **Workplace**.

    ![](../Image/IW-Help-pics/W81-1-workplacejoin.png)

2.  Enter your work or school email for the User ID, if required, and then tap **Join**.

    If your user ID is not required,  the email address that you entered when you logged into this device is used.

3.  Type the password for your work or school email.

    ![](../Image/IW-Help-pics/W81-2-workplacesettings_signin.png)

4.  Under **Turn on device management**, tap **Turn on**.

    ![](../Image/IW-Help-pics/W81-3-dev-mgt-turn-on.png)

5.  In the **Allow apps and services from IT admin** dialog,  select the  **I agree** check box, and then tap **Turn on**.

    ![](../Image/IW-Help-pics/W81-4-agree-allow-apps-services.png)

    When you have successfully enrolled, you'll see the following screen.

    ![](../Image/IW-Help-pics/W81-5-enrolled-done.png)

We also recommend that you install the Company Portal app, which lets you easily identify and get the company apps that are relevant to you and your role. Depending on how your company  configured Intune, the Company Portal app may have been installed as part of your enrollment process. To check if you have the app, look for **Company Portal** in your apps list. If you don't see the Company Portal in your list of apps, follow these steps to install it.

1.  Tap **Start** &gt; **Store**.

2.  Tap **Search** and type **company portal**.

3.  In the list of results, tap **Company Portal**.

4.  Tap  either **Install** or **Free**. The option shown depends on how your company configured the app.

### <a name="BKMK_enrollment_rt"></a>Windows RT
To enroll your device:

1.  Tap **Start**, and then type **System Configuration**.

2.  Tap the dialog box to open the **Company Apps**. You may be asked to accept your company’s Terms and Conditions.

3.  Sign in using your credentials.

We also recommend that you install the Company Portal app, which lets you easily identify and get the company apps that are relevant to you and your role. Depending on how your company  configured Intune, the Company Portal app may have been installed as part of your enrollment process. To check if you have the app, look for **Company Portal** in your apps list. If you don't see the Company Portal in your list of apps, follow these steps to install it.

1.  Tap **Start** &gt; **Store**.

2.  Tap **Search** and type **company portal**.

3.  In the list of results, tap **Company Portal**.

4.  Tap **Company Portal** &gt; **Install**.

### <a name="BKMK_enrollment_81"></a>Windows Phone 8.1
To enroll your device in Intune, follow the instructions that apply to your company:

-   [If your company lets you use the Company Portal from the Windows Store](#BKMK_comp_allows_cp)

-   [If you aren’t allowed to access the Windows Store from your Windows Phone, or if you don’t have a Microsoft Account](#BKMK_comp_doesnt_allow_cp)

#### <a name="BKMK_comp_allows_cp"></a>If your company lets you use the Company Portal from the Windows Store
Install the Company Portal app on your device:

1.  Tap **Start** &gt; **Store**.

2.  Tap **Search** and type **company portal**.

3.  In the list of results, tap **Company Portal**.

    ![](../Image/IW-Help-pics/WP81-1-CP-search-store-v2.png)

4.  Tap **Company Portal**  &gt; **Install**.

    ![](../Image/IW-Help-pics/WP81-2-CP-install-v2.png)

Enroll your device:

1.  On the device, open the **Microsoft Intune Company Portal** app.

2.  Provide your credentials. You may be asked to accept your company’s Terms and Conditions, if applicable.

3.  Swipe to **My Devices**.

4.  Tap **Tap to enroll or identify this device**.

    ![](../Image/IW-Help-pics/WP81-enroll-1-swipe-my-devices.png)

5.  Tap **Enroll this device**.

    ![](../Image/IW-Help-pics/WP81-enroll-2-enroll-this-device.png)

6.  Tap **Add account**.

    ![](../Image/IW-Help-pics/WP81-enroll-3-workplace-add-acct.png)

7.  Enter additional information as requested and then tap **sign in** to complete the enrollment. You should now see your workplace account listed on the **Settings** &gt; **Workplace** page.

    ![](../Image/IW-Help-pics/WP81-enroll-4-account-added.png)

#### <a name="BKMK_comp_doesnt_allow_cp"></a>If you aren’t allowed to access the Windows Store from your Windows Phone, or if you don’t have a Microsoft Account

1.  Tap  **Settings** &gt; **workplace**.

2.  Tap **add account**, and then sign in using your work account.

3.  Enter additional information as requested, and then tap **sign in** to complete the enrollment.

4.  If prompted to install the company app or Hub, make sure the relevant box is checked and then tap **done**.

If your IT admin has configured the Company Portal to be installed  during enrollment, you will see the Company Portal appear in your app list.

### <a name="BKMK_enrollment_wp8"></a>Windows Phone 8
Enroll your device:

1.  On the device, tap  **Settings** &gt; **company apps**.

2.  Tap **add account**, and then sign in using your work account.

3.  After the account is successfully added, you should be prompted to install the company app or Hub. Make sure the relevant box is checked and then tap **done**.

The Company Portal will appear in your app list after it is installed.

## <a name="BKMK_what_happns_enroll_all"></a>What happens when I install the Company Portal app and enroll my device in Intune?

### <a name="BKMK_what_happens_w10"></a>What happens when I install the Company Portal app and enroll my Windows 10 device in Intune?
When you install the Company Portal app and then use the app to enroll your Windows 10 Enterprise  or Professional device in Intune, you can then use the Company Portal app to:

-   Access the company’s network, and your email and work files

-   Get company apps from the Company Portal

-   Automatically configure your company email account

-   Reset your phone to factory settings if it is lost or stolen

For the steps to enroll, see [Windows 10](#BKMK_enrollment_w10). For information about what your IT admin can and can't see on your device, see [What can my IT admin see when I enroll my device in Intune?](#BKMK_win_what_IT_can_see)

When you add a computer:

-   You’ll have some software installed on your computer to make it possible for your IT administrator to manage the computer, and make it possible for you to get to company resources like apps and support information. This software may be updated automatically by your IT administrator.

-   [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] Endpoint Protection may be installed on your computer. This is software that checks for viruses and malware. For more information, please refer to the [Endpoint Protection Privacy Statement](http://go.microsoft.com/fwlink/?LinkID=247324).

-   Your IT administrator can take an inventory of all of the software installed on the computer, including software you have personally installed.

-   Require you to accept terms and conditions.

-   Your IT administrator can collect or delete data from your computer’s hard drive. Your IT administrator could also delete the entire hard drive.

-   Your IT administrator can install apps and updates on your computer.

-   Your IT administrator may enforce policies on the computer. For example, you might be required to set a password or PIN on the computer, which may lock you out of the computer, or delete all data from your computer’s hard drive, if there are too many incorrect password attempts.

### <a name="BKMK_what_happens_w81"></a>What happens when I install the Company Portal app and enroll my Windows 8.1 or Windows RT device in Intune?
When you install the Company Portal app and then use the app to enroll your Windows 8.1 Enterprise  or Professional or Windows RT device in Intune, you can then use the Company Portal app to:

-   Access the company’s network, and your email and work files

-   Get company apps from the Company Portal

-   Automatically configure your company email account

-   Reset your phone to factory settings if it is lost or stolen

For the steps to enroll, see [Windows 8.1 or Windows RT 8.1](#BKMK_enrollment_w81orwrt81). For information about what your IT admin can and can't see on your device, see [What can my IT admin see when I enroll my device in Intune?](#BKMK_win_what_IT_can_see)

When you add a computer:

-   You’ll have some software installed on your computer to make it possible for your IT administrator to manage the computer, and make it possible for you to get to company resources like apps and support information. This software may be updated automatically by your IT administrator.

-   [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] Endpoint Protection may be installed on your computer. This is software that checks for viruses and malware. For more information, please refer to the [Endpoint Protection Privacy Statement](http://go.microsoft.com/fwlink/?LinkID=247324).

-   Your IT administrator can take an inventory of all of the software installed on the computer, including software you have personally installed.

-   Require you to accept terms and conditions.

-   Your IT administrator can collect or delete data from your computer’s hard drive. Your IT administrator could also delete the entire hard drive.

-   Your IT administrator can install apps and updates on your computer.

-   Your IT administrator may enforce policies on the computer. For example, you might be required to set a password or PIN on the computer, which may lock you out of the computer, or delete all data from your computer’s hard drive, if there are too many incorrect password attempts.

### <a name="BKMK_what_happens_phone8"></a>What happens when I install the Company Portal app and enroll my Windows Phone 8.1 or Windows Phone 8 device in Intune?
When you install the Company Portal app and then use the app to enroll your Windows Phone 8.1 or Windows Phone 8 device in Intune, you can then use the Company Portal app to:

-   Access the company’s network, and your email and work files

-   Get company apps from the Company Portal

-   Automatically configure your company email account

-   Reset your phone to factory settings if it is lost or stolen

For the steps to enroll, see[Windows Phone 8.1](#BKMK_enrollment_81) or [Windows Phone 8](#BKMK_enrollment_wp8).  For information about what your IT admin can and can't see on your device, see [What can my IT admin see when I enroll my device in Intune?](#BKMK_win_what_IT_can_see).

When you add your Windows Phone device, you are giving your IT administrator permission to access the device. They can do things like:

-   Reset your device back to manufacturer’s default settings. This is helpful if the device is lost or stolen.

-   Remove all company related data and business apps that were installed. Your personal data and settings aren’t removed.

-   Force you to have a password or PIN on the device, which may lock you out of the device, or reset your device back to manufacturer’s default settings, which may include the deletion of data, if there are too many incorrect password attempts.

-   Force all the data on the device to be encrypted. This helps protect the data if the device is lost or stolen.

-   Require you to accept terms and conditions.

-   Disable the SD card.

-   Install updates to apps on your device. This applies to updates only. Your IT administrator cannot force new apps to install on your device, but you can choose to install apps you see in the company portal.

-   After your device is added to the company portal, approximately every 8 hours it will:

    -   Download any policy or app updates that your IT administrator has made available.

    -   Send any hardware inventory updates.

    -   Send any company app inventory updates.

### <a name="BKMK_what_happens_vista"></a>What happens when I install the Company Portal app and enroll my Windows 7 or  Vista device in Intune?
When you install the Company Portal app and then use the app to enroll your Windows 7 or Vista device in Intune, you can then use the Company Portal app to:

-   Access the company’s network, and your email and work files

-   Get company apps from the Company Portal

-   Automatically configure your company email account

-   Reset your phone to factory settings if it is lost or stolen

For information about what your IT admin can and can't see on your device, see [What can my IT admin see when I enroll my device in Intune?](#BKMK_win_what_IT_can_see).

When you add a computer:

-   You’ll have some software installed on your computer to make it possible for your IT administrator to manage the computer, and make it possible for you to get to company resources like apps and support information. This software may be updated automatically by your IT administrator.

-   [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] Endpoint Protection may be installed on your computer. This is software that checks for viruses and malware. For more information, please refer to the [Endpoint Protection Privacy Statement](http://go.microsoft.com/fwlink/?LinkID=247324).

-   Your IT administrator can take an inventory of all of the software installed on the computer, including software you have personally installed.

-   Require you to accept terms and conditions.

-   Your IT administrator can collect or delete data from your computer’s hard drive. Your IT administrator could also delete the entire hard drive.

-   Your IT administrator can install apps and updates on your computer.

-   Your IT administrator may enforce policies on the computer. For example, you might be required to set a password or PIN on the computer, which may lock you out of the computer, or delete all data from your computer’s hard drive, if there are too many incorrect password attempts.

## <a name="BKMK_win_what_IT_can_see"></a>What can my IT admin see when I enroll my device in Intune?
When  you enroll your device in Intune, you are giving your IT administrator permission to manage your device to help protect the company information on the device.

**What IT cannot see**

-   Call history

-   Text messages

-   Personal email, contacts, and calendar

-   Web history

-   Location

-   Camera roll

-   Personal data

**What IT can see**

-   Owner

-   Device name

-   Serial number

-   Manufacturer

-   Model

-   Operating system

-   Company apps

-   Personal apps

## <a name="BKMK_win_whatis_cp_website"></a>What is the Company Portal website?
The Company Portal website is your company’s web interface that you use to  manage your work computers and devices, and your personal computers and devices that you choose to use at work.

Once you add your computer or device to the Company Portal, you can:

-   Browse for and download company apps

-   Manage devices that you have added to the Company Portal

-   Find contact information for your IT administrator

When you add a computer or device to the Company Portal, some software may be installed or an app may be downloaded (depending on the device). You are also giving your IT administrator permission to manage your device to help protect the company information on the device.

## <a name="BKMK_win_encrypt_device"></a>Encrypt your device
You can encrypt your device either by adding a Microsoft account or by enabling BitLocker.

**Option 1: Add a Microsoft account**

1.  Search for, then start the **PC Settings** app.

2.  Click **Accounts** &gt; **Your account**, and then click **Connect to a Microsoft account**.

3.  Follow the instructions shown.

4.  Ensure that your device is enrolled with [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] by following the instructions in [Enroll your device to use it at work](http://go.microsoft.com/fwlink/?LinkId=519071).

**Option 2: Enable BitLocker**

1.  Search for, then start the **Manage BitLocker** app.

2.  Click **Turn on BitLocker**, then follow the instructions shown to encrypt each of your drives.

3.  Ensure that your device is enrolled with [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] by following the instructions in [Enroll your device to use it at work](http://go.microsoft.com/fwlink/?LinkId=519071).

## <a name="BKMK_win_erase_lost_device"></a>Reset (erase) your lost or stolen device
If your device is enrolled in Intune, and your device is lost or stolen, you can reset it to factory defaults.

> [!WARNING]
> Resetting a device to factor defaults removes both your personal and work information from it. For more about what happens when you reset your device, see [What happens if I reset my Windows device using the Company Portal?](#BKMK).

1.  In your browser, open your Company Portal, and sign in to your work account.

2.  Under **My Devices**, select the lost or stolen device.

3.  Tap **Reset** &gt; **Reset**.

> [!NOTE]
> If you are unable to reset your lost or stolen device, contact IT to reset it for you.

## <a name="BKMK_win_what_happs_reset_devc"></a>What happens if I reset my Windows device using the Company Portal?
When you use the Company Portal to reset your personal device, some apps and settings on your device may be deleted, including some of your personal data. What happens on each device depends on the type of device you have and how you are using the device, as described in the following table. For instructions on how to reset your lost or stolen device, see [Reset (erase) your lost or stolen device](#BKMK_win_erase_lost_device).

|Device configuration and management|Device type|
|---------------------------------------|---------------|
|Your IT admin manages your mobile device|**Android**<br /><br />When you reset your Android device, your device won’t appear in the company portal anymore and your company email account will be deleted and unsaved email will be deleted.<br /><br />**iOS Devices (iPhone and iPad)**, your device won’t appear in the company portal anymore and the company portal tries to reset the device back to the manufacturer’s default settings. Your personal data, apps and settings will be removed.<br /><br />**Windows Phone 8.1 and Windows Phone 8**, your device won’t appear in the company portal anymore and the company portal tries to reset the device back to the manufacturer’s default settings. Your personal data, apps and settings will be removed.<br /><br />**Windows RT**<br /><br />You cannot reset a Windows RT device unless it is used for email only.|
|Your device can access company email only|**Android**<br /><br />Your device won’t appear in the company portal anymore and the company portal tries to reset the device back to the manufacturer’s defaults. All your personal data and settings will be removed.<br /><br />**iOS Devices (iPhone and iPad)**<br /><br />Your device won’t appear in the company portal anymore and your company email account will be deleted and unsaved email will be deleted.<br /><br />**Windows Phone 8.1 and Windows Phone 8**<br /><br />Your device won’t appear in the company portal anymore and your company email account will be deleted and unsaved email will be deleted.<br /><br />**Windows RT**<br /><br />Your device won’t appear in the company portal anymore and your company email account will be deleted and unsaved email will be deleted.<br /><br />**Windows 7 or Windows Vista Computers**<br /><br />You cannot reset a computer that is running Windows 7 or earlier that is used for email only.<br /><br />**Windows 8.1 and Windows 8 Computers**<br /><br />Your device won’t appear in the company portal anymore and your company email account will be deleted and unsaved email will be deleted.|
|PCs and laptops|**Windows 8.1 and Windows 8 Computers**<br /><br />You cannot reset a computer that is running Windows 8 or Windows 8.1 unless it is used for email only.<br /><br />**Windows 7 or Windows Vista Computers**<br /><br />You cannot reset a computer that is running Windows 7 or earlier.|

## <a name="BKMK_win_unenroll_device"></a>Unenroll your device from Intune
If you enrolled in Intune, but no longer want to use your device for work or school and don't need to access work or school email, apps, or other resources, you need to unenroll your device.   Once you unenroll your device from Intune, you will no longer be able to access these resources. For more about what happens when you unenroll your device, see [What happens when I remove my device from the Company Portal?](#BKMK_what_happs_unenroll_win).

To unenroll your device, use the steps that match the device you're using.

### <a name="BKMK_win_unenroll_w10"></a>Unenroll your Windows 10 device

1.  From your apps list, tap the **Company Portal** app.

2.  Sign in using your work or school credentials.

3.  In **My Devices**, select the device you want to unenroll.

4.  Tap **Remove** &gt; **Remove**.

### Unenroll your Windows 8.1 computer

1.  Go to **PC Settings** &gt; **Network** &gt; **Workplace**.

2.  Under **Workplace Join**, tap **Leave**.

3.  Under **Turn on device management,** tap **Turn off**.

4.  On the popup window that opens, tap **Turn off**.

### Unenroll your Windows Phone 8.1 device

1.  Go to **Settings** &gt; **Workplace**.

2.  Tap the workplace account that you want to unenroll.

3.  Tap **Delete** at the bottom of the screen.

4.  On the **Delete account** dialog, tap **Delete**.

## <a name="BKMK_what_happs_unenroll_win"></a>What happens when I remove my device from the Company Portal?
The following events happen when you remove my device from the Company Portal

**Windows Phone 8.1 or Windows Phone 8**

-   The Company Portal app is uninstalled from your device, which means that your device won’t appear in the company portal anymore, and you won't be able to install apps from the Company Portal app or Company Portal website.

-   You can’t use company apps and company data on your device anymore.

-   Any settings that were changed on your device when you added it, for example disabling the camera, or requiring a certain password length, will no longer apply.

    > [!IMPORTANT]
    > The only exception to this is encryption policies, which will still apply. If your company policy required that your Windows Phone be encrypted, the only way to unencrypt your phone is to reset your phone using the **Settings** menu on your Windows Phone.

**Windows RT running Windows 8.1 or Windows RT**

-   The Company Portal app is uninstalled from your device, which means that your device won’t appear in the company portal anymore, and you won't be able to install apps from the Company Portal.

-   You can’t use company apps and company data on your device anymore.

-   Any settings that were changed on your device when you added it, for example disabling the camera, or requiring a certain password length, will no longer apply.

-   You might not be able to connect to your company network using Wi-Fi or a Virtual Private Network anymore.

-   You might not have access to some company resources, such as file shares or internal web sites, on your device anymore.

-   Some mail apps, such as Windows Mail, won’t be able to access company email that is stored on your device anymore.

When you remove your Windows RT device, the following happens:

-   The Company Portal app is uninstalled from your device, which means that your device won’t appear in the company portal anymore, and you won't be able to install apps from the Company Portal.

-   You can’t use company apps and company data on your device anymore.

-   Any settings that were changed on your device when you added it, for example disabling the camera, or requiring a certain password length, will no longer apply.

**Windows 8.1, Windows 8, Windows 7, Vista**

-   Your device won’t appear in the company portal anymore, and you can’t install apps from the company portal anymore.

-   If you installed the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] client software, it’s removed from your computer.

-   The [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] Endpoint Protection software is removed from your computer. If your computer has other virus protection software installed and it is disabled, that software may be re-enabled after [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] Endpoint Protection is removed. You should check your computer after removing it from the company portal.

    > [!IMPORTANT]
    > If the other virus protection software is not re-enabled or no other virus protection software is installed, your computer may be vulnerable to viruses and malware.

-   Any settings that were changed on your device when you added it (for example, disabling the camera, will no longer apply).

-   Your computer will no longer receive automatic software updates or antivirus software updates from the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] service. However, depending on how it is configured, your computer may still receive updates from the Windows Server Update Services, Windows Update, or Microsoft Update.

In addition, for Windows 8.1:

-   You can’t use company apps and company data on your device anymore.

-   Some mail apps, such as Windows Mail, won’t be able to access company email that is stored on your device anymore.

-   You might not be able to connect to your company network using Wi-Fi or a Virtual Private Network.

-   You might not have access to some company resources, such as file shares or internal web sites, on your device anymore.

## <a name="BKMK_windows_pc_data_collect"></a>Turn off Microsoft usage data collection
In order to improve its products and services, Microsoft automatically collects anonymous data about the reliability and performance of the Company Portal app and how it is used. You can turn off the collection of that data by using the Usage Data setting in the Company Portal app. IT administrators have no control over the collection of the data, and they cannot change your selection for the setting.

## <a name="BKMK_win_troubleshoot_device"></a>Fix issues with your device
Use this information to fix issues with your device when you're trying to install the Company Portal app, enroll your device in Intune, or if you've already enrolled in Intune.

### <a name="BKMK_win_no_min_os"></a>Device doesn't have the required minimum operating system version
Your device doesn’t meet the minimum operating system version required by your IT department. Before updating your mobile device, check the current operating system version by tapping **Settings** &gt; **about**, and then tap **Settings** &gt; **phone update** &gt; **check for updates** to update your device.

Before updating your computer, search for **operating system** and follow the prompts to identify your current operating system version. To update computers with operating systems earlier than Windows 10, search for **Windows updates**.

> [!NOTE]
> If your Windows operating system version is 8.1, you’ll see 6.3.xxxx instead of 8.1 when you check your update version.

### <a name="BKMK_win_no_max_os"></a>Device doesn't comply with the maximum operating system version
Your device does not comply with your IT admin's policy for the maximum version of the operating system. Contact your IT admin for help.

