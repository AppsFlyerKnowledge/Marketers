---
title: "Vizio integration with AppsFlyer"
excerpt: "Integrate your Vizio Connected TV (CTV) app (channel) with AppsFlyer to receive attribution and event data for your campaigns on Vizio."
x-zendesk:
  id: 5045234293777
  url: https://support.appsflyer.com/hc/en-us/articles/5045234293777-Vizio-integration-with-AppsFlyer
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Promoting CTV apps
  section_id: 15328952633489
  position: 5
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-roi-tamir, Marketers, CTV Attribution]
  labels: [Developers, CTV, Marketers, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2022-03-27T15:48:04Z'
  edited_at: '2024-05-07T09:27:49Z'
---
## About Vizio CTV attribution

The Vizio SmartCast OS for streaming runs across all Vizio TVs.

CTV apps streaming on Vizio can integrate with AppsFlyer via API to receive attribution data and performance measurements about which sources (non-organic or organic) and paid campaigns drive app open and in-app events. Marketers rely on these insights to measure and optimize marketing activities.

The Vizio API integration supports:

* Vizio Smart TVs.
* CTV-to-CTV attribution and event recording. Meaning, attribution and recording of Vizio first app opens (the equivalent of installs) and events that occur on a user's Vizio device.

### Vizio attribution flow

![CTV_attribution_flow_-_Vizio__1_.png](https://files.readme.io/f4ab4b6c9e045fe00b537814fa9f10746b525a5512e5805e62eb0c2e4c9a8615-6318406872337.png)

## Integration procedures

The following table lists the tasks required to integrate your Vizio CTV app with AppsFlyer.

| Task | Actions | Who's involved |
| --- | --- | --- |
| App setup | <ul><li>[Create an AppsFlyer account](https://www.appsflyer.com/get-started/)</li><li>[Add account users with appropriate permissions](/docs/user-management)</li><li>[Add your Vizio CTV app in AppsFlyer](/docs/adding-an-app-to-appsflyer)</li></ul> | Marketer |
| API integration with your app (via S2S) | [Integrate the AppsFlyer CTV API](https://dev.appsflyer.com/hc/reference/overview-4) into your CTV app with commands to report the following events to AppsFlyer.<ul><li>First opens</li><li>In-app events</li><li>Sessions</li></ul>**Note**:<ul><li>Installs must be reported before in-app events and sessions.</li><li>Send events using the API. Tell your developer which events to send. Verify that when you set up the API, you set up and map the events to send to AppsFlyer.</li></ul>To report owned media engagements, integrate the [impression engagement API.](https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id) | App developer |
| Partner integration | Add Vizio as an ad network (integrated partner) in AppsFlyer:<ol><li>[Activate partner](/docs/set-up-an-integrated-partner#a-activate-partner)</li><li>[Optional] Turn on **[View-through attribution](/docs/set-up-an-integrated-partner#e-install-attribution).**</li></ol> | Marketer |
| Link setup | [Learn how to create direct attribution links](/docs/ctv-pc-and-console-platform-direct-attribution-links) | Marketer |
| Report setup/view data | [Learn about data availability in dashboards and reports](/docs/ctv-pc-and-console-platform-attribution-concepts#data-availability) | Marketer/Data engineer |

<div id="traits-and-limitations" />

<Accordion title="Traits and limitations">

| Trait | Remarks |
| --- | --- |
| Retargeting | Not currently supported |
| View-through attribution | Default is 24 hours |
| Cost data | Cost data must be sent via [Cost Import](/docs/import-cost-data) using the upload file by email method. |

</Accordion>

> 📘 **See also**
>
> * <span id="overview"></span>[CTV, PC, and console platform overview](/docs/ctv-pc-and-console-platform-attribution-concepts)

<div data-zendesk-anchors="01H7Z16QWWCPR309JDKV7H0469=about-vizio-ctv-attribution 01H7Z16QWW3GJEAGV0F3JHTKE1=vizio-attribution-flow 01H7Z16QWW1WX5F947WPH9HBQX=integration-procedures 01H7Z16QWX24K8QCEJVBX1SQEA=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=see-also" />
