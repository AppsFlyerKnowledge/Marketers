---
title: "Data collaboration platform (DCP) - Collaboration measurement - Overview"
excerpt: "Learn about collaboration measurement, its basic concepts, and data flow within the Data Collaboration Platform (DCP)."
---
**At a glance:** Learn about collaboration measurement, its basic concepts, and data flow.

## The three data sources of measurement

The DCP measurement model attributes conversion events to engagement events occurring in a collaboration context. This process requires data from three key data sources: conversions, engagements, and campaign mapping. Each source plays a critical role in the attribution flow.

### Conversions

Conversion data contains details about user actions such as purchases and their associated Stock Keeping Units (SKUs) or Consumer Packaged Goods (CPGs). Each conversion instance represents a single conversion event, capturing details such as the SKU, user ID, and event time.

**Conversion parameters example**



| **Field** | **Value** |
| --- | --- |
| `app_id` | FoodDelivery |
| `user_id` | 5abe2ddccca43000af58f0b |
| `event_time` | 2024-08-21T16:06:32.393Z |
| `event_name` | purchase |
| `sku` | 8711327623057 |
| `sku_revenue` | 6.94 |
| `sku_quantity` | 1 |



AppsFlyer provides access to app conversions through integration with your app using the AppsFlyer SDK or via custom data sources provided by the collaborators. Web and in-store conversion events can also be provided using custom data sources.

### Engagements

The engagement source contains details about user interactions with ads, such as clicks or impressions. Each instance represents an engagement event and includes attributes such as the campaign ID, media source, and touch type (e.g., click or impression).

**Engagement parameters example**



| **Field** | **Value** |
| --- | --- |
| `appsflyer_id` | 1727548724223 |
| `media_source` | google |
| `campaign` | grc\_web\_ftu\_seq |
| `attributed_touch_time` | 2024-09-28T17:05:34 |
| `attributed_touch_type` | impression |
| `event_name` | start\_game |



