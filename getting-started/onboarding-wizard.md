# Onboarding Wizard

## Introduction

The onboarding wizard consists of four steps that guide you through selecting and configuring the source of your device data, allowing you to connect your PSAs credentials and define your own sync options. The wizard then allows you to review and confirm the settings before applying changes.

***

{% stepper %}
{% step %}
## Select Your Source

The first step is setting up your data source. Available options are:

1. [#manual-csv-import](../inputs/csv-import.md#manual-csv-import "mention")
2. [#azure-blob-storage-import](../inputs/csv-import.md#azure-blob-storage-import "mention")
3. **PSA Integration**
   1. [autotask-psa](../inputs/psa-integrations/autotask-psa/ "mention")
   2. [connectwise-psa](../inputs/psa-integrations/connectwise-psa/ "mention")
   3. [halopsa](../inputs/psa-integrations/halopsa/ "mention")

{% hint style="info" %}
**Note**: Selecting a PSA tool requires you to provide relevant credentials in the next step.
{% endhint %}
{% endstep %}

{% step %}
## Configure Your Source

Depending on your choice in Step 1, the wizard will guide you through the appropriate setup process.

* **For PSA Integration:** For each [psa-integrations](../inputs/psa-integrations/ "mention"), you need to enter specific credentials to connect successfully. For detailed instructions, refer to the respective integration pages linked in Step 1.
* **For CSV Import:** Upload the CSV file containing your device data via either manual import or Azure Blob Storage. Ensure that the file format meets the requirements. Check out the [csv-import.md](../inputs/csv-import.md "mention") page for more details.

{% hint style="warning" %}
Ensure the CSV file is correctly formatted with no empty columns. Only valid entries will be imported successfully.
{% endhint %}
{% endstep %}

{% step %}
## Select your Sync Options

Configure your preferences for email notifications (and device types & clients if integrating via PSA) according to your needs in this step.

### Email Notifications

Manage email alerts for different events to stay informed about the status of your sync processes:

* **Sync Completed**: Notify when a sync completes successfully.
* **Sync Failed**: Alert if a sync attempt fails.
* **Warranties Updated**: Inform when warranty information is updated.

### Device Types Sync (PSA Only)

If you're using a PSA integration you can configure which device types to include by toggling the switch next to each type. This allows you to control which devices are synced based on your current management needs.

### Client Sync (PSA Only)

Tell COW which clients from your PSA should be synced:

* **Sync All Clients**: Enable this option to sync data for all clients.
* **Selective Client Sync**: Disable `Sync All Clients` to select specific clients for synchronization.

{% hint style="info" %}
Carefully review each sync option to ensure your configurations align with your organizational needs.
{% endhint %}
{% endstep %}

{% step %}
## Confirmation

{% hint style="warning" %}
For PSA Integrations:

* Click the "Test" button to verify your credentials and connection. Ensure you see a success message before continuing.
* If the test fails, review the error messages displayed and correct any issues before proceeding.
{% endhint %}
{% endstep %}
{% endstepper %}

{% hint style="info" %}
After completing the onboarding process, monitor the initial syncs to confirm that data is being managed as expected. You can revisit this step later from the [settings.md](navigation/settings.md "mention") page to adjust based on your requirements.
{% endhint %}
