---
title: "Data collaboration platform (DCP) - Prepare collaboration measurement"
excerpt: "Learn how to create measurement data sources, and how to provide access to them in a way that can be digested by the attribution job."
x-zendesk:
  id: 32144170371985
  url: https://support.appsflyer.com/hc/en-us/articles/32144170371985-Data-collaboration-platform-DCP-Prepare-collaboration-measurement
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Collaboration measurement
  section_id: 38034865098641
  position: 2
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-yael-sharabi, Marketers, Data Management]
  labels: [Marketers]
  promoted: false
  comments_disabled: false
  created_at: '2025-01-27T08:47:05Z'
  edited_at: '2026-06-22T07:25:10Z'
---
## Overview

The first step in setting up the measurement process is to prepare the three inputs that feed it: conversions, engagements, and campaign mapping. These inputs must be prepared based on the predefined schema or event structure, depending on the data provision mode: in-app events or custom source files.

When the provision mode is custom source files, the attribution job is triggered automatically when the required conversion and engagement record folders are uploaded to the cloud. For in-app event mode, the job is triggered when relevant in-app events are selected.

## Prepare in-app events

You can send conversion and engagement data via in-app events sent by the AppsFlyer SDK integrated into your app.

> 📘 **Note**
>
> If you are already passing AppsFlyer in-app events through SDK or via server-to-server requests, this option might be easier to implement than the custom source file option.

<div id="prepare-conversion-inapp-events" />

<Accordion title="Prepare conversion in-app events">

The conversion in-app event must include the SKU information nested in the `af_order_info` key.

```
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

For information about how to prepare in-app events, see the [Create in-app events](#create-inapp-events) section below.

</Accordion>

<div id="prepare-engagement-inapp-events" />

<Accordion title="Prepare engagement in-app events">

[On-site campaigns](/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#onsite-and-offsite-campaign-measurement) can receive engagements via in-app events. The engagement in-app event should include the attribution data in the `event_value` key. See, as an example, the following `event_value` JSON structure:

```
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

You can use the fields below in your `evant_value` JSON key:

