---
title: "ROI360 cost aggregation overview"
excerpt: "Learn about methods for advertisers to aggregate and view marketing cost data, including API, Cost Import, and attribution link methods."
---
**At a glance:** Learn about methods for advertisers to aggregate and view marketing cost data.

## Cost aggregation

**ROI360**:

* Provides aggregate advertising cost data and cost-related LTV (lifetime value) performance metrics. These are available via dashboards and performance reports. The cost-related metrics available include ROI, ROAS (return on ad spend), clicks, impressions, campaign ROI, and average effective cost per installation (eCPI) over time.
* Covers advertising costs across all platforms, including mobile apps, web browsers, CTV, PCs, and consoles.
* Supports different cost models used by the partner, for example, CPI, CPA, CPC, and CPM.
* Records advertising cost by API, Cost Import (CSV file upload), and [cost on the attribution link](/docs/view-aggregated-cost-data-for-attribution-links).
* Agencies can access ROI360 cost data for advertisers with an ROI360 subscription.

The following metrics are available to advertisers without an ROI360 subscription:

* [Cost data is reported on the attribution link](/docs/view-aggregated-cost-data-for-attribution-links).
* SRN (self-reporting network) clicks and impressions data, configured via the SRN integrated partner **Cost** tab.

## Principles of cost data aggregation

This section describes the main principles of aggregating campaign cost data.

### Cost aggregation methods

