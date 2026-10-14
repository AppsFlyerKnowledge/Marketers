---
title: Samsung integration with AppsFlyer
excerpt: >-
  Integrate your Samsung Connected TV (CTV) app with AppsFlyer to receive
  attribution and event data for your campaigns on Samsung.
metadata:
  keywords:
    - Advertisers
    - Developers
    - CTV
    - Marketers
    - CTV Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2022-05-03T09:19:48Z'
  edited_at: '2026-10-05T07:00:31Z'
  id: 5860544738065
  locale: en-us
  section: Promoting CTV apps
  section_id: 15328952633489
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/5860544738065-Samsung-integration-with-AppsFlyer
---
## About Samsung CTV attribution

The Samsung Tizen OS for streaming runs across all Samsung TVs.

CTV apps streaming on Samsung can integrate with AppsFlyer via API to receive attribution data and performance measurements about which sources (organic and non-organic) and campaigns drive app open and in-app events. Marketers rely on these insights to measure and optimize marketing activities.

The Samsung API integration supports:

* Samsung Smart TVs.
* CTV-to-CTV attribution and event recording, meaning attribution and recording take place on a user's Samsung device.

### Samsung attribution flow

![[CONFIRM: Diagram of the Samsung CTV attribution flow, showing install, session, and in-app event data moving from the Samsung app to AppsFlyer via the S2S API or SDK]](https://files.readme.io/a1031878e8aced81da5762d06ae0163770cd73b9a7c91224ea7665aa142d2ce8-7215151128209.png)

## Integration procedures

The following table lists the tasks required to integrate your Samsung CTV app with AppsFlyer.

| Task | Actions | Who's involved |
| --- | --- | --- |
| App setup | To integrate your Samsung CTV app with AppsFlyer:<ul><li>[Create an AppsFlyer account](https://www.appsflyer.com/get-started/)</li><li>[Add account users with appropriate permissions](/docs/user-management)</li><li>[Add your Samsung CTV app in AppsFlyer](/docs/adding-an-app-to-appsflyer)</li></ul> | Marketer |
| API integration with your app (via S2S or SDK) | There are two methods of integration you can use: server-to-server (S2S) and SDK.<br /><br />For the S2S method, [integrate the AppsFlyer API](https://dev.appsflyer.com/hc/reference/pc-console-ctv-api-overview) into your app with commands to report the following events to AppsFlyer.<ul><li>First opens</li><li>In-app events</li><li>Sessions</li></ul>**<span id="h_01M349521V96NRS5CJKXZKMA6P"></span>Note**<ul><li>Report installs before in-app events and sessions.</li><li>Send events using the API. Tell your developer which events to send, and verify that you set up and map the events to send to AppsFlyer.</li></ul><br /><br />To report owned media engagements, integrate the [impression engagement API](https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id).<br /><br />For the SDK method, see the developer hub for [Samsung documentation](https://github.com/AppsFlyerSDK/appsflyer-html5-ctv-sdk). | App developer |
| Partner integration | Add Samsung as an ad network (integrated partner) in AppsFlyer.<ol><li>[Activate partner](/docs/set-up-an-integrated-partner#a-activate-partner)</li><li>[Optional] Turn on [**View-through attribution**](/docs/set-up-an-integrated-partner#e-install-attribution).</li></ol> | Marketer |
| Link setup | [Learn how to create direct attribution links](/docs/ctv-pc-and-console-platform-direct-attribution-links) | Marketer |
| Report setup/view data | [Learn about data availability in dashboards and reports](/docs/ctv-pc-and-console-platform-attribution-concepts#data-availability) | Marketer/Data engineer |

## Traits and limitations

| Trait | Remarks |
| --- | --- |
| Retargeting | Not currently supported |
| Cost data | Import cost data via [Cost Import](/docs/import-cost-data) using the upload file **by email** method. You can also pull data **via API** for Google, Meta, or TikTok. |
| Supported regions | CTV and preload campaign support varies by region, as follows.<ul><li>AppsFlyer supports Connected TV (CTV) campaigns only in the US, including sharing postbacks with Samsung through the Samsung demand-side platform (DSP) integration (`samsungdsp_int`).</li><li>In the EMEA (Europe, Middle East, and Africa) region, AppsFlyer supports CTV campaigns without sharing postbacks with Samsung through the Samsung EMEA DSP integration (`samsungemea_int`).</li><li>Other regions don't support CTV campaigns.</li><li>AppsFlyer supports preload campaigns globally.</li></ul> |

<div data-zendesk-anchors="01H7Z17A1QPJQH9R5MRBVTMG37=about-samsung-ctv-attribution 01H7Z17A1Q03CEJT848FRFHDPQ=samsung-attribution-flow 01H7Z17A1QQN4FYJXZFS5FP2NY=integration-procedures 01H7Z17A1QVW58B2FZE7SDJHHJ=traits-and-limitations" />
