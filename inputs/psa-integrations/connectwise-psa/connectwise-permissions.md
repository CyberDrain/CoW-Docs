# Connectwise Permissions

To enable secure warranty sync while following least privilege principles, you’ll need to create a dedicated API member and role.

### Custom Role Creation

{% stepper %}
{% step %}
### Open System > Security Roles


{% endstep %}

{% step %}
### Create a new Role

Best practice is to create a custom role for each integration to be sure to scope the integration to the least priviledged access. Be sure to name the role something easily identifiable, e.g. `CyberDrain Only Warranties`
{% endstep %}

{% step %}
### Set Required Permissions

The following permissions are needed for COW to function properly. All other settings can remain set as `None`:

| Module    | Function            | Add | Edit | Delete | Inquire |
| --------- | ------------------- | --- | ---- | ------ | ------- |
| Companies | Company Maintenance |     |      |        | All     |
|           | Configurations      |     | All  |        | All     |
| System    | Table Setup         |     |      |        | All     |

For the Table Setup function, click the customize link next to the function and select the following and add them to the "Allow Access to these" section:

* Company / Company Status
* Company / Company Type
* Company / Configuration
* Company / Configuration Status
{% endstep %}
{% endstepper %}

### **API Member Creation**

{% stepper %}
{% step %}
Go to System > Members > API Members


{% endstep %}

{% step %}
Create new API member


{% endstep %}

{% step %}
Assign the custom role created above


{% endstep %}

{% step %}
Under **API Keys**, generate the **Public/Private Key Pair**


{% endstep %}

{% step %}
Save the **Company, Site, URL**, and **Keys** in your warranty sync setup


{% endstep %}
{% endstepper %}
