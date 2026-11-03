---
title: LG integration with AppsFlyer
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
  content_tags:
    - pm-roi-tamir
    - Marketers
    - CTV Attribution
  created_at: '2022-07-03T10:31:42Z'
  edited_at: '2026-05-04T09:28:51Z'
  id: 7341725624081
  locale: en-us
  section: Promoting CTV apps
  section_id: 15328952633489
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/7341725624081-LG-integration-with-AppsFlyer
---
> **At a glance:** Integrate your LG Connected TV (CTV) app with AppsFlyer to receive attribution and event data for your campaigns on LG.

## About LG CTV attribution

The LG Webos OS for streaming runs across all LG TVs.

CTV apps streaming on LG can integrate with AppsFlyer via API to receive attribution data and performance measurements about which sources (organic and non-organic) and campaigns drive app open and in-app events. Marketers rely on these insights to measure and optimize marketing activities.

The LG API integration supports:

* LG Smart TVs.
* CTV-to-CTV attribution and event recording. Meaning, attribution and recording on a user's LG device.

## Integration procedures

The following table lists the tasks required to integrate your LG CTV app with AppsFlyer.

| Task | Actions | Who's involved |
| --- | --- | --- |
| App setup | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Create an AppsFlyer account</Anchor></li><li><Anchor target="_blank" href="/marketers/id/docs/user-management">Add account users with appropriate permissions</Anchor></li><li><Anchor target="_blank" href="/marketers/id/docs/adding-an-app-to-appsflyer">Add your LG CTV app in AppsFlyer</Anchor></li></ul> | Marketer |
| API integration with your app (via S2S or SDK) | There are two methods of integration you can use: S2S and SDK.<br /><br />For the S2S method, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-4">integrate the AppsFlyer API</Anchor> into your app with commands to report the following events to AppsFlyer.<ul><li>First opens</li><li>In-app events</li><li>Sessions</li></ul>**Note**:<ul><li>Installs must be reported before in-app events and sessions.</li><li>Send events using the API. Tell your developer which events to send. Verify that when you set up the API, you set up and map the events to send to AppsFlyer.</li></ul>To report owned media engagements, integrate the <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">impression engagement API.</Anchor><br /><br />For the SDK method, see the developer hub for <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-html5-ctv-sdk">LG documentation</Anchor>. | App developer |
| Partner integration | Add LG Ads as an ad network (integrated partner) in AppsFlyer.<ol><li><Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#a-activate-partner">Activate partner</Anchor></li><li>[Optional] Turn on <Anchor target="_blank" href="/marketers/id/docs/set-up-an-integrated-partner#e-install-attribution">**View-through attribution**</Anchor>.</li></ol> | Marketer |
| Link setup | <Anchor target="_blank" href="/marketers/id/docs/ctv-pc-and-console-platform-direct-attribution-links">Learn how to create direct attribution links</Anchor> | Marketer |
| Report setup/view data | <Anchor target="_blank" href="/marketers/id/docs/ctv-pc-and-console-platform-attribution-concepts#ketersediaan-data">Learn about data availability in dashboards and reports</Anchor> | Mareketer/Data engineer |

<div id="traits-and-limitations" />

<Accordion title="Traits and limitations">

| Trait | Remarks |
| --- | --- |
| Retargeting | Not currently supported |
| Cost data | Cost data must be sent via <Anchor target="_blank" href="/marketers/id/docs/import-cost-data">Cost Import</Anchor> using the upload file by email method. |
| Attribution | LG Ads uses probabilistic modeling for attribution; ID matching isn't currently available. |
| Customer ID | Populate this parameter with the LG customer ID (`cust_id`) obtained from LG Ads. |
| Deterministic attribution | There is an option to enable deterministic ad ID matching for attribution. To do so, the following requirements must be met:<ul><li>LG must conduct a legal review before content partner apps can be enabled to surface the AD ID.</li><li>This legal review involves the content partner working directly with LG Electronics and requires both parties to sign a legal agreement.</li><li>Content partner apps must integrate the functionality to collect and transmit the LG AD ID, and release a user-initiated app update to begin surfacing the AD ID to AppsFlyer.</li><li>For more information, contact your AppsFlyer CSM and  [partnerships@lgads.tv](mailto:partnerships@lgads.tv)</li></ul> |

</Accordion>

> 📄 **See also**
>
> * <Anchor target="_blank" href="/marketers/id/docs/ctv-pc-and-console-platform-attribution-concepts">CTV, PC, and console platform overview</Anchor>

<div data-zendesk-anchors="01H7Z17N0YAAGTDPMGZ89F7AVB=about-lg-ctv-attribution 01H7Z17N0Y8RE5PS15N2JG5NRH=integration-procedures 01H7Z17N0YCX89SYYJ1AMPM6W4=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=see-also" />
