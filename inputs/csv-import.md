# CSV Import

The easiest way to test out COW and start importing device details is through a manual CSV import. This method allows users who prefer or require manual entry to efficiently integrate their data.

### File Requirements

Before importing your data, ensure that your CSV file meets the following specifications:

* **Columns**: Your CSV file must contain the following columns:
  * `ClientName`: The name of the client associated with each device.
  * `DeviceSerial`: The unique serial number of each device.
  * `DeviceProductNumber`: The product number for each device if required.
  * `DeviceManufacturer`: The manufacturer of each device.

#### Example CSV

**Download Sample**: To help you format your file correctly, download an [example CSV file](data:text/csv;charset=utf-8,%EF%BB%BFClientName%2CDeviceSerial%2CDeviceProductNumber%2CDeviceManufacturer%0A) that includes the required columns. This template ensures that your data is properly structured for successful import.

{% hint style="warning" %}
Ensure your CSV file adheres to the specified format with no missing or extra columns. Keep your file size manageable to prevent slow uploads or potential errors during processing.
{% endhint %}

### Import Options

#### Manual CSV Import

You can manually upload the CSV to COW directly once it is properly formatted.

#### Azure Blob Storage Import

Save the file to Azure Blob Storage and create a [shared access signature (SAS) link](https://learn.microsoft.com/en-us/azure/ai-services/translator/document-translation/how-to-guides/create-sas-tokens?tabs=Containers).

{% hint style="warning" %}
The SAS link needs Read, Create, and Write permissions and must be valid for at least a year
{% endhint %}
