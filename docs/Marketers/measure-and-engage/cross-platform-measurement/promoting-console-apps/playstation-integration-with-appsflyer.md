---
title: PlayStation integration with AppsFlyer
metadata:
  keywords:
    - CTV
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2022-11-03T15:12:14Z'
  edited_at: '2026-09-15T07:20:35Z'
  id: 10342860530961
  locale: en-us
  section: Promoting Console apps
  section_id: 15329052471057
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/10342860530961-PlayStation-integration-with-AppsFlyer
---
> **At a glance:** Learn how to integrate your PlayStation app with AppsFlyer and how to measure ads that run on PlayStation.

This article covers two related but distinct integrations.

* [Integrate your PlayStation app with AppsFlyer](#integrate-your-playstation-app-with-appsflyer): receive attribution and event data for your PlayStation app, regardless of where your users come from.
* [Measure ads that run on PlayStation](#measure-ads-that-run-on-playstation): activate the PlayStation Ads integration to measure ads that run on PlayStation consoles and drive installs of your app.

<div id="integrate-your-playstation-app-with-appsflyer" />

## Integrate your PlayStation app with AppsFlyer

The PlayStation OS for console and CTV (Connected TV) apps runs across all PlayStation devices.

Apps running on PlayStation can integrate with AppsFlyer via S2S (server-to-server) API to receive attribution data and performance measurements about which sources and campaigns drive app open and in-app events. Marketers rely on these insights to measure and optimize marketing activities.

The PlayStation API integration supports:

* PlayStations.
* Attribution and event recording for PlayStation apps, which means attribution and recording on a user's PlayStation device.

<div id="example-attribution-flow" />

### Example attribution flow

The following is an example flow that highlights the most important steps in a user journey from ad engagement to attribution. It includes the AppsFlyer-recommended cross-platform landing page. **Note**: While we recommend using the cross-platform landing page, you can also use direct attribution links.

<Image align="center" alt="Diagram of the attribution flow from a marketing touchpoint through a cross-platform landing page to installing a PlayStation app" src="https://files.readme.io/eaa57bd6977d5eae5dff2d135bc80e847040103eacb00dff6add79e02b450763-small-49667524948369.jpg" width="3938px" />

1. <span id="marketing-touchpoint"></span>Marketing touchpoints: Customers interact with your brand through online or offline channels. These can include email and newsletters, social media, mobile web, and more.
2. Game landing page: A game landing page directs customers to your download app page. This step is important for collecting UTM (Urchin Tracking Module) and other URL parameters to attribute customers from the click/install to the original media sources or to your owned media sources.  
   The landing page is also useful because it provides links to the various platforms your game supports. For example, you can also have links to your Xbox, Microsoft Store, and Steam page on your landing page.
3. App page: This is the URL to your PlayStation app page that hosts your app for customers to download.
4. Game install: The user installs the game, triggering attribution and the recording of in-app events and sessions.

<div id="integration-procedures" />

### Integration procedures

The following table lists the tasks required to integrate your PlayStation app with AppsFlyer.

| Task | Actions | Who's involved |
| --- | --- | --- |
| App setup | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Create an AppsFlyer account</Anchor></li><li><Anchor target="_blank" href="/marketers/docs/user-management">Add account users with appropriate permissions</Anchor></li><li><Anchor target="_blank" href="/marketers/docs/adding-an-app-to-appsflyer">Add your PlayStation app to AppsFlyer</Anchor></li></ul> | Marketer |
| API integration with your app (via S2S) | <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/pc-console-ctv-api-overview">Integrate the AppsFlyer API</Anchor> into your app with commands to report the following events to AppsFlyer.<ul><li>First opens</li><li>In-app events</li><li>Sessions</li></ul>**Note**:<ul><li>Report the first app open event before in-app events and sessions.</li><li>For the `device_ids` parameter, select the type `custom`.<ul><li>The `custom` generated ID for <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_first-open-app-platform-app-id">first opens</Anchor> must match the ID you use for <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_inapp-app-platform-app-id">in-app events</Anchor> and <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_session-app-platform-app-id">sessions</Anchor>.</li></ul></li><li>Send events using the API. Tell your developer which events to send. When you set up the API, verify that you've mapped the events you want to send to AppsFlyer.</li><li>The `psid` device ID type is intended for use as an advertising ID. At the moment, PlayStation does not support advertising ID matching, so there is no need to use this device ID type.</li><li>We recommend sharing the `psn_uid`, which is the PlayStation account ID in the `customer_user_id` field. Make sure to anonymize the value before sharing it.</li></ul>To report owned media engagements, integrate the <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">impression engagement API.</Anchor> | App developer |
| Cross-platform landing page setup | **Recommended**: A cross-platform landing page running the AppsFlyer Smart Script lets you perform web-to-app attribution. It's recommended when your campaign promotes an app that's also available on other platforms, like Epic and Native PC.<br /><br /><Anchor target="_blank" href="/marketers/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">Learn about cross-platform landing pages</Anchor><br /><br /><Anchor target="_blank" href="/marketers/docs/cross-platform-landing-pages-with-smart-script">Learn how to set up a cross-platform landing page</Anchor><br /><br />**Note**:<br /><br />For PlayStation, the following parameters are required:<ul><li>**platform**: playstation</li><li>**app\_id**: The ID of the app</li><li>**media\_source**</li></ul>The following parameters are not required but recommended:<ul><li>**campaign**</li><li>**ad**</li><li>**ad\_set**</li></ul> | Marketer (may require developer assistance) |
| Link setup | If you don't use a cross-platform landing page, you can create direct attribution links to place behind ads.<br /><br /><Anchor target="_blank" href="/marketers/docs/ctv-pc-and-console-platform-direct-attribution-links">Learn how to create direct attribution links</Anchor> | Marketer |
| Report setup/view data | <Anchor target="_blank" href="/marketers/docs/ctv-pc-and-console-platform-attribution-concepts#data-availability">Learn about data availability in dashboards and reports</Anchor> | Marketer/Data engineer |

<div id="measure-ads-that-run-on-playstation" />

## Measure ads that run on PlayStation

AppsFlyer supports measurement for ads that run on PlayStation consoles and drive installs of your PlayStation app. This flow is separate from the general integration in [Integration procedures](#integration-procedures) above, it only applies if PlayStation is also one of your ad sources, and it's available to advertisers who already have an active PlayStation app set up in AppsFlyer.

To run and measure PlayStation ads:

1. **Create an attribution link.** Follow the guidelines in <Anchor target="_blank" href="/marketers/docs/ctv-pc-and-console-platform-direct-attribution-links">CTV, PC, and console platform direct attribution links</Anchor>, and set the platform value to `playstation`.
2. **Send the link to PlayStation.** Ask your PlayStation ads management team to place the attribution link in your ads.
3. **Activate the PlayStation Ads integration in AppsFlyer.** Use partner ID `playstation_int`. For the general activation steps, see <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner">Set up an integrated partner</Anchor>.
4. **View the results in AppsFlyer.** Performance appears in your standard AppsFlyer dashboards and reports, attributed to the PlayStation media source.

<div id="important" />

> 🚧 **Important**
>
> At this stage, you can't share signals, such as conversions, events, or postbacks, back to the PlayStation ads team. Measurement data stays in AppsFlyer and isn't sent back to PlayStation for optimization.

<div id="sample-attribution-links" />

### Sample attribution links

The following are sample click and impression attribution links for PlayStation.

**Click**

```
https://engagements.appsflyer.com/v1.0/s2s/click/app/playstation/10000000
?af_media_source=playstation_int
&af_campaign_id={campaign_id}
&af_ip={USER_IP}
&af_campaign={campaign_name}
```

**Impression**

```
https://engagements.appsflyer.com/v1.0/s2s/impression/app/playstation/10000000
?af_media_source=playstation_int
&af_campaign_id={campaign_id}
&af_ip={USER_IP}
&af_campaign={campaign_name}
```

| Placeholder | Type | Meaning |
| --- | --- | --- |
| 10000000 | Path parameter | The advertiser's PlayStation app ID in AppsFlyer. Replace with the real app ID, with no platform prefix. |
| s2s / c2s | Path parameter | Whether the request is sent server-to-server (s2s) or client-to-server (c2s). Replaces the s2s segment shown in the example URLs above. The PlayStation Ads team decides which one applies. |
| `{campaign_id}` | Query parameter | Campaign ID, populated by PlayStation. |
| `{campaign_name}` | Query parameter | Campaign name, populated by PlayStation. |
| `{USER_IP}` | Query parameter | End-user IP address, populated by PlayStation. |

<div id="traits-and-limitations" />

## Traits and limitations

| Trait | Description |
| --- | --- |
| Cost data | Send cost data via <Anchor target="_blank" href="/marketers/docs/import-cost-data">Ad Spend Ingestion</Anchor>, using the upload file by email method. |

<div id="see-also" />

> 📄 **See also**
>
> * <Anchor target="_blank" href="/marketers/docs/ctv-pc-and-console-platform-attribution-concepts">CTV, PC, and console platform overview</Anchor>

<div data-zendesk-anchors="01H7Z1HPD0AB0VP6REMBF2HCR8=integrate-your-playstation-app-with-appsflyer h_01HP1Q8B11P0Q8F2Z2FRDSPNDE=example-attribution-flow 01H7Z19FJ54WZ7XV91Y36EKYQ6=marketing-touchpoint 01H7Z1HPD0VAMPEHBPN8MAT3ST=integration-procedures run-and-measure-ads-on-playstation=measure-ads-that-run-on-playstation h_01M2FS60HDHKN7GZWFADVMAEKD=measure-ads-that-run-on-playstation h_01M2FS60HDVJVBNN2MGCA8CVXG=important h_01M2FS60HDQGDT1KCSGCPJAFJC=sample-attribution-links 01H7Z1HPD0CS7CTX2KS2RVD3VA=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=see-also" />
