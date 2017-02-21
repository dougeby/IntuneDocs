## Set up Windows 10 and Windows 10 Mobile automatic enrollment with Azure Active Directory Premium

Automatic enrollment lets users enroll either company-owned or personal Windows 10 PCs and Windows 10 Mobile devices in Intune by adding a work or school account and agreeing to be managed. Simple as that. In the background, the user's device registers and joins Azure Active Directory. Once registered, the device is managed with Intune.

**Prerequisites**
- Azure Active Directory Premium subscription ([trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845))
- Microsoft Intune subscription


### Configure automatic MDM enrollment

1. In the [Azure management portal](https://portal.azure.com) (https://manage.windowsazure.com), navigate to the **Active Directory** node and select your directory.

2. Choose the **Applications** tab. **Microsoft Intune** appears in the list of applications.

    ![Azure AD apps with Microsoft Intune](../media/aad-intune-app.png)

3. Select the arrow for **Microsoft Intune**. A page opens that enables you to configure Microsoft Intune.

4. Select **Configure** to start configuring automatic MDM enrollment with Microsoft Intune.

5. Use the default values for the following URLs:

  - **MDM Enrollment**
  - **MDM Terms of Use** 
  - **MDM Compliance**

6.  Specify which users’ devices should be managed by Microsoft Intune. These users’ Windows 10 devices will be automatically enrolled for management with Microsoft Intune.

  - **All**
  - **Groups**
  - **None**

7. Choose **Save**.
