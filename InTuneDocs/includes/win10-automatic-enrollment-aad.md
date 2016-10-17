## Azure Active Directory enrollment

Automatic enrollment lets users enroll either company-owned or personal Windows 10 PCs and Windows 10 Mobile devices in Intune by adding a work or school account and agreeing to be managed. Simple as that. In the background, the user's device registers and joins Azure Active Directory. Once registered, the device is managed with Intune.

**Prerequisites**
- Azure Active Directory Premium subscription ([trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845))
- Microsoft Intune subscription


### Configure automatic MDM enrollment

1. In the [Azure management portal](https://manage.windowsazure.com) (https://manage.windowsazure.com), navigate to the **Active Directory** node and select your directory.

2. Click the **Applications** tab and you should see **Microsoft Intune** in the list of applications.

    ![Azure AD apps with Microsoft Intune](../media/aad-intune-app.png)

3. Click on the arrow for **Microsoft Intune** and you should see a page that enables you to configure Microsoft Intune.

4. Click **Configure** to start configuring automatic MDM enrollment with Microsoft Intune.

5. Specify the URLs for Intune:

  - **MDM Enrollment URL** – Use the default value.
  - **MDM Terms of Use URL** – Use the default value. This URL displays terms of use for users when enrolling devices.
  - **MDM Compliance URL** – Use the default value. If a device is found to be out of compliance, an **Access denied** message is displayed with this URL. The URL points to a page that helps users understand why their device is not compliant with policy and how they can bring it back into compliance.

6.  Specify which users’ devices should be managed by Microsoft Intune. These users’ Windows 10 devices will be automatically enrolled for management with Microsoft Intune.

  - **All**
  - **Groups**
  - **None**

7. Choose **Save**.
