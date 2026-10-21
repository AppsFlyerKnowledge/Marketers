---
title: ROI360 cost aggregation overview
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Premium
    - Premium Feature
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Marketers
    - Agencies
    - ROI360
  created_at: '2015-12-24T10:45:16Z'
  edited_at: '2026-10-05T06:57:44Z'
  id: 207040526
  locale: en-us
  section: Cost aggregation
  section_id: 6551029483281
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/207040526-ROI360-cost-aggregation-overview
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

**At a glance:** Learn about methods for advertisers to aggregate and view marketing cost data.

## Cost aggregation

ROI360 does the following:

* Provides aggregate advertising cost data and cost-related lifetime value (LTV) performance metrics. These are available via dashboards and performance reports. The cost-related metrics available include return on investment (ROI), return on ad spend (ROAS), clicks, impressions, campaign ROI, and average effective cost per install (eCPI) over time.
* Covers advertising costs across all platforms, including mobile apps, web browsers, connected TV (CTV), PCs, and consoles.
* Supports different cost models used by the media source, for example, cost per install (CPI), cost per action (CPA), cost per click (CPC), and cost per mille (CPM).
* Records advertising cost by API, Cost Import (CSV file upload), and <Anchor target="_blank" href="/marketers/docs/view-aggregated-cost-data-for-attribution-links">cost on the attribution link</Anchor>.
* Enables agencies to access ROI360 cost data for advertisers with an ROI360 subscription.

The following data is available to advertisers without an ROI360 subscription:

* <Anchor target="_blank" href="/marketers/docs/view-aggregated-cost-data-for-attribution-links">Cost data on the attribution link</Anchor>
* Self-reporting network (SRN) clicks and impressions data, which you configure in the **Cost** tab of the SRN integrated partner

## Principles of cost data aggregation

This section describes the main principles of aggregating campaign cost data.

<div id="cost-aggregation-methods" />

<Accordion title="Cost aggregation methods">

