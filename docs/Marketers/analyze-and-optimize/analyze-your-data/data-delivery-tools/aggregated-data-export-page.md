---
title: "Aggregated data export page"
excerpt: "Download lifetime value (LTV) aggregate reports filtered by attribution date and media source."
---
## Aggregate data reports

[User acquisition](/docs/aggregated-and-analytics-reporting-overview#ua-ltv-aggregate-data-reports-containing-nonorganic-and-organic-users) and [retargeting](/docs/aggregated-and-analytics-reporting-overview#retargeting) reports have these characteristics:

- Contain LTV data of users performing an Attribution Event during the specified date range.
- An Attribution Event is any of the following:
  - Install
  - Re-engagement
  - Re-attribution (retargeting reinstall)
- LTV data means as follows:
  - Install and Re-attribution: Events performed by a user starting with the Attribution Event until the present
  - Re-engagements: Events performed by the user starting during the re-engagement window
- Reports, depending on size, can take several minutes to download.
- Reports hold up to 200K rows.
- [Rate limitations](/docs/report-generation-quotas-rate-limitations)

### Download aggregate data reports

**To download a report:**

1. In AppsFlyer, go to **Reports** > **Aggregated Data Export.**
2. [Optional] Select a media source.
3. Select the Attribution Event date range.
4. Select a report, click **Download.**

<Cards>
  <Card title="Aggregated and analytics reporting overview" href="/docs/aggregated-and-analytics-reporting-overview" icon="fa-solid fa-chart-column">
    Learn more about aggregated and analytics reporting in AppsFlyer.
  </Card>
</Cards>