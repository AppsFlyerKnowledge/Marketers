---
title: "Prepare Collaboration Measurement"
excerpt: "Learn how to create measurement data sources and provide access to them for the attribution job in the Data Collaboration Platform."
---
The first step in setting up the measurement process is to prepare the three inputs that feed it: conversions, engagements, and campaign mapping. These inputs must be prepared based on the predefined schema or event structure, depending on the data provision mode: in-app events or custom source files.

When the provision mode is custom source files, the attribution job is triggered automatically when the required conversion and engagement record folders are uploaded to the cloud. For in-app event mode, the job is triggered when relevant in-app events are selected.

## Prepare in-app events

You can send conversion and engagement data via in-app events sent by the AppsFlyer SDK integrated into your app.

> 📘 Note
>
> If you are already passing AppsFlyer in-app events through SDK or via server-to-server requests, this option might be easier to implement than the custom source file option.

### Prepare conversion in-app events

The conversion in-app event must include the SKU information nested in the `af_order_info` key.

```json
"event_value": {
    "event_id": "<event_id>",
    "af_content": "retail",
    "af_order_id": "637f7c400f0e3fddd9e5bcbc",
    "af_order_info": [
        {
            "sku": "a",
            "revenue": 1.1,
            "qty": 2
        },
        {
            "sku": "b",
            "revenue": 100.5,
            "qty": 1
        }
    ]
}
```