AppsFlyer obtains cost data from media sources using one or more methods. If a media source reports cost through more than one method, then the [cost prioritization mechanism](#cost-prioritization-mechanism) determines which data AppsFlyer uses. This prevents cost data from being inflated.

After AppsFlyer processes the data, it shows in UTC time zone (default) or according to your <Anchor target="_blank" href="/marketers/docs/changing-app-time-zone-settings">app-specific time zone</Anchor> settings.

<table><thead><tr><th>Cost aggregation method</th><th>Cost models supported</th><th>Data granularity</th><th>Data freshness</th><th>Remarks</th></tr></thead><tbody><tr><td><a href="./set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api" target="_blank">API</a>\*</td><td>All</td><td>Level depends on the integration</td><td><a href="./about-data-freshness-and-timezone-support#intraday-during-the-day" target="_blank">Intraday</a></td><td>Data might change after the cost event because AppsFlyer tries to retrieve data up to 7 days back (depending on the media source). This lets AppsFlyer account for retroactive changes made by the media source.</td></tr><tr><td><a href="./import-cost-data" target="_blank">Cost Import (file upload)</a></td><td>All</td><td>Level depends on the file uploaded</td><td>Up to 4 hours after import</td><td>You can revert the reported cost and submit corrected data for up to 90 days.</td></tr><tr><td><a href="./view-aggregated-cost-data-for-attribution-links" target="_blank">Cost on the attribution link</a></td><td>CPI</td><td>User-level</td><td><p>Minimum: real time</p><p>Maximum: Up to 4 hours after the link is clicked</p></td><td>No change possible</td></tr><tr><td colspan="5">\* API integrations between media sources and AppsFlyer are by either Cost API or InCost API (never both). The API used and the data granularity provided are media source-dependent.</td></tr></tbody></table>

</Accordion>

<div id="cost-data-availability-and-reports" />

<Accordion title="Cost data availability and reports">

The table at the end of this section indicates where cost data is available.

For the purposes of understanding the table, the following explanations apply, unless otherwise indicated in the table remarks:

#### Cost in the UA view

AppsFlyer classifies campaign cost data as user acquisition (UA) based on matching rules that vary by media source, as shown below.

| Media sources | Matching rule |
| --- | --- |
| Google Ads, DV360, Facebook, TikTok, Apple Search Ads, and Aura | AppsFlyer classifies cost as UA if it records at least one install, click, or impression within ±10 days of the install date (the date the media source reports the cost). |
| All other media sources | AppsFlyer classifies cost as UA if it records at least one install, click, or impression on the media source's own processing date. No ±10-day window applies. |

> 📘 **Note**
>
> This applies to both rows. AppsFlyer bases matches on the media source, campaign ID, and agency.

#### Cost in the Unified view

The Unified view includes cost data for all campaigns of the selected app, regardless of whether installs, clicks, or impressions exist within ±10 days of the cost reporting date (install date).

#### Example

The following examples show how the ±10-day window affects where cost appears:

* If a media source that uses the ±10-day window reports the cost for campaign X on March 15, and campaign X has at least one click, install, or impression between March 5 and March 25, the cost for March 15 appears in UA and in Unified.
  * If no activity exists in that time window, the cost for March 15 appears **only in Unified**. For media sources that match by processing date only, the same rule applies to March 15 itself, with no ±10-day window.

#### Cost data availability and reports table

| Reporting method | View/data type | Campaign name change support | Remarks |
| --- | --- | --- | --- |
| Overview dashboard | <ul><li>UA</li><li>Unified</li></ul> | Yes | Retargeting view doesn't display cost. Cost for retargeting displays in the Unified view. |
| Activity dashboard | UA | Yes |  |
| Cohort dashboard | <ul><li>UA</li><li>Unified</li></ul> | Yes | <ul><li>Retargeting view doesn't display cost</li><li>This Unified data is available only for campaigns with at least one install, click, or impression recorded within ±10 days of the cost reporting date (install date) for Google Ads, DV360, Facebook, TikTok, Apple Search Ads, and Aura. For all other media sources, this data is available only for campaigns with activity recorded on the same processing date as the cost.</li></ul> |
| Cohort API | <ul><li>UA</li><li>Unified</li></ul> | Yes | This Unified data is available only for campaigns with at least one install, click, or impression recorded within ±10 days of the cost reporting date (install date) for Google Ads, DV360, Facebook, TikTok, Apple Search Ads, and Aura. For all other media sources, this data is available only for campaigns with activity recorded on the same processing date as the cost. |
| SKAN dashboard | SKAN | No | This dashboard displays SKAdNetwork (SKAN) installs, along with cost data for **all** installs (including non-SKAN installs). |
| SKAN Aggregated Performance API | SKAN | No | This API displays SKAN installs, along with cost data for **all** installs (including non-SKAN installs). |
| Pivot dashboard | UA | No |  |
| Master API | UA | No |  |
| Custom dashboard | UA | No |  |
| Cost ETL | Unified | Yes | All available cost data displays. |
| Aggregated Pull API | UA | No |  |
| Push API | Raw click data (not aggregated) | Not relevant |  |
| Raw data Pull API | Raw click data (not aggregated) | Not relevant |  |
| Data Locker | Raw click data (not aggregated) | Not relevant | Data Locker Cohort doesn't support cost. |

> 📘 **Note**
>
> The following points apply to the table:
>
> * Data granularity can vary by dashboard/report type. The <Anchor target="_blank" href="/marketers/docs/set-up-and-use-roi360-cost-etl-reports">Cost ETL</Anchor> reporting tool contains the complete dataset. This includes campaign hierarchy details (media source, campaign name, ad, adset, and the dimensions available from the media source, including geo, channel, site ID, and keywords).
> * Cost data reported on the attribution link is available in raw data reports.
> * If a media source doesn't support campaign name changes, both campaign names display: one with attribution data and one with cost data. Neither campaign name includes the complete data picture.

</Accordion>

<div id="cost-prioritization-mechanism" />

<Accordion title="Cost prioritization mechanism">

For a given media source, cost can be provided by more than one method. To avoid cost inflation, a campaign cost prioritization mechanism decides which cost data appears in the platform. AppsFlyer gives priority according to the aggregation method. The priority from lowest to highest is: Cost on the attribution link > Cost API > Cost Import.

![Diagram showing the cost prioritization order: Cost on the attribution link, then Cost API, then Cost Import](https://files.readme.io/8dbea1b8561d67f77d27cad85ab109e5203930273f32d2a9b04900b810c46ec2-25433450962577.png)

The cost prioritization mechanism impacts aggregate data reports and dashboards. It doesn't impact attribution link cost data in raw data reports, as noted above.

**Considerations**:

* The priority mechanism works at the campaign level. This means that if you get two cost inputs for one campaign via different mechanisms, then they compete and the higher priority wins for the entire campaign.
  * On any day, when there's cost data for a specific app and media source (or agency) via Cost API, AppsFlyer ignores cost data on the attribution link.
* If you change cost aggregation methods, the change has a retroactive impact. Historical aggregate cost data can change.
* A change to the cost aggregation method affects agency-generated traffic the same way. This includes both transparent and non-transparent agencies.

> 📄 **Example**
>
> **Scenario:** A media source reports cost on the attribution link, but you decide to enable the media source's Cost API.
>
> **Result:** AppsFlyer aggregates cost from both the attribution link and the Cost API. Because the Cost API has priority, AppsFlyer ignores the cost on the attribution link.

</Accordion>

<div id="closed-beta--cost-split" />

<Accordion title="Cost split">

Some media sources report the campaign cost data without an associated app ID. When this happens, AppsFlyer completes the app ID(s) using engagement and attribution data.

AppsFlyer matches apps based on those associated with the campaign's clicks, impressions, and conversions within a **±10-day window** around the reported cost date.

If the app completion process results in multiple matched apps, AppsFlyer distributes the campaign cost across those apps as follows:

#### Proportional split (by conversions)

If conversions (installs, reattributions, and re-engagements) exist on the reported cost date, AppsFlyer splits the cost proportionally based on each app's number of conversions.

**Example:** If the total cost on Day 1 is **$100**, and the campaign drives **60 installs on iOS** and **40 installs on Android**, then:

* iOS: **$60**
* Android: **$40**

> 📘 **Note**
>
> The proportional (conversion-based) split applies only when the conversion granularity available in attribution exactly matches the granularity the media source reports for its cost data. When the two only partially match, AppsFlyer can't map the cost to each app's conversions, so it applies the equal split across the matched apps instead.

#### Equal split (no conversions)

If no conversions exist on the reported cost date, AppsFlyer splits the cost equally across the matched apps.

**Example:** If the total cost on Day 1 is **$100** and the campaign has impressions but no conversions on that date, then:

* iOS: **$50**
* Android: **$50**

#### Limitations

The following limitations apply to this feature:

* AppsFlyer supports this feature for Google, TikTok, and DV360 cross-platform and web-to-app (W2A) campaigns (campaigns with a campaign objective that is different from mobile/app).
* **Google Performance Max (PMAX) campaigns**: The proportional (conversion-based) split doesn't apply. Google's API doesn't report Ad ID or Geo granularity for PMAX campaigns, so AppsFlyer splits the cost equally across the matched apps, regardless of the number of conversions per app. At the campaign level, when all platforms (iOS, Android, etc.) are selected in the dashboard, the total cost still matches Google's reported cost.

</Accordion>

## Additional information

<div id="ad-networks-supporting-cost-api" />

<Accordion title="List of media sources supporting the Cost API">

The downloadable table below lists all media sources supporting Cost API, with the data granularity available for each:

* Dimensions
* Supported features and their characteristics
* Metrics (as reported by the media sources)

Download file: <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQT0acJlUFIwS5NUuD8tJ5MA7OmL0N9a55qLp4ib5FYL_eat1H4IWNW9ZCtAEeDa1kTZK5bRD2ez-ee/pub?output=csv">CSV</Anchor>, <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQT0acJlUFIwS5NUuD8tJ5MA7OmL0N9a55qLp4ib5FYL_eat1H4IWNW9ZCtAEeDa1kTZK5bRD2ez-ee/pub?output=xlsx">XLSX</Anchor>

</Accordion>

<div id="changing-campaign-names" />

<Accordion title="Changing campaign names">

AppsFlyer displays campaigns using the campaign ID as the key.

To avoid display anomalies, make sure that:

* Each campaign has a unique campaign ID.
* You don't use the same campaign name with different campaign IDs.

<Anchor target="_blank" href="/marketers/docs/campaign-name-changes">Learn more about campaign name changes</Anchor>

</Accordion>

<div id="costs-without-installs" />

<Accordion title="Costs without installs">

**Why do I see cost data with no installs?** This occurs when a media source provides cost at a higher level in the hierarchy (for example, the campaign level) but provides performance information (clicks and installs) at a lower level in the advertising hierarchy (for example, the ad adset level).

AppsFlyer completes the cost data for missing dimensions from an upper-level hierarchy. This guarantees a full view of the cost data at any level and minimizes internal discrepancies.

> 📄 **Example**
>
> An advertiser runs a campaign. The advertising hierarchy is as follows:
>
> * **Media source**: media\_eg
> * **Campaign**: campaign\_eg
> * **Adsets**: **adset\_1**, **adset\_2**
>
> The following table shows information relating to the media source.
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
> Drilling down into campaign\_eg shows the adset level.
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
> In this case, AppsFlyer provides the $100 cost of campaign\_eg at the campaign level. When drilling down to the adset level, which in this case is the lowest level of the hierarchy, AppsFlyer can't break down the cost by adset.
>
> To overcome this, AppsFlyer breaks down the cost from the campaign level and displays it in a separate row. In this case, the adset displays as None, and the installs field stays blank.

</Accordion>

<div id="cost-currency-conversion" />

<Accordion title="Cost currency conversion">

If the campaign cost currency provided by the media source differs from the app-defined currency on the platform, AppsFlyer converts the cost to the app-defined currency as follows:

* AppsFlyer gets the rates from <Anchor target="_blank" href="https://openexchangerates.org/">openexchangerates.org</Anchor>.
* AppsFlyer updates exchange rates hourly for data up to seven days back.
* AppsFlyer performs currency conversions using the last known rate.

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Traits and limitations">

| Trait | Description |
| --- | --- |
| Agencies | <ul><li>When transparent agencies run campaigns, advertisers can see costs displayed in dashboards and reports, providing a unified view. [Learn more about cost data availability and reports](#cost-data-availability-and-reports)</li><li>If an advertiser ends their relationship with an agency and the agency has cost configured for the app, AppsFlyer continues to pull cost data even if the advertiser disables the agency permissions at the app level. To prevent this, the advertiser must ask the agency to deactivate their cost integration in AppsFlyer before disabling the agency permissions.</li><li>For some media sources, agencies must contact the advertiser to activate the integration, and the AppsFlyer UI prompts them to do so. For these media sources, agencies and advertisers must make sure that when the media source sends data, it includes the `af_prt` parameter, required for agency cost attribution.</li><li>For X Ads, cost data for SKAN-only campaigns (those with only SKAN installs and no "regular" installs) isn't available to agencies. The advertiser must set up the cost integration. Only the advertiser can view the data.</li></ul> |
| API data freshness | <ul><li><Anchor target="_blank" href="/marketers/docs/about-data-freshness-and-timezone-support#intraday-during-the-day">Intraday</Anchor> (except for Moloco)</li><li>Mintegral data is available via the API the following day, approximately 4 hours after the previous day ends. For example, if the event occurred on Day 1, cost data is available by Day 2, at approximately 4:00.</li></ul> |
| Campaign name changes | Ad spend data displays the most recent reported campaign name. This applies to aggregate data only, not to the raw data itself. |
| Time zone | If a media source supports only one time zone, and that time zone differs from the one set in your app settings, AppsFlyer uses the media source's time zone. |
| CTV, PC, and console platforms | For apps on these platforms, import data via <Anchor target="_blank" href="/marketers/docs/import-cost-data">Ad Spend Ingestion</Anchor> using the upload-by-email method.<br /><br />You can also pull data via API for Google, Meta, or TikTok in the following platforms:<ul><li>Steam</li><li>Native PC</li><li>Smart Cast</li><li>Tizen</li><li>Quest</li></ul> |
| Cross-platform | Cost data isn't available for cross-platform clicks and impressions, meaning the impression/click might occur on one platform and the app install on another. |
| Out-of-store apps | Cost data from Mintegral isn't available for out-of-store apps (apps from platforms other than Google Play and App Store). |
| Geo | Geo/country breakdown isn't available for Mistplay bundled campaigns (campaigns targeted to several countries). For such campaigns, geo displays as N/A. |
| Smadex | Dashboards and Cost ETL reports might show cost and attribution data separately. This occurs when Smadex includes additional elements (such as an inventory ID) in the site ID value. |
| Apple Search Ads (ASA) | For SKAN-only reporting, ASA cost data isn't available in the SKAN dashboard or the Pull API because Apple doesn't include campaign-level data in SKAN postbacks. However, cost data is available in single-source-of-truth (SSOT) reports via AppsFlyer's classic integration. |
| Cost data dimension character limit | For the media sources listed below, the following dimensions must not exceed the specified character lengths. If you don't comply with these limits, AppsFlyer excludes the dimension values from the report.<ul><li>`app_id`: up to 100 characters</li><li>`publisher`: up to 250 characters</li><li>`partner`: up to 250 characters</li><li>`campaign`: up to 250 characters</li><li>`campaign_id`: up to 250 characters</li><li>`adset`: up to 250 characters</li><li>`adset_id`: up to 250 characters</li><li>`ad`: up to 250 characters</li><li>`ad_id`: up to 250 characters</li><li>`site_id`: up to 250 characters</li><li>`site_name`: up to 250 characters</li><li>`channel`: up to 250 characters</li><li>`ad_account`: up to 250 characters</li><li>`ad_account_name`: up to 250 characters</li></ul>The limitations apply only to the following media sources:<ul><li>`mintegral_int`</li><li>`moloco_int`</li><li>`applovin_int`</li><li>`liftoff_int`</li><li>`aura_int`</li><li>`tiktokglobal_int`</li><li>`pinterest_int`</li><li>`vungle_int`</li><li>`iossearchads_int`</li></ul> |
| API Cost data availability | AppsFlyer displays API cost data only for customers with an active ROI360 asset. If ROI360 is deactivated, cost data from API sources becomes unavailable, and the dashboard shows only CPI-based cost data. |
| Mintegral: ad-level granularity | To get cost reporting with ad-level granularity from Mintegral, each ad account requires the following ad network permissions: **Sub/Package × Creative dimension**. |

</Accordion>

<div data-zendesk-anchors="h_01HC7K2Y627P56F5JH9QT47GB2=cost-aggregation h_01HC7K2Y62ZC932EDX00YP7DAW=principles-of-cost-data-aggregation h_01HC7K2Y62K78M02ZN034N99T0=cost-aggregation-methods h_01HC7K2Y62YPM3A6Z0HBY58J00=cost-data-availability-and-reports h_01KGS7NM964HW175AW2CF59P5K=cost-in-the-ua-view h_01M3VZAVTP7F3TF607B49TGZQ4=note cost-in-unified-view=cost-in-the-unified-view h_01KGS7QG5GNKG1YVACWQKCQFZ4=cost-in-the-unified-view h_01KGS7R5SJ3NSVJAHG3BM922VS=example cost-data-availability-and-reports::865c5bcd=cost-data-availability-and-reports-table h_01HC7K2Y62ZY6HWG5TJDEPHZKH=cost-data-availability-and-reports-table h_01M3VZAVTPK4Q2X817ER2CW62D=note-1 h_01HC7K2Y62112X308A0Y7DDDRM=cost-prioritization-mechanism h_01HC7K2Y62SZKXD4W0EJGYF6RS=example-1 %5Bclosed-beta%5D-cost-split=closed-beta--cost-split h_01KHR3PQTNF5XP7J4HZEYVRK95=closed-beta--cost-split h_01KHR3PQTNMDX8AGM1C73N7SMK=proportional-split-by-conversions h_01KZ8TMT06KNYFZ7VBX1GY07JB=note-2 h_01KHR3PQTPG8GTHV64MFCM628H=equal-split-no-conversions h_01KHR3PQTPPJYKXRYKNHM4W95A=limitations list-of-ad-networks=additional-information h_01HC7K2Y63T9GK0WW95YM39B5C=additional-information h_01HC7K2Y63MG10M4Z66VHY5WYW=ad-networks-supporting-cost-api h_01HE0T3TGPZFB2ZBHFGGWXY6AP=changing-campaign-names h_01HE0T3TGQGK6135KM7AYJ7S1G=costs-without-installs h_01HE0T3TGQMK285N8RV48KG8N9=example-2 h_01HE0T3TGQ7MSSB09GFNPYFKR1=cost-currency-conversion h_01HJ10FMTJKH48CEXM0G40Y9J1=traits-and-limitations" />
