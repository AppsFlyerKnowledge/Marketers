---
title: "Attribution discrepancies between TikTok for Business and AppsFlyer"
excerpt: "Learn about the differences in attribution models and install reporting between TikTok for Business and AppsFlyer, and how to reduce discrepancies."
---
At a glance: Learn about the differences in attribution models between TikTok for Business and AppsFlyer.

## Overview

As two major players in the mobile user acquisition ecosystem, TikTok for Business and AppsFlyer use distinct attribution models. This may cause discrepancies between TikTok for Business and AppsFlyer dashboards. While we work closely with TikTok for Business to minimize these discrepancies, advertisers need to be aware of potential causes.

## Differences in attribution models

The table below describes possible reasons for discrepancies between the TikTok Ads Manager and the AppsFlyer dashboards:

| Cause | TikTok Ads Manager | AppsFlyer |
| --- | --- | --- |
| **Click-through attribution lookback window** | The default window is 7 days. However, this can be configured differently for Android apps and for apps that were transitioned to TikTok's self-attribution (TikTok—SRN). | The default window is 7 days. The window can be configured between 1-30 days. Make sure to align with the TikTok attribution window. |
| **View-through attribution lookback window** | The default window is 1 day. However, this can be configured differently for Android apps and for apps that were transitioned to TikTok's self-attribution (TikTok—SRN). | The default window is 1 day. The window can be configured between 1-48 hours. Make sure to align with the TikTok attribution window. |
| **Multi-channel source attribution** | TikTok self-attributes installs regardless of other media sources. | AppsFlyer uses last-click attribution (learn more about [AppsFlyer's attribution model](/docs/appsflyer-attribution-model)). |
| **Cross-device attribution** | TikTok attributes users performing both the engagement and the install using different devices, such as iOS, Android, and desktop. | AppsFlyer attributes users performing both the engagement and the install on the same device. |
| **Different timezones** | [TikTok's timezone](https://ads.tiktok.com/help/article/time-zone) (displayed next to the date range) can't be adjusted. It was configured while creating the ad account. | AppsFlyer's default app timezone is UTC+0. To match the timezone defined in the TikTok Events Manager, change the timezone set for the app on the [app settings page](/docs/app-settings#localization-time-zone). |
| **iOS attribution** | For iOS apps, the TikTok ads manager only displays SKAN attribution results | For iOS apps, AppsFlyer displays SKAN attribution results, along with AppsFlyer attribution for both SRNs and Advanced SRNs, and deduped SSOT data. Only SKAN data is expected to match in both platforms. |
| **In-app event attribution periods** | Attribution on each platform may differ based on period windows from the initial install: |
| Day 1-90 | No attribution discrepancy. Both platforms attribute in-app events to the install time. |
| Day 91-180 | After 90 days, in-app events aren't reported on TikTok. | AppsFlyer attributes in-app events to the install time. |
| Day 180+ | Due to [TikTok's data retention policy](/docs/user-level-data-retention#partner-data-retention-periods), in-app events are attributed as organic. |

## Differences in installs

In some cases, TikTok for Business includes installs that AppsFlyer rejects or doesn't account them as new installs.

### Re-engagement campaigns

A re-engagement campaign can cause users to open an app that's already installed (**re-engagement**). When AppsFlyer recognizes a previous install of the app on the same device, AppsFlyer refers to that conversion as a **re-attribution**.

Users are recorded on AppsFlyer as **new user acquisition installs** if they install the app for the first time from a TikTok for Business re-engagement campaign. Additionally, if users install the app **after the designated [re-attribution window](/docs/set-up-re-attribution-window)** following the initial install, they are also considered new acquisitions.

On the other hand, installs that occur **within the set re-attribution window** following the original install are categorized as re-attributions. These installs are visible on the AppsFlyer retargeting page. However, they might be considered new installs by TikTok for Business.

### Rejected installs when using Validation rules and Protect360

[Validation Rules](/docs/implement-validation-rules-to-prevent-fraud) and [Protect360](/docs/protect360-anti-fraud-guide) are AppsFlyer features that add protection by rejecting (blocking) certain installs. When using these features, rejected installs originating from TikTok for Business are blocked by AppsFlyer while TikTok for Business self-reports these installs.

#### Example

Jeff, the UA manager of GreatApp, creates a campaign called SPNA, which targets only Spanish speakers in North America. To verify this, Jeff defines a validation rule, that accepts users from Canada and the US only.

When a TikTok for Business user from Spain clicks and installs the app, TikTok for Business self-reports the install, while AppsFlyer rejects the install that doesn't pass the validation rule.

## Reducing discrepancies

Although there are differences in attribution models, in some cases, discrepancies can be reduced.

### Click-through and view-through attribution

AppsFlyer supports both click-through and view-through attribution. To reduce discrepancies between TikTok for Business and AppsFlyer, ensure that both the click-through and view-through lookback windows are consistent with the ones defined by TikTok for Business.

#### Example

Suppose the TikTok for Business click-through lookback window is configured on AppsFlyer to 1 day for your app `com.greatapp`, while on TikTok for Business, it's configured to the default value of 7 days. Users who click Greatapp's ad on TikTok but launch the app for the first time after 2-7 days are attributed as organic users on AppsFlyer, while TikTok for Business self-reports these users.

### In-app event attribution

The differences between platforms may also be present with post-install events (for example, in-app purchases), that are displayed on TikTok for Business and on AppsFlyer. The following table describes the most common reasons for these differences and advises on how to reduce them:

| Cause | Description | AppsFlyer's Tip |
| --- | --- | --- |
| **Self-attribution** | TikTok always attributes installs and events to its own campaigns, while AppsFlyer attributes them to the acquisition source. Such events are indicated as TikTok assists in AppsFlyer. | Combine raw data of TikTok's attributed conversions with raw data where TikTok is the contributor. |
| **Unmapped events** | AppsFlyer gets SDK-originated events, but they are not mapped to TikTok for Business and therefore aren't sent. | Make sure to [map with TikTok for Business](/docs/tiktok-for-business-advanced-srn-integration-setup#inapp-event-postbacks) in-app events that signify user quality. |
| **Unsent Revenue** | AppsFlyer gets the revenue from the SDK-originated events, but they are not sent to TikTok for Business. | Make sure to include revenue when [mapping TikTok for Business in-app events](/docs/tiktok-for-business-advanced-srn-integration-setup#inapp-event-postbacks). |
| **Missing event values on TikTok for Business** | AppsFlyer sends parameters and values to TikTok for Business as part of the events mapping, if they have the correct structures. | Build your SDK in-app events according to [AppsFlyer's recommended structures](/docs/in-app-events-event-structure) to fully map the event values with TikTok for Business. |