| **Field** | **Description** | **Required** | **Available within in-app event schema** | **Type** |
| --- | --- | --- | --- | --- |
| `campaign_id` | Campaign ID | Yes | No | `string` |
| `campaign_name` | Campaign name | No | No | `string` |
| `engagement_type` | Differentiates between clicks and impressions | Yes | No | `string` |
| `media_source` | Media source attributed to an event or restricted ([see more](/docs/about-raw-data-identifier-restrictions#media-source-restrictions)) | Yes | No | `string` |
| `ad_id` | Ad ID | No | No | `string` |
| `ad_name` | Ad name | No | No | `string` |
| `ad_type` | Example: banner, footer | No | No | `string` |
| `adset_id` | Adset ID, identifying a group that contains one or more ads | No | No | `string` |
| `adset_name` | Adset name, identifying a group that contains one or more ads | No | No | `string` |
| `channel` | Media source channel. Example: YouTube for Google, Instagram for Meta ads | No | No | `string` |

For more information, about how to prepare in-app events, see the Create in-app events section below.

</Accordion>

<div id="create-inapp-events" />

<Accordion title="Create in-app events">

To provide conversion and engagement data through in-app events configure the AppsFlyer SDK integrated into your app. For more information about creating in-app events, see:

* [In-app events overview](/docs/in-app-events-overview)
* [Implement in-app events in AppsFlyer SDK for developers](http://dev.appsflyer.com/hc/docs/in-app-events-sdk)

</Accordion>

## Prepare custom source files

If you are running an [on-site campaign](#onsite-and-offsite-campaign-measurement) you can use custom source files as the source of your conversions and engagements with the schema outlined in the tables below.

<div id="the-conversion-source-scheme" />

<Accordion title="Prepare the conversion custom source">

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

<table><colgroup><col/><col/><col/><col/><col/><col/><col/><col/><col/></colgroup><thead><tr><th>Category</th><th>Parameter</th><th>Description</th><th>Type</th><th>CMN</th><th colspan="4">Media partners</th></tr><tr><th></th><th></th><th></th><th></th><th></th><th colspan="2">App</th><th colspan="2">Web</th></tr><tr><th></th><th></th><th></th><th></th><th></th><th>G</th><th>M</th><th>G</th><th>M</th></tr></thead><tbody><tr><td>Event</td><td>event_id</td><td>Unique identifier for the event.</td><td>string</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>event_name</td><td>Name or type of the event (e.g., "purchase", "click").</td><td>string</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>event_time</td><td>Timestamp when the event occurred.</td><td>datetime</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>App info</td><td>app_id</td><td>Unique identifier for the application.</td><td>string</td><td>✓</td><td>✓</td><td>✓</td><td></td><td></td></tr><tr><td> </td><td>app_name</td><td>Name of the application.</td><td>string</td><td>✓</td><td></td><td>✓</td><td></td><td></td></tr><tr><td> </td><td>app_version</td><td>Version number of the application.</td><td>string</td><td>✓</td><td></td><td>✓</td><td></td><td></td></tr><tr><td>Attribution Data</td><td>facebook_browser_id</td><td>Unique identifier for Facebook browser tracking.</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>facebook_cookie</td><td>Click identifier for Facebook ad attribution.</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>gbraid</td><td>Google ad attribution identifier.</td><td>string</td><td></td><td>✓</td><td></td><td></td><td></td></tr><tr><td> </td><td>google_click_id</td><td>Unique ID for Google Ads click tracking.</td><td>string</td><td></td><td>✓</td><td></td><td>✓</td><td></td></tr><tr><td> </td><td>wbraid</td><td>Web-based attribution identifier for Google.</td><td>string</td><td></td><td>✓</td><td></td><td></td><td></td></tr><tr><td> </td><td>tiktok_id</td><td>Unique identifier for TikTok tracking.</td><td>string</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>Campaign Data</td><td>campaign_id</td><td>Unique identifier for the marketing campaign.</td><td>string</td><td></td><td></td><td>✓</td><td></td><td></td></tr><tr><td> </td><td>install_id</td><td>Identifier for the app install event.</td><td>string</td><td></td><td></td><td>✓</td><td></td><td></td></tr><tr><td>Conversion Data</td><td>sku</td><td>SKUs of products involved in the conversion.</td><td>string</td><td>✓</td><td></td><td></td><td></td><td></td></tr><tr><td> </td><td>sku_quantity</td><td>Unique identifier for a product (SKU).</td><td>integer</td><td>✓</td><td></td><td></td><td></td><td></td></tr><tr><td> </td><td>sku_revenue</td><td>Quantity of the SKU purchased or involved.</td><td>decimal</td><td>✓</td><td></td><td></td><td></td><td></td></tr><tr><td> </td><td>event_revenue</td><td>Revenue generated by the event.</td><td>decimal</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>event_revenue_currency</td><td>Currency for the revenue amount.</td><td>decimal</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Device info</td><td>client_ip</td><td>IP address of the user or device.</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>client_user_agent</td><td>User agent string from the user's device/browser.</td><td>string</td><td></td><td></td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>device_category</td><td>Category of the user's device (e.g., mobile, desktop).</td><td>string</td><td>✓</td><td></td><td></td><td></td><td></td></tr><tr><td> </td><td>platform (os?)</td><td>Operating system of the user's device (e.g., iOS, Android).</td><td>string</td><td>✓</td><td></td><td>✓</td><td></td><td></td></tr><tr><td> </td><td>os_version</td><td>Version of the device's operating system.</td><td>string</td><td></td><td></td><td>✓</td><td></td><td></td></tr><tr><td>User ID</td><td>advertising_id</td><td>Unique identifier for advertising purposes (e.g., IDFA).</td><td>string</td><td>✓</td><td></td><td></td><td></td><td></td></tr><tr><td> </td><td>appsflyer_id</td><td>Unique ID for tracking via Appsflyer.</td><td>string</td><td>✓</td><td></td><td></td><td></td><td></td></tr><tr><td> </td><td>android_id</td><td>Unique Android device identifier.</td><td>string</td><td>✓</td><td></td><td>✓</td><td></td><td></td></tr><tr><td> </td><td>idfa</td><td>Identifier for Advertisers (iOS).</td><td>string</td><td>✓</td><td></td><td>✓</td><td></td><td></td></tr><tr><td> </td><td>idfv</td><td>Identifier for Vendor (iOS).</td><td>string</td><td>✓</td><td></td><td>✓</td><td></td><td></td></tr><tr><td> </td><td>client_id</td><td>Unique client identifier (e.g., generated by the system).</td><td>string</td><td>✓</td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>facebook_hashed_client_id</td><td>no rules specified</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>tiktok_hashed_client_id</td><td>trim, lowercase</td><td>string</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td> </td><td>cookie</td><td>Browser cookie data for user/session tracking.</td><td>string</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td> </td><td>first_name</td><td>User's first name.</td><td>string</td><td></td><td></td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>last_name</td><td>User's last name.</td><td>string</td><td></td><td></td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>phone_number</td><td>User's phone number.</td><td>integer</td><td></td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>date_of_birth</td><td>User's date of birth.</td><td>datetime</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>gender</td><td>Gender of the user.</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>language</td><td>User's preferred language or locale.</td><td>string</td><td></td><td></td><td>✓</td><td></td><td></td></tr><tr><td> </td><td>email</td><td>User's email address.</td><td>string</td><td></td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>tiktok_hashed_email</td><td>trim, lowercase, remove dots for google email adresses</td><td>string</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td> </td><td>tiktok_hashed_phone</td><td>E164</td><td>string</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td> </td><td>google_hashed_email</td><td>trim, lowercase, remove dots for google email adresses</td><td>string</td><td></td><td>✓</td><td></td><td>✓</td><td></td></tr><tr><td> </td><td>google_hashed_phone</td><td>E164</td><td>string</td><td></td><td>✓</td><td></td><td>✓</td><td></td></tr><tr><td> </td><td>google_hashed_first_name</td><td>trim, lowercase</td><td>string</td><td></td><td></td><td></td><td>✓</td><td></td></tr><tr><td> </td><td>google_hashed_last_name</td><td>trim, lowercase</td><td>string</td><td></td><td></td><td></td><td>✓</td><td></td></tr><tr><td> </td><td>facebook_hashed_email</td><td>trim, lowercase</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>facebook_hashed_phone</td><td>custom format (no +?)</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>facebook_hashed_first_name</td><td>lowercace, no punctuation</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>facebook_hashed_last_name</td><td>lowercace, no punctuation</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>facebook_hashed_date_of_birth</td><td>YYYYMMDD</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>facebook_hashed_gender</td><td>f/m is suggested, but any hashed value is OK</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td>User Attributes</td><td>att_status</td><td>App Tracking Transparency (ATT) status for user consent.</td><td>string</td><td></td><td>✓</td><td>✓</td><td></td><td></td></tr><tr><td>Device location</td><td>region</td><td>Geographic region of the user.</td><td>string</td><td>✓</td><td></td><td></td><td></td><td></td></tr><tr><td> </td><td>city</td><td>City associated with the user.</td><td>string</td><td>✓</td><td></td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>state</td><td>State or province of the user.</td><td>string</td><td>✓</td><td></td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>country_code</td><td>ISO code for the user's country.</td><td>string</td><td>✓</td><td></td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>zip_code</td><td>Postal/ZIP code of the user.</td><td>string</td><td></td><td></td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>street</td><td>Street address of the user (if available).</td><td>string</td><td></td><td></td><td></td><td>✓</td><td></td></tr><tr><td> </td><td>google_hashed_street</td><td>trim, lowercase</td><td>string</td><td></td><td></td><td></td><td>✓</td><td></td></tr><tr><td> </td><td>facebook_hashed_city</td><td>lowercase, no punctuation, no spaces</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>facebook_hashed_state</td><td>ANSI for US, lowercase, no punctuation, no spaces</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>facebook_hashed_zip_code</td><td>special rules for US/UK, lowercase, no punctuation, no spaces</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>facebook_hashed_country_code</td><td>2-letter country codes in ISO 3166-1 alpha-2, lowercase</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td>Referral/Traffic Data</td><td>referrer_url</td><td>URL of the site that referred the user to the current page.</td><td>string</td><td></td><td></td><td></td><td></td><td>✓</td></tr><tr><td> </td><td>source_url</td><td>Source URL where the user first interacted with the campaign.</td><td>string</td><td></td><td></td><td></td><td></td><td>✓</td></tr></tbody></table>

</Accordion>

<div id="the-engagement-source-scheme" />

<Accordion title="Prepare the engagement custom source">

Use the schema below to create the engagement data source.

> 📘 **Note**
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
| `media_source` | Media source attributed to an event or restricted ([see more](/docs/about-raw-data-identifier-restrictions#media-source-restrictions)) | Mandatory | `string` |
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

</Accordion>

For more information about how to prepare sources and upload them to your cloud service, see the [Create and connect custom data sources](#create-and-connect-custom-data-sources) section of this document.

## Prepare campaign mapping source

The source of your campaign mapping data is a custom data source file with the schema outlined in the table below.

> 📘 **Note**
>
> We recommend using a single mapping file for all collaborations, as it is easier to maintain and update.

<div id="the-campaign-mapping-scheme" />

<Accordion title="The campaign mapping scheme">

Use the schema below to create the campaign mapping source.

| **Field type** | **Required?** | **Expected Value** | **Description** |
| --- | --- | --- | --- |
| collaborator\_name | Yes | string | The name of the collaborator you work with. |
| collaborator\_id | Yes | string | A unique identifier for the collaborator. |
| campaign\_id | Yes | string | The unique identifier for the campaign. |
| conversion\_targets | Yes | string array | A parameter that expects a comma-separated list of the campaign target SKUs, for example, sku1, sku2, etc. |
| campaign\_name | No | string | The name of the campaign. |

</Accordion>

For more information about how to create source files and upload them to your cloud service, see the [Create and connect custom data sources](#create-and-connect-custom-data-sources) section of this document.

## Attribution job ingestion flow

Each attribution job is dedicated to a single day and runs after the day ends. At the beginning of this process, the job ingests the relevant conversions, engagements, and campaign mapping data from the cloud service or from in-app events.

<div id="campaign-mapping-source-ingestion" />

<Accordion title="Campaign mapping source ingestion">

Before each attribution run, DCP loads campaign mapping records from the custom sources. You can choose between two modes for loading these records:

* **Latest Strategy**: DCP takes the most recent records based on the record upload date.

  For example, if the source contains records with upload dates of Jan 18, Jan 17, or Dec 29, the system will select the records with the Jan 18 date.
* **Daily Strategy**: DCP only takes records whose upload date matches the day of the attribution run. For example, if the run occurs at midnight on Jan 19, the system will only select campaign records with the Jan 19 upload date.

</Accordion>

<div id="conversion-source-ingestion" />

<Accordion title="Conversion source ingestion">

At the end of each day, DCP runs the attribution job for that day **only if it can access the folder dedicated to that day and the conversion records within it**. However, you can upload the folder for a certain day at a later date. For example, you can upload the Jan 17 folder on Jan 22.

* At the end of each day, DCP runs the attribution job for that day. The job will run **only if DCP can find the folder for that day**. The folder name is identical to the day name.
* The day folder can include records for events dating back 30 days from the day of the folder. For example, in the Jan 17 folder, the job processes records from December 18 to January 17.
* If you skip uploading the folder for a certain day, you have 30 days to upload it. For example, if you skipped uploading the Jan 17 folder, you can upload it until Feb 17. However, we recommend uploading it as close as possible to the folder date.
* If DCP does not find the current day’s folder, it will continue searching for the folder every 10 minutes for the next 7 days.

</Accordion>

<div id="engagement-source-ingestion" />

<Accordion title="Engagement source ingestion">

For each conversion record, DCP searches for the engagement events that triggered it.

* The engagement records are included in dated folders. However, you don’t have to upload an engagement folder for each day. For example, you can upload a Jan 13 and Jan 15 folder without uploading the Jan 14 folder. In this example, the records from Jan 14 will be taken from the Jan 15 folder.
* **The attribution job for a given conversion folder will start only if an engagement folder with the same date as the conversion folder or a later date exists.** For example, the attribution job for the Jan 17 **conversion** folder will start only if the Jan 17 engagement folder or folders with later dates, such as Jan 18, exist.
* The attribution job collects all engagement events that fall within the engagement lookback window.

</Accordion>

<div id="inapp-data-ingestion" />

<Accordion title="In-app data ingestion">

Conversion and engagement data can come from in-app events, custom sources, or a combination of both. DCP lets you choose whether to use a single mode or mix them, allowing conversions to come from in-app events while engagements are sourced from custom files, or vice versa.

When configuring in-app events for conversions, engagements, or both, you must specify the app ID and the conversion or engagement event name. At the end of the day, the attribution job selects all events with the specified name and app ID that have the same event date as the conversion day.

</Accordion>

## Create and connect custom data sources

To connect data through custom sources customer will first need to follow the instructions in the following DCP knowledge base articles:

* [Data Collaboration Platform — Set up your cloud services](/docs/data-collaboration-platform-dcp-set-up-your-cloud-services)
* [Data Collaboration Platform — Add connections](/docs/data-collaboration-platform-dcp-add-connections)
* [Data Collaboration Platform — Create and manage sources](/docs/data-collaboration-platform-dcp-create-and-manage-sources)

<div data-zendesk-anchors="h_01JJKFW5Z2D7Y1MM5A7YR0TY0T=overview prepare-inapp-events-for-conversions-and-engagements=prepare-in-app-events h_01JJKFW5Z22DG4CKFMXPGR3BW0=prepare-in-app-events h_01JJKFW5Z2NP9187GYHS0YEXED=note h_01JJKFW5Z2AX7SHHZ23P0KDQJY=prepare-conversion-inapp-events h_01JJKFW5Z2YD0B151VSR3TG6SP=prepare-engagement-inapp-events h_01JJKFW5Z3QES9BAZX7KNSPCM8=create-inapp-events prepare-custom-source-files-for-engagements-and-conversions=prepare-custom-source-files h_01JJKFW5Z3QX33NK3XP452AAFB=prepare-custom-source-files h_01JK3QFQCK30A7SSPWXSH3VP0D=the-conversion-source-scheme h_01K399C7NME67HQGJKRG1A5JB2=media-partners h_01K399DC8ZAEA86DD4W0181EM6=background-colors h_01JK3QFQCKD1TV5G4N0KP85AWS=the-engagement-source-scheme h_01JK3QFQCK6C16SCW8EYQNS47F=note-1 h_01JJKFW5Z3QR107P3M111P4STG=prepare-campaign-mapping-source h_01JJKFW5Z3ZSYET4HMWD7TWSD8=note-2 h_01JJKFW5Z3Q6F3DP0EMTNQRD8R=the-campaign-mapping-scheme prepare-data-for-attribution-job-ingestion=attribution-job-ingestion-flow h_01JJKFW5Z38W581F4CBW3T4CPZ=attribution-job-ingestion-flow h_01JK5R1VPJ0WAF3WX4R1ECE0R7=campaign-mapping-source-ingestion h_01JK5R1VPJT41RF2EN8806ZY5C=conversion-source-ingestion h_01JK5R1VPJN8KTFTN21DA3619Y=engagement-source-ingestion h_01JK5R1VPJV6F5Y5JB3Q45R89B=inapp-data-ingestion h_01JJKFW5Z3NKB0MB7GN2FC87H5=create-and-connect-custom-data-sources" />
