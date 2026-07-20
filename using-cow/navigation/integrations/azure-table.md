# Azure Table

Connect CoW to an **Azure Table Storage** table containing your devices — the self-serve option for technical MSPs who want to push and pull data programmatically. You run the table in your own Azure tenant and populate it however you like (script, Rewst, Power Automate, PSA export). COW reads your devices, looks up warranties, and — optionally — writes the results back into the same rows.

### Prerequisites

Your table must contain these columns (all required — the Test step fails if any are missing):

* `ClientName`: the end client each device belongs to.
* `DeviceSerial`: the device serial number (CoW's lookup key).
* `DeviceManufacturer`: the manufacturer. If blank or `Unknown`, CoW attempts to detect it from the serial.
* `DeviceName`: a friendly device name.
* `CompanyId`: your identifier for the client.
* `DeviceId`: your identifier for the device.

{% hint style="info" %}
**Optional**: `StartDate` / `EndDate` if you already hold warranty dates (CoW reads them, and overwrites on write-back). Each row's Azure `PartitionKey`/`RowKey` are used to target write-back — keep them stable.
{% endhint %}

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

### What CoW writes back

With **Write Back to Table** on, for each device where a warranty is found CoW updates that device's **existing row** (matched on its original `PartitionKey`/`RowKey`) with `StartDate`, `EndDate` (both `YYYY-MM-DD`), `Warranty` (description), `Status`, and `WarrantyJSON` (a compact JSON of all of it plus the lookup time). Unresolved devices are left untouched and retried next sync.

### Troubleshooting

* **Test fails "missing required columns"** — add the exact column names above (case-sensitive).
* **Test fails "table is empty"** — the column check needs at least one row.
* **Some devices never appear** — filtered for empty/placeholder `DeviceSerial`, blank `ClientName`, undetectable manufacturer, or your plan's device cap (upgrade to raise it).
* **Warranties aren't writing back** — confirm write-back is on, the SAS has Add/Update, and rows still have the `PartitionKey`/`RowKey` CoW first read them under.

{% hint style="warning" %}
For write-back, the SAS token needs Read, Add, and Update. Set the expiry well into the future — syncs stop when it expires.
{% endhint %}
