# Halo PSA Permissions

**General Authentication Permission**

* The user must have valid API credentials and be enabled for token-based auth.

**Read Access to Assets**

* This checks that the account can retrieve at least one asset/device.

**Read Access to Asset Types**

* These are typically under **Asset Type Management** or **Configuration** settings.

**Read Access to Clients**

* Used to associate devices with clients during sync.

***

To support the above operations securely with least privilege access, you require view permissions for Assets, Asset Types, Clients as well as Edit permission for Asset Types in order to write back.

**Role Creation Steps:**

* Create a new Role: `COW Warranty Sync`
* Set **default** access to **none/deny**, then grant only what's needed:

**Permissions to Grant:**

| Area                             | Permission  | Why                                                       |
| -------------------------------- | ----------- | --------------------------------------------------------- |
| **Assets / Configuration Items** | View All    | To retrieve device data                                   |
| **Asset Types**                  | View All    | To interpret classification & sync metadata               |
| **Clients / Companies**          | View All    | To associate devices with companies                       |
| For Writebacks                   | Edit Assets | To allow sync to update device records with warranty info |
