---
description: >-
  This overview helps users understand how to manage device info and warranties
  efficiently via the Devices page.
---

# Devices

## Actions

| Action                  | Description                                                                                                                                                                                                                                               |
| ----------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Import CSV              | This will allow you to import a CSV of devices if you need to utilize COW outside of one of the supported [integrations](../integrations/ "mention"). See [csv-import.md](csv-import.md "mention") for more information.                                  |
| Sync Devices            | Syncs the device list from your PSA to fill the table with the latest info based on the filters that you set during configuration.                                                                                                                        |
| Device Lifecycle Report | Generates a PDF lifecycle report. This is fully brandable with your own custom logo and primary color scheme. Select the client, report currency, and average replacement cost to update the PDF. Once completed, click `Download PDF` to save your copy. |

{% hint style="warning" %}
Make sure you download any latest data prior to updating to ensure the most up to date details are being reflected in your sync.
{% endhint %}

## Dashboard

| Component       | Description                                                 |
| --------------- | ----------------------------------------------------------- |
| Total Devices   | Displays the total # of devices identified from the import. |
| Percentage OK   | Shows the % of devices with valid warranties.               |
| Active Devices  | Displays the # of devices with active warranties.           |
| Expired Devices | Displays the # of devices with expired warranties.          |

### Sync Status Bar

This bar will show you the status of your warranty sync. It shows the current stage of the sync process along with a percentage of completion.

## Clients and Devices Table

The table provides detailed information about each device, with functionality to search, filter, sort, and manage data effectively.

### Table Details

| Column               | Description                                                                                                             |
| -------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| Client               | Displays the name of the client associated with each device.                                                            |
| Serial               | Shows the unique serial number of each device.                                                                          |
| Manufacturer         | Indicates the manufacturer of the device.                                                                               |
| Last Warranty Lookup | The date when the warranty was last checked.                                                                            |
| Expires in (days)    | Number of days remaining before the warranty expires. Will display as a negative number for already expired warranties. |
| Status               | Current status of the device’s warranty (e.g., No lookup performed).                                                    |
| Start Date           | The start date of the device’s warranty.                                                                                |
| End Date             | The expiration date of the warranty.                                                                                    |
| Warranty Type        | Describes the type of warranty (e.g., Unknown).                                                                         |

### Table Features

| Feature             | Description                                                                                                                           |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| Search Bar          | Quickly find devices by entering keywords such as client name, serial number, or manufacturer.                                        |
| Show / Hide Filters | Show or hide filters to refine the device list based on various in-line criteria at once like client, serial number, and manufacturer |
| Show / Hide Columns | Customize your view by showing or hiding specific columns for a tailored display of information.                                      |
| Density Toggle      | Adjust the table density for compact or comfortable viewing                                                                           |
| Density Toggle      | Export the table data to a PDF file for offline viewing or sharing or a CSV file for further processing.                              |

### Table Actions

<table><thead><tr><th>Action</th><th>Description</th><th data-type="checkbox">Bulk Action Available</th></tr></thead><tbody><tr><td>Get Warranty</td><td>Fetches the latest warranty details for the selected device from the CyberDrain Warranty API.</td><td>true</td></tr><tr><td>Delete Device(s)</td><td>Removes the device from the list. Use this action with caution, as it cannot be undone.</td><td>true</td></tr></tbody></table>
