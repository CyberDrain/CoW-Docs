# FAQ

#### What PSA platforms are supported?

COW currently supports the following platforms for device synchronization:

* **HaloPSA**
* **ConnectWise Manage**
* **Autotask**

You can also import devices via **CSV upload** if your PSA is not supported.

#### How is access controlled?

* Access is scoped by **email domain**.
* The **first person** from a domain to sign up becomes the **org owner**.
* Additional users can be added automatically (via domain match) or manually invited.
* Only approved users can access organization data.

#### What device data is synced?

COW pulls device information from your PSA or CSV source.\
The level of detail varies by manufacturer, but typically includes:

* Serial number
* Purchase or manufacture date
* Model information
* Warranty status
* Service entitlements (if available)

If manufacturer data is incomplete, the device is still tracked but marked with limited metadata.

#### Can I import devices in bulk?

Yes. Both PSA-connected and CSV-loaded environments support:

* Bulk imports
* Duplicate detection and de-duplication
* Device removal (if needed)

Note: Devices already synced will not be re-imported unless modified.

#### What happens during syncing?

* Only **one sync** runs at a time.
* If a new sync is triggered while one is already running, it will be **queued** and executed afterward.
* This avoids unnecessary load and helps preserve data integrity.

#### How often are devices checked?

* Devices are automatically re-checked every **30 days** if no changes are made.
* Manual re-syncs can be triggered at any time.

#### Are lookups rate-limited?

Yes. Lookups are subject to throttling to prevent overuse of vendor APIs and ensure reliable responses.\
This helps ensure fairness and availability across all users.

#### What manufacturers are supported?

Warranty data is currently available for:

* **Dell**
* **HP**
* **Lenovo**
* **Microsoft Surface**
* **Toshiba**
* **Apple** (devices manufactured before 2022)

Additional manufacturers may be added over time.

#### What can I do with the synced data?

Inside the app, you can:

* View all devices and their warranty status
* Export device data (CSV)
* Filter by key attributes (manufacturer, expiry, client, etc.)
* View sync status cards showing:
  * Total devices found
  * Devices pending sync
  * Sync failures or incomplete records
  * Devices with updated warranty data

#### Is there a device limit?

Yes.

* **Free Tier**: up to **250 concurrently tracked devices**
* **Pro Tier**: up to **50,000 devices** for **$69/month**
* A **lifetime grace buffer** of up to 400 devices is available for short-term overages.
* If you require more than 50,000 devices, **enterprise options are available**.

#### What’s included in the pricing?

* **Free**: 0–250 tracked devices
* **Pro**: $69/month for up to 50,000 tracked devices
* **Enterprise / White-label / Vendor**: Contact us for custom pricing

All subscriptions are **month-to-month**, and you may cancel at any time.
