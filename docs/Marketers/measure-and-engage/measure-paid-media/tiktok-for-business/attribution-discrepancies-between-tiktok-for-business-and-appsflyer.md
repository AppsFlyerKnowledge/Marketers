---
title: Attribution discrepancies between TikTok for Business and AppsFlyer
excerpt: >-
  Learn about the differences in attribution models between TikTok for Business
  and AppsFlyer.
metadata:
  keywords:
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2023-10-30T07:45:29Z'
  edited_at: '2024-05-01T00:00:56Z'
  id: 19733501619473
  locale: en-us
  section: TikTok for Business
  section_id: 12192554266385
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/19733501619473-Attribution-discrepancies-between-TikTok-for-Business-and-AppsFlyer
---
## Overview

As two major players in the mobile user acquisition ecosystem, TikTok for Business and AppsFlyer use distinct attribution models. This may cause discrepancies between TikTok for Business and AppsFlyer dashboards. While we work closely with TikTok for Business to minimize these discrepancies, advertisers need to be aware of potential causes.

## Differences in attribution models

The table below describes possible reasons for discrepancies between the TikTok Ads Manager and the AppsFlyer dashboards:

<table><thead><tr><th>Cause</th><th>TikTok Ads Manager</th><th>AppsFlyer</th></tr></thead><tbody><tr><td><span id="click-attribution-lookback-window"></span><p><strong>Click-through attribution lookback window</strong></p></td><td><p>The default window is 7 days. However, this can be configured differently for Android apps and for apps that were transitioned to TikTok's self-attribution (TikTok—SRN).</p></td><td><p>The default window is 7 days. The window can be configured between 1-30 days. Make sure to align with the TikTok attribution window.</p></td></tr><tr><td><span id="viewthrough-attribution-lookback-window"></span><p><strong>View-through attribution lookback window</strong></p></td><td><p>The default window is 1 day. However, this can be configured differently for Android apps and for apps that were transitioned to TikTok's self-attribution (TikTok—SRN).</p></td><td><p>The default window is 1 day. The window can be configured between 1-48 hours. Make sure to align with the TikTok attribution window.</p></td></tr><tr><td><span id="multichannel-sourceattribution"></span><p><strong>Multi-channel source attribution</strong></p></td><td><p>TikTok self-attributes installs regardless of other media sources.</p></td><td><p>AppsFlyer uses last-click attribution (learn more about <a href="./appsflyer-attribution-model">AppsFlyer's attribution model</a>).</p></td></tr><tr><td><span id="crossdevice-attribution"></span><p><strong>Cross-device attribution</strong></p></td><td><p>TikTok attributes users performing both the engagement and the install using different devices, such as iOS, Android, and desktop.</p></td><td><p>AppsFlyer attributes users performing both the engagement and the install on the same device.</p></td></tr><tr><td><span id="different-time-zones"></span><p><strong>Different timezones</strong></p></td><td><p><a href="https://ads.tiktok.com/help/article/time-zone">TikTok's timezone</a> (displayed next to the date range) can't be adjusted. It was configured while creating the ad account.</p></td><td><p>AppsFlyer's default app timezone is UTC+0. To match the timezone defined in the TikTok Events Manager, change the timezone set for the app on the <a href="./app-settings#localization-time-zone">app settings page</a>.</p></td></tr><tr><td><span id="ios-attribution"></span><p><strong>iOS attribution</strong></p></td><td><p>For iOS apps, the TikTok ads manager only displays SKAN attribution results</p></td><td><p>For iOS apps, AppsFlyer displays SKAN attribution results, along with AppsFlyer attribution for both SRNs and Advanced SRNs, and deduped SSOT data. Only SKAN data is expected to match in both platforms. </p></td></tr><tr><td><span id="in-app-event-attribution-periods"></span><p><strong>In-app event attribution periods</strong></p></td><td colspan="2"><p>Attribution on each platform may differ based on period windows from the initial install:</p></td></tr><tr><td><span id="day-1-90"></span><p>Day 1-90</p></td><td colspan="2"><p>No attribution discrepancy. Both platforms attribute in-app events to the install time.</p></td></tr><tr><td><span id="day-91-180"></span><p>Day 91-180</p></td><td rowspan="2"><p>After 90 days, in-app events aren't reported on TikTok.</p></td><td><div><div><div>AppsFlyer attributes in-app events to the install time.</div></div></div></td></tr><tr><td><span id="day-180"></span><p>Day 180+</p></td><td><div><div><div>Due to <a href="./user-level-data-retention#partner-data-retention-periods">TikTok's data retention policy</a>, in-app events are attributed as organic.</div></div></div></td></tr></tbody></table>

## Differences in installs

In some cases, TikTok for Business includes installs that AppsFlyer rejects or doesn't account them as new installs.

### Re-engagement campaigns

A re-engagement campaign can cause users to open an app that's already installed (**re-engagement**). When AppsFlyer recognizes a previous install of the app on the same device, AppsFlyer refers to that conversion as a **re-attribution**.

Users are recorded on AppsFlyer as **new user acquisition installs** if they install the app for the first time from a TikTok for Business re-engagement campaign. Additionally, if users install the app **after the designated [re-attribution window](/docs/set-up-re-attribution-window)** following the initial install, they are also considered new acquisitions.

On the other hand, installs that occur **within the set re-attribution window** following the original install are categorized as re-attributions. These installs are visible on the AppsFlyer retargeting page. However, they might be considered new installs by TikTok for Business.

### Rejected installs when using Validation rules and Protect360

[Validation Rules](/docs/implement-validation-rules-to-prevent-fraud) and [Protect360](/docs/protect360-anti-fraud-guide) are AppsFlyer features that add protection by rejecting (blocking) certain installs. When using these features, rejected installs originating from TikTok for Business are blocked by AppsFlyer while TikTok for Business self-reports these installs.

> 📘 **Example**
>
> Jeff, the UA manager of GreatApp, creates a campaign called SPNA, which targets only Spanish speakers in North America. To verify this, Jeff defines a validation rule, that accepts users from Canada and the US only.
> When a TikTok for Business user from Spain clicks and installs the app, TikTok for Business self-reports the install, while AppsFlyer rejects the install that doesn't pass the validation rule.

## Reducing discrepancies

Although there are differences in attribution models, in some cases, discrepancies can be reduced.

### Click-through and view-through attribution

AppsFlyer supports both click-through and view-through attribution. To reduce discrepancies between TikTok for Business and AppsFlyer, ensure that both the click-through and view-through lookback windows are consistent with the ones defined by TikTok for Business.

> 📘 **Example**
>
> Suppose the TikTok for Business click-through lookback window is configured on AppsFlyer to 1 day for your app `com.greatapp`, while on TikTok for Business, it's configured to the default value of 7 days. Users who click Greatapp's ad on TikTok but launch the app for the first time after 2-7 days are attributed as organic users on AppsFlyer, while TikTok for Business self-reports these users.

### In-app event attribution

The differences between platforms may also be present with post-install events (for example, in-app purchases), that are displayed on TikTok for Business and on AppsFlyer. The following table describes the most common reasons for these differences and advises on how to reduce them:

| Cause | Description | AppsFlyer's Tip |
| --- | --- | --- |
| <span id="selfattribution"></span>**Self-attribution** | TikTok always attributes installs and events to its own campaigns, while AppsFlyer attributes them to the acquisition source. Such events are indicated as TikTok assists in AppsFlyer. | Combine raw data of TikTok's attributed conversions with raw data where TikTok is the contributor. |
| <span id="unmapped-events"></span>**Unmapped events** | AppsFlyer gets SDK-originated events, but they are not mapped to TikTok for Business and therefore aren't sent. | Make sure to [map with TikTok for Business](/docs/tiktok-for-business-advanced-srn-integration-setup#in-app-event-postbacks) in-app events that signify user quality. |
| <span id="unsent-revenue"></span>**Unsent Revenue** | AppsFlyer gets the revenue from the SDK-originated events, but they are not sent to TikTok for Business. | Make sure to include revenue when [mapping TikTok for Business in-app events](/docs/tiktok-for-business-advanced-srn-integration-setup#in-app-event-postbacks). |
| <span id="missing-event-values-on-tiktok"></span>**Missing event values on TikTok for Business** | AppsFlyer sends parameters and values to TikTok for Business as part of the events mapping, if they have the correct structures. | Build your SDK in-app events according to [AppsFlyer's recommended structures](/docs/in-app-events-event-structure) to fully map the event values with TikTok for Business. |

<div data-zendesk-anchors="h_01HFXTVVZNJQJFAAR1F3HW1D5M=overview h_01HFXTVVZN79JX9E5PTXMPB8BS=differences-in-attribution-models h_01HFXTVVZNDQKNW85BBWR0PE2Z=differences-in-installs reengagement-campaigns=re-engagement-campaigns h_01HFXTVVZNA1R59KCA41H2YSBJ=re-engagement-campaigns h_01HFXTVVZNJVFHE0W5DTP5PDCG=rejected-installs-when-using-validation-rules-and-protect360 01H890CZSYCTQZCAYAZP9TCBBF=example minimizing-discrepancies=reducing-discrepancies h_01HFXTVVZNW9GZB8QYMR1KTNMN=reducing-discrepancies clickthrough-and-viewthrough-attribution=click-through-and-view-through-attribution h_01HFXTVVZNN45WY997DK9K8WA4=click-through-and-view-through-attribution h_01HFRQMF6HTT84J4EDFXZMK7CP=example-1 inapp-event-attribution=in-app-event-attribution h_01HFXTVVZNG7TKQVY1229X594G=in-app-event-attribution" />
