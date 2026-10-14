---
title: Discrepancies between AppsFlyer and third-party platforms
excerpt: >-
  Learn about the reasons for differences in attribution between AppsFlyer and
  third-party platforms.
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2023-10-16T08:59:17Z'
  edited_at: '2026-08-14T16:14:52Z'
  id: 19384888063249
  locale: en-us
  section: Integrate 3rd-party platforms
  section_id: 6551084534545
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/19384888063249-Discrepancies-between-AppsFlyer-and-third-party-platforms
---
## Overview

Due to media sources' data-sharing policies, not all user-level [data is shared with third-party platforms](/docs/about-raw-data-identifier-restrictions#media-source-restrictions) (such as analytics and marketing platforms). For these reasons, there may be discrepancies in attribution between data displayed on third-party platforms and data in AppsFlyer.

**Note**

Aggregated and analytics data from the AppsFlyer platform is available without limitation.

## Postback restrictions on third-party platforms

When it comes to sending postbacks to third-party platforms, there are different levels of media source restrictions. Postbacks can either not be sent at all, be sent without attribution, or be sent without restriction.

#### Types of postback restrictions

<div id="no-postbacks-sent" />

<Accordion title="No postbacks are sent">

Postbacks for raw data events restricted by media sources, as detailed in [this table](/docs/about-raw-data-identifier-restrictions#media-source-restrictions), aren't sent to third-party platforms. This means third-party platforms don't get postbacks of such events, leading to less attribution on their platform compared to AppsFlyer.

</Accordion>

<div id="postbacks-with-no-attribution" />

<Accordion title="Postbacks are sent with no attribution">

For events other than restricted raw data events, the ad networks listed below require advertisers to redact the media source when sharing postbacks to third-party platforms. AppsFlyer does this by **substituting the original media source with organic attribution**. This means postbacks of such events sent to third-party platforms don't include attribution to the media source, leading to less attribution on their platform compared to AppsFlyer:

* Amazon
* Meta ads
* Pinterest
* Snapchat ([TOS](https://businesshelp.snapchat.com/en-US/article/attribution-terms))
* X Ads
* Bing
* Yahoo (Oath: Ad Platforms / Yahoo Gemini)

**Note**

For Meta ads, postback behavior depends on whether the advertiser has accepted the Advanced Mobile Measurement (AMM) terms:

* **AMM not accepted:** Postbacks are sent only for installs [attributed by an install referrer](/docs/appsflyer-attribution-model#install-referrer-android-only). The postbacks do not include attribution data.
* **AMM accepted:** Postbacks are sent for installs attributed by [all attribution methods](/docs/appsflyer-attribution-model#attribution-methods). However, the postback data does not include attribution data, meaning all postbacks are sent to third-party platforms as unattributed (organic) data.

</Accordion>

<div id="regular-postbacks" />

<Accordion title="Regular postbacks">

All other events that aren't restricted or the media source isn't redacted are sent as regular postbacks. This includes aggregated events.

</Accordion>

<table><colgroup><col/><col/><col/><col/><col/><col/></colgroup><thead><tr><th colspan="6">Postback restrictions are applicable to all third-party platforms integrated with AppsFlyer, including the following:</th></tr></thead><tbody><tr><td><span id="airship"></span>Airship</td><td>Amplitude</td><td>Batch</td><td>Braze</td><td>CleverTap</td><td>Cloud</td></tr><tr><td><span id="convertro"></span>Convertro</td><td>deltaDNA</td><td>Eulerian</td><td>GameAnalytics</td><td>IBM UBX</td><td>Insider</td></tr><tr><td><span id="itunes"></span>iTunes</td><td>Kahuna</td><td>Leanplum</td><td>Liquid</td><td>Localytics</td><td>Luna labs</td></tr><tr><td><span id="Medialyzer"></span>Medialyzer</td><td>Mixpanel</td><td>MoEngage</td><td>mParticle</td><td>OneSignal</td><td>Rocketbox</td></tr><tr><td><span id="salesforce"></span>Salesforce</td><td>Marketing</td><td>MobilePush</td><td>Segment</td><td>Spoteffects</td><td>Swrve</td></tr><tr><td><span id="tapcart"></span>Tapcart</td><td>Tealium</td><td>WebEngage</td><td>Winclap Analytics</td><td>Google Analytics 4</td><td> </td></tr></tbody></table>

## Examples of discrepancies

<div id="example-1" />

<Accordion title="Raw data restrictions on Mixpanel">

<Accordion title="AMM not accepted">

**Example 1**

An advertiser uses Meta ads to place an ad. They are also working with Mixpanel to better understand how users behave and interact with their app. The advertiser checks to see the number of installs attributed to Meta ads in the last month:

| On AppsFlyer | On Mixpanel |
| --- | --- |
| The advertiser sees 100 installs attributed to Meta ads.<br /><br />30 of the installs were attributed using the `gp_referrer` parameter. These events are not restricted and appear in raw data reports. | The advertiser sees only 30 installs attributed to organic.<br /><br />Mixpanel does not get postbacks for the 70 restricted events. The postbacks for the 30 installs attributed using the `gp_referrer` parameter are sent as organic. |

</Accordion>

<Accordion title="AMM accepted">

**Example 1**

An advertiser uses Meta ads to place an ad and has accepted the AMM terms. They are also working with Mixpanel to better understand how users behave and interact with their app. The advertiser checks to see the number of installs attributed to Meta ads in the last month:

| On AppsFlyer | On Mixpanel |
| --- | --- |
| The advertiser sees 100 installs attributed to Meta ads.<br /><br />The install raw data report will include all 100 installs, not just the installs attributed via the gp\_referrer method | The advertiser sees 100 installs attributed to organic.<br /><br />Because AMM is accepted, Mixpanel receives postbacks for all 100 installs. However, none of the postbacks include attribution data, so all installs appear as organic. |

</Accordion>

</Accordion>

<div id="example-2" />

<Accordion title="Raw data restrictions on MoEngage">

**Example 2**

An advertiser uses Pinterest to place an ad. They're also working with MoEngage to get insights on customer engagement. The advertiser checks to see how many "Add to wishlist" events were attributed to Pinterest in the last month:

| On AppsFlyer | On MoEngage |
| --- | --- |
| The advertiser sees 97 "Add to wishlist" events attributed to Pinterest. | The advertiser doesn't see any "Add to wishlist" events attributed to Pinterest. MoEngage didn't get click-through and view-through event postbacks from Pinterest since they're restricted events. |

</Accordion>

<div id="example-3" />

<Accordion title="Restrictions on Airship">

**Example 3**

An advertiser uses Bing to place an ad. They're also working with Airship to optimize the user journey on their mobile app. The advertiser checks to see how many purchase events were attributed to Bing in the last month:

| On AppsFlyer | On Airship |
| --- | --- |
| The advertiser sees 35 purchase events attributed to Bing. | The advertiser sees 84 purchase events from organic sources. 35 of them came from Bing, but they wouldn't know that since those purchase events appear as organic. |

</Accordion>

**See also**

FAQs on [raw data content restrictions](/docs/about-raw-data-identifier-restrictions#faq).

<div data-zendesk-anchors="Overview=overview h_01HCVTKD7ZH991A8JF7XCNNE91=overview postback-restrictions=postback-restrictions-on-third-party-platforms h_01HDDR9JG5303R38QCAB2ZF6CW=postback-restrictions-on-third-party-platforms h_01HE05EXEFJF6SGYTKZ78FPP7Z=types-of-postback-restrictions h_01HDDRVF8J36N3J9AB3YRD8TZP=no-postbacks-sent h_01HDDRVF8JP2FWCA7PH58TZDBY=postbacks-with-no-attribution h_01HDDRVF8J9QRWN8MCKXRV0J3M=regular-postbacks examples=examples-of-discrepancies h_01HCW4HS35ZTAEWPXB9JKCR725=examples-of-discrepancies h_01HDDS499QJTX5RJY6CR98BDFB=example-1 h_01HDDS499QG48D1AFR3Z59J1HP=example-2 h_01KQZ0Q440XSG96Q3W65RYVYAG=example-3" />
