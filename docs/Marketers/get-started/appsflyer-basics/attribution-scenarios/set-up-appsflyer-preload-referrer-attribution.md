---
title: "Set up AppsFlyer preload referrer attribution"
excerpt: "AppsFlyer uses preload referrer to attribute installs to preload campaigns, where marketers contract with Original Equipment Manufacturers (OEMs), mobile carriers, and app discovery partners to preload their app at the factory or at the time the device is first turned on by the user."
x-zendesk:
  id: 4543811207313
  url: https://support.appsflyer.com/hc/en-us/articles/4543811207313-Set-up-AppsFlyer-preload-referrer-attribution
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Attribution scenarios
  section_id: 6551328497041
  position: 2
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-alina-koifman, Marketers, Mobile Attribution]
  labels: [Advertisers, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2022-03-02T09:54:10Z'
  edited_at: '2026-09-15T11:20:06Z'
---
## Overview

In preload campaigns, Original Device Manufacturers (OEMs), mobile carriers, and app discovery partners preload apps on devices before they reach the user. This can be done by the OEM at the factory or by providers upon first device activation.

Preload campaigns allow advertisers to reach a potentially large audience without running online campaigns.

Preload referrer attribution (1 of 3 [preload attribution methods](/docs/appsflyer-attribution-model#preload-campaigns)) gives marketers an accurate and privacy-preserving mechanism to measure the performance of preload campaigns. This method provides marketers with deterministic attribution results and simultaneously ensures that user privacy is preserved since attribution is performed via referrer matching with a referrer generated independently of the device and user identifiers.

The solution provides:

* Transparent support for app updates and app redownloads.
* Visibility and measurement capabilities between the first device activation and the first app launch. This lets you see how many devices were activated with the app preloaded on the devices by a specific partner, and then see when the app is launched for the first time.

## Partners supporting preload referrer campaigns

The information in this article is relevant for advertisers that are integrated with the partners specified in the following table:

<table><thead><tr><th rowspan="2">Partner</th><th rowspan="2">PID</th><th colspan="2">Preload referrer campaign options <a href="./set-up-appsflyer-preload-referrer-attribution#preload-referrer-options"><span>Learn more</span></a></th></tr><tr><th>Preload</th><th>Click to download</th></tr></thead><tbody><tr><td><a href="#samsung-preload-referrer">Samsung</a></td><td>samsung_int</td><td><span><strong>✓</strong></span></td><td> </td></tr><tr><td>Digital Turbine On Device</td><td>digitalturbine_int</td><td><span><strong>✓</strong></span></td><td>Coming soon</td></tr><tr><td>Aura from Unity</td><td>aura_int</td><td><span><strong>✓</strong></span></td><td>Coming soon</td></tr><tr><td>Appnext</td><td>appnext_int</td><td><span><strong>✓</strong></span></td><td>Coming soon</td></tr><tr><td>Glance<br/> </td><td>glance_int</td><td><span><strong>✓</strong></span></td><td><span><strong>✓</strong></span></td></tr></tbody></table>

## Preload referrer options

Referrers can be used to attribute installs by preload or by click-to-download. See the table that follows for more details.

AppsFlyer gives the highest priority to preload attribution. This means that if a user engages with other campaigns before opening the app for the first time, the preload campaign is still awarded the attribution. Other engagements are regarded as assisted installs. **Note**: You can enable equal priority for preload engagements. This gives deterministic clicks the same attribution priority as preload engagements for the entire preload lookback window, so attribution to the preload campaign can be superseded by another ad engagement.

| Referrer option | Description | UA installs raw data match type |
| --- | --- | --- |
| Preload | <ul><li>The app is preloaded at the factory or is preloaded the first time the device is activated. Alternatively, a wizard prompts users to download the app when the device is first activated.</li><li>A preload event, equivalent to a click, is reported to AppsFlyer when the device is turned on for the first time.</li><li>Attribution occurs when the user opens the app for the first time.</li><li>The preload event has the highest attribution priority (unless equal attribution priority is turned on).</li></ul> | `preload_rfr` |
| Click to download | <ul><li>App installation takes place later in the device lifecycle, via push notifications, partner alternative stores, etc.</li><li>When the user engages with an ad or with a push message, the app is automatically downloaded and installed on the device without redirecting to an app store.</li><li>Attribution is awarded using the AppsFlyer last-click win rules.</li></ul> | `af_referrer` |

## View preload attribution data

Preload/click to download engagement campaign performance data is available as follows:

* **Overview dashboard:** Engagements count as clicks in aggregate reports and dashboards. They are aggregated at the preload partner (media source) and campaign levels.
* **Raw data:** Engagements are available in the clicks reports available only via Data Locker. They're found in the original URL field and can be identified in the af\_engagement\_type parameter as either preload or click\_to\_download. For installs, see the table in the previous section to see how the match type displays in raw data.

## Set up preload referrer attribution

**Prerequisites:**

* Integrate AppsFlyer [Android SDK 6.10.1+](/docs/appsflyer-android-sdk-release-notes).
* Contract with an AppsFlyer preload partner.

**To set up preload referrer attribution**:

1. In AppsFlyer, from the side menu, select **Collaborate** > **Partner Integrations** > **Active Integrations**.
2. Select the preload partner.
3. In the **Integration** tab, turn on **Preload attribution**.  
   [![](https://files.readme.io/d2c08125ca318b4bde60b51668692f21b88e292ca1b3f4fef54b77df779815cb-15585078780433.png)](https://files.readme.io/d2c08125ca318b4bde60b51668692f21b88e292ca1b3f4fef54b77df779815cb-15585078780433.png)
4. Set the **Preload lookback window** duration. Range: 1-180 days.
5. [Optional] Turn on **Preload equal attribution priority**.  
   This gives deterministic clicks the same attribution priority as preload attribution, meaning that if a deterministic click is registered between the preload referrer engagement and install, the click gets the attribution under the standard last-touch attribution logic, instead of being superseded by the preload referrer.
6. Click **Save Integration**.
7. Let the preload partner know that you are ready to attribute their campaigns.

## Samsung preload referrer

Samsung’s preload referrer integration with AppsFlyer provides you with detailed visibility from the initial app download, to first launch allowing for a clearer understanding of user behavior.

### Set up Samsung preload referrer attribution

To set up Samsung preload referrer attribution, see the [general instructions for preload referrers](#set-up-preload-referrer-attribution).

### Traits and limitations

The traits specific to Samsung preload referrer are as follows:

| Trait | Remarks |
| --- | --- |
| Integration name | samsung\_int |
| SDK version | v6.16.0 |
| Match type | `preload_rfr` |
| Overview dashboard | Engagements count as clicks in aggregate reports and dashboards. They are aggregated at the preload partner (media source) and campaign levels. |
| Raw data reports | <ul><li>Engagements are available in the clicks reports only via Data Locker.</li><li>In the install reports, the preload events are NOT found in the original URL due to Samsung’s privacy restrictions.</li><li>They can be identified in the `af_engagement_type` parameter as `preload`.</li></ul> |

<div data-zendesk-anchors="appsflyer-preload-referrer-attribution=overview h_01HEKAF7K41PH189PSCKBRF070=overview h_01HEKAF7K5CWX2P9TY8M0MTQAM=partners-supporting-preload-referrer-campaigns h_01HEKAF7K4H3HNAMEYM6C58Y29=preload-referrer-options h_01HEKAF7K4GJDDPHCFTTC75YBS=view-preload-attribution-data h_01HEKAF7K41RBRVXC6GF6PCN3Y=set-up-preload-referrer-attribution h_01JCB6K81QRK2NM983SJBYD9M3=samsung-preload-referrer h_01M2JCPMNY1ZACWQTDDGZCF2X9=set-up-samsung-preload-referrer-attribution traits-and-limitation=traits-and-limitations h_01JDPYAV86PT14C91ZQ2D9XTZ2=traits-and-limitations" />
