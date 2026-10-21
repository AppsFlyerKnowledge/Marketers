---
title: SKAN aggregated postback arrival date API
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2020-12-21T09:03:09Z'
  edited_at: '2024-09-18T06:25:36Z'
  id: 360016646557
  locale: en-us
  section: SKAN solution
  section_id: 6552135379985
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360016646557-SKAN-aggregated-postback-arrival-date-API
---
**At a glance:** Aggregated SKAdNetwork postbacks via API. Data is aggregated using postback arrival date.

## SKAN aggregated postback arrival date API

The API returns aggregated SKAdNetwork postbacks, using the postback arrival date range.

**Note**! Postback arrival date differs from the install date used in the SKAdNetwork dashboard and reports.

<div id="using-skan-aggregated-performance-report-api" />

<Accordion title="Using SKAN aggregated postback arrival date API">

**To use SKAN aggregated postback arrival date API**:

1. Get the API token. An admin needs to retrieve the token.
2. Give your developer the API token to be used in the authentication header.
3. Give your developers the parameters to input when they make the API call, as described in the section that follow. The parameters determine what the report focuses on, how it's organized, and provide a reporting timeframe.
4. Tell your developer to follow their <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/skan-agg-postback-arrival-date-api-get">SKAN aggregated postback arrival date API</Anchor> in the developer hub.

#### Parameters

| Parameter name | Details | Mandatory |
| --- | --- | --- |
| `start_date` | The postback arrival date range is bounded by start\_date and end\_date. Note! The arrival date differs from the install date used in the SKAdNetwork dashboard and reports.<ul><li>YYYY-MM-DD</li><li>Earliest date permitted: 2020-11-01<br />Example: `2020-11-05`</li></ul> | Yes |
| `end_date` | <ul><li>YYYY-MM-DD</li><li>Maximum number of days per report call: 60 days</li><li>Example: `2020-11-12`</li></ul> | Yes |
| `ad_network_name` | Filter by media source | No |
| `geo` | Filter by country code using ISO 3166 (alpha-2). Example: `US`, `CN` | No |
| `skad_redownload` | Filter by `true` or `false` | No |
| `skad_source_app_id` | Filter by source app ID | No |
| `ad_network_campaign_id` | Filter by ad network campaign ID.<br /><br />**Note**: This is not the campaign ID reported by SKAdNetwork. | No |
| `modeled_conversion_values` | <ul><li>Only supported from V2</li><li>Value can be either `true` or `false`</li><li>If `true`, the postback populates the “count” column with modeled conversion value data.  [See available field for modeled data](/docs/skan-aggregated-postback-arrival-date-api#report-structure-and-example)</li><li>If `false`, the postback presents the conversion value count and with all available fields as received by listed in the report structure, without modeled data.</li><li>Default value is `false`.</li></ul> | No |

</Accordion>

<div id="report-structure-and-example" />

<Accordion title="Report structure and example">

The API returns a CSV file.

Columns and metrics available are listed in the table that follows.

Examples: <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRXgsWlkyvMS20HgZuOQnH1YC8QQcRhOMYIOxyj_fcgikfDfmW6wNAMHO6alPWVA1j_KZwtqowohqrK/pub?gid=0&single=true&output=csv">V1</Anchor> | <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRMFEELm8JCAQBBAIJqAc1eE5YdN0kOcSVkOPd_Ki2ngnX61wHL4sXypVouOhto8u-JCQmdIYY_5UG6/pub?gid=219191499&single=true&output=csv">V2</Anchor>

| Column name | Dimension or measure | Available with API V1 token | Available with API V2 token | Available with API V2 token (for SKAN 4) | Available with modeled data only filter |
| --- | --- | --- | --- | --- | --- |
| skad\_postback\_sequence\_index | Group by | N | N | Y | Y |
| skad\_conversion\_value | Group by | Y | Y | Y | Y |
| skad\_coarse\_conversion\_value | Group by | N | N | Y | Y |
| skad\_ad\_network\_id<br /><br />Some SRNs don't share their ID with us. In this case, the field is blank and ad\_network\_name is populated. | Group by | Y | Y | Y | Y |
| ad\_network\_name<br /><br />Currently,  in most cases this field is blank. We do populate it in the case of SRNs who don't share their skad\_ad\_network\_id | Group by | Y | Y | Y | Y |
| skad\_source\_identifier | Group by | N | N | Y | Y |
| skad\_campaign\_id | Group by | Y | Y | Y | Y |
| ad\_network\_campaign\_id | Group by | Y | Y | Y | Y |
| ad\_network\_campaign\_name | Group by | Y | Y | Y | Y |
| ad\_network\_adset\_id | Group by | N | Y | Y | Y |
| ad\_network\_adset\_name | Group by | N | Y | Y | Y |
| ad\_network\_ad\_id | Group by | N | Y | Y | N |
| ad\_network\_ad\_name | Group by | N | Y | Y | N |
| ad\_network\_creative | Group by | N | N | Y | N |
| ad\_network\_channel | Group by | N | N | Y | N |
| skad\_version | Group by | Y | Y | Y | N |
| skad\_redownload | Group by | Y | Y | Y | N |
| skad\_source\_app\_id | Group by | Y | Y | Y | N |
| skad\_source\_domain | Group by | N | N | Y | Y |
| skad\_fidelity\_type | Group by | N | Y | Y | N |
| geo | Group by | Y | Y | Y | N |
| arrival\_date | Group by | Y | Y | Y | Y |
| count | Measure | Y | Y | Y | Y |

</Accordion>

<div id="specifications-and-limitations" />

<Accordion title="Specifications and limitations">

| Spec | Remarks |
| --- | --- |
| Data freshness | The report updates <Anchor target="_blank" href="/marketers/docs/about-data-freshness-and-timezone-support#eod">Daily.</Anchor><br /><br />Data availability is according to the <Anchor target="_blank" href="/marketers/docs/about-data-freshness-and-timezone-support#skan">SKAdNetwork</Anchor> data freshness rate. |
| Date range | <ul><li>Earliest date supported: November 1, 2020</li><li>Maximum query range: 60 days</li></ul> |
| Rate limit | <ul><li>Queries return up to 200K rows</li><li>60 calls per minute</li></ul> |
| SRNs | Google Ads: The postback arrival date is derived using the last-click time reported by Google. |
| Ad network access | Available to analytics partners if the advertiser grants permission. |
| Agency access | Not available |
| App-specific time zone | UTC only |
| App-specific currency | Always USD |
| Organic data | Not available with this API |
| Non-organic data | Calculated using SKAdNetwork postbacks received by AppsFlyer |
| Historical data | Earliest conversion data (install or retarget) supported: November 1, 2020 |
| Account user access | The authorization token is available to an admin user in the dashboard. |

</Accordion>

> 📄 **See also**
>
> * <Anchor target="_blank" href="/marketers/docs/skan-aggregated-performance-report-api">SKAN aggregated performance report API</Anchor>

<div data-zendesk-anchors="skadnetwork-postback-arrival-date-aggregation-reporting-api=skan-aggregated-postback-arrival-date-api h_01HDNZKFEHWET0FPX9WN136MB2=skan-aggregated-postback-arrival-date-api h_01HDNZKFEH76Y06091QS6Y5K1Z=using-skan-aggregated-performance-report-api h_01HDNZKFEHA6N6EE4RMG0HGABA=parameters h_01HDNZKFEHM2D7GS3RMSRCKZY7=report-structure-and-example h_01HDNZKFEJ5P3245V1R99DGAQW=specifications-and-limitations h_01HDNZP87CWGVJ3G1BDXAR1WN0=see-also" />
