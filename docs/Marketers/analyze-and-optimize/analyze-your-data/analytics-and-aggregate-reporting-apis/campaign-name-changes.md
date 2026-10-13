---
title: "Campaign name changes"
excerpt: "Change the names of campaigns without creating duplicate data displays."
x-zendesk:
  id: 14038324952465
  url: https://support.appsflyer.com/hc/en-us/articles/14038324952465-Campaign-name-changes
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  position: 4
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-nohar-avigal, Marketers, Marketing Analytics, Agencies, Ad Networks]
  labels: [Aggregated Data, Agencies, Ad Networks, Marketers, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2023-03-26T10:56:19Z'
  edited_at: '2024-04-24T14:48:53Z'
---
## Campaign name changes

Changing the names of campaigns affects the display of **aggregate data** in dashboards and reports. AppsFlyer displays campaigns using the campaign ID as the key. If there is more than one name associated with the same campaign ID, the most recently reported name is used to display data.

> 📘 Note
>
> * Although we refer to **campaign** name changes in this article, the same rules apply to adset and ad name changes.
> * The name change affects the display of all data connected to the campaign, including installs, in-app events, cost, and revenue.
> * Most ad networks support campaign name changes, but a few don't, and for these you may see duplicate rows with the same data.
> * Raw data isn't affected by the name changes.

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

#### Example

- On January 1, campaign **example\_a1** began to run.
- On January 2, the campaign name was changed from **example\_a1** to **example\_a2**.

#### Example campaign data

| Date | Campaign name | Campaign ID | Installs | Ad spend |
| --- | --- | --- | --- | --- |
| January 1 | example\_a1 | 123 | 100 | $100 |
| January 2 | example\_a2 | 123 | 200 | $200 |

#### Overview dashboard display

| Campaign | Campaign ID | Installs | Ad spend |
| --- | --- | --- | --- |
| example\_a2 | 123 | 300 | $300 |
| Result: Data displays under the most recent campaign name. | | | |

### Best practice

- Most ad networks support campaign name changes, but a few don't, and for these you may see duplicate rows with the same data. To avoid such display anomalies ensure that campaigns have a unique campaign ID assigned to them.
- Don't use the same campaign name with different campaign IDs.
- Don't use the same ad name with different ad IDs.