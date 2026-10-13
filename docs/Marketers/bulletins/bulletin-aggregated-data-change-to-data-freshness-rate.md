---
title: "Bulletin: Aggregated data change to data freshness rate"
excerpt: "An overview of the changes to the data freshness rates of installs and in-app event data in AppsFlyer analytics reports and dashboards."
table_of_contents: false
x-zendesk:
  id: 4404329828497
  url: https://support.appsflyer.com/hc/en-us/articles/4404329828497-Bulletin-Aggregated-data-change-to-data-freshness-rate
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Bulletins
  section_id: 6551161473041
  position: 53
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-nohar-avigal, Marketers, Marketing Analytics, Ad Networks]
  labels: [Advertisers, Ad Networks, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2021-07-20T11:47:58Z'
  edited_at: '2023-10-26T16:50:27Z'
---
<table><tbody><tr><td>Headline</td><td>Data freshness rate of installs and in-app events in analytics reports and dashboards</td></tr><tr><td><span>Bulletin date</span></td><td>August 24, 2021</td></tr><tr><td><p>What's changing</p></td><td><p>The data freshness rates of installs and in-app event data is changing. The table details the freshness before and after the change. </p><h4>Data freshness rate per event type</h4><table><tbody><tr><th>Event type</th><th>Before the change (minutes)</th><th><p>After the change</p><p>(minutes)</p></th></tr><tr><td>Install, re-attribution, re-engagement</td><td>3-5 </td><td>15-30 </td></tr><tr><td>In-app event</td><td>90 </td><td>30-60</td></tr></tbody></table></td></tr><tr><td>Where is it changing</td><td><p>The data freshness change affects the dashboards and reporting tools listed. The change takes place in phases as follows:</p><p><strong>Phase 1—s<span>tarting September 12, 2021 (subject to change)</span></strong><span></span></p><ul><li>Dashboards:<ul><li>Overview</li><li>Overview V2</li><li>Retargeting </li><li>Events</li><li>Custom </li></ul></li><li>Aggregated reports via Pull API</li></ul><p><strong>Phase 2—starting <span>October 6, 2021 (planned) </span></strong></p><ul><li>Dashboards:<ul><li>Activity</li><li>Cohort </li></ul></li><li>API: Cohort</li></ul></td></tr><tr><td>What's not changing</td><td>Master API and raw data </td></tr><tr><td>Action required</td><td><ul><li>When viewing or downloading data, consider the changed data freshness.</li><li>If you use the Overview dashboard to test SDK integration or integration with an ad network partner, install events will take longer to display. Consider using raw data reports to verify your integration tests. </li></ul></td></tr></tbody></table>


> 📘 **See also**
>
> * [AppsFlyer data freshness](/docs/about-data-freshness-and-timezone-support)
> * What's new in AppsFlyer