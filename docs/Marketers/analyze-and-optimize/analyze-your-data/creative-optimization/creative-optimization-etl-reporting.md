---
title: "Creative Optimization ETL reporting"
excerpt: "Creative Optimization ETL streams your creative performance data to cloud storage daily for direct loading into your business intelligence (BI) systems, with no manual exports needed. Choose between Standard Creative ETL , which delivers a fixed report structure, and Custom Creative ETL , which lets you choose exactly which dimensions, metrics, and events to include."
x-zendesk:
  id: 19253873174801
  url: https://support.appsflyer.com/hc/en-us/articles/19253873174801-Creative-Optimization-ETL-reporting
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Creative Optimization
  section_id: 4419063475217
  position: 6
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-omer-katzburg, Marketers, Creative Optimization]
  labels: [Premium, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2023-10-10T14:33:17Z'
  edited_at: '2026-07-06T07:18:48Z'
---
## About Creative Optimization ETL reporting

Creative Optimization ETL automatically streams your creative performance data to cloud storage daily, making it available for programmatic loading into your BI systems. Two options are available depending on your needs and subscription plan.

**Standard Creative ETL** is configured via Data Locker and delivers a fixed daily report covering core creative dimensions and performance metrics. It's available to all Creative Optimization customers.

**Custom Creative ETL** gives you full control over your report schema (the dimensions, metrics, and events that make up your report, and the order they appear in). Configure your schema directly in the Creative ETL UI, selecting exactly the dimensions, metrics, AI dimensions, and in-app events you need, including retargeting and unified attribution breakdowns. It's available to Creative Optimization Premium plan subscribers.

<Accordion title="Standard Creative ETL">

Creative Optimization ETL equips your data analysts with the information they need for creative performance analysis. It does this by automatically streaming Creative Optimization reporting data to cloud storage for programmatic loading into your BI systems.

Full asset-level performance reporting is provided, including all key performance indicators (KPIs), upper- and lower-funnel KPIs, attribution data, and creative asset data.

Standard Creative ETL uses Data Locker to send your reporting data to cloud storage. You can choose from a range of storage destinations, including an AppsFlyer-owned bucket in Amazon Web Services (AWS), or your own storage in AWS, Google Cloud Storage (GCS), Yandex, BigQuery, Snowflake, and more. Data Locker supports multiple destinations, you can send all data to one or more locations, route specific data to certain destinations, and customize delivery to your needs.

> 📘 **Note**
>
> Standard Creative ETL has a fixed schema and doesn't support in-app events, AI dimensions, or retargeting/unified breakdowns. For a fully customizable schema, see [Custom Creative ETL](#custom-creative-etl) below.

#### Get started

This section describes how to set up Data Locker for Creative Optimization reporting.

**Prerequisite**

* A Creative Optimization Premium subscription (contact your AppsFlyer customer success manager)

**To set up Data Locker:**

1. Follow the [Data Locker setup instructions](/docs/data-locker-cloud-service-setup).
2. When setting up Data Locker, select **Creative Optimization** under **Select reports** on the Data Locker configuration page.

#### Edit Data Locker configuration

This section describes how to add Creative Optimization reporting to an existing Data Locker setup.

**To add Creative Optimization reporting to Data Locker:**

1. In AppsFlyer, go to **Export** > **Data Locker**.
2. On the Data Locker configuration page, under **Select reports**, select **Creative Optimization**.

#### Data freshness

Once configured, the Creative Optimization report streams to Data Locker once per day. Each delivery includes data for the last 30 days, streamed daily at UTC+12. The exact local time depends on your time zone:

* New York: UTC+12 − 5 = 7:00 AM
* Berlin: UTC+12 + 1 = 1:00 PM
* Shanghai: UTC+12 + 8 = 8:00 PM

#### Available data

The following Creative data is available in Data Locker.

| Field | Type |
| --- | --- |
| date | String |
| asset\_link | String |
| creative | String |
| media\_source | String |
| campaign | String |
| campaign\_id | String |
| ad | String |
| ad\_id | String |
| adset | String |
| adset\_id | String |
| app\_name | String |
| app\_id | String |
| creative\_first\_seen | String |
| creative\_age | String |
| creative\_type | String |
| duration | String |
| end\_card\_type | String |
| geo | String |
| platform | String |
| orientation | String |
| resolution | String |
| impressions | String |
| clicks | String |
| installs | String |
| ctr | String |
| cvr | String |
| ipm | String |
| cost | String |
| ecpi | String |
| reattributions | String |
| reengagements | String |
| cpm | String |
| roas\_d1 | String |
| roas\_d7 | String |
| roas\_d14 | String |
| roas\_d30 | String |
| roas\_d60 | String |
| roas\_d90 | String |
| retention\_d1 | String |
| retention\_d7 | String |
| retention\_d14 | String |
| retention\_d30 | String |
| retention\_d60 | String |
| retention\_d90 | String |
| revenue\_d1 | String |
| revenue\_d7 | String |
| revenue\_d14 | String |
| revenue\_d30 | String |
| revenue\_d60 | String |
| revenue\_d90 | String |
| partner\_cpm | String |
| partner\_ctr | String |
| partner\_cvr | String |
| partner\_clicks | String |
| partner\_cost | String |
| partner\_ipm | String |
| partner\_impressions | String |
| partner\_installs | String |
| partner\_ecpi | String |

See [definitions for standard metrics and metrics unique to Creative Optimization](/docs/creative-optimization-guide#standard-metrics-and-dimensions).

> 📘 **Note**
>
> When an ad has no available preview, the `asset_link` and `creative` columns won't be populated.

The following data is **not** available in Standard Creative ETL:

* Custom dimensions
* Custom metrics
* In-app events
* AI data (elements and scenes)
* Retargeting data

</Accordion>

<div id="custom-creative-etl" />

<Accordion title="Custom Creative ETL">

Custom Creative ETL gives you full control over your report schema. You configure reports directly in the Creative ETL UI, choosing dimensions, metrics, AI dimensions, attribution type breakdowns, and in-app events. Data is delivered daily to your Data Locker destination.

Unlike Standard Creative ETL's fixed schema, Custom Creative ETL lets you build reports exactly the way you need them:

* **Full in-app event data**, include up to 30 in-app events per report, with sub-metrics for event count, unique users, revenue, and cost per action (CPA).
* **Attribution type breakdowns**, report on User Acquisition, Retargeting, or a Unified view combining both.
* **AI dimensions**, include AI-generated creative tags (auto-tags and custom dimensions) alongside standard performance data.
* **Self-serve setup**, create, edit, and manage reports directly in the Creative ETL UI, with no backend configuration or customer success manager involvement required.

#### Before you begin

Before setting up Custom Creative ETL, make sure the following are in place:

* **Creative Optimization Premium subscription.** Custom Creative ETL is available exclusively on the Premium plan. Contact your AppsFlyer representative to confirm your subscription.
* **Admin permissions.** Only admin users can create, edit, or delete ETL report configurations.
* **Data Locker destination.** Custom Creative ETL delivers data to a Data Locker connection. You must have at least one connection already configured, or create one as part of the report setup (see Step 1 below). Supported destinations include AWS S3, GCS, BigQuery, Snowflake, Azure Blob [beta], and Yandex [beta]. See [Set up a Data Locker connection](/docs/data-locker-cloud-service-setup).

#### Set up Custom Creative ETL

Custom Creative ETL setup is a three-step process: configure your data destination, define report details, and select the schema (the columns that appear in your report output).

**To set up Custom Creative ETL:**

1. In AppsFlyer, go to **Export** > **Creative ETL**.
2. Click **Create report**.

##### Step 1 - Destination

Select or configure the Data Locker connection where your report will be delivered.

3. In the **Data Locker connections** dropdown, select an existing connection.
   * If you don't have a connection yet, click **+ New connection in Data Locker**. This opens the Data Locker setup page. Once you've created a connection, return to Creative ETL and select it from the dropdown.
   * You can select multiple connections if you want the same report delivered to more than one destination.
4. Click **Next**.

##### Step 2 - Details

Define the report name and report type.

5. Enter a **Report name**. This name identifies the report in the report list and can't be changed after saving.

   > 📘 **Note**
   >
   > Use letters, numbers, and underscores only. The name must be between 2 and 80 characters.

6. Select a **Report type**:

| Report type | Description |
| --- | --- |
| User Acquisition | New user installs attributed to paid media |
| Retargeting | Re-engagement and re-attribution activity |
| Unified | Combined view of User Acquisition and Retargeting in a single report |

7. Click **Next**.

##### Step 3 - Schema

Select the dimensions, metrics, AI dimensions, and in-app events to include in your report output.

> 📘 **What is a schema?**
>
> A schema defines the columns in your report, which dimensions (attributes like campaign, geo, or creative type) and metrics (performance numbers like installs, CTR, or ROAS) are included, and in what order. The order you select fields in the UI determines the column order in the output file.

9. Under **Dimensions**, select the creative and campaign dimensions to include.

   > 📘 **Note**
   >
   > The **Event date** (event attribution date), **App ID**, **Creative**, and **Asset link** fields are mandatory and can't be removed. Two additional fields, `dt` (partition date) and `version` (run version for backfill scenarios), are always included in every report but are hidden in the UI.

10. Under **AI Dimensions**, select any auto-tag or custom dimension fields to include. These fields are generated by AppsFlyer's AI creative analysis pipeline.

    > 📘 **Note**
    >
    > AI dimensions are populated only for creatives that have been processed by the AI tagging pipeline. There may be a delay before AI tags are available for recently uploaded creatives.

11. Under **Metrics**, select the performance KPIs to include.
12. Under **In-app events**, select the events to include. Each selected event automatically includes four sub-metrics in the report output: event count, unique users, revenue, and CPA.

    > 📘 **Important!**
    >
    > You can include a maximum of **30 in-app events** per report.

13. Click **Save** to activate the report.

The report is now configured. The first delivery will occur on the next daily run.

#### Edit an existing report

You can modify an existing Custom Creative ETL report, including its schema, report type, and data connection. The report name can't be changed after the report is saved.

**To edit a report:**

1. In AppsFlyer, go to **Export** > **Creative ETL**.
2. In the report list, click the **Edit** (pencil) icon on the report you want to modify.
3. Make your changes across the three setup steps.
4. Click **Save changes**.

> 📘 **Note**
>
> Changes to the schema apply to future report runs only. Previously delivered files are not retroactively updated.
>
> The **Event date**, **App ID**, **Asset link**, and **Creative** dimensions are mandatory and can't be removed.

You can also **duplicate** or **delete** a report using the action icons on each row.

> 📘 **Important!**
>
> Deleting a report permanently removes the report configuration and all associated run history. This action can't be undone.

#### Report management

The Creative ETL page lists all Custom Creative ETL reports configured for your account. For each report, you can see the report name, report type, and the timestamp of the last successful delivery.

The following actions are available from the action icons on each report row:

* **View** (eye icon), opens a read-only view of the full report configuration.
* **Edit** (pencil icon), opens the report in edit mode.
* **Duplicate** (copy icon), creates a copy of the report configuration.
* **Delete** (trash icon), permanently removes the report and its run history.

> 📘 **Note**
>
> Each account can have a maximum of **5 active Custom Creative ETL reports**.

If you have a Standard Creative ETL report configured via Data Locker, a notification banner appears at the top of the Creative ETL page. Clicking it takes you to Data Locker, where the standard report is configured.

#### Data delivery

**Delivery schedule**

Custom Creative ETL reports are delivered once per day. To monitor delivery status, check the **Last successful run** timestamp in the Creative ETL report list.

**Lookback window**

Each daily delivery includes data for a 30-day lookback window. Each file reflects the complete rolling window, not just the most recent day. When loading data into your BI system, replace data for all dates in the delivery window rather than appending only the latest day's rows.

**Folder structure**

Data files are organized within your delivery folder based on the setting you choose in your Data Locker connection configuration:

* **Unified (default):** All apps are included in unified data files. Use the row-level `app_id` field to distinguish between apps when consuming the data.
* **By app:** Data is organized into subfolders, one per app.

See [app segregation in Data Locker](/docs/data-locker-for-marketers#app-segregation) to learn more.

#### Schema reference

##### Mandatory fields

The following fields are always included in every Custom Creative ETL report and can't be removed.

| Field | Type | Description |
| --- | --- | --- |
| `event_date` | String | The date to which the event or install is attributed |
| `app_id` | String | AppsFlyer app ID |
| `creative` | String | Creative name |
| `asset_link` | String | URL to the creative asset preview. Not populated when no preview is available |
| `dt` | String (YYYY-MM-DD) | Partition date, the date the report data was written to storage |
| `version` | String | Run version identifier, increments for backfill reruns on the same `dt` |

##### Dimensions

You can select any combination of the following dimensions to include in your report.

| Field | Type | Description |
| --- | --- | --- |
| `app_name` | String | App name |
| `ad` | String | Ad name |
| `ad_id` | String | Ad ID |
| `adset` | String | Ad set name |
| `adset_id` | String | Ad set ID |
| `agency` | String | Agency responsible for the ad placement |
| `campaign` | String | Campaign name |
| `campaign_id` | String | Campaign ID |
| `channel` | String | Channel within the media source hierarchy |
| `creative_age` | String | Number of days a creative has run, calculated from the first impression, click, or install received by AppsFlyer |
| `creative_similarity` | String | Groups image and video creatives that share the same visual theme or concept |
| `creative_type` | String | Asset type (for example, image, video, or playable) |
| `duration` | String | Video duration in seconds (for video creatives) |
| `end_card` | String | End card name |
| `end_card_duration` | String | End card display duration in seconds |
| `end_card_orientation` | String | End card orientation (portrait or landscape) |
| `end_card_resolution` | String | End card resolution |
| `end_card_type` | String | End card type |
| `first_seen` | String | Date when performance data was first received for the creative |
| `geo` | String (ISO 3166-1 alpha-2) | Country code |
| `media_source` | String | Media source (ad network) |
| `orientation` | String | Creative orientation (portrait or landscape) |
| `platform` | String | Device platform (iOS or Android) |
| `resolution` | String | Creative resolution |
| `text_type` | String | Text type classification for the creative |

##### AI dimensions

AI dimensions are generated by AppsFlyer's AI creative analysis engine and include auto-tags, smart tags, and custom dimensions.

| Group | Field prefix | Description |
| --- | --- | --- |
| Auto-tags | `at_` | AI-generated tags for creative elements, scenes, emotions, and narrative attributes. Available tags are account-specific |
| Smart tags | `cd_ai_label` | AI-generated smart tags |
| Custom dimensions | `cd_` | User-defined creative attributes configured for your account |

> 📘 **Note**
>
> AI dimensions are only populated for creatives that have been processed by the AI tagging pipeline. Newly uploaded creatives may not have AI tags immediately available.

##### Metrics

| Field | Type | Description |
| --- | --- | --- |
| `impressions` | Integer | Number of ad impressions |
| `clicks` | Integer | Number of ad clicks |
| `installs` | Integer | Number of installs attributed to the creative |
| `reattributions` | Integer | Number of re-attributions (retargeting) |
| `reengagements` | Integer | Number of re-engagements (retargeting) |
| `cost` | Decimal | Total ad spend |
| `ctr` | Decimal | Click-through rate (clicks / impressions) |
| `cvr` | Decimal | Conversion rate (installs / clicks) |
| `ipm` | Decimal | Installs per mille (installs per 1,000 impressions) |
| `cpm` | Decimal | Cost per mille (cost per 1,000 impressions) |
| `ecpi` | Decimal | Effective cost per install |
| `roas_d0` | Decimal | Return on ad spend at Day 0 |
| `roas_d1` | Decimal | Return on ad spend at Day 1 |
| `roas_d3` | Decimal | Return on ad spend at Day 3 |
| `roas_d7` | Decimal | Return on ad spend at Day 7 |
| `roas_d14` | Decimal | Return on ad spend at Day 14 |
| `roas_d30` | Decimal | Return on ad spend at Day 30 |
| `roas_d60` | Decimal | Return on ad spend at Day 60 |
| `roas_d90` | Decimal | Return on ad spend at Day 90 |
| `retention_d0` | Decimal | Day 0 retention rate |
| `retention_d1` | Decimal | Day 1 retention rate |
| `retention_d3` | Decimal | Day 3 retention rate |
| `retention_d7` | Decimal | Day 7 retention rate |
| `retention_d14` | Decimal | Day 14 retention rate |
| `retention_d30` | Decimal | Day 30 retention rate |
| `retention_d60` | Decimal | Day 60 retention rate |
| `retention_d90` | Decimal | Day 90 retention rate |
| `unique_users_0` | Integer | Unique users on Day 0 |
| `unique_users_1` | Integer | Unique users on Day 1 |
| `unique_users_3` | Integer | Unique users on Day 3 |
| `unique_users_7` | Integer | Unique users on Day 7 |
| `unique_users_14` | Integer | Unique users on Day 14 |
| `unique_users_30` | Integer | Unique users on Day 30 |
| `unique_users_60` | Integer | Unique users on Day 60 |
| `unique_users_90` | Integer | Unique users on Day 90 |
| `revenue_d0` | Decimal | Total revenue at Day 0 |
| `revenue_d1` | Decimal | Total revenue at Day 1 |
| `revenue_d3` | Decimal | Total revenue at Day 3 |
| `revenue_d7` | Decimal | Total revenue at Day 7 |
| `revenue_d14` | Decimal | Total revenue at Day 14 |
| `revenue_d30` | Decimal | Total revenue at Day 30 |
| `revenue_d60` | Decimal | Total revenue at Day 60 |
| `revenue_d90` | Decimal | Total revenue at Day 90 |
| `ad_revenue_d0` | Decimal | Ad revenue at Day 0 |
| `ad_revenue_d1` | Decimal | Ad revenue at Day 1 |
| `ad_revenue_d3` | Decimal | Ad revenue at Day 3 |
| `ad_revenue_d7` | Decimal | Ad revenue at Day 7 |
| `ad_revenue_d14` | Decimal | Ad revenue at Day 14 |
| `ad_revenue_d30` | Decimal | Ad revenue at Day 30 |
| `ad_revenue_d60` | Decimal | Ad revenue at Day 60 |
| `ad_revenue_d90` | Decimal | Ad revenue at Day 90 |
| `partner_impressions` | Integer | Impressions as reported by the media source |
| `partner_clicks` | Integer | Clicks as reported by the media source |
| `partner_installs` | Integer | Installs as reported by the media source |
| `partner_cost` | Decimal | Cost as reported by the media source |
| `partner_cpm` | Decimal | CPM as reported by the media source |
| `partner_ctr` | Decimal | CTR as reported by the media source |
| `partner_cvr` | Decimal | CVR as reported by the media source |
| `partner_ipm` | Decimal | IPM as reported by the media source |
| `partner_ecpi` | Decimal | eCPI as reported by the media source |
| `partner_video_viewed_2s` | Integer | Video views at 2 seconds (partner-reported) |
| `partner_video_viewed_3s` | Integer | Video views at 3 seconds (partner-reported) |
| `partner_video_viewed_6s` | Integer | Video views at 6 seconds (partner-reported) |
| `partner_engaged_views_6s` | Integer | Engaged views at 6 seconds (partner-reported) |
| `partner_engaged_views_15s` | Integer | Engaged views at 15 seconds (partner-reported) |
| `partner_video_started` | Integer | Video starts (partner-reported) |
| `partner_video_25p_views` | Integer | Video played to 25% (partner-reported) |
| `partner_video_50p_views` | Integer | Video played to 50% (partner-reported) |
| `partner_video_75p_views` | Integer | Video played to 75% (partner-reported) |
| `partner_video_completions` | Integer | Video completions (partner-reported) |

##### In-app events

In-app events appear in the report as metric columns using the format `{event_name}.{sub_metric}`. When you select an event, all four sub-metrics are automatically included. For example, selecting `af_purchase` generates the following columns: `af_purchase.event_count`, `af_purchase.unique_users`, `af_purchase.revenue`, and `af_purchase.cpa`.

| Sub-metric | Description |
| --- | --- |
| `event_count` | Total number of times the event was fired |
| `unique_users` | Number of unique users who triggered the event |
| `revenue` | Total revenue attributed to the event |
| `cpa` | Cost per action (cost / event count) |

Limits:

* Maximum of **30 in-app events** per report.
* Available events are account-specific and reflect the events your apps actively send to AppsFlyer.

#### Limitations

| Limitation | Details |
| --- | --- |
| Reports per account | Maximum 5 active reports per account |
| In-app events per report | Maximum 30 events per report |
| Total columns per report | Maximum 150 columns (dimensions + metrics + in-app event sub-metrics combined) |
| Data window | Data is available for a 30-day lookback window. Historical data outside this window isn’t available. |
| Delivery frequency | Once per day. Intraday delivery isn't supported |
| AI dimension availability | AI dimensions are populated only for creatives processed by the AI tagging pipeline. Newly uploaded creatives may have a delay |
| Custom metrics | Not yet supported |
| Conversion actions (web) | Not yet supported |
| App selection | All apps within your account are included in each report. The ability to filter by specific apps is planned for a future release |

</Accordion>

## FAQ

A list of frequently asked questions about ETL reporting.

<Accordion title="What's the difference between Standard Creative ETL and Custom Creative ETL?">

**Standard Creative ETL** is configured via Data Locker's Select reports page and delivers a fixed set of fields (schema) once per day. It doesn't support in-app events, retargeting or unified breakdowns, or AI dimensions.

**Custom Creative ETL** is configured directly in the AppsFlyer UI with a fully customizable set of fields. You can include up to 30 in-app events, AI dimensions, and User Acquisition/Retargeting/Unified breakdowns, with no backend configuration or customer success manager involvement required.

</Accordion>

<Accordion title="Can I run both Standard Creative ETL and Custom Creative ETL at the same time?">

Yes. Both can run in parallel. If you have a Standard Creative ETL report active, a notification banner appears on the Creative ETL page with a link to your Data Locker configuration.

</Accordion>

<Accordion title="Can I have multiple Custom Creative ETL reports with different report types?">

Yes. Each report is configured with a single report type (User Acquisition, Retargeting, or Unified), and you can create up to 5 reports per account.

</Accordion>

<Accordion title="How do I add new in-app events to an existing Custom Creative ETL report?">

Go to **Export** > **Creative ETL**, click the **Edit** icon on the report, go to **Step 3 (Schema)**, and add the new events. Changes take effect on the next daily delivery.

</Accordion>

<Accordion title="What happens if a report runs more than once on the same day?">

If a report is re-run (typically during a backfill), each run receives an incremented `version` value. Always use the highest version available for a given `dt` partition.

</Accordion>

> 📘 **See also**
>
> * [Creative Optimization guide](/docs/creative-optimization-guide)
> * [Data Locker advertiser reports](/docs/data-locker-advertiser-reports)
> * [Set up a Data Locker connection](/docs/data-locker-cloud-service-setup)
> * [Set up and use ROI360 cost ETL reports](/docs/set-up-and-use-roi360-cost-etl-reports)