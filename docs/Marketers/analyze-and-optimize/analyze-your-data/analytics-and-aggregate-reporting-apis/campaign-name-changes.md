---
title: Campaign name changes
metadata:
  keywords:
    - Aggregated Data
    - Agencies
    - Ad Networks
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
    - Agencies
    - Ad Networks
  created_at: '2023-03-26T10:56:19Z'
  edited_at: '2024-04-24T14:48:53Z'
  id: 14038324952465
  locale: en-us
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/14038324952465-Campaign-name-changes
---
> **At a glance:** Change the names of campaigns without creating duplicate data displays.

<div id="campaign-name-changes" />

## Campaign name changes

Changing the names of campaigns affects the display of **aggregate data** in dashboards and reports. AppsFlyer displays campaigns using the campaign ID as the key. If there is more than one name associated with the same campaign ID, the most recently reported name is used to display data.

* Although we refer to **campaign** name changes in this article, the same rules apply to adset and ad name changes.
* The name change affects the display of all data connected to the campaign, including installs, in-app events, cost, and revenue.
* Most ad networks support campaign name changes, but a few don't, and for these you may see duplicate rows with the same data.
* Raw data isn't affected by the name changes.

The following table shows which dashboards and reports support campaign name changes.

| Dashboard/report | Supports campaign name changes |
| --- | --- |
| Overview dashboard | Yes, except for CTV view |
| Activity dashboard | Yes |
| Cohort dashboard | Yes |
| Cohort API | Yes |
| Pull API | Not supported by Pull API V5 and lower |
| Pivot dashboard | No |
| Custom dashboard | No |
| Retention dashboard | No |
| Events dashboard | No |
| Protect360 dashboard | No |
| Cost ETL | Yes |
| SKAN overview dashboard | No |

<div id="example" />

> 📄 **Example**
>
> * On January 1, campaign **example\_a1** began to run.
> * On January 2, the campaign name was changed from **example\_a1** to **example\_a2**.
>
> #### <span id="example-campaign-data"></span>Example campaign data
>
>
>
> | Date | Campaign name | Campaign ID | Installs | Ad spend |
> | --- | --- | --- | --- | --- |
> | January 1 | example\_a1 | 123 | 100 | $100 |
> | January 2 | example\_a2 | 123 | 200 | $200 |
>
>
>
> #### <span id="overview-dashboard-display"></span>Overview dashboard display
>
>
>
> <table><tbody><tr><th><p><span>Campaign</span></p></th><th><p><span>Campaign ID</span></p></th><th><p><span>Installs</span></p></th><th><p><span>Ad spend</span></p></th></tr><tr><td><p><span>example_a2</span></p></td><td><p><span>123</span></p></td><td><p><span>300</span></p></td><td><p><span>$300</span></p></td></tr><tr><td colspan="4"><p>Result: Data displays under the most recent campaign name.</p></td></tr></tbody></table>

<div id="best-practice" />

### Best practice

* Most ad networks support campaign name changes, but a few don't, and for these you may see duplicate rows with the same data. To avoid such display anomalies ensure that campaigns have a unique campaign ID assigned to them.
* Don't use the same campaign name with different campaign IDs.
* Don't use the same ad name with different ad IDs.

<div data-zendesk-anchors="rollout-details=campaign-name-changes h_01HW896QQ2T4J0N5PDY6YFTJ49=campaign-name-changes h_01HW896QQ34YVGF6P212ZHAQHG=example h_01HW896QQ3G07XM06HR2CRXA3G=example-campaign-data overview-dashboard-display-before-the-behavior-change=overview-dashboard-display h_01HW896QQ3J9NE9GZRKKAPX46B=overview-dashboard-display h_01HW896QQ4RAQ51GPD17YYZBJF=best-practice" />
