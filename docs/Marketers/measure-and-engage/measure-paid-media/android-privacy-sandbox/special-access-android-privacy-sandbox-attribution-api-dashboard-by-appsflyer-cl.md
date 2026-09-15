---
title: "[Special access] Android privacy sandbox attribution API dashboard by AppsFlyer (closed beta)"
excerpt: "Learn how to use the AppsFlyer Sandbox attribution dashboard to view campaign performance metrics reported via the Android Privacy Sandbox attribution reporting API."
---
The Sandbox attribution dashboard displays campaign metrics reported via Android Privacy Sandbox attribution reporting API and additional data points during the post-install attribution exclusivity window.

![beta feature.png](https://files.readme.io/be2c471d3fa41ef07daa06c160ace5ec9539d01a6cb715a98ea9eea7c1d42139-27984370150289.png)

## Dashboard principles

The dashboard contains Sandbox campaign performance data and adheres to the following principles:

- Sandbox attribution results can contain "noise". Which is the addition of random data to user-related information to protect individual privacy.
- Metrics are calculated as follows:
  - Non-organic metrics in the dashboard are calculated using Sandbox attribution data received by AppsFlyer.
  - Organic data is not available.
- Agency-driven traffic is treated as coming from a transparent agency.
- Data freshness:
  - Daily
  - Sandbox aggregatable reports received on a given day are processed at the end of the next day—UTC starting at 00:01. The data is available 8 hours later. In other words, it takes around 32-56 hours to process the data, with an average delay of 44 hours.

    > 📘 For example
    >
    > A report received on Monday is processed and ready on Wednesday. The dashboard will be updated by Wednesday 08:00 UTC.

## Dashboard use

### Filter options

| Filter | Remarks |
| --- | --- |
| Date range | - The attributed install date.<br />- The date range is limited to 90 days. |
| Media source | - The ad network attributed to the install.<br />- Agency-driven traffic: The actual media source displays irrespective of the agency transparency status. Consequently, you may see media sources that you aren't familiar with. |
| Campaign | - Campaign name and ID as set by the ad network.<br />- If a given campaign ID has multiple campaign names associated with it, then all names are displayed in the dashboard. **Note:** The ad network provides the campaign ID and name. |
| Adset | Available if the ad network provides this data point. |
| Ad | Available if the ad network provides this data point. |
| Site ID | Available if the ad network provides this data point. |

### Charts

| Chart metric | Remarks |
| --- | --- |
| Installs over time | Elements available: Media source, Campaign, Campaign ID, Ad, Ad ID, Adset, Adset ID, Site ID. |

### Tables

#### About the metrics table

- Use the table to compare the performance of campaigns and media sources.
- Initially, the top 20 media sources display, sorted by the number of installs in descending order.
- To sort the table, click on a column header. Click again to reverse the sort order.

#### Table dimensions

| Dimension | Remarks |
| --- | --- |
| Media source | The ad network attributed to the install, in-app event, or revenue. |
| Campaign | The campaign name attributed to the install, in-app event, or revenue. |
| Campaign ID | The campaign ID attributed to the install, in-app event, or revenue. |
| Ad | The ad attributed to the install, in-app event, or revenue. |
| Ad ID | The ad ID attributed to the install, in-app event, or revenue. |
| Adset | The adset attributed to the install, in-app event, or revenue. |
| Adset ID | The adset ID attributed to the install, in-app event, or revenue. |
| Site ID | The site ID attributed to the install, in-app event, or revenue. |
| Attributed touch type | The engagement type leading to the install. |
| Channel | The channel attributed with the install/in-app event/revenue. |

#### Table metrics

| Metric | Formula/remarks |
| --- | --- |
| Installs | Total number of installs. |
| Click-through installs | Users brought via click-through attribution. |
| View-through installs | Users brought via view-through attribution. |
| Revenue | Up to day 30 revenue post-ad interaction. Requires AppsFlyer [V6.16.0 SDK](/docs/sdk-integration-overview) or above. |
| ARPU | Average revenue per user (Revenue / Installs). |
| Estimated noise range | The range represents the confidence interval applied to the reported results, indicating the expected variability in the value. This interval reflects noise added by Privacy Sandbox to protect user privacy while preserving the overall reliability of the results. |
| Event count | Up to day 30 event count post-ad interaction. Requires AppsFlyer [V6.16.1 SDK](/docs/sdk-integration-overview) or above. |
| Event ratio | Event count / Installs * 100 |

## FAQ

<Accordion title="Why are there differences between the Overview dashboard and the Sandbox attribution dashboard?">

It is not possible to properly compare the Sandbox results to AppsFlyer attribution results for the following reasons:

1. There are fewer ad networks currently integrated with Sandbox attribution compared to AppsFlyer. Therefore, in the case of multi-touch and cross-network attribution flows, the results can differ. For example,

Day 1: User clicks on an ad run by Unity

Day 2: User clicks on an ad run by TikTok

Day 3: User installs App

In the regular AppsFlyer flow, TikTok - being the last touchpoint - will win the attribution. However, with Sandbox, assuming TikTok is still not integrated with Sandbox, Unity Ads will win the attribution.
2. Sandbox attribution results can also contain "noise". Which is the addition of random data to user-related information to protect individual privacy. This technique is used to obscure specific details about user actions, making it more difficult to measure or identify individual users while still allowing for the aggregation and analysis of overall trends and patterns.

</Accordion>

<Accordion title="What revenue metrics are available in the Sandbox attribution dashboard?">

Currently, total revenue derived exclusively from in-app purchases collected via non-S2S events is supported.

</Accordion>

<Accordion title="What in-app event metrics are available in the Sandbox attribution dashboard?">

The Sandbox attribution overview dashboard currently supports predefined in-app events only.

</Accordion>

<Accordion title="How does the customer configure which predefined in-app events they want to measure for their app?">

1. Click the **"Configure In-App Events"** button at the top-right corner of the dashboard.
2. Select up to five predefined events.
3. Click Save.

</Accordion>

### See also

<Cards>
  <Card title="[Closed Beta] Android privacy sandbox - Attribution API" href="/docs/closed-beta-android-privacy-sandbox-attribution-api" icon="fa-solid fa-user-shield">
    Learn more about the Android privacy sandbox Attribution API.
  </Card>
</Cards>