To access engagement data, in [on-site campaigns](/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#onsite-and-offsite-campaign-measurement), you can either set up new in-app events with attribution data in the `event_value` parameter using the AppsFlyer SDK or share the data through a custom source.

In [off-site campaigns, engagement data is received from a third party](/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#onsite-and-offsite-campaign-measurement) and not via in-app events or a custom source.

### Campaign mapping

The campaign mapping source enables us to determine the engagement that triggered each conversion. A campaign mapping record links conversion events to engagement events by pairing SKUs or CPGs with campaign IDs. Using this mapping, DCP links a conversion event that includes a given SKU to an engagement event containing the corresponding campaign ID.

**Campaign mapping parameters example**



| **Field** | **Value** |
| --- | --- |
| `collaborator_name` | fashion\_site |
| `collaborator_id` | 10079 |
| `campaign_id` | 49fd77a2-8b64-4c9d... |
| `campaign_name` | off\_season\_25\_1 |
| `conversion_targets` | 8711327621978, 8711327622289, 8711327623057 |



The campaign mapping information is provided to AppsFlyer as a custom data source.

## On-site vs. Off-site campaigns

DCP measures campaigns differently based on where they run — either on a collaborator’s owned site (on-site) or on the media partner platform (off-site). These differences affect how audiences are reached, how data is collected, and how attribution is performed.

### Off-site campaigns

Off-site campaigns involve user engagements on third-party platforms (such as Meta or Google), with conversions occurring within the collaborator’s owned properties and attributed to those off-site engagements.

* **Example:** A brand runs a Facebook ad targeted at the CMN’s segmented customer data. When users see the ad in Facebook and click it, they are taken to the CMN’s product page.
* **Attribution:** DCP shares conversion events with the third party, which performs its own attribution; DCP then retrieves aggregated results via the third party’s reporting API.

### On-site campaigns

On-site campaigns involve user engagements and conversions that occur within a collaborator’s owned properties (such as their app or website), with conversions attributed to on-site engagements.

* **Example:** A brand promotes a product on a Commerce Media Network website. The audience includes past shoppers of the CMN platform, segmented by parameters like category interest or purchase history. When users see and click the campaign banner, they are taken to the product detail page on the same site.
* **Attribution:** DCP directly attributes conversions to on-site campaigns using first-party engagement data from the collaborator’s website or app.

### Combined on-site and off-site campaigns

Combined campaigns involve user engagements that occur both on-site and off-site, with conversions occurring within the collaborator’s owned properties and attributed to engagements from either source using unified measurement and deduplication.

* **Example:** A brand promotes a product on the CMN’s website and also runs Facebook ads targeting the CMN’s customers. Engagements and conversions from both the on-site campaign and the Facebook campaign are captured, deduplicated, and measured together.
* **Attribution:** DCP consolidates conversion data from both on-site and off-site channels into a shared attribution table, applying deduplication logic and presenting unified metrics per campaign and SKU.

## The DCP measurement process

The DCP measurement process defines how conversion records from SDK in-app events and custom source files are validated, normalized, and matched to campaign engagements across [on-site and off-site campaigns](https://www.notion.so/Collaboration-measurement-Overview-255b7b13af5f80fa83d2dc77e337c960?pvs=21).

### On-site measurement flow

The DCP On-site measurement flow process in-app events and custom source records collected from the CMN or advertiser’s mobile app or website. DCP attributes these conversions internally using AppsFlyer’s attribution logic.

The on-site measurement flow processes conversion and engagement data originating from two primary sources:

* **In-app events (IAEs)** are collected through the AppsFlyer SDK embedded in the collaborator mobile app.
* **Custom source event files** are sent by the collaborators to AppsFlyer.

Both event types are normalized into a unified structure and processed through the same attribution engine.

### 1. Configure measurement sources

Collaborators configure the DCP online measurement process:

* **In-app events:** Collaborators identify which in-app events (e.g., purchase, signup) should be measured as conversions or engagements. These events must already be collected via the AppsFlyer SDK, and the app and event names must be explicitly selected in the DCP configuration.
* **Custom source event files:** Collaborators configure access to external data files (e.g., from BigQuery, S3, or Snowflake) and map key fields like user\_id, campaign\_id, and SKU to the DCP schema to support attribution.

### 2. Prepare and map conversion data

Conversion events include SKUs and user identifiers that DCP uses to determine campaign-triggered activity.

* DCP maps the campaign mapping data source with the SKUs found in the conversion events to identify conversions triggered by the measured campaign.
* Conversions that cannot be matched to any campaign are marked as **organic**.

### 3. Link conversions to engagements

DCP links matched conversions to engagements using the following criteria:

* A shared **user ID**
* The same **campaign ID**

This results in attributed conversion records enriched with both campaign and engagement metadata.

### 4. Split multi-SKU conversions

If a conversion event includes multiple SKUs:

* DCP splits the record into multiple **single-SKU** records.
* Each record reflects attribution for a single **conversion target**.

### 5. Filter non-target SKUs

To ensure only relevant conversions are retained:

* DCP filters out records whose SKUs are not defined as conversion targets for the associated campaign.

### 6. Deduplicate conversion events

Before attribution, DCP removes duplicates:

* Duplicate records from the same custom source (e.g., repeated uploads) are discarded.
* If a matching in-app event (IAE) exists, it overrides the custom source record.

### 7. Apply attribution logic

DCP applies AppsFlyer’s last-touch attribution model with the following rules:

* **Multiple engagements per conversion**: The **last touch** is selected based on the AppsFlyer priority scale.
* **One engagement linked to multiple conversions**: Only the **first** conversion is attributed to the engagement; additional conversions remain unattributed.

> For more details, see Attribution method priorities (Attribution waterfall).

### 8. Output: Attributed conversion dataset

The final output includes:

* Attribution to a single campaign engagement per conversion
* Cleaned and validated SKU-level conversion records
* DCP aggregates attributed conversions to create insights, including total conversions.
* Conversion records ready for analytics dashboards and exports

### Off-site measurement flow

**Off-site conversion events** are supplied by collaborators through **custom source files** and must include the necessary identifiers for attribution, such as Google click ID (`gclid`) or Facebook click ID (`fbclid`). These events are shared with the external platforms like Google and Meta, which match the data against their campaign records and return **enriched metadata**, including campaign, adset, and creative identifiers.

### 1. Prepare Conversion Data

Conversion records are standardized based on the collaboration setup:

* Collaborators map custom fields to a unified conversion DCP schema.
* Google Ads and Meta Ads require specific fields; validation rules ensure mappings meet each partner’s standards before continuing.

### 2. Deduplicate Conversion Events

Before attribution, DCP removes duplicate records from the same custom source (e.g., repeated uploads) are discarded.

### 3. Filter for Sharing Eligibility

DCP checks if off-site conversions meet the criteria for sharing:

* A valid channel-specific identifier is present (e.g., GCLID, FBCLID).
* The conversion matches a defined campaign action or SKU.
* The conversion falls within the lookback window:
  * Meta: 1, 7, or 28 days for both click and view-through.
  * Google: Defined in-platform; API override not supported.

Conversions failing any criteria are excluded from partner sharing.

### 4. Filter according to Last-Touch Attribution

Attribution is assigned based on the most recent touchpoint:

* If a valid Google or Meta click ID is more recent, attribution goes to that partner and is shared with that partner only.
* If both click IDs exist on the conversion, the most recent wins.

### 5. Share with Google and Meta

Eligible conversions are shared securely via partner APIs:

* **Meta:** Conversions API (CAPI)
* **Google:** Offline Conversion API (OCI)

Each conversion is sent to only one partner. Collaborators must configure the destination account (Meta Dataset ID or Google Conversion Action ID).

### 6. Google and Meta response enrichment

Google and Meta return enriched attribution data via their Insights APIs, including:

* Campaign ID
* Ad Set ID
* Ad ID
* Creative ID

AppsFlyer performs attribution based on the enriched records.

### 7. Output: Attributed conversion dataset

The final output includes:

* Cleaned and validated SKU-level conversion records
* DCP aggregates attributed conversions to create insights, including total conversions.
* Conversion records are ready for analytics dashboards and exports

### Combined on-site and off-site measurement flow

This flow outlines how AppsFlyer’s Data Collaboration Platform (DCP) processes conversion data from multiple sources, including:

* **On-site conversions**, which include in-app events and custom source records collected from the CMN or advertiser’s mobile app or website. DCP attributes these conversions internally using AppsFlyer’s attribution logic.
* **Off-site conversions**, where conversion data originates from a custom source and is shared with external platforms such as Google and Meta. These platforms match the data to their own campaign records and return enriched metadata, including campaign, ad set, and creative identifiers.

The DCP off-site and on-site attribution flow deduplicates, attributes, enriches, and joins all conversion data to produce a single, unified performance dataset.

[![Notion 2025-08-25 16.10.35.png](https://files.readme.io/1552e0c84bf4ca98ef0fd9f96096f68bbf1a1f846f3fcc995e1aa0afe065a651-38422017654929.png)](https://files.readme.io/1552e0c84bf4ca98ef0fd9f96096f68bbf1a1f846f3fcc995e1aa0afe065a651-38422017654929.png)

### 1. On-site and off-site record processing is performed

Conversion records are standardized based on the collaboration setup:

* On-site processing up to and including step 6 in on-site attribution.
* Off-site processing up to and including step 4 in off-site attribution.

### 2. Apply Last-Touch Attribution

Attribution is assigned based on the most recent touchpoint:

* If a CMN (on-site) event is most recent, the conversion is attributed to CMN and not shared with Meta or Google.
* If a valid Google or Meta click ID is more recent, attribution goes to that partner and is shared with that partner only.
* If both click IDs exist on the conversion, the most recent wins.

### 3. Share with Google and Meta

Eligible conversions are shared securely via partner APIs:

* **Meta:** Conversions API (CAPI)
* **Google:** Offline Conversion API (OCI)

Each conversion is sent to only one partner. Advertisers must configure the destination account (Meta Dataset ID or Google Conversion Action ID).

### 4. Off-site response enrichment

Google and Meta return enriched attribution data via their Insights APIs, including:

* Campaign ID
* Ad Set ID
* Ad ID
* Creative ID

### 5. On-site and off-site conversion merge

DCP merges these Off-site conversions with On-site conversions into a final dataset where each conversion is:

* Attributed to a single source: Google, Meta, or CMN
* Enriched with campaign metadata
* Ready for dashboards, exports, and performance analytics

## Set up collaboration measurement in four steps

The measurement setup process can be described in four steps, each of which has a dedicated article:

1. [Determine your collaboration measurement use case](/docs/data-collaboration-platform-dcp-determine-your-collaboration-measurement-use-cas)
2. [Prepare the data sources that feed the attribution process](/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement)
3. [Configure DCP to access the data sources and perform attribution](/docs/data-collaboration-platform-dcp-configure-collaboration-measurement)
4. [Consume the attributed measurement data in dashboards](/docs/data-collaboration-platform-dcp-view-measurement-dashboard)
5. [Consume the attributed measurement data in reports](/docs/data-collaboration-platform-dcp-view-measurement-reports)