## Enable Windows 10 automatic enrollment

Automatic enrollment lets users enroll either company-owned or personal Windows 10 PCs and Windows 10 Mobile devices in Intune by adding a work or school account and agreeing to be managed. Simple as that. In the background, the user's device registers and joins Azure Active Directory. Once registered, the device is managed with Intune.

**Prerequisites**
- Azure Active Directory Premium subscription ([trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845))
- Microsoft Intune subscription


### Configure automatic MDM enrollment

1. Sign in to the [Azure management portal](https://portal.azure.com) (https://manage.windowsazure.com), and select **Azure Active Directory**.

  ![Screenshot of the Azure portal](../media/auto-enroll-azure-main.png)

2. Select **Mobility (MDM and MAM)**.

  ![Screenshot of the Azure portal](../media/auto-enroll-mdm.png)

3. Select **Microsoft Intune**.

  ![Screenshot of the Azure portal](../media/auto-enroll-intune.png)

4. Configure which users will automatically enroll.

  ![Screenshot of the Azure portal](../media/auto-enroll-scope.png)

  Use the default values for the following URLs:
  - **MDM Enrollment**
  - **MDM Terms of Use**
  - **MDM Compliance**

5. Specify which users’ devices should be managed by Microsoft Intune. These users’ Windows 10 devices will be automatically enrolled for management with Microsoft Intune.

  - **All**
  - **Groups**
  - **None**

6. Select **Save**.
