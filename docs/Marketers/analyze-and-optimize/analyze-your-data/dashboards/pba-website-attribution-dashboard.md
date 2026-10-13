---
title: "PBA Website Attribution dashboard"
excerpt: "Measure the impact of marketing efforts to drive effective website traffic. Which media sources, types, and channels are responsible for visits, conversion events and ad-level metrics are available."
x-zendesk:
  id: 360000654377
  url: https://support.appsflyer.com/hc/en-us/articles/360000654377-PBA-Website-Attribution-dashboard
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Dashboards
  section_id: 6550925337873
  position: 16
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-gil-or, Marketers, Cross-Platform Measurement]
  labels: [Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2018-12-09T07:49:24Z'
  edited_at: '2024-04-15T18:13:50Z'
---
![Website_Attribution.jpg](https://files.readme.io/59cda285cb1f2b88c6992f3d303ee87e33176f82f0cf7afedb4711ee363e3a73-360015253418.jpg)

## PBA Website Attribution

Using the Website Attribution dashboard advertisers gain an insight as to the media sources driving visitors and conversions.

- Use the trend chart to view the overall trend and contribution breakdown by media source and media channel.
- Get granular details down to the ad/adset level, and view performance metrics for every conversion event.

**Marketers use the dashboard to answer questions like:**

|     |     |
| --- | --- |
| ![icon2.png](https://files.readme.io/77fda01229f4b1b50755bc94f35cc021928ba7af1e3b5b45e61606ab18e8fd7a-360013383917.png) | **Performance**<br />What media sources and campaigns drive the most visits, conversions, and value on my website? |
| ![Icon1.png](https://files.readme.io/b20da70a56d881dd2fe31b18df8919db43b47e3e2338b89da7ef5ef6467590d6-360013383937.png) | **Effectiveness**<br />Which acquisition channels deliver the best performance KPIs—such as conversion rate or ARPU? |
| ![s4.png](https://files.readme.io/9a426232668022a9b4d006e685d2384d61efe4814c377aa9295e9b7887f14fef-360013383957.png) | **Comparative analysis**<br />How do my paid campaigns compare to my owned channels and earned traffic? On which device types and platforms do my web users convert? |

## Dashboard reference

**To go to PBA dashboards do one of the following:**

- In AppsFlyer, from the side menu, **Analyze** > **People-Based Attribution.**
- In AppsFlyer, from the top menu, select **My Apps** > **View brand bundles**. Click **PBA dashboards.** Go to **Website Attribution** tab.

| Component | Description |
| --- | --- |
| Date picker and filters | ![WebsiteAttributionFilterPaner_us-en.jpg](https://files.readme.io/1d4cb6145bd0a297d9d358b904968cdffadc4235499ba661048983de8dbc348c-360013057737.jpg)<br />- Select the attribution date range, [filter, and grouping options](/docs/using-pba-dashboards).<br />- **Filter by**: Media source, media type, media channel, geo, conversion event<br />- **Group by:** Media source/campaign, media type, media channel, device type, platform. |
| Chart | **Website activity over time**<br />![WebsiteAttribution_us-en__1_.jpg](https://files.readme.io/cfa214a82b39db1fdbed128029dd28fdf4b623f2c0c7d7f51e067d5e182431ca-360013057717.jpg)<br />- Display the sources of visits and conversions for a given period.<br />- View by options: Media channel, media source |
| Table | **Attribution table**<br /><br />![WebsiteAttributionTable_us-en.jpg](https://files.readme.io/46f03ee216dc23f3f184663aeef7d6b64ae6fb9a64e7a161ff0482e4d2eab204-360013057757.jpg)<br /><br />- Metrics are available for the website as a whole with a breakdown per conversion event.<br />- Drill down from the media source to the ad level to uncover specific media sources and ads driving traffic to the website.<br />- Compare ad performance in driving traffic and generating conversions. |

| Total metrics | Description |
| --- | --- |
| Visits | Sessions of users visiting the website |
| Unique visitors | Unique visitors to the site. Unique users are determined by PBA by using the PBA private-user graph. To maintain graph integrity you must implement [CUID](/docs/pba-web-sdk-integration-guide#identifying-users-using-customer-user-id-cuid). The same user arriving at the site using different browsers is counted once. |
| Conversions | Number of conversion events performed |
| Conversion rate | Formula: Conversions / Visits \* 100 |
| ACPU | The average number of Conversions per Unique visitor. Formula: Conversions / Unique visitors |
| Revenue | Revenue from all events combined |
| ARPU | Average Revenue per User. Formula: Revenue / Unique users |

| Conversion event metrics | Description |
| --- | --- |
| Event count | Number of times the event was performed |
| Unique users | Unique users performing the conversion event |
| Revenue | Revenue associated with this conversion event |
| ARPE | Average Revenue per Conversion Event. Formula: Revenue / Event count |
| Export CSV | Click **Export CSV,** to export the table. |