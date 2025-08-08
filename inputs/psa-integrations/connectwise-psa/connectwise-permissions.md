# Connectwise Permissions

To enable secure warranty sync while following least privilege principles, you’ll need to create a dedicated API member and role.

**API Member Setup Steps**

1. Go to **System > Members > API Members**
2. Create new API member (or reuse existing if scoped)
3. Assign the custom role above (e.g., `Warranty Sync - Limited`)
4. Under **API Keys**, generate the **Public/Private Key Pair**
5. Save the **Company, Site, URL**, and **Keys** in your warranty sync setup

#### **REQUIRED PERMISSIONS**

| **Module**    | **Function**           | **Access Level**   | **Why**                                                  |
| ------------- | ---------------------- | ------------------ | -------------------------------------------------------- |
| Companies     | Company Maintenance    | **Inquire Only**   | Fetch company list, types, statuses                      |
| Companies     | Company Statuses       | **Inquire Only**   | Filter to active companies only                          |
| Companies     | Company Types          | **Inquire Only**   | Allow filtering by partner type (MSP, client, etc.)      |
| Configuration | Configurations         | **Inquire + Edit** | Read and update warranty data                            |
| Configuration | Configuration Types    | **Inquire Only**   | Filter relevant device categories                        |
| Configuration | Configuration Statuses | **Inquire Only**   | 🔒 **Required**: avoids pulling inactive/retired devices |
