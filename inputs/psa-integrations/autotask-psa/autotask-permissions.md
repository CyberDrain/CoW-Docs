# Autotask Permissions

To enable secure warranty sync while following least privilege principles, you’ll need to create a dedicated API account and role.

### API  Security Levels setup

1. Go to Admin > Account Settings & users > Security Levels
2. Make a copy of API User (system) (API-only)
3. Click on "No Permission" for all items to prevent setting incorrect permissions
4. Click on the "CRM" header
5. Add "Customer & Cancelation" with "All" permission
6. Add "Configuration Items & Subscriptions" with "View All" and "Edit All" permissions
7. Click on the "Inventory" header
8. Add "Products" with "View All" permissions
9. Save this permission with your own name, such as "Cow.Tech Warranty Permissions"



**API account Setup Steps**

1. Go to **Admin >** Resources/Users **> API Members**
2. Create a new API user. Select the Security level we've just created.
3. Setup the API account according to your own procedures, giving it an email, internal location, and generate the credentials
4. Select the "CyberDrain B.V." API Tracking integration vendor.
5. Save the account and enter your credentials in cow.tech.
