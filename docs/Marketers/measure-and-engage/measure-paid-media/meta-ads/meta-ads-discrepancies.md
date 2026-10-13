---
title: "Meta ads discrepancies"
excerpt: "Learn about the differences in attribution models, lookback windows, and in-app event reporting between Meta ads and AppsFlyer."
x-zendesk:
  id: 4410481130641
  url: https://support.appsflyer.com/hc/en-us/articles/4410481130641-Meta-ads-discrepancies
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Meta ads
  section_id: 6551109855761
  position: 6
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-shay-maoz, Marketers, Mobile Attribution, Agencies]
  labels: [Facebook, Advertisers, Agencies, facebook, Marketers, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2021-11-09T10:10:54Z'
  edited_at: '2025-11-17T00:01:08Z'
---
As any two major players in the mobile user acquisition eco-system, AppsFlyer and Meta ads differ in their attribution models. This may cause discrepancies to occur between Meta ads and AppsFlyer dashboards.

While we work closely with Meta ads to minimize these discrepancies, advertisers should be aware of the following causes for them.

### Detect a discrepancy between AppsFlyer and Meta ads

Compare events listed in Meta ads **Event Manager** to those in AppsFlyer reports. If the number of events varies significantly, there may be a discrepancy.

## Differences in attribution models

| Cause | Meta ads | AppsFlyer |
| --- | --- | --- |
| **Click attribution lookback window** | 7 days (Note that [there are some specific cases where the default is different](https://www.facebook.com/business/help/395050428485124?id=428636648170202)). | 1-30 days. Make sure to set to 7 days with Meta ads. |
| **View-through attribution lookback window** | 1 day (Note that [there are some specific cases where the default is different](https://www.facebook.com/business/help/395050428485124?id=428636648170202)). | 1 day by default, but can be configured to be 1-48 hours (keep this default value) |
| **Multi-channel source**<br />**attribution** | Meta ads self-attributes installs regardless of other media sources. | AppsFlyer uses last-click attribution (more information about AppsFlyer attribution available [here](/docs/appsflyer-attribution-model "AppsFlyer Attribution Model")) |
| **Cross-device attribution** | Meta ads attributes its users that click and install on different devices, for example, iOS/Android/desktop. | AppsFlyer attributes single devices, which perform both the engagement and the install |
| **Different time zones** | Meta ads default reporting time zone is PST. Make sure to [change it in Meta ads Manager](https://www.facebook.com/business/help/754049591334898) to match the app time zone defined in the app settings in AppsFlyer. | AppsFlyer's default app time zone is UTC+0. You can change the time zone set for the app in the [app settings page](/docs/app-settings#localization-time-zone) to match the time zone defined in Meta ads Manager. |
| **Install referrers** | When an install without an advertiser ID is attributed to Meta ads via the Google Play install referrer, Facebook install referrer, or Instagram install referrer, AppsFlyer does not report it back to Meta ads. This can lead to discrepancies, as it will appear in AppsFlyer but not in Meta ads. | |

## Click-through and view-through attribution

AppsFlyer supports both click-through and view-through attribution. To minimize discrepancies between Meta ads and AppsFlyer, make sure that both the Click-through and View-through lookback windows are consistent with the default ones defined by Meta ads.

Meta ads' default click-through lookback window is set to 7 days. Although [there are some specific cases where the default is different](https://www.facebook.com/business/help/395050428485124?id=428636648170202), it is recommended to set the click-through lookback window in AppsFlyer to 7 days to cover all Meta ads' default options.

We recommend configuring the attribution windows on AppsFlyer according to Meta ads values. [See Meta for Developers documentation on comparing attribution settings.](https://www.facebook.com/business/help/654970342692714)

<Image src="https://files.readme.io/215d2234aae1ec6b4e1c6ac922915851bf8ab02574a874119d286fa49c64f9ba-25899749062033.png" alt="Attribution settings comparison" />

#### Example

Suppose that the Meta ads click lookback window is configured on AppsFlyer to 1 day for your app com.greatapp, while on Meta ads it has the default value of 7 days. Users that click on Greatapp's ad on Facebook, but launch the app for the first time after 2-7 days are attributed as organic users on AppsFlyer, while Meta ads self-reports these users.

## In-app events differences

The differences between platforms may also be present with post-install events (for example, in-app purchases), that are displayed on Meta ads and on AppsFlyer. The following table describes the most common reasons for these differences and advised on how to minimize them:

| Cause | Description | AppsFlyer's Tip |
| --- | --- | --- |
| **Different lifetime definition** | A user's lifetime on Meta ads is defined as up to 7 days, meaning Meta ads doesn't show events if they occurred over 7 days after the ad click.<br />In AppsFlyer, a Meta ads user's lifetime is defined as up to 180 days. | When assessing the value of users from Meta ads campaigns that occurred after 7 days, use AppsFlyer's data to get a broader picture. |
| **Unmapped events** | AppsFlyer gets SDK originated events, but they are not mapped to Meta ads, and therefore aren't sent. | Make sure to [map with Meta ads](/docs/meta-ads-in-app-event-mapping) all the in-app events that signify users' quality. |
| **Unsent Revenue** | AppsFlyer gets the revenue from the SDK originated events, but they are not sent to Meta ads. | Make sure the **Send Revenue** boxes of the in-app events are always checked, for example, the purchase event in the capture below. |
| **Missing event values on Meta ads** | AppsFlyer sends parameters and values to Meta ads as part of the events mapping, if they have the correct structures. | Build your SDK in-app events according to [AppsFlyer's recommended structures](/docs/in-app-events-event-structure) to fully map the event values with Meta ads. |
| **Different event count** | The count for a specified in-app event (e.g., purchase event) in the Facebook (FB) dashboard differs from its corresponding count in the AppsFlyer (AF) dashboard. | The Facebook (FB) dashboard is activity-based, while the AppsFlyer (AF) Overview and Event dashboards are LTV-based. For event count comparisons, use an AF activity-based dashboard. For more information, see [LTV vs. Activity](/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports#ltv-vs-activity) |

## Installs from re-engagement campaigns in my UA dashboard?

A re-engagement campaign can cause users to open an already installed app( **re-engagement**). Alternately, when AppsFlyer recognizes a previous install of the app existed on the same device, AppsFlyer may refer to that conversion as a **re-attribution**.

If, on a re-engagement campaign, Meta ads targets **new users** or users that have installed the app for the first time **after more than the set** [**re-attribution window**](/docs/set-up-re-attribution-window) following the original installation, these users are recorded as **new user acquisition installs on AppsFlyer**, which belong to a re-engagement campaigns on Meta ads.

On the other hand, installs that take place **within the set re-attribution window** following the original installation, are considered as re-attributions and appear on the retargeting page of AppsFlyer, while they may be appearing as new installs by Meta ads.

> 📘 Note
>
> While Meta ads shows all installs of a retargeting campaign in the same place, on the AppsFlyer dashboard, installs are divided between the Overview page (new installs) and the Retargeting page (re-attribution and re-engagements).

## Cross-device attribution

Meta ads reports on cross-device attribution. This could sometimes cause issues where a campaign for one platform (iOS/Android) shows installs on another platform.

#### Example

Linda clicks on a mobile ad of GreatApp on Facebook using her Android phone. Meta ads records the click done by Linda under the original Android targeted campaign "Android Females". Linda decides to install GreatApp on her home iPad. Upon first launch, AppsFlyer asks Meta ads for the origin of this iOS install, and Meta ads answers with the campaign "Android Females".

## Validation rules and Protect360

If you use [AppsFlyer's Validation Rules](/docs/implement-validation-rules-to-prevent-fraud), results may differ between AppsFlyer and Meta ads when there are rejected installs that originally come from Meta ads. In these cases Meta ads self-reports installs to itself, while AppsFlyer rejects the same installs.

Similarly, if you use AppsFlyer's anti-fraud solution, Protect360, there may be installs since Meta ads self-reports, while AppsFlyer rejects.

#### Example

Jeff, the UA manager of GreatApp, creates a campaign called SPNA, which targets only Spanish speakers in North America. To verify this Jeff defines a validation rule, that accepts users from Canada and the US only.

When a Meta ads user from Spain clicks and installs the app, Meta ads self-reports the install, while AppsFlyer rejects the install that doesn't pass the validation rule.

## SDK related discrepancies

There could be [several occasions when advertisers implement both AppsFlyer and Facebook SDKs](/docs/meta-ads-faq#who-needs-facebooks-sdk). This might cause discrepancies for in-app events. Meta ads doesn't de-duplicate in-app events that are reported from both SDKs. This means that Meta ads may falsely report revenue and other events.

* Use **either** of the following methods to avoid duplicate in-app event reporting in Meta ads:
  * Don't configure events in the Facebook SDK.
  * Disable the [Meta ads in-app events mapping](/docs/meta-ads-in-app-event-mapping) from AppsFlyer.

## Meta probabilistic modeling (AEM) discrepancies in iOS apps

When Aggregated Event Measurement (AEM) is enabled for iOS apps, Meta may attribute installs or in-app events using its probabilistic modeling. **Meta may apply different modeling methods in its internal reporting compared to what it shares with AppsFlyer.** Due to these differences in modeling methods, install counts shown in Meta Ads Manager and AppsFlyer can vary—sometimes higher, sometimes lower. Specifically:

* Meta may record conversions internally but choose not to send corresponding AEM claims to AppsFlyer.
* Meta may send AppsFlyer an AEM claim for a modeled conversion that doesn’t appear in Ads Manager.