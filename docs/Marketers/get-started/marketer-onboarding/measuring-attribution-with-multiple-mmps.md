---
title: Measuring attribution with multiple MMPs
metadata:
  keywords:
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2023-07-27T08:29:19Z'
  edited_at: '2024-03-04T15:00:00Z'
  id: 17316973509393
  locale: en-us
  section: Marketer onboarding
  section_id: 6550866490129
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/17316973509393-Measuring-attribution-with-multiple-MMPs
---
> **At a glance:** See which media sources are able to measure attribution when working with multiple MMPs simultaneously so you can compare attribution results between AppsFlyer and your other MMP.

<div id="overview" />

## Overview

When looking into migrating from another MMP to AppsFlyer, advertisers may wish to simultaneously compare both MMP measurements over the same media sources and campaigns. To do this, the following requirements must be met:

* The tested app must have **both MMP SDKs integrated**
* The media sources must be **configured to support attribution with two MMPs**

However, not all media sources support measurement with more than one MMP.  

<div id="details-and-limitations-of-media-source-measurement" />

## Details and limitations of media source measurement

Following are details and limitations of media source measurement when working with multiple MMPs simultaneously.

<div id="self-reporting-networks" />

### Self-reporting networks

| SRN | Details and limitations | Supports measurement |
| --- | --- | --- |
| Apple Search Ads | ASA supports multiple MMP measurements without limitation. When there is an API call request from multiple MMPs, data is sent to the corresponding MMPs. | ✓ |
| DV360 (GMP) | Multiple MMPs are possible, but the campaign setup must have separate line items for each floodlight tracking (Link ID). | ✓ |
| Google Ads | Google Ads supports multiple MMP measurements:<ul><li>Advertisers can link multiple MMP Link IDs to a single Google Ads account and receive postbacks from each MMP</li><li>Google Ads can receive postbacks from multiple MMPs</li><li>Multiple MMP performances can be measured</li></ul>**Note:** Once data flows in the new MMP, Google Ads recommends stopping the existing integration. | ✓ |
| Meta ads | Meta ads receives data requests from multiple MMPs. However, they strongly recommend **not** having more than one MMP for the following reasons:<ul><li>Meta ads can only handle deduplication on installs, not for events. Therefore, events should be sent only from one MMP</li><li>When inserting multiple SDKs from MMPs there's a very high probability of issues and secondary errors during the process of deduplication</li><li>When a large amount of data is sent to Meta ads, doubled data may be fed into their optimization and measurement systems.</li></ul>Therefore, multiple MMP attribution may be supported for a short term only. | With limitation |
| Snapchat | Transferring data between Snapchat and multiple MMPs is possible. However, it’s recommended to minimize the overlapping migration period. When receiving multiple MMP data, there is no option to optimize by selecting a specific MMP. This means optimization is performed for both MMPs and overlapping data is highly likely. | With limitation |
| TikTok for Business | Sending postbacks to TikTok for Business is supported for one MMP only. When migrating from another MMP, to enable AppsFlyer to attribute conversions to TikTok for Business, you’ll first need to turn off postbacks from the other MMP and then configure AppsFlyer. | x |
| X Ads | X Ads doesn't support multiple MMP integration | x |

<div id="skan" />

### SKAN

Sending <Anchor target="_blank" href="/marketers/docs/skan-conversion-studio#skan-conversion-studio-basics">SKAN conversion postbacks</Anchor> **isn't supported for multiple MMPs**. Only one SDK can trigger sending SKAN postbacks to partners. This means that when more than one SDK is integrated into your app, SKAN postbacks are only sent to one SDK.

<div id="non-srn-ad-networks" />

### Non-SRN ad networks

MMP attribution links record the engagements of users on non-SRN ad networks and are subsequently used to attribute the engagements that become actual installs. To enable attribution for multiple MMPs simultaneously, the ad network must make sure the following requirements are met:

| Ad network requirement | Details |
| --- | --- |
| Data for a single engagement must be sent to both MMPs | <ul><li>**Clicks:** As attribution links redirect users to the app store, only one attribution link can be used. We recommend continuing to use the attribution link from the existing MMP while <Anchor target="_blank" href="/partners/docs/redirecting-users-to-the-app-store#overview">sending click-attribution data to AppsFlyer</Anchor>.</li><li>**Impressions:** As impressions don't redirect users to the app store, the ad network should send impression data to both MMPs.</li></ul> |
| Received install postbacks should be deduped | Ad networks receive install postbacks from both MMPs. To avoid double charges, the ad network should dedupe one of these postbacks. |
| Received in-app event postbacks should be deduped | When each of the MMPs is configured to send in-app event postbacks, ad networks receive in-app event postbacks from both MMPs. To avoid double attribution resulting in double charges, the ad network should dedupe one of these postbacks. If the ad network can't dedupe double in-app event postbacks, make sure in-app event postbacks are configured in only one MMP. |

<div id="owned-media" />

### Owned media

As with non-SRN ad networks, attributing installs from owned media requires using MMP attribution links. However, for some types of owned media, such as email lists, SMSs, or QR codes, MMPs can send data on a single engagement only once. AppsFlyer's <Anchor target="_blank" href="/marketers/docs/convert-your-mobile-web-visitors-to-app-users">mobile web-to-app attribution</Anchor> solution enables measuring **installs coming from a website or a landing page**. The advantage of using owned media for comparing MMP attribution is the fact that no install or event deduping is needed.

<div id="avoiding-attribution-discrepancies" />

## Avoiding attribution discrepancies

When MMPs use different attribution models to measure traffic, it may lead to discrepancies. You can minimize discrepancies with these steps:

* Make sure both MMPs use the same timezone for the app. Here's how to <Anchor target="_blank" href="/marketers/docs/changing-app-time-zone-settings">set the app timezone in AppsFlyer</Anchor>.
* For non-SRNs and owned media: Make sure to configure the attribution link using the same parameter values. For example, set the same lookback window in both MMPs.
* When comparing the data on the MMPs dashboards or reports, make sure to compare the same criteria, such as traffic from the same date range, and geo.

<div data-zendesk-anchors="ability-to-measure-with-multiple-mmps=overview 01H7TP9P86DE0J04VHXJYKE3PA=overview 01H81ANMGMEKCZCS2FNBY67321=details-and-limitations-of-media-source-measurement selfreporting-networks=self-reporting-networks 01H81APGNBGCMREZVFXJW9KN6H=self-reporting-networks 01H7TP9P86YQ75N0XFY7EW2JHQ=skan nonsrn-ad-networks=non-srn-ad-networks 01H7TP9P86TEWC47MZZVQ1965K=non-srn-ad-networks 01H7W2YTXYMAEN403WCHYH8G7W=owned-media 01H7YVHVW3YY8XY8GHQX1B0WZN=avoiding-attribution-discrepancies" />
