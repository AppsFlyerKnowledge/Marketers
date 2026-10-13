---
title: "Vidaa integration with AppsFlyer"
excerpt: "Integrate your Vidaa Connected TV (CTV) app with AppsFlyer to receive attribution and event data for your campaigns on Vidaa."
x-zendesk:
  id: 10400222972433
  url: https://support.appsflyer.com/hc/en-us/articles/10400222972433-Vidaa-integration-with-AppsFlyer
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Promoting CTV apps
  section_id: 15328952633489
  position: 8
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-roi-tamir, Marketers, CTV Attribution]
  labels: [CTV, Marketers, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2022-11-06T08:13:09Z'
  edited_at: '2025-10-30T13:20:27Z'
---
## About Vidaa CTV attribution

The Vidaa OS for streaming runs across all Vidaa TVs.

CTV apps streaming on Vidaa can integrate with AppsFlyer via API to receive attribution data and performance measurements about which sources (organic) and campaigns drive app open and in-app events. Marketers rely on these insights to measure and optimize marketing activities.

The Vidaa API integration supports:

- Vidaa Smart TVs.
- CTV-to-CTV attribution and event recording. Meaning, attribution and recording on a user's Vidaa device.

## Integration procedures

The following table lists the tasks required to integrate your Vidaa CTV app with AppsFlyer. To record your progress, download this [spreadsheet](https://docs.google.com/spreadsheets/d/e/2PACX-1vSFsuk9liZ_z34w3kHMyOFzASh5PBDtdn_HxgMqxAYY0wEt5RxCdrXeyLvteC5Cp-x-6ESwO5YbJ0n-/pub?output=xlsx).

| Task | Actions | Who's involved |
| --- | --- | --- |
| App setup | - [Create an AppsFlyer account](https://www.appsflyer.com/get-started/)<br />- [Add account users with appropriate permissions](/docs/user-management)<br />- [Add your Vidaa CTV app in AppsFlyer](/docs/adding-an-app-to-appsflyer) | Marketer |
| API integration with your app (via S2S) | [Integrate the AppsFlyer CTV API](https://dev.appsflyer.com/hc/reference/overview-4) into your CTV app with commands to report the following events to AppsFlyer.<br />- First opens<br />- In-app events<br />- Sessions<br />**Note**:<br />- Installs must be reported before in-app events and sessions.<br />- Send events using the API. Tell your developer which events to send.Verify that when you set up the API, you set up and map the events to send to AppsFlyer. <br />- For the`device_ids` parameter, select the type `vidaaid`.<br />To report owned media engagements, integrate the [impression engagement API.](https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id) | App developer |
| Link setup | [Learn how to create direct attribution links](/docs/ctv-pc-and-console-platform-direct-attribution-links) | Marketer |
| Report setup/view data | [Learn about data availability in dashboards and reports](/docs/ctv-pc-and-console-platform-attribution-concepts#data-availability) | Marketer/Data engineer |

## Traits and limitations

| Trait | Remarks |
| --- | --- |
| Non-organic sources | Coming soon |
| Retargeting | Not currently supported |
| Cost data | Cost data must be sent via [Cost Import](/docs/import-cost-data) using the upload file by email method. |

<Cards>
  <Card title="CTV, PC, and console platform overview" href="/docs/ctv-pc-and-console-platform-attribution-concepts" icon="fa-solid fa-diagram-project">
    Learn more about the platform overview for CTV, PC, and console.
  </Card>
</Cards>