Cost data is obtained from partners using one or more methods. If cost is reported by more than one method, then the [cost prioritization mechanism](/docs/roi360-cost-aggregation-overview#cost-prioritization-mechanism) determines which data is used. This ensures that cost data is not inflated.

After AppsFlyer processes the data, it shows in UTC timezone (default) or according to your [app-specific timezone](/docs/changing-app-time-zone-settings) settings.

| Cost aggregation method | Cost models supported | Data granularity | Data freshness | Remarks |
| --- | --- | --- | --- | --- |
| [API](/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api)* | All | Level depends on the integration | [Intraday](/docs/about-data-freshness-and-timezone-support#intraday-during-the-day) | Data may change after the cost event as we try to receive data up to 7 days back (depending on the media source). This enables us to account for retroactive changes made by the media source. |
| [Cost Import (file upload)](/docs/import-cost-data) | All | Level depends on the file uploaded | Up to 4 hours after import | The reported cost can be reverted, and corrected data can be submitted for up to 90 days. |
| [Cost on the attribution link](/docs/view-aggregated-cost-data-for-attribution-links) | CPI | User-level | Minimum: real-time  Maximum: Up to 4 hours after the link is clicked | No change possible |
| * API integrations between partners and AppsFlyer are by either Cost API or InCost API (never both). The API used and the data granularity provided are partner-dependent. | | | | |

### Cost data availability and reports

The following table indicates where cost data is available.

For the purposes of understanding the table, the following explanations apply, unless otherwise indicated in the table remarks:

#### Cost in the UA view

Campaign cost data is classified as User Acquisition if the campaign has at least one install, click, or impression recorded on the date the cost is reported (install date) and within ±10 days of that date. Matching is done using the media source, campaign ID, and agency.

#### Cost in the Unified view

The Unified view includes cost data for all campaigns of the selected app, regardless of whether installs, clicks, or impressions exist within ±10 days of the cost reporting date (install date).

#### Example

* If cost for campaign X is reported on March 10 and campaign X has at least one click or install between March 1–March 20, the cost for March 10 appears in UA and in Unified.

  * If no activity exists in that time window, the cost for March 10 appears **only in Unified**.
* If campaign name changes are not supported, both campaign names will display: one with attribution data and one with cost data. Neither campaign name displayed will include the complete data picture.

#### Cost data availability and reports table

| Reporting method | View/data type | Campaign name change support | Remarks |
| --- | --- | --- | --- |
| Overview dashboard | * UA<br />* Unified | Yes | Retargeting view doesn't display cost. Cost for retargeting displays in the unified view. |
| Activity dashboard | UA | Yes |  |
| Cohort dashboard | * UA<br />* Unified | Yes | * Retargeting view doesn't display cost<br />* This unified data is available only for campaigns with at least one install, click, or impression recorded within ±10 days of the cost reporting date (install date). |
| Cohort API | * UA<br />* Unified | Yes | This unified data is available only for campaigns with at least one install, click, or impression recorded within ±10 days of the cost reporting date (install date). |
| SKAN dashboard | SKAN | No | SKAN installs are displayed, along with cost data for **all** installs (including non-SKAN installs). |
| SKAN Aggregated Performance API | SKAN | No | SKAN installs are displayed, along with cost data for **all** installs (including non-SKAN installs). |
| Pivot dashboard | UA | No |  |
| Master API | UA | No |  |
| Custom dashboard | UA | No |  |
| Cost ETL | Unified | Yes | All available cost data displays. |
| Aggregated Pull API | UA | No |  |
| Push API | Raw click data (not aggregated) | Not relevant |  |
| Raw data Pull API | Raw click data (not aggregated) | Not relevant |  |
| Data Locker | Raw click data (not aggregated) | Not relevant | Data Locker Cohort doesn't support cost. |

**Note**:

* Data granularity can vary by dashboard/report type. The [Cost ETL](/docs/set-up-and-use-roi360-cost-etl-reports) reporting tool contains the complete dataset. This includes campaign hierarchy details (media source, campaign name, ad adset, and the dimensions available from the media source, including geo, channel, site ID, and keywords).
* Cost data reported on the attribution link is available in raw data reports.

### Cost prioritization mechanism

![](https://support.appsflyer.com/hc/article_attachments/25433450962577)

For a given media source, cost can be provided by more than one method. To avoid cost inflation, a campaign cost prioritization mechanism decides which cost data is made available in the platform. Priority is given according to the aggregation method. The priority from lowest to highest is: Cost on the attribution link > Cost API > Cost Import.

The cost prioritization mechanism impacts aggregate data reports and dashboards. Attribution link cost data available in raw data reports are not impacted by the prioritization mechanism.

**Considerations**:

* The priority mechanism works at the campaign level. This means that if you get 2 cost inputs for one campaign via different mechanisms, then they compete and the higher priority wins for the entire campaign.
  * On any day, when there's cost data for a specific app and media source (or agency) via Cost API, cost data on the attribution link is ignored.
* If you change cost aggregation methods, the change has a retroactive impact. Historical aggregate cost data can change.
* Change to the cost aggregation method affects agency-generated traffic in the same manner. This includes both transparent and non-transparent agencies.

> 📘 **Note**
>
> #### Example
>
> **Scenario:** A media source reports cost on the attribution link, but you decide to enable the media source's Cost API.
>
> **Result:** Cost is aggregated from both the attribution link and the Cost API. Because the Cost API has priority, the cost on the attribution link is ignored.

### Cost split

There are ad networks that report the campaign cost data without an associated app ID. When this happens, AppsFlyer completes the app ID(s) using engagement and attribution data.

AppsFlyer matches apps based on those associated with the campaign's clicks, impressions, and conversions within a **±10-day window** around the reported cost date.

If the app completion process results in multiple matched apps, AppsFlyer distributes the campaign cost across those apps as follows:

#### Proportional split (by conversions)

If conversions (installs, reattributions, and re-engagements) exist on the reported cost date, the cost is split proportionally based on each app's number of conversions.

**Example:** If the total cost on Day 1 is **$100**, and the campaign drives **60 installs on iOS** and **40 installs on Android**, then:

* iOS: **$60**
* Android: **$40**

#### Equal split (no conversions)

If no conversions exist on the reported cost date, the cost is split equally across the matched apps.

**Example:** If the total cost on Day 1 is **$100** and the campaign has impressions but no conversions on that date, then:

* iOS: **$50**
* Android: **$50**

> 📘 **Note**
>
> #### Note
>
> The proportional (conversion-based) split applies only when the conversion granularity available in attribution exactly matches the granularity the ad network reports for its cost data. When the two only partially match, AppsFlyer can't map the cost to each app's conversions, so it applies the equal split across the matched apps instead.

#### Limitations

* This feature is supported for Google, TikTok, and DV360 cross-platform and web-to-app (W2A) campaigns (campaigns with a campaign objective that is different from mobile/app).
* **Google Performance Max (PMAX) campaigns**: The proportional (conversion-based) split doesn't apply. Google's API doesn't report Ad ID or Geo granularity for PMAX campaigns, so the conversion granularity only partially matches, and the cost can't be mapped to each app's installs, reattributions, and re-engagements. As a result, the cost is split equally across the matched apps, regardless of the number of conversions per app. At the campaign level, when all platforms (iOS, Android, and so on) are selected in the dashboard, the total cost still matches the cost reported by Google.

## Additional information

### List of media sources supporting the Cost API

The downloadable table below lists all media sources supporting Cost API, with the data granularity available for each:

* Dimensions
* Supported features and their characteristics
* Metrics (as reported by the media sources)

Download file: [CSV](https://docs.google.com/spreadsheets/d/e/2PACX-1vQT0acJlUFIwS5NUuD8tJ5MA7OmL0N9a55qLp4ib5FYL_eat1H4IWNW9ZCtAEeDa1kTZK5bRD2ez-ee/pub?output=csv), [XLS](https://docs.google.com/spreadsheets/d/e/2PACX-1vQT0acJlUFIwS5NUuD8tJ5MA7OmL0N9a55qLp4ib5FYL_eat1H4IWNW9ZCtAEeDa1kTZK5bRD2ez-ee/pub?output=xlsx)

### Changing campaign names

AppsFlyer displays campaigns using the campaign ID as the key.

To avoid display anomalies, make sure that:

* Each campaign has a unique campaign ID assigned to it.
* You don't use the same campaign name with different campaign IDs.

[Learn more about campaign name changes](/docs/campaign-name-changes)

### Costs without installs

**Why do I see cost data with no installs?** This occurs when cost is provided at a higher level in the hierarchy (for example, campaign level), but performance information (clicks and installs) is provided at a lower level in the advertising hierarchy (for example, ad adset).

AppsFlyer completes the cost data for missing dimensions from an upper-level hierarchy. This guarantees a full view of the cost data at any level and minimizes internal discrepancies.

> 📘 **Note**
>
> #### Example
>
> An advertiser runs a campaign. The advertising hierarchy is as follows:
>
> * **Media source**: media\_eg
> * **Campaign**: campaign\_eg
> * **Adsets**: **adset1**, **adset2**
>
> The following information relating to the media source is displayed.
>
> Hierarchy: All Media Sources > media\_eg
>
>
>
> | Campaign | Cost | Installs |
> | --- | --- | --- |
> | campaign\_eg | $100 | 100 |
> | campaign\_yy | $200 | 1000 |
> | campaign\_zz | $300 | 2000 |
>
>
>
> Drilling down into campaign\_eg, the adset level is shown.
>
> Hierarchy: All Media Sources > media\_eg > campaign\_eg
>
>
>
> | Adset | Cost | Installs |
> | --- | --- | --- |
> | None | $100 |  |
> | adset\_1 | N/A | 30 |
> | adset\_2 | N/A | 70 |
>
>
>
> In this case, the cost of campaign\_eg is $100 and is provided at the campaign level. When drilling down to the adset level, which in this case is the component level, the cost cannot be broken down by adset.
>
> To overcome this, AppsFlyer carries down the cost from the campaign level and displays it in a separate row. In this case, the adset is shown as none, and the installs field is left blank

### Cost currency conversion

If the campaign cost currency provided by the media source differs from that of the app-defined currency set on the platform, the cost is converted to the app-defined currency as follows:

* AppsFlyer gets the rates from [openexchangerates.org.](https://openexchangerates.org/)
* Exchange rates are updated hourly for data up to 7 days back.
* Currency conversions are performed using the last known rate.

### Traits and limitations

| Trait | Description |
| --- | --- |
| Agencies | * Agencies can access ROI360 cost data for advertisers with an ROI360 subscription.<br />* When transparent agencies run campaigns, advertisers can see costs displayed in dashboards and reports, providing a unified view. [Learn more](/docs/roi360-cost-aggregation-overview#cost-data-availability-and-reports)<br />* If an advertiser ends their relationship with an agency and the agency has cost configured for the app, cost data continues to be pulled even if the advertiser disables the agency permissions at the app level. To prevent this, the advertiser must ask the agency to disable their cost integration in AppsFlyer before disabling the agency permissions.<br />* For some media sources, agencies must contact the advertiser to activate the integration and are prompted to do so in the AppsFlyer UI. For these networks, agencies, and advertisers must make sure that when the media source sends data, it includes the `af_prt` parameter, required for agency cost attribution.<br />* For X Ads, cost data for SKAN-only campaigns (those with only SKAN installs and no "regular" installs) isn't available to agencies. The cost integration must be set up by the advertiser. And the data can only be viewed by the advertiser. |
| API data freshness | * [Intraday](/docs/about-data-freshness-and-timezone-support#intraday-during-the-day) (except for Moloco)<br />* Mintegral data is available via the API the following day, approximately 4 hours after the previous day ends. Meaning, if the event occurred on Day 1, cost data is available by Day 2, at approximately 4:00. |
| Campaign name changes | Ad spend data displays using the most recent campaign name reported. **Note**: This is for displaying aggregate data, not the raw data itself. |
| Timezone | If a media source supports only one timezone and there is a discrepancy between the timezone the media source supports and the timezone set in your app settings, the timezone the media source supports is used. |
| CTV, PC, and console platforms | For apps on these platforms, cost data must be sent via [Ad Spend Ingestion](/docs/import-cost-data) using the upload file by email method. |
| Cross-platform | Cost data isn't available for cross-platform clicks and impressions, meaning the impression/click may occur on one platform and the app install on another. |
| Out-of-store apps | Cost data from Mintegral isn't available for out-of-store apps (apps from platforms other than Google Play and App Store). |
| Geo | Geo/country breakdown isn't available for Mistplay bundled campaigns (campaigns targeted to several countries). For such campaigns, geo displays as N/A. |
| Smadex | Dashboards and cost ETL reports may show cost and attribution data separately. This occurs when Smadex includes additional elements (such as an inventory ID) in the site ID value. |
| Apple Search Ads (ASA) | For SKAN-only reporting, ASA cost data isn't available in the SKAN dashboard or the Pull API because Apple doesn't include campaign-level data in SKAN postbacks. However, cost data is available in SSOT reports via our classic integration. |
| Cost data dimension character limit | For the networks listed below, the following dimensions must not exceed the specified character lengths. Failing to comply with these limits will result in the exclusion of dimension values from the report.<br /><br />* `app_id` &lt;=100<br />* `publisher` &lt;=250<br />* `partner` &lt;=250<br />* `campaign` &lt;=250<br />* `campaign_id` &lt;=250<br />* `adset` &lt;=250<br />* `adset_id` &lt;=250<br />* `ad` &lt;=250<br />* `ad_id` &lt;=250<br />* `site_id` &lt;=250<br />* `site_name` &lt;=250<br />* `channel` &lt;=250<br />* `ad_account` &lt;=250<br />* `ad_account_name` &lt;=250<br /><br />The limitations apply only to the following networks:<br /><br />* mintegral\_int,<br />* moloco\_int,<br />* applovin\_int,<br />* liftoff\_int,<br />* aura\_int,<br />* tiktokglobal\_int,<br />* pinterest\_int,<br />* vungle\_int,<br />* iossearchads\_int |
| API Cost data availability | API cost data is displayed only for customers with an active ROI360 asset. If ROI360 is deactivated, cost data from API sources is no longer available, and only CPI-based cost data will be shown in the dashboard. |
| Mintegral: ad level granularity | To get cost reporting with ad-level granularity from Mintegral, the following ad network permissions are required per ad account: **Sub/Package × Creative dimension**. |

> 📘 **Note**
>
> #### See also
>
> * [Cost aggregation overview](/docs/roi360-cost-aggregation-overview)
> * [Cost on the attribution link](/docs/view-aggregated-cost-data-for-attribution-links)
> * [Data freshness and time zone support](/docs/about-data-freshness-and-timezone-support)
> * [Campaign name changes](/docs/campaign-name-changes)