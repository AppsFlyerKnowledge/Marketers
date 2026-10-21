---
title: Historical aggregate data availability
metadata:
  keywords:
    - Aggregated Data
    - Advertisers
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2023-05-24T08:38:43Z'
  edited_at: '2026-10-14T09:43:06Z'
  id: 15557418667537
  locale: en-us
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/15557418667537-Historical-aggregate-data-availability
---
**At a glance:** See what historical data is available via different AppsFlyer aggregate dashboards and reports.

## Historical aggregate data availability

The following table displays how far back historical data is available via different AppsFlyer aggregate dashboards and reports.

As of April 1, 2026, aggregated LTV data (including clicks, impressions, and installs) is retained for 25 months (2 years + 1 month) instead of 5 years. See <Anchor target="_blank" href="/marketers/docs/bulletin-aggregated-ltv-data-availability">Bulletin: Aggregated LTV data availability</Anchor> for details.

<table><thead><tr><th>Reporting method</th><th>Historical data availability</th></tr></thead><tbody><tr><td>Overview dashboard</td><td>25 months (2 years + 1 month)</td></tr><tr><td>Master API</td><td><ul><li>LTV data: 25 months (2 years + 1 month)</li><li>Cohort data (daily cohort): 2 years</li><li>Activity data: 3 years</li></ul></td></tr><tr><td><p>Pull API</p><p>(aggregate reports)</p></td><td>25 months (2 years + 1 month)</td></tr><tr><td><p>Export data page</p><p>(aggregate reports)</p></td><td>25 months (2 years + 1 month)</td></tr><tr><td>SKAN overview</td><td>Earliest conversion data supported: November 1, 2020</td></tr><tr><td>SKAN aggregate data APIs</td><td>Earliest conversion data supported: November 1, 2020</td></tr><tr><td>Protect360 dashboard</td><td>Data is available from the start of the Protect360 subscription</td></tr><tr><td>Activity dashboard</td><td><ul><li>3 years</li><li>High-level tab: 1 year</li></ul></td></tr><tr><td>Events</td><td>25 months (2 years + 1 month)</td></tr><tr><td>Retention</td><td>2 years</td></tr><tr><td>Cohort dashboard</td><td><ul><li>Daily cohort: 2 years</li><li>Weekly/monthly cohorts: 3 years</li></ul></td></tr><tr><td>Cohort API</td><td>Daily cohort: 2 years</td></tr><tr><td>Cohort Data Locker</td><td>Not relevant\*</td></tr><tr><td>Custom dashboard</td><td>25 months (2 years + 1 month)</td></tr><tr><td>Pivot reports</td><td><ul><li>LTV data: 25 months (2 years + 1 month)</li><li>Activity data: 3 years</li></ul></td></tr><tr><td>Cost ETL</td><td>Not relevant\*\*</td></tr><tr><td colspan="2"><p>\* Data Locker reports are sent daily with conversions, sessions, and events generated from users converted over the past year (3 years in beta).</p><p>\*\* Cost ETL reports are sent multiple times per day. They provide cost data for the current day and the previous 6 days (referred to as 7 days in this article), as well as days 14, 29, and 88. The retroactive data allows for updates and corrections in the cost data reporting.</p></td></tr></tbody></table>

<div data-zendesk-anchors="h_01KYPDRP64DHB3RN8E51NTGPFE=historical-aggregate-data-availability" />
