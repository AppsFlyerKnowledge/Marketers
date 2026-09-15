---
title: "SKAN aggregated postback arrival date API"
excerpt: "Retrieve aggregated SKAdNetwork postbacks via API using the postback arrival date range."
---
Aggregated SKAdNetwork postbacks via API. Data is aggregated using postback arrival date.

## SKAN aggregated postback arrival date API

The API returns aggregated SKAdNetwork postbacks, using the postback arrival date range.

> 🚧 Note
>
> Postback arrival date differs from the install date used in the SKAdNetwork dashboard and reports.

### Using SKAN aggregated postback arrival date API

**To use SKAN aggregated postback arrival date API**:

1. Get the API token. An admin needs to retrieve the token.
2. Give your developer the API token to be used in the authentication header.
3. Give your developers the parameters to input when they make the API call, as described in the section that follow. The parameters determine what the report focuses on, how it's organized, and provide a reporting timeframe.
4. Tell your developer to follow their [SKAN aggregated postback arrival date API](https://dev.appsflyer.com/hc/reference/skan-agg-postback-arrival-date-api-get) in the developer hub.

#### Parameters

| Parameter name | Details | Mandatory |
| --- | --- | --- |
| `start_date` | The postback arrival date range is bounded by start\_date and end\_date. Note! The arrival date differs from the install date used in the SKAdNetwork dashboard and reports.<br />- YYYY-MM-DD <br />- Earliest date permitted: 2020-11-01<br />  <br />  Example: `2020-11-05` | Yes |
| `end_date` | - YYYY-MM-DD<br />- Maximum number of days per report call: 60 days <br />- Example: `2020-11-12` | Yes |
| `ad_network_name` | Filter by media source | No |
| `geo` | Filter by country code using ISO 3166 (alpha-2). Example: `US`, `CN` | No |
| `skad_redownload` | Filter by `true` or `false` | No |
| `skad_source_app_id` | Filter by source app ID | No |
| `ad_network_campaign_id` | Filter by ad network campaign ID.<br />**Note**: This is not the campaign ID reported by SKAdNetwork. | No |
| `modeled_conversion_values` | - Only supported from V2<br />- Value can be either `true` or `false`<br />- If `true`, the postback populates the “count” column with modeled conversion value data.  [See available field for modeled data](/docs/skan-aggregated-postback-arrival-date-api#report-structure-and-example)<br />- If `false`, the postback presents the conversion value count and with all available fields as received by listed in the report structure, without modeled data.<br />- Default value is `false`. | No |

### Report structure and example

The API returns a CSV file.

Columns and metrics available are listed in the table that follows.

Examples: [V1](https://docs.google.com/spreadsheets/d/e/2PACX-1vRXgsWlkyvMS20HgZuOQnH1YC8QQcRhOMYIOxyj_fcgikfDfmW6wNAMHO6alPWVA1j_KZwtqowohqrK/pub?gid=0&single=true&output=csv) \| [V2](https://docs.google.com/spreadsheets/d/e/2PACX-1vRMFEELm8JCAQBBAIJqAc1eE5YdN0kOcSVkOPd_Ki2ngnX61wHL4sXypVouOhto8u-JCQmdIYY_5UG6/pub?gid=219191499&single=true&output=csv)

| Column name | Dimension or measure | Available with API V1 token | Available with API V2 token | Available with API V2 token (for SKAN 4) | Available with modeled data only filter |
| --- | --- | --- | --- | --- | --- |
| skad\_postback\_sequence\_index | Group by | N | N | Y | Y |
| skad\_conversion\_value | Group by | Y | Y | Y | Y |
| skad\_coarse\_conversion\_value | Group by | N | N | Y | Y |
| skad\_ad\_network\_id<br />Some SRNs don't share their ID with us. In this case, the field is blank and ad\_network\_name is populated. | Group by | Y | Y | Y | Y |
| ad\_network\_name<br />Currently,  in most cases this field is blank. We do populate it in the case of SRNs who don't share their skad\_ad\_network\_id | Group by | Y | Y | Y | Y |
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

SKAdNetwork aggregate report structure

### Specifications and limitations

| Spec | Remarks |
| --- | --- |
| Data freshness | The report updates [Daily.](/docs/about-data-freshness-and-timezone-support#eod)<br />Data availability is according to the [SKAdNetwork](/docs/about-data-freshness-and-timezone-support#skan) data freshness rate. |
| Date range | - Earliest date supported: November 1, 2020<br />- Maximum query range: 60 days |
| Rate limit | - Queries return up to 200K rows<br />- 60 calls per minute |
| SRNs | Google Ads: The postback arrival date is derived using the last-click time reported by Google. |
| Ad network access | Available to analytics partners if the advertiser grants permission. |
| Agency access | Not available |
| App-specific time zone | UTC only |
| App-specific currency | Always USD |
| Organic data | Not available with this API |
| Non-organic data | Calculated using SKAdNetwork postbacks received by AppsFlyer |
| Historical data | Earliest conversion data (install or retarget) supported: November 1, 2020 |
| Account user access | The authorization token is available to an admin user in the dashboard. |

<Cards>
  <Card title="SKAN aggregated performance report API" href="/docs/skan-aggregated-performance-report-api">
    View the documentation for the SKAN aggregated performance report API.
  </Card>
</Cards>