# Azure Table

Connect CoW to an Azure Table Storage table containing your devices. COW reads your devices from the table, looks up warranties, and (optionally) writes the results back into the same rows.

### Prerequisites

Your table must contain these columns (all required — the Test step fails if any are missing):

* `ClientName`: the end client each device belongs to.
* `DeviceSerial`: the device serial number (CoW's lookup key).
* `DeviceManufacturer`: the manufacturer. If blank or `Unknown`, CoW attempts to detect it from the serial.
* `DeviceName`: a friendly device name.
* `CompanyId`: your identifier for the client.
* `DeviceId`: your identifier for the device.

`StartDate` and `EndDate` are optional (CoW reads existing warranty dates if present, and overwrites them on write-back). Each row's Azure `PartitionKey`/`RowKey` are used to target write-back, so keep them stable.

## Import Steps

{% stepper %}
{% step %}
### Create a SAS link

Follow Microsoft's documentation to create a [shared access signature (SAS) link](https://learn.microsoft.com/en-us/azure/ai-services/translator/document-translation/how-to-guides/create-sas-tokens?tabs=Containers).
{% endstep %}

{% step %}
### Enter SAS Details

Enter the Storage Account Name, Table Name, and SAS token.
{% endstep %}

{% step %}
### Test the Connection

Click Test to confirm the token authenticates, the table is readable, and all required columns are present (your table needs at least one row for the column check).
{% endstep %}

{% step %}
### Enable the Integration

Toggle on "Enable Integration". Optionally toggle "Write Back to Table" to save warranty results (`StartDate`, `EndDate`, `Warranty`, `Status`, `WarrantyJSON`) back onto your existing rows.
{% endstep %}

{% step %}
### Submit

Click Submit to save the enablement of the integration
{% endstep %}
{% endstepper %}

{% hint style="warning" %}
For write-back, the SAS token needs Read, Add, and Update permissions. Set the expiry well into the future — syncs stop when the token expires.
{% endhint %}
