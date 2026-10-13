---
title: "[Closed beta] Sandbox Data Locker report for ad networks"
x-zendesk:
  id: 28637170445073
  url: https://support.appsflyer.com/hc/en-us/articles/28637170445073--Closed-beta-Sandbox-Data-Locker-report-for-ad-networks
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Android privacy sandbox
  section_id: 25467093087761
  position: 3
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-rona-einat, Marketers, Data Locker]
  labels: [Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2024-09-24T14:41:32Z'
  edited_at: '2024-12-12T12:34:53Z'
---
At a glance: Sandbox raw data reports contain aggregated data generated after translating and decoding reports received by AppsFlyer from Android Privacy Sandbox Attribution API. Data is available via [Data Locker](/docs/data-locker-partners).

## Sandbox raw data reports for ad networks

Principles:

- **Data is provided by:**  - [**Data Locker**](/docs/data-locker-for-partners)    - If you aren't currently using Data Locker, an admin user must configure Data Locker and enable the sandbox reports. To do so, go to **Reports** \> **Data Locker**. Select the Sandbox attribution reports.
    - **Data freshness rate**: Data is contained in the h=23 folder of the date the aggregated report is received by AppsFlyer. Example: If the report was received on Monday, it is processed after the end of the next day. Processing is completed by 10:00 AM UTC Wednesday, and the data is written to the Monday h=23 folder.
    - **Timezone**: UTC
    - **Metrics**: Metrics are incremental. As an example, on DT = 20-06-2024 we received 10 installs for install date = 18-06-2024 and a few days later we received another 5 installs for the same install date (18-06-2024) then the event count column will mention 5 additional installs.
    - **Permissions**: The report is only available to ad networks. Ad networks will be able to access specific app data only if the app owner has given permission to [get app data](/docs/aggregated-campaign-performance-report-for-ad-networks#permission-to-get-aggregated-performance-data).

## Sandbox raw data report format and content

### Raw data report types

| Report type | Topic Name | Report name | Description |
| --- | --- | --- | --- |
| Decoded aggregated report | sandbox\_attribution\_ad\_network\_performance | Sandbox attribution ad network aggregated performance |  |

### Raw data field format types

#### Field formats

| Format name | Description |
| --- | --- |
| String [n] | The maximum length of the string. We don't usually enforce field length limitations on receipt of the data, but data may be truncated thereafter. |
| Time string | String having the format, `yyyy-mm-dd hh:mm:ss`. For example, `2019-09-17 00:09:25` |
| Enum [n] | Enum fields can only contain specific values. For example, Cost currency has 3 characters and can contain only currency codes as specified. |
| Timestamp | 10-digit UNIX timestamp. Example:<br />August 4, 2020, 07:25 UTC translates to `"timestamp": "1596525944"` |
| Boolean | The value of the field can be either `TRUE` or `FALSE` |
| Integer | Integer |
| Float | Real floating number that can have a decimal point and values after the decimal point. |

### Report structure

| Field name | Description | Format | Dimension or metric |
| --- | --- | --- | --- |
| app\_id | The app ID (advertiser app) | String | Dimension |
| Install date | Install date | String | Dimension |
| af\_ad | Ad name | String | Dimension |
| af\_adset\_id |  | String | Dimension |
| af\_adset |  | String | Dimension |
| af\_ad\_id | Ad ID | String | Dimension |
| af\_ad | Ad name | String | Dimension |
| attributed\_touch\_type | click, impression | String | Dimension |
| engagement\_type | click\_to\_app, view, engaged\_view, engaged\_click, null | String | Dimension |
| af\_c\_id | campaign ID | String | Dimension |
| campaign | campaign name | String | Dimension |
| af\_channel |  | String | Dimension |
| media\_source | Attributed media source received from the Sandbox API | String | Dimension |
| sandbox\_resolution | Dimensions that are available for that resolution | String | Dimension |
| event\_name |  | String | Dimension |
| conversion\_type | install, re\_attribution, re\_engagement, re\_download | String | Dimension |
| event\_count | count of the total aggregated results | Long | Metric |
| revenue\_usd |  | Decimal | Metric |

## Additional information

### Traits and limitations

| Trait | Remarks |
| --- | --- |
| Ad network access | Only available for ad networks |
| Timezone | UTC |
| Currency | USD |
| Organic data | Not available |
| Non-organic data | Based on Sandbox attribution |
| Data freshness | [Daily](/docs/closed-beta-sandbox-data-locker-report-for-ad-networks#skan-raw-data-reports) |