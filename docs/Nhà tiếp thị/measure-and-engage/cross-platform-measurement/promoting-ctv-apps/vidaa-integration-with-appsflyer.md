---
title: Vidaa integration with AppsFlyer
metadata:
  keywords:
    - CTV
    - Marketers
    - CTV Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - CTV Attribution
  created_at: '2022-11-06T08:13:09Z'
  edited_at: '2025-10-30T13:20:27Z'
  id: 10400222972433
  locale: en-us
  section: Promoting CTV apps
  section_id: 15328952633489
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/10400222972433-Vidaa-integration-with-AppsFlyer
---
> **At a glance:** Integrate your Vidaa Connected TV (CTV) app with AppsFlyer to receive attribution and event data for your campaigns on Vidaa.

## About Vidaa CTV attribution

The Vidaa OS for streaming runs across all Vidaa TVs.

CTV apps streaming on Vidaa can integrate with AppsFlyer via API to receive attribution data and performance measurements about which sources (organic) and campaigns drive app open and in-app events. Marketers rely on these insights to measure and optimize marketing activities.

The Vidaa API integration supports:

* Vidaa Smart TVs.
* CTV-to-CTV attribution and event recording. Meaning, attribution and recording on a user's Vidaa device.

## Integration procedures

The following table lists the tasks required to integrate your Vidaa CTV app with AppsFlyer. To record your progress, download this <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vSFsuk9liZ_z34w3kHMyOFzASh5PBDtdn_HxgMqxAYY0wEt5RxCdrXeyLvteC5Cp-x-6ESwO5YbJ0n-/pub?output=xlsx">spreadsheet</Anchor>.

| Task | Actions | Who's involved |
| --- | --- | --- |
| App setup | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Create an AppsFlyer account</Anchor></li><li><Anchor target="_blank" href="/marketers/vi/docs/user-management">Add account users with appropriate permissions</Anchor></li><li><Anchor target="_blank" href="/marketers/vi/docs/adding-an-app-to-appsflyer">Add your Vidaa CTV app in AppsFlyer</Anchor></li></ul> | Marketer |
| API integration with your app (via S2S) | <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-4">Integrate the AppsFlyer CTV API</Anchor> into your CTV app with commands to report the following events to AppsFlyer.<ul><li>First opens</li><li>In-app events</li><li>Sessions</li></ul>**Note**:<ul><li>Installs must be reported before in-app events and sessions.</li><li>Send events using the API. Tell your developer which events to send. Verify that when you set up the API, you set up and map the events to send to AppsFlyer.</li><li>For the`device_ids` parameter, select the type `vidaaid`.</li></ul>To report owned media engagements, integrate the <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">impression engagement API.</Anchor> | App developer |
| Link setup | <Anchor target="_blank" href="/marketers/vi/docs/ctv-pc-and-console-platform-direct-attribution-links">Learn how to create direct attribution links</Anchor> | Marketer |
| Report setup/view data | <Anchor target="_blank" href="/marketers/vi/docs/ctv-pc-and-console-platform-attribution-concepts#tính-khả-dụng-của-dữ-liệu">Learn about data availability in dashboards and reports</Anchor> | Marketer/Data engineer |

<div id="traits-and-limitations" />

<Accordion title="Traits and limitations">

| Trait | Remarks |
| --- | --- |
| Non-organic sources | Coming soon |
| Retargeting | Not currently supported |
| Cost data | Cost data must be sent via <Anchor target="_blank" href="/marketers/vi/docs/import-cost-data">Cost Import</Anchor> using the upload file by email method. |

</Accordion>

> 📄 **See also**
>
> * <span id="overview"></span><Anchor target="_blank" href="/marketers/vi/docs/ctv-pc-and-console-platform-attribution-concepts">CTV, PC, and console platform overview</Anchor>

<div data-zendesk-anchors="01H7Z180QRR77E1GBQ0P0RHVN5=about-vidaa-ctv-attribution 01H7Z180QR6HT4R3N9DYSM8WB9=integration-procedures 01H7Z180QR0QQ0HK3N5N1G4ENZ=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=see-also" />
