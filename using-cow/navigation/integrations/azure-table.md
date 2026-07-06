# Azure Table

This option will allow you to connect to Azure Blob Storage and pull your devices from a table stored there.&#x20;

## Prerequisites

Before importing your data, ensure that your table meets the following specifications:

* **Columns**: Your table file must contain the following columns:
  * `ClientName`: The name of the client associated with each device.
  * `DeviceSerial`: The unique serial number of each device.
  * `DeviceProductNumber`: The product number for each device if required.
  * `DeviceManufacturer`: The manufacturer of each device.

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

Click the Test button to ensure the saved credentials are properly working
{% endstep %}

{% step %}
### Enable the Integration

Toggle on "Enable Integration". You can optionally toggle on "Write Back to Table" which will save the warranty data to your table
{% endstep %}

{% step %}
### Submit

Click Submit to save the enablement of the integration
{% endstep %}
{% endstepper %}

{% hint style="warning" %}
The SAS link needs Read, Create, and Write permissions and must be valid for at least a year
{% endhint %}
