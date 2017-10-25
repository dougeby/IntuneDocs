<!-- This include is part of the Intune Data Warehouse documentation. -->

## Azure AD and Intune credential requirements

Authentication and authorization are based on Azure AD credentials and Intune role-based access control (RBAC). All global administrators and Intune service administrators for your tenant have access to the Data warehouse by default. Use Intune roles to provide access for more users by giving them access to the **Reporting resource**.

Requirements for accessing the Intune Data Warehouse (including the API) are:

  -  Intune license must be assigned to the user
  -  User must be one of:
      -  Azure AD global administrator
      -  An Intune service administrator
      -  User with role-based access to **Reports** resource