For information about how to prepare in-app events, see the [Create in-app events](#create-in-app-events) section below.

### Prepare engagement in-app events

[On-site campaigns](https://support.appsflyer.com/hc/articles/32143318560017--WIP-Data-collaboration-platform-Collaboration-measurement-Overview#onsite-and-offsite-campaign-measurement) can receive engagements via in-app events. The engagement in-app event should include the attribution data in the `event_value` key. See, as an example, the following `event_value` JSON structure:

```json
"event_value": {
    "ad_name": "Spring_Sale_Ad_01",
    "ad_id": "ad_123456",
    "ad_type": "video",
    "adset_name": "Spring_Sale_Set_A",
    "adset_id": "adset_7890",
    "campaign_name": "Spring_2025_Promo",
    "campaign_id": "camp_456123",
    "channel": "facebook",
    "media_source": "meta_ads",
    "engagement_type": "click",
    "event_id": "evt_20250410_001"
}
```

You can use the fields below in your `event_value` JSON key:

| **Field** | **Description** | **Required** | **Available within in-app event schema** | **Type** |
| --- | --- | --- | --- | --- |
| `campaign_id` | Campaign ID | Yes | No | `string` |
| `campaign_name` | Campaign name | No | No | `string` |
| `engagement_type` | Differentiates between clicks and impressions | Yes | No | `string` |
| `media_source` | Media source attributed to an event or restricted ( [see more](https://support.appsflyer.com/hc/articles/360006868017#media-source-restrictions)) | Yes | No | `string` |
| `ad_id` | Ad ID | No | No | `string` |
| `ad_name` | Ad name | No | No | `string` |
| `ad_type` | Example: banner, footer | No | No | `string` |
| `adset_id` | Adset ID, identifying a group that contains one or more ads | No | No | `string` |
| `adset_name` | Adset name, identifying a group that contains one or more ads | No | No | `string` |
| `channel` | Media source channel. Example: YouTube for Google, Instagram for Meta ads | No | No | `string` |

For more information, about how to prepare in-app events, see the Create in-app events section below.

### Create in-app events

To provide conversion and engagement data through in-app events configure the AppsFlyer SDK integrated into your app. For more information about creating in-app events, see:

- [In-app events overview](/docs/in-app-events-overview)
- [Implement in-app events in AppsFlyer SDK for developers](http://dev.appsflyer.com/hc/docs/in-app-events-sdk)

## Prepare custom source files

If you are running an [on-site campaign](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#onsite-and-offsite-campaign-measurement) you can use custom source files as the source of your conversions and engagements with the schema outlined in the tables below.

### Prepare the conversion custom source

Use the scheme in the table below to create a conversion custom source file.

The conversion scheme is unitary for off-site and on-site campaign types and for the different media partners.

#### Media partners:
**G**: Google
**M**: Meta

#### Background colors:
Required fields
Recommended fields
Either of the selected fields is required
Fields are hashed according to SRN-specified rules.

| Category | Parameter | Description | Type | CMN | Media partners | | | |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| | | | | | App | | Web | |
| | | | | | G | M | G | M |
| Event | event\_id | Unique identifier for the event. | string | ✓ | ✓ | ✓ | ✓ | ✓ |
| | event\_name | Name or type of the event (e.g., "purchase", "click"). | string | ✓ | ✓ | ✓ | ✓ | ✓ |
| | event\_time | Timestamp when the event occurred. | datetime | ✓ | ✓ | ✓ | ✓ | ✓ |
| App info | app\_id | Unique identifier for the application. | string | ✓ | ✓ | ✓ | | |
| | app\_name | Name of the application. | string | ✓ | | ✓ | | |
| | app\_version | Version number of the application. | string | ✓ | | ✓ | | |
| Attribution Data | facebook\_browser\_id | Unique identifier for Facebook browser tracking. | string | | | ✓ | | ✓ |
| | facebook\_cookie | Click identifier for Facebook ad attribution. | string | | | ✓ | | ✓ |
| | gbraid | Google ad attribution identifier. | string | | ✓ | | | |
| | google\_click\_id | Unique ID for Google Ads click tracking. | string | | ✓ | | ✓ | |
| | wbraid | Web-based attribution identifier for Google. | string | | ✓ | | | |
| | tiktok\_id | Unique identifier for TikTok tracking. | string | | | | | |
| Campaign Data | campaign\_id | Unique identifier for the marketing campaign. | string | | | ✓ | | |
| | install\_id | Identifier for the app install event. | string | | | ✓ | | |
| Conversion Data | sku | SKUs of products involved in the conversion. | string | ✓ | | | | |
| | sku\_quantity | Unique identifier for a product (SKU). | integer | ✓ | | | | |
| | sku\_revenue | Quantity of the SKU purchased or involved. | decimal | ✓ | | | | |
| | event\_revenue | Revenue generated by the event. | decimal | ✓ | ✓ | ✓ | ✓ | ✓ |
| | event\_revenue\_currency | Currency for the revenue amount. | decimal | ✓ | ✓ | ✓ | ✓ | ✓ |
| Device info | client\_ip | IP address of the user or device. | string | | | ✓ | | ✓ |
| | client\_user\_agent | User agent string from the user's device/browser. | string | | | ✓ | ✓ | ✓ |
| | device\_category | Category of the user's device (e.g., mobile, desktop). | string | ✓ | | | | |
| | platform (os?) | Operating system of the user's device (e.g., iOS, Android). | string | ✓ | | ✓ | | |
| | os\_version | Version of the device's operating system. | string | | | ✓ | | |
| User ID | advertising\_id | Unique identifier for advertising purposes (e.g., IDFA). | string | ✓ | | | | |
| | appsflyer\_id | Unique ID for tracking via Appsflyer. | string | ✓ | | | | |
| | android\_id | Unique Android device identifier. | string | ✓ | | ✓ | | |
| | idfa | Identifier for Advertisers (iOS). | string | ✓ | | ✓ | | |
| | idfv | Identifier for Vendor (iOS). | string | ✓ | | ✓ | | |
| | client\_id | Unique client identifier (e.g., generated by the system). | string | ✓ | | ✓ | | ✓ |
| | facebook\_hashed\_client\_id | no rules specified | string | | | ✓ | | ✓ |
| | tiktok\_hashed\_client\_id | trim, lowercase | string | | | | | |
| | cookie | Browser cookie data for user/session tracking. | string | | | | | |
| | first\_name | User's first name. | string | | | ✓ | ✓ | ✓ |
| | last\_name | User's last name. | string | | | ✓ | ✓ | ✓ |
| | phone\_number | User's phone number. | integer | | ✓ | ✓ | ✓ | ✓ |
| | date\_of\_birth | User's date of birth. | datetime | | | ✓ | | ✓ |
| | gender | Gender of the user. | string | | | ✓ | | ✓ |
| | language | User's preferred language or locale. | string | | | ✓ | | |
| | email | User's email address. | string | | ✓ | ✓ | ✓ | ✓ |
| | tiktok\_hashed\_email | trim, lowercase, remove dots for google email adresses | string | | | | | |
| | tiktok\_hashed\_phone | E164 | string | | | | | |
| | google\_hashed\_email | trim, lowercase, remove dots for google email adresses | string | | ✓ | | ✓ | |
| | google\_hashed\_phone | E164 | string | | ✓ | | ✓ | |
| | google\_hashed\_first\_name | trim, lowercase | string | | | | ✓ | |
| | google\_hashed\_last\_name | trim, lowercase | string | | | | ✓ | |
| | facebook\_hashed\_email | trim, lowercase | string | | | ✓ | | ✓ |
| | facebook\_hashed\_phone | custom format (no +?) | string | | | ✓ | | ✓ |
| | facebook\_hashed\_first\_name | lowercace, no punctuation | string | | | ✓ | | ✓ |
| | facebook\_hashed\_last\_name | lowercace, no punctuation | string | | | ✓ | | ✓ |
| | facebook\_hashed\_date\_of\_birth | YYYYMMDD | string | | | ✓ | | ✓ |
| | facebook\_hashed\_gender | f/m is suggested, but any hashed value is OK | string | | | ✓ | | ✓ |
| User Attributes | att\_status | App Tracking Transparency (ATT) status for user consent. | string | | ✓ | ✓ | | |
| Device location | region | Geographic region of the user. | string | ✓ | | | | |
| | city | City associated with the user. | string | ✓ | | ✓ | ✓ | ✓ |
| | state | State or province of the user. | string | ✓ | | ✓ | ✓ | ✓ |
| | country\_code | ISO code for the user's country. | string | ✓ | | ✓ | ✓ | ✓ |
| | zip\_code | Postal/ZIP code of the user. | string | | | ✓ | ✓ | ✓ |
| | street | Street address of the user (if available). | string | | | | ✓ | |
| | google\_hashed\_street | trim, lowercase | string | | | | ✓ | |
| | facebook\_hashed\_city | lowercase, no punctuation, no spaces | string | | | ✓ | | ✓ |
| | facebook\_hashed\_state | ANSI for US, lowercase, no punctuation, no spaces | string | | | ✓ | | ✓ |
| | facebook\_hashed\_zip\_code | special rules for US/UK, lowercase, no punctuation, no spaces | string | | | ✓ | | ✓ |
| | facebook\_hashed\_country\_code | 2-letter country codes in ISO 3166-1 alpha-2, lowercase | string | | | ✓ | | ✓ |
| Referral/Traffic Data | referrer\_url | URL of the site that referred the user to the current page. | string | | | | | ✓ |
| | source\_url | Source URL where the user first interacted with the campaign. | string | | | | | ✓ |

### Prepare the engagement custom source

Use the schema below to create the engagement data source.

> 📘 Note
>
> The Personally identifiable information (PII) fields mapped in the engagement source scheme should have a non-empty intersection with the PIIs mapped in the conversion source scheme above

| **Field** | **Description** | Required | **Expected value type** |
| --- | --- | --- | --- |
| `appsflyer_id` | Unique ID generated by the SDK when the app is installed | Optional PII field. One of the PII fields is required. | `string` |
| `cuid` | Unique app user ID set by the app owner | Optional PII field. One of the PII fields is required. | `string` |
| `idfa` | User-resettable advertising ID for iOS devices. If unavailable, it is populated with zeros | Optional PII field. One of the PII fields is required. | `string` |
| `idfv` | Vendor ID provided by iOS | Optional PII field. One of the PII fields is required. | `string` |
| `app_id` | Unique app identifier in AppsFlyer. Example: iOS: `id123456789`, Android: `com.appsflyer.referrersender` | Optional | `string` |
| `campaign_id` | Campaign ID | Mandatory | `string` |
| `campaign_name` | Campaign name | Optional | `string` |
| `media_source` | Media source attributed to an event or restricted ( [see more](https://support.appsflyer.com/hc/articles/360006868017#media-source-restrictions)) | Mandatory | `string` |
| `engagement_type` | Differentiates between clicks and impressions | Mandatory | `string` |
| `event_name` | Set by the advertiser | Mandatory | `string` |
| `event_time` | Event time, rounded down to the nearest hour | Mandatory | `datetime` |
| `app_name` | Set by the advertiser | Optional | `string` |
| `app_version` | Set by the advertiser | Optional | `string` |
| `ad_id` | Ad ID | Optional | `string` |
| `ad_name` | Ad name | Optional | `string` |
| `ad_type` | Example: banner, footer | Optional | `string` |
| `adset_id` | Adset ID, identifying a group that contains one or more ads | Optional | `string` |
| `adset_name` | Adset name, identifying a group that contains one or more ads | Optional | `string` |
| `channel` | Media source channel. Example: YouTube for Google, Instagram for Meta ads | Optional | `string` |
| `platform` | Device platform: iOS, Android, or Windows Mobile | Optional | `string` |

For more information about how to prepare sources and upload them to your cloud service, see the [Create and connect custom data sources](#create-and-connect-custom-data-sources) section of this document.

## Prepare campaign mapping source

The source of your campaign mapping data is a custom data source file with the schema outlined in the table below.

> 📘 Note
>
> We recommend using a single mapping file for all collaborations, as it is easier to maintain and update.

### The campaign mapping scheme

Use the schema below to create the campaign mapping source.

| **Field type** | **Required?** | **Expected Value** | **Description** |
| --- | --- | --- | --- |
| collaborator\_name | Yes | string | The name of the collaborator you work with. |
| collaborator\_id | Yes | string | A unique identifier for the collaborator. |
| campaign\_id | Yes | string | The unique identifier for the campaign. |
| conversion\_targets | Yes | string array | A parameter that expects a comma-separated list of the campaign target SKUs, for example, sku1, sku2, etc. |
| campaign\_name | No | string | The name of the campaign. |

For more information about how to create source files and upload them to your cloud service, see the [Create and connect custom data sources](#create-and-connect-custom-data-sources) section of this document.

## Attribution job ingestion flow

Each attribution job is dedicated to a single day and runs after the day ends. At the beginning of this process, the job ingests the relevant conversions, engagements, and campaign mapping data from the cloud service or from in-app events.

### Campaign mapping source ingestion

Before each attribution run, DCP loads campaign mapping records from the custom sources. You can choose between two modes for loading these records:

- **Latest Strategy**: DCP takes the most recent records based on the record upload date. For example, if the source contains records with upload dates of Jan 18, Jan 17, or Dec 29, the system will select the records with the Jan 18 date.
- **Daily Strategy**: DCP only takes records whose upload date matches the day of the attribution run. For example, if the run occurs at midnight on Jan 19, the system will only select campaign records with the Jan 19 upload date.

### Conversion source ingestion

At the end of each day, DCP runs the attribution job for that day **only if it can access the folder dedicated to that day and the conversion records within it**. However, you can upload the folder for a certain day at a later date. For example, you can upload the Jan 17 folder on Jan 22.

- At the end of each day, DCP runs the attribution job for that day. The job will run **only if DCP can find the folder for that day**. The folder name is identical to the day name.
- The day folder can include records for events dating back 30 days from the day of the folder. For example, in the Jan 17 folder, the job processes records from December 18 to January 17.
- If you skip uploading the folder for a certain day, you have 30 days to upload it. For example, if you skipped uploading the Jan 17 folder, you can upload it until Feb 17. However, we recommend uploading it as close as possible to the folder date.
- If DCP does not find the current day’s folder, it will continue searching for the folder every 10 minutes for the next 7 days.

### Engagement source ingestion

For each conversion record, DCP searches for the engagement events that triggered it.

- The engagement records are included in dated folders. However, you don’t have to upload an engagement folder for each day. For example, you can upload a Jan 13 and Jan 15 folder without uploading the Jan 14 folder. In this example, the records from Jan 14 will be taken from the Jan 15 folder.
- **The attribution job for a given conversion folder will start only if an engagement folder with the same date as the conversion folder or a later date exists.** For example, the attribution job for the Jan 17 **conversion** folder will start only if the Jan 17 engagement folder or folders with later dates, such as Jan 18, exist.
- The attribution job collects all engagement events that fall within the engagement lookback window.

### In-app data ingestion

Conversion and engagement data can come from in-app events, custom sources, or a combination of both. DCP lets you choose whether to use a single mode or mix them, allowing conversions to come from in-app events while engagements are sourced from custom files, or vice versa.

When configuring in-app events for conversions, engagements, or both, you must specify the app ID and the conversion or engagement event name. At the end of the day, the attribution job selects all events with the specified name and app ID that have the same event date as the conversion day.

## Create and connect custom data sources

To connect data through custom sources customer will first need to follow the instructions in the following DCP knowledge base articles:

<Cards>
  <Card title="Set up your cloud services" href="/docs/data-collaboration-platform-dcp-set-up-your-cloud-services">
    Learn how to configure cloud storage and permissions for DCP.
  </Card>
  <Card title="Add connections" href="/docs/data-collaboration-platform-dcp-add-connections">
    Learn how to link your cloud storage connections to the platform.
  </Card>
  <Card title="Create and manage sources" href="/docs/data-collaboration-platform-dcp-create-and-manage-sources">
    Learn how to define and manage data sources within DCP.
  </Card>
</Cards>