---
title: "Historical aggregate data availability"
excerpt: "A comprehensive reference guide detailing how far back historical data is retained and accessible across different AppsFlyer aggregate dashboards, reports, and APIs."
---
**At a glance:** See what historical data is available via different AppsFlyer aggregate dashboards and reports.

## Historical aggregate data availability

The following table displays how far back historical data is available via different AppsFlyer aggregate dashboards and reports.

As of April 1, 2026, aggregated LTV data (including clicks, impressions, and installs) is retained for 25 months (2 years + 1 month) instead of 5 years. See [Bulletin: Aggregated LTV data availability](/docs/bulletin-aggregated-ltv-data-availability) for details.

| Reporting method | Historical data availability |
| --- | --- |
| Overview dashboard | 25 months (2 years + 1 month) |
| Master API | - LTV data: 25 months (2 years + 1 month)<br />- Cohort data (daily cohort): 2 years<br />- Activity data: 3 years |
| Pull API<br />(aggregate reports) | 25 months (2 years + 1 month) |
| Export data page<br />(aggregate reports) | 25 months (2 years + 1 month) |
| SKAN overview | Earliest conversion data supported: November 1, 2020 |
| SKAN aggregate data APIs | Earliest conversion data supported: November 1, 2020 |
| Protect360 dashboard | Data is available from the start of the Protect360 subscription |
| Activity dashboard | - 3 years<br />- High-level tab: 1 year |
| Events | 25 months (2 years + 1 month) |
| Retention | 2 years |
| Cohort dashboard | - Daily cohort: 2 years<br />- Weekly/monthly cohorts: 3 years |
| Cohort API | Daily cohort: 2 years |
| Cohort Data Locker | Not relevant\* |
| Custom dashboard | 25 months (2 years + 1 month) |
| Pivot reports | - LTV data: 25 months (2 years + 1 month)<br />- Activity data: 3 years |
| Cost ETL | Not relevant\*\* |

\* Data Locker reports are sent daily with conversions, sessions, and events generated from users converted over the past year (3 years in beta).  
\*\* Cost ETL reports are sent multiple times per day. They provide cost data for the current day and the previous 6 days (referred to as 7 days in this article), as well as days 14, 29, and 88. The retroactive data allows for updates and corrections in the cost data reporting.