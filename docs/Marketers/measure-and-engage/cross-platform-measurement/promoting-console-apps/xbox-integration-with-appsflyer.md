---
title: "Xbox integration with AppsFlyer"
excerpt: "Integrate your Xbox app with AppsFlyer to receive attribution and event data for your campaigns on Xbox."
x-zendesk:
  id: 14504812967057
  url: https://support.appsflyer.com/hc/en-us/articles/14504812967057-Xbox-integration-with-AppsFlyer
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Promoting Console apps
  section_id: 15329052471057
  position: 13
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-roi-tamir, Marketers, PC & Console Attribution]
  labels: [Marketers, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2023-04-13T08:28:00Z'
  edited_at: '2024-05-07T09:10:17Z'
---
## About Xbox attribution

The Xbox OS for console and CTV apps runs across all Xboxes.

Apps running on Xbox can integrate with AppsFlyer via S2S API to receive attribution data and performance measurements about which sources (organic) and campaigns drive app open and in-app events. Marketers rely on these insights to measure and optimize marketing activities.

The Xbox API integration supports:

* Xboxes.
* Attribution and event recording for Xbox apps. Meaning, attribution and recording on a user's Xbox device.

## Integration procedures

The following table lists the tasks required to integrate your Xbox app with AppsFlyer.

| Task | Actions | Who's involved |
| --- | --- | --- |
| App setup | <ul><li>[Create an AppsFlyer account](https://www.appsflyer.com/get-started/)</li><li>[Add account users with appropriate permissions](/docs/user-management)</li><li>[Add your Xbox app in AppsFlyer](/docs/adding-an-app-to-appsflyer)</li></ul> | Marketer |
| API integration with your app (via S2S) | [Integrate the AppsFlyer API](https://dev.appsflyer.com/hc/reference/overview-4) into your app with commands to report the following events to AppsFlyer.<ul><li>First opens</li><li>In-app events</li><li>Sessions</li></ul>**Note**:<ul><li>First app opens must be reported before in-app events and sessions.</li><li>For the `device_ids` parameter, select the type `custom`.</li><li>Send events using the API. Tell your developer which events to send. Verify that when you set up the API, you set up and map the events to send to AppsFlyer.</li></ul>To report owned media engagements, integrate the [impression engagement API.](https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id) | App developer |
| Reports setup | [Learn about data availability in dashboards and reports](/docs/ctv-pc-and-console-platform-attribution-concepts#data-availability) | Marketer/Data engineer |

<Accordion title="Traits and limitations">

| Trait | Remarks |
| --- | --- |
| Retargeting | Not currently supported |
| Cost data | Cost data must be sent via [Cost Import](/docs/import-cost-data) using the upload file by email method. |

</Accordion>

> 📘 **See also**
>
> * [CTV, PC, and console platform overview](/docs/ctv-pc-and-console-platform-attribution-concepts)