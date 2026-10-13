---
title: "Dashboard - Cost and ad Revenue Status"
excerpt: "Check the operational status of your cost and ad revenue integrations, view headline metrics, and troubleshoot API issues."
x-zendesk:
  id: 360016789458
  url: https://support.appsflyer.com/hc/en-us/articles/360016789458-Dashboard-Cost-and-ad-Revenue-Status
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Cost aggregation
  section_id: 6551029483281
  position: 6
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-michael-talapov, Marketers, Agencies, ROI360]
  labels: [ad revenue, cost, Advertisers, Agencies, Xpend, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2020-12-23T12:52:57Z'
  edited_at: '2026-08-13T16:29:42Z'
---
Advertisers and agencies can check the status of cost and ad revenue integrations.

## Cost and Ad Revenue integration status

- The dashboard displays the current operational status of your cost/ad revenue integrations.
  - Advertisers see statuses for all apps, media sources, and agencies in their account.
  - Agencies see statuses for all apps and media sources that they work with.
- Ad Revenue integrations are listed by the ad revenue media source; not by the user-acquisition media source.
- For integrations that require corrective actions, the action required displays.
- To view cost and ad revenue status, in AppsFlyer, from the side menu, select **Settings** > **Cost & Ad Revenue Status**.
- The image and table that follow breaks down the dashboard components.

#### Cost & Ad Revenue Status dashboard

![cost_and_ad_revenue_status_dashboard.jpg](https://files.readme.io/da713daae6c7044e8e4f32274520961e1b43c183d8e4cb95f58854cb614efb39-360016000898.jpg)

| Section | Description |
| --- | --- |
| A. Filters | - App<br />- Agencies<br />- Media source<br />- Status<br />- Integration type (cost or ad revenue)<br />- Problem |
| B. Headline metrics | - **Total integrations**: Number of apps/partners for which integration is enabled, irrespective of the status. For example, if you have an Android and iOS app, both integrated with Meta ads, the total integrations is two.<br />- **Action required**: Number of apps and media sources in your account with API issues that need updating. <br />- **Warning**: Number of integrations for which there is no data or that are experiencing a temporary network error.<br />- **Waiting for sync**: Number of integrations that are connected but waiting for data to be pulled. It can take up to 24 hours to see the data in AppsFlyer.<br />- **Active**: Number of partners with the cost/ad revenue APIs synced and operational. |
| C. Status | Each status has a separate table in the dashboard with all integrations that apply. For status definitions, see headline metrics above. <br />- **Action required**<br />- **Warning**<br />- **Waiting for sync**<br />- **Active** |
| D. Columns | Each status section contains several columns:<br />- Media source<br />- App: App with cost or ad revenue data API integration.<br />- Last sync: The most recent time that data was received.<br />- Integration type:<br />  - Cost<br />  - Ad revenue (attr.): Meaning ad revenue is attributed to the user acquisition media source<br />  - Ad revenue (aggr.): Meaning ad revenue is aggregated based on the monetization source (the media source that displayed the ad)<br />- Campaign cost/revenue (based on API): Campaign cost or ad revenue for the app per media source for the last 7 days.<br />- Problem: See list that below.<br />- Action: Action required to enable data, if the API integration has an issue. Clicking **Reconnect** leads to the required action. |
| E. Problem | - **Invalid credentials**: AppsFlyer can't get data via the API because the credentials are not valid. Reconnect using the correct credentials.<br />- **Waiting for first sync**: Waiting for initial data pull from partner. Check back again in several hours.<br />- **Not enabled**: Advertiser or agency received traffic and more than 20 installs from this partner in the last 28 days, but cost integration is not enabled. Enable the cost integration.<br />- **No data**: Active integration, but the partner is not returning data.   - To receive a notification when the problem occurs enable the Ad Revenue data failure email alert.<br />- **Not available**: Active integration but there's no cost data for the past 30 days from the partner due to no active campaigns. <br />- **Network problem**: There's a temporary problem with this partner. Check back again in several hours.<br />- **General error**: There's a temporary problem with this partner. Contact support.<br />- **Old API version**: Review integration and update API credentials.<br />- **Invalid configuration**: Configured event name not found for revenue attribution. Review configuration and update Event Source name.<br />- **Disabled integration**: Reconnect your integration.<br />- **Restricted by partner**: Your account is not enabled on the partner's system to get cost. Contact the partner.<br />- **Suspended integration**: Partner integration had a Warning status for 30 consecutive days. Reconnect with the partner.   - To receive a notification when the problem occurs enable the Ad Revenue suspended integration email alert.<br />  - **Note**: After 180 days, partners with a suspended integration don't display in the Status dashboard.<br />- **API/attribution mismatch**: Partner API is not returning matching cost data. This happens because:  - You integrated a different partner ad account when logging into the partner via AppsFlyer (for example, a different Meta ads account). Check you connected the right partner ad account.<br />  - One of the credential fields in the partner cost integration is incorrect. For example, the bundle ID. Review and correct the integration credentials.<br />- **Setup error**: Partner API is not returning data. This happens because:  - Your campaigns are paused and there is no data.<br />  - You integrated a different partner ad account when logging into the partner via AppsFlyer (for example, a different Meta ads account). Check you connected the right partner ad account.<br />  - One of the credential fields in the partner cost integration is incorrect. For example, bundle ID. Review and correct the integration credentials. |