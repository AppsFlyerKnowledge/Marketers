---
title: Amazon Vega OS integration with AppsFlyer
metadata:
  keywords:
    - Marketers
    - CTV Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - CTV Attribution
  created_at: '2026-01-19T07:36:38Z'
  edited_at: '2026-02-23T11:15:01Z'
  id: 42971481283601
  locale: en-us
  section: Promoting CTV apps
  section_id: 15328952633489
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/42971481283601-Amazon-Vega-OS-integration-with-AppsFlyer
---
> **At a glance:** Integrate your Amazon Vega OS Connected TV (CTV) app with AppsFlyer to receive attribution and event data for your campaigns on Amazon Vega OS.

## **About Amazon Vega OS CTV attribution**

The Amazon Vega OS for streaming runs across all Amazon Vega OS devices.

CTV apps streaming on Amazon Vega OS can integrate with AppsFlyer via API to receive attribution data and performance measurements about which sources (organic) and campaigns drive app open and in-app events. Marketers rely on these insights to measure and optimize marketing activities.

The Amazon Vega OS API integration supports:

* Amazon Vega OS Smart TVs.
* CTV-to-CTV attribution and event recording. Meaning, attribution and recording on a user's Amazon Vega OS device.

## **Integration procedures**

The following table lists the tasks required to integrate your Amazon Vega OS CTV app with AppsFlyer. To record your progress, download this [spreadsheet](https://docs.google.com/spreadsheets/d/e/2PACX-1vSFsuk9liZ_z34w3kHMyOFzASh5PBDtdn_HxgMqxAYY0wEt5RxCdrXeyLvteC5Cp-x-6ESwO5YbJ0n-/pub?output=xlsx).

| **Task** | **Actions** | **Who's involved** |
| --- | --- | --- |
| App setup | <ul><li>[Create an AppsFlyer account](https://www.appsflyer.com/get-started/)</li><li><Anchor target="_blank" href="/marketers/vi/docs/user-management">Add account users with appropriate permissions</Anchor></li><li><Anchor target="_blank" href="/marketers/vi/docs/adding-an-app-to-appsflyer">Add your Amazon Vega OS CTV app in AppsFlyer</Anchor> using the <Anchor target="_blank" href="/marketers/vi/docs/adding-an-app-to-appsflyer#amazon-vega-os">Amazon Vega app ID structure</Anchor>.</li></ul> | Marketer |
| API integration with your app (via S2S) | [Integrate the AppsFlyer CTV API](https://dev.appsflyer.com/hc/reference/overview-4) into your CTV app with commands to report the following events to AppsFlyer.<ul><li>First opens</li><li>In-app events</li><li>Sessions</li></ul>**Note**:ƒ<ul><li>Installs must be reported before in-app events and sessions.</li><li>Send events using the API. Tell your developer which events to send. Verify that when you set up the API, you set up and map the events to send to AppsFlyer.</li><li>For the `device_ids` parameter, select the type `vegaid`.</li><li>To report owned media engagements, integrate the [impression engagement API.](https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id)</li></ul> | App developer |
| Link setup | <Anchor target="_blank" href="/marketers/vi/docs/ctv-pc-and-console-platform-direct-attribution-links">Learn how to create direct attribution links</Anchor> | Marketer |
| Report setup/view data | <Anchor target="_blank" href="/marketers/vi/docs/ctv-pc-and-console-platform-attribution-concepts#tính-khả-dụng-của-dữ-liệu">Learn about data availability in dashboards and reports</Anchor> | Marketer/Data engineer |

## Traits and limitations

| Trait | Remarks |
| --- | --- |
| Non-organic sources | Coming soon |
| Retargeting | Not currently supported |
| Cost data | Cost data must be sent via <Anchor target="_blank" href="/marketers/vi/docs/import-cost-data">Cost Import</Anchor> using the upload file by email method. |

### **See also**

* <Anchor target="_blank" href="/marketers/vi/docs/ctv-pc-and-console-platform-attribution-concepts">CTV, PC, and console platform overview</Anchor>

<div data-zendesk-anchors="h_01KFAJYYX01B4E6CDMCH6REGY9=about-amazon-vega-os-ctv-attribution h_01KFAJYYX0WZY682B0SSWJM40V=integration-procedures h_01KFAJYYX0E95XEYQCQPCTN700=traits-and-limitations h_01KFAJYYX00K3RKMYB9QX6KXKN=see-also" />
