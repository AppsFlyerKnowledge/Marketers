---
title: Xbox integration with AppsFlyer
metadata:
  keywords:
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2023-04-13T08:28:00Z'
  edited_at: '2024-05-07T09:10:17Z'
  id: 14504812967057
  locale: en-us
  section: Promoting Console apps
  section_id: 15329052471057
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/14504812967057-Xbox-integration-with-AppsFlyer
---
> **At a glance:** Integrate your Xbox app with AppsFlyer to receive attribution and event data for your campaigns on Xbox.

<div id="about-xbox-attribution" />

## About Xbox attribution

The Xbox OS for console and CTV apps runs across all Xboxes.

Apps running on Xbox can integrate with AppsFlyer via S2S API to receive attribution data and performance measurements about which sources (organic) and campaigns drive app open and in-app events. Marketers rely on these insights to measure and optimize marketing activities.

The Xbox API integration supports:

* Xboxes.
* Attribution and event recording for Xbox apps. Meaning, attribution and recording on a user's Xbox device.

<div id="integration-procedures" />

## Integration procedures

The following table lists the tasks required to integrate your Xbox app with AppsFlyer.

| Task | Actions | Who's involved |
| --- | --- | --- |
| App setup | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Create an AppsFlyer account</Anchor></li><li><Anchor target="_blank" href="/marketers/docs/user-management">Add account users with appropriate permissions</Anchor></li><li><Anchor target="_blank" href="/marketers/docs/adding-an-app-to-appsflyer">Add your Xbox app in AppsFlyer</Anchor></li></ul> | Marketer |
| API integration with your app (via S2S) | <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-4">Integrate the AppsFlyer API</Anchor> into your app with commands to report the following events to AppsFlyer.<ul><li>First opens</li><li>In-app events</li><li>Sessions</li></ul>**Note**:<ul><li>First app opens must be reported before in-app events and sessions.</li><li>For the `device_ids` parameter, select the type `custom`.</li><li>Send events using the API. Tell your developer which events to send. Verify that when you set up the API, you set up and map the events to send to AppsFlyer.</li></ul>To report owned media engagements, integrate the <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">impression engagement API.</Anchor> | App developer |
| Reports setup | <Anchor target="_blank" href="/marketers/docs/ctv-pc-and-console-platform-attribution-concepts#data-availability">Learn about data availability in dashboards and reports</Anchor> | Marketer/Data engineer |

<div id="traits-and-limitations" />

<Accordion title="Traits and limitations">

| Trait | Remarks |
| --- | --- |
| Retargeting | Not currently supported |
| Cost data | Cost data must be sent via <Anchor target="_blank" href="/marketers/docs/import-cost-data">Cost Import</Anchor> using the upload file by email method. |

</Accordion>

<div id="see-also" />

> 📄 **See also**
>
> * <Anchor target="_blank" href="/marketers/docs/ctv-pc-and-console-platform-attribution-concepts">CTV, PC, and console platform overview</Anchor>

<div data-zendesk-anchors="about-playstation-attribution=about-xbox-attribution 01H7Z1NEAJMRWKHS4K168V0753=about-xbox-attribution 01H7Z1NEAJJY4ZRVKY74ACXAAR=integration-procedures 01H7Z1NEAJRA11P7NG05KRKR8Q=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=see-also" />
