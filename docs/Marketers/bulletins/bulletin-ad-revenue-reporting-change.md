---
title: "Bulletin: Ad revenue reporting change"
excerpt: "This bulletin outlines the change in AppsFlyer's ad revenue reporting, aligning data to the actual day of the ad display event instead of the day after."
x-zendesk:
  id: 360007980057
  url: https://support.appsflyer.com/hc/en-us/articles/360007980057-Bulletin-Ad-revenue-reporting-change
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Bulletins
  section_id: 6551161473041
  position: 62
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-michael-talapov, Marketers, Agencies, ROI360]
  labels: [ad revenue, Agencies, data freshness, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2020-05-05T15:30:21Z'
  edited_at: '2023-02-15T13:15:06Z'
---
* **What's changing**: The date of Ad revenue data (user-level and aggregate-level) in the platform is the day of the ad display event itself (the day the ad revenue occurs), instead of the day after. Meaning if an ad displays on Monday, the revenue displays under Monday. This gives advertisers a more accurate and actionable understanding of their ad revenue data.
* **Who is impacted**: App owners, agencies
* **Where is it changing**: Essentially, data alignment to the day of the ad display event is active in all reports and APIs, for all types of network integrations.See the following table for where and when the alignment took effect.

#### Ad revenue reporting change



| Reporting method | Effective date (date change occurs) | Publication date (date of announcement) |
| --- | --- | --- |
| Cohort reports | May 13, 2020 | May 7, 2020 |
| Raw data reports | June 17, 2020 | June 14, 2020 |
| Pull API (for raw data) | June 17, 2020 | June 14, 2020 |
| Activity dashboard | June 17, 2020 | June 14, 2020 |
| Data Locker (h=23 folder) | August 3, 2020 | August 3, 2020 |
| Pull API (for aggregate data) | September 1, 2020 | August 31, 2020 |



### Before the change

The date of Ad revenue data in the platform is the day after the ad display event itself. Meaning if an ad displays on Monday, the revenue displays under Tuesday. The data is available in the platform on Wednesday, after processing.

This means that the ad revenue date is not aligned with actual user engagement. For some verticals, this lack of alignment distorts KPIs significantly.

### After the change

The change is dependent on the integration type between the app and the monetization network as follows:

* This change affects user-level and aggregate-level ad revenue available via the reporting methods outlined in the table prior.
* The date of ad revenue data in the platform is the day of the ad display event itself. Meaning if an ad displays on Monday, the revenue displays under Monday. The data is available in reports from Wednesday after processing.
* There is no change to historical data recorded before the effective date.
* The revenue on the effective date includes two days' revenue, meaning the revenue of the effective date and the previous day’s revenue. Depending on the reporting scenario, you may discern a revenue spike on this day.

See the example that follows.

> 📘 **Example**
>
> * Ads display and ad revenue occurs on Day 0 (the day of user acquisition).
> * Ad revenue data is pulled on Day 1.
> * Ad revenue data is processed and available in the AppsFlyer platform on Day 2.
> * Ad revenue data is reported under Day 0.
>   * In the Activity dashboard, Data Locker (h=23 folder), and raw data reports, the ad display time is also available.
>
> [![](https://files.readme.io/b22207f1e7009f3f8f1172fbb8bf9147c1251e7d1f51864b777cbf4eab4b84e4-360010993537.jpg)](https://files.readme.io/b22207f1e7009f3f8f1172fbb8bf9147c1251e7d1f51864b777cbf4eab4b84e4-360010993537.jpg)