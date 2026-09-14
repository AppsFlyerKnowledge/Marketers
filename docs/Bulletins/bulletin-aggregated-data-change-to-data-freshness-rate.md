---
title: "Bulletin: Aggregated data change to data freshness rate"
excerpt: "An overview of the changes to the data freshness rates of installs and in-app event data in AppsFlyer analytics reports and dashboards."
---
| Headline | Data freshness rate of installs and in-app events in analytics reports and dashboards |
| Bulletin date | August 24, 2021 |
| What's changing | The data freshness rates of installs and in-app event data is changing. The table details the freshness before and after the change.

#### Data freshness rate per event type

| Event type | Before the change (minutes) | After the change<br>(minutes) |
| --- | --- | --- |
| Install, re-attribution, re-engagement | 3-5 | 15-30 |
| In-app event | 90 | 30-60 | |
| Where is it changing | The data freshness change affects the dashboards and reporting tools listed. The change takes place in phases as follows:<br>**Phase 1—starting September 12, 2021 (subject to change)**<br>- Dashboards:<br>  - Overview<br>  - Overview V2<br>  - Retargeting <br>  - Events<br>  - Custom<br>- Aggregated reports via Pull API<br>**Phase 2—starting October 6, 2021 (planned)**<br>- Dashboards:<br>  - Activity<br>  - Cohort<br>- API: Cohort |
| What's not changing | Master API and raw data |
| Action required | - When viewing or downloading data, consider the changed data freshness.<br>- If you use the Overview dashboard to test SDK integration or integration with an ad network partner, install events will take longer to display. Consider using raw data reports to verify your integration tests. |

<Cards>
  <Card title="AppsFlyer data freshness" href="https://support.appsflyer.com/hc/articles/360000310629">
    Learn more about how data freshness works in AppsFlyer.
  </Card>
  <Card title="What's new in AppsFlyer" href="https://support.appsflyer.com/hc/articles/360003083598">
    Stay up to date with the latest product updates and announcements.
  </Card>
</Cards>