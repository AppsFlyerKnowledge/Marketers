---
title: Vizio integration with AppsFlyer
metadata:
  keywords:
    - Developers
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
  created_at: '2022-03-27T15:48:04Z'
  edited_at: '2024-05-07T09:27:49Z'
  id: 5045234293777
  locale: en-us
  section: Promoting CTV apps
  section_id: 15328952633489
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/5045234293777-Vizio-integration-with-AppsFlyer
---
**At a glance:** Integrate your Vizio Connected TV (CTV) app (channel) with AppsFlyer to receive attribution and event data for your campaigns on Vizio.

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
| App setup | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Create an AppsFlyer account</Anchor></li><li><Anchor target="_blank" href="/marketers/docs/user-management">Add account users with appropriate permissions</Anchor></li><li><Anchor target="_blank" href="/marketers/docs/adding-an-app-to-appsflyer">Add your Vizio CTV app in AppsFlyer</Anchor></li></ul> | Marketer |
| API integration with your app (via S2S) | <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-4">Integrate the AppsFlyer CTV API</Anchor> into your CTV app with commands to report the following events to AppsFlyer.<ul><li>First opens</li><li>In-app events</li><li>Sessions</li></ul>**Note**:<ul><li>Installs must be reported before in-app events and sessions.</li><li>Send events using the API. Tell your developer which events to send. Verify that when you set up the API, you set up and map the events to send to AppsFlyer.</li></ul>To report owned media engagements, integrate the <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">impression engagement API.</Anchor> | App developer |
| Partner integration | Add Vizio as an ad network (integrated partner) in AppsFlyer:<ol><li><Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#a-activate-partner">Activate partner</Anchor></li><li>[Optional] Turn on **<Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#e-install-attribution">View-through attribution</Anchor>.**</li></ol> | Marketer |
| Link setup | <Anchor target="_blank" href="/marketers/docs/ctv-pc-and-console-platform-direct-attribution-links">Learn how to create direct attribution links</Anchor> | Marketer |
| Report setup/view data | <Anchor target="_blank" href="/marketers/docs/ctv-pc-and-console-platform-attribution-concepts#data-availability">Learn about data availability in dashboards and reports</Anchor> | Marketer/Data engineer |

<div id="traits-and-limitations" />

<Accordion title="Traits and limitations">

| Trait | Remarks |
| --- | --- |
| Retargeting | Not currently supported |
| View-through attribution | Default is 24 hours |
| Cost data | Cost data must be sent via <Anchor target="_blank" href="/marketers/docs/import-cost-data">Cost Import</Anchor> using the upload file by email method. |

</Accordion>

> 📄 **See also**
>
> * <span id="overview"></span><Anchor target="_blank" href="/marketers/docs/ctv-pc-and-console-platform-attribution-concepts">CTV, PC, and console platform overview</Anchor>

<div data-zendesk-anchors="01H7Z16QWWCPR309JDKV7H0469=about-vizio-ctv-attribution 01H7Z16QWW3GJEAGV0F3JHTKE1=vizio-attribution-flow 01H7Z16QWW1WX5F947WPH9HBQX=integration-procedures 01H7Z16QWX24K8QCEJVBX1SQEA=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=see-also" />
