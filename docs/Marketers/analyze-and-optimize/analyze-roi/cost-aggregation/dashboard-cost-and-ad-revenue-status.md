---
title: Dashboard - Cost and ad Revenue Status
metadata:
  keywords:
    - ad revenue
    - cost
    - Advertisers
    - Agencies
    - Xpend
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - Agencies
    - ROI360
  created_at: '2020-12-23T12:52:57Z'
  edited_at: '2026-08-13T16:29:42Z'
  id: 360016789458
  locale: en-us
  section: Cost aggregation
  section_id: 6551029483281
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360016789458-Dashboard-Cost-and-ad-Revenue-Status
---
> **At a glance:** Advertisers and agencies can check the status of cost and ad revenue integrations.

<div id="cost-and-ad-revenue-integration-status" />

## Cost and Ad Revenue integration status

* The dashboard displays the current operational status of your cost/ad revenue integrations.
  * Advertisers see statuses for all apps, media sources, and agencies in their account.
  * Agencies see statuses for all apps and media sources that they work with.
* Ad Revenue integrations are listed by the ad revenue media source; not by the user-acquisition media source.
* For integrations that require corrective actions, the action required displays.
* To view cost and ad revenue status, in AppsFlyer, from the side menu, select **Settings** > **Cost & Ad Revenue Status**.
* The image and table that follow breaks down the dashboard components.

<div id="cost--ad-revenue-status-dashboard" />

#### Cost & Ad Revenue Status dashboard

[![cost_and_ad_revenue_status_dashboard.jpg](https://files.readme.io/da713daae6c7044e8e4f32274520961e1b43c183d8e4cb95f58854cb614efb39-360016000898.jpg)](https://files.readme.io/da713daae6c7044e8e4f32274520961e1b43c183d8e4cb95f58854cb614efb39-360016000898.jpg)

| Section | Description |
| --- | --- |
| <span id="a-filters"></span>A. Filters | <ul><li>App</li><li>Agencies</li><li>Media source</li><li>Status</li><li>Integration type (cost or ad revenue)</li><li>Problem</li></ul> |
| <span id="b-headline-metrics"></span>B. Headline metrics | <ul><li>**Total integrations**: Number of apps/partners for which integration is enabled, irrespective of the status. For example, if you have an Android and iOS app, both integrated with Meta ads, the total integrations is two.</li><li>**Action required**: Number of apps and media sources in your account with API issues that need updating.</li><li>**Warning**: Number of integrations for which there is no data or that are experiencing a temporary network error.</li><li>**Waiting for sync**: Number of integrations that are connected but waiting for data to be pulled. It can take up to 24 hours to see the data in AppsFlyer.</li><li>**Active**: Number of partners with the cost/ad revenue APIs synced and operational.</li></ul> |
| <span id="c-status"></span>C. Status | Each status has a separate table in the dashboard with all integrations that apply. For status definitions, see headline metrics above.<ul><li>**Action required**</li><li>**Warning**</li><li>**Waiting for sync**</li><li>**Active**</li></ul> |
| <span id="d-columns"></span>D. Columns | Each status section contains several columns:<ul><li>Media source</li><li>App: App with cost or ad revenue data API integration.</li><li>Last sync: The most recent time that data was received.</li><li>Integration type:<ul><li>Cost</li><li>Ad revenue (attr.): Meaning ad revenue is attributed to the user acquisition media source</li><li>Ad revenue (aggr.): Meaning ad revenue is aggregated based on the monetization source (the media source that displayed the ad)</li></ul></li><li>Campaign cost/revenue (based on API): Campaign cost or ad revenue for the app per media source for the last 7 days.</li><li>Problem: See list that below.</li><li>Action: Action required to enable data, if the API integration has an issue. Clicking **Reconnect** leads to the required action.</li></ul> |
| <span id="e-problem"></span>E. Problem | <ul><li>**Invalid credentials**: AppsFlyer can't get data via the API because the credentials are not valid. Reconnect using the correct credentials.</li><li>**Waiting for first sync**: Waiting for initial data pull from partner. Check back again in several hours.</li><li>**Not enabled**: Advertiser or agency received traffic and more than 20 installs from this partner in the last 28 days, but cost integration is not enabled. Enable the cost integration.</li><li>**No data**: Active integration, but the partner is not returning data.<ul><li>To receive a notification when the problem occurs enable the Ad Revenue data failure email alert.</li></ul></li><li>**Not available**: Active integration but there's no cost data for the past 30 days from the partner due to no active campaigns.</li><li>**Network problem**: There's a temporary problem with this partner. Check back again in several hours.</li><li>**General error**: There's a temporary problem with this partner. Contact support.</li><li>**Old API version**: Review integration and update API credentials.</li><li>**Invalid configuration**: Configured event name not found for revenue attribution. Review configuration and update Event Source name.</li><li>**Disabled integration**: Reconnect your integration.</li><li>**Restricted by partner**: Your account is not enabled on the partner's system to get cost. Contact the partner.</li><li>**Suspended integration**: Partner integration had a Warning status for 30 consecutive days. Reconnect with the partner.<ul><li>To receive a notification when the problem occurs enable the Ad Revenue suspended integration email alert.</li><li>**Note**: After 180 days, partners with a suspended integration don't display in the Status dashboard.</li></ul></li><li>**API/attribution mismatch**: Partner API is not returning matching cost data. This happens because:<ul><li>You integrated a different partner ad account when logging into the partner via AppsFlyer (for example, a different Meta ads account). Check you connected the right partner ad account.</li><li>One of the credential fields in the partner cost integration is incorrect. For example, the bundle ID. Review and correct the integration credentials.</li></ul></li><li>**Setup error**: Partner API is not returning data. This happens because:<ul><li>Your campaigns are paused and there is no data.</li><li>You integrated a different partner ad account when logging into the partner via AppsFlyer (for example, a different Meta ads account). Check you connected the right partner ad account.</li><li>One of the credential fields in the partner cost integration is incorrect. For example, bundle ID. Review and correct the integration credentials.</li></ul></li></ul> |

<div data-zendesk-anchors="h_01HKW10FWXCZ1QFFJA1FTYH50F=cost-and-ad-revenue-integration-status cost-ad-revenue-status-dashboard=cost--ad-revenue-status-dashboard h_01HKW10FWXGWHSQKFTHRDHGWSP=cost--ad-revenue-status-dashboard" />
