---
title: "Meta ads discrepancies"
excerpt: "Learn about the differences in attribution models between Meta ads and AppsFlyer."
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
## Meta ads discrepancies with AppsFlyer

As any two major players in the mobile user acquisition eco-system, AppsFlyer and Meta ads differ in their attribution models. This may cause discrepancies to occur between Meta ads and AppsFlyer dashboards.

While we work closely with Meta ads to minimize these discrepancies, advertisers should be aware of the following causes for them.

### Detect a discrepancy between AppsFlyer and Meta ads

Compare events listed in Meta ads **Event Manager** to those in AppsFlyer reports. If the number of events varies significantly, there may be a discrepancy.

## Differences in attribution models

<table><thead><tr><th>Cause</th><th>Meta ads</th><th>AppsFlyer</th></tr></thead><tbody><tr><td><span id="click-attribution-lookback-window"></span><strong>Click attribution lookback window</strong></td><td>7 days (Note that <a href="https://www.facebook.com/business/help/395050428485124?id=428636648170202">there are some specific cases where the default is different</a>).</td><td>1-30 days. Make sure to set to 7 days with Meta ads.</td></tr><tr><td><span id="viewthrough-attribution-lookback-window"></span><strong>View-through attribution lookback window</strong></td><td>1 day (Note that <a href="https://www.facebook.com/business/help/395050428485124?id=428636648170202">there are some specific cases where the default is different</a>).</td><td>1 day by default, but can be configured to be 1-48 hours (keep this default value)</td></tr><tr><td><span id="multichannel-sourceattribution"></span><strong>Multi-channel source</strong><br/><strong>attribution</strong></td><td>Meta ads self-attributes installs regardless of other media sources.</td><td>AppsFlyer uses last-click attribution (more information about AppsFlyer attribution available <a href="./appsflyer-attribution-model" title="AppsFlyer Attribution Model">here</a>)</td></tr><tr><td><span id="crossdevice-attribution"></span><strong>Cross-device attribution</strong></td><td>Meta ads attributes its users that click and install on different devices, for example, iOS/Android/desktop.</td><td>AppsFlyer attributes single devices, which perform both the engagement and the install</td></tr><tr><td><span id="different-time-zones"></span><strong>Different time zones</strong></td><td>Meta ads default reporting time zone is PST. Make sure to <a href="https://www.facebook.com/business/help/754049591334898">change it in Meta ads Manager</a> to match the app time zone defined in the app settings in AppsFlyer.</td><td>AppsFlyer's default app time zone is UTC+0. You can change the time zone set for the app in the <a href="./app-settings#localization-time-zone">app settings page</a> to match the time zone defined in Meta ads Manager.</td></tr><tr><td><span id="google-install-referrer"></span><strong>Install referrers</strong></td><td colspan="2">When an install without an advertiser ID is attributed to Meta ads via the Google Play install referrer, Facebook install referrer, or Instagram install referrer, AppsFlyer does not report it back to Meta ads. This can lead to discrepancies, as it will appear in AppsFlyer but not in Meta ads.</td></tr></tbody></table>

## Click-through and view-through attribution

AppsFlyer supports both click-through and view-through attribution. To minimize discrepancies between Meta ads and AppsFlyer, make sure that both the Click-through and View-through lookback windows are consistent with the default ones defined by Meta ads.

Meta ads' default click-through lookback window is set to 7 days. Although [there are some specific cases where the default is different](https://www.facebook.com/business/help/395050428485124?id=428636648170202), it is recommended to set the click-through lookback window in AppsFlyer to 7 days to cover all Meta ads' default options.

We recommend configuring the attribution windows on AppsFlyer according to Meta ads values. [See Meta for Developers documentation on comparing attribution settings.](https://www.facebook.com/business/help/654970342692714)

![image (13).png](https://files.readme.io/215d2234aae1ec6b4e1c6ac922915851bf8ab02574a874119d286fa49c64f9ba-25899749062033.png)

> 📘 **Example**
>
> Suppose that the Meta ads click lookback window is configured on AppsFlyer to 1 day for your app com.greatapp, while on Meta ads it has the default value of 7 days. Users that click on Greatapp's ad on Facebook, but launch the app for the first time after 2-7 days are attributed as organic users on AppsFlyer, while Meta ads self-reports these users.

## In-app events differences

The differences between platforms may also be present with post-install events (for example, in-app purchases), that are displayed on Meta ads and on AppsFlyer. The following table describes the most common reasons for these differences and advised on how to minimize them:

| Cause | Description | AppsFlyer's Tip |
| --- | --- | --- |
| <span id="different-lifetime-definition"></span>**Different lifetime definition** | A user's lifetime on Meta ads is defined as up to 7 days, meaning Meta ads doesn't show events if they occurred over 7 days after the ad click.  <br />In AppsFlyer, a Meta ads user's lifetime is defined as up to 180 days. | When assessing the value of users from Meta ads campaigns that occurred after 7 days, use AppsFlyer's data to get a broader picture. |
| <span id="unmapped-events"></span>**Unmapped events** | AppsFlyer gets SDK originated events, but they are not mapped to Meta ads, and therefore aren't sent. | Make sure to [map with Meta ads](/docs/meta-ads-in-app-event-mapping) all the in-app events that signify users' quality. |
| <span id="unsent-revenue"></span>**Unsent Revenue** | AppsFlyer gets the revenue from the SDK originated events, but they are not sent to Meta ads. | Make sure the **Send Revenue** boxes of the in-app events are always checked, for example, the purchase event in the capture below. |
| <span id="missing-event-values-on-facebook"></span>**Missing event values on Meta ads** | AppsFlyer sends parameters and values to Meta ads as part of the events mapping, if they have the correct structures. | Build your SDK in-app events according to [AppsFlyer's recommended structures](/docs/in-app-events-event-structure) to fully map the event values with Meta ads. |
| <span id="different-event-count"></span>**Different event count** | The count for a specified in-app event (e.g., purchase event) in the Facebook (FB) dashboard differs from its corresponding count in the AppsFlyer (AF) dashboard. | The Facebook (FB) dashboard is activity-based, while the AppsFlyer (AF) Overview and Event dashboards are LTV-based. For event count comparisons, use an AF activity-based dashboard. For more information, see [LTV vs. Activity](/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports#about-data-differences-and-discrepancies) |

## Installs from re-engagement campaigns in my UA dashboard?

A re-engagement campaign can cause users to open an already installed app(**re-engagement**). Alternately, when AppsFlyer recognizes a previous install of the app existed on the same device, AppsFlyer may refer to that conversion as a **re-attribution**.

If, on a re-engagement campaign, Meta ads targets **new users** or users that have installed the app for the first time **after more than the set** [**re-attribution window**](/docs/set-up-re-attribution-window) following the original installation, these users are recorded as **new user acquisition installs on AppsFlyer**, which belong to a re-engagement campaigns on Meta ads.

On the other hand, installs that take place **within the set re-attribution window** following the original installation, are considered as re-attributions and appear on the retargeting page of AppsFlyer, while they may be appearing as new installs by Meta ads.

> 📘 **Note**
>
> While Meta ads shows all installs of a retargeting campaign in the same place, on the AppsFlyer dashboard, installs are divided between the Overview page (new installs) and the Retargeting page (re-attribution and re-engagements).

## Cross-device attribution

Meta ads reports on cross-device attribution. This could sometimes cause issues where a campaign for one platform (iOS/Android) shows installs on another platform.

> 📘 **Example**
>
> Linda clicks on a mobile ad of GreatApp on Facebook using her Android phone. Meta ads records the click done by Linda under the original Android targeted campaign "Android Females". Linda decides to install GreatApp on her home iPad. Upon first launch, AppsFlyer asks Meta ads for the origin of this iOS install, and Meta ads answers with the campaign "Android Females".

## Validation rules and Protect360

If you use [AppsFlyer's Validation Rules](/docs/implement-validation-rules-to-prevent-fraud), results may differ between AppsFlyer and Meta ads when there are rejected installs that originally come from Meta ads. In these cases Meta ads self-reports installs to itself, while AppsFlyer rejects the same installs.

Similarly, if you use AppsFlyer's anti-fraud solution, Protect360, there may be installs since Meta ads self-reports, while AppsFlyer rejects.

> 📘 **Example**
>
> Jeff, the UA manager of GreatApp, creates a campaign called SPNA, which targets only Spanish speakers in North America. To verify this Jeff defines a validation rule, that accepts users from Canada and the US only.
> When a Meta ads user from Spain clicks and installs the app, Meta ads self-reports the install, while AppsFlyer rejects the install that doesn't pass the validation rule.

## SDK related discrepancies

There could be [several occasions when advertisers implement both AppsFlyer and Facebook SDKs](/docs/meta-ads-faq#who-needs-facebooks-sdk). This might cause discrepancies for in-app events. Meta ads doesn't de-duplicate in-app events that are reported from both SDKs. This means that Meta ads may falsely report revenue and other events.

* Use **either** of the following methods to avoid duplicate in-app event reporting in Meta ads:
  * Don't configure events in the Facebook SDK.
  * Disable the [Meta ads in-app events mapping](/docs/meta-ads-in-app-event-mapping) from AppsFlyer.

## Meta probabilistic modeling (AEM) discrepancies in iOS apps

When Aggregated Event Measurement (AEM) is enabled for iOS apps, Meta may attribute installs or in-app events using its probabilistic modeling. **Meta may apply different modeling methods in its internal reporting compared to what it shares with AppsFlyer.** Due to these differences in modeling methods, install counts shown in Meta Ads Manager and AppsFlyer can vary—sometimes higher, sometimes lower. Specifically:

* Meta may record conversions internally but choose not to send corresponding AEM claims to AppsFlyer.
* Meta may send AppsFlyer an AEM claim for a modeled conversion that doesn’t appear in Ads Manager.

<div data-zendesk-anchors="facebook-ads-discrepancies-with-appsflyer=meta-ads-discrepancies-with-appsflyer 01H890CZSXPMK0BDMC4202HNYM=meta-ads-discrepancies-with-appsflyer detect-a-discrepancy-between-appsflyer-and-facebook=detect-a-discrepancy-between-appsflyer-and-meta-ads 01H890CZSXGHVBH21SQA0671JQ=detect-a-discrepancy-between-appsflyer-and-meta-ads 01H890CZSX8M6VGGREYX4W2X37=differences-in-attribution-models clickthrough-and-viewthrough-attribution=click-through-and-view-through-attribution 01H890CZSX40JDGY8P8AQ4CYGS=click-through-and-view-through-attribution 01H890CZSXRD7PCZBK52GW7QE9=example inapp-events-differences=in-app-events-differences 01H890CZSXKC5JKK9051MC0VY6=in-app-events-differences installs-from-reengagement-campaigns-in-my-ua-dashboard=installs-from-re-engagement-campaigns-in-my-ua-dashboard 01H890CZSYE21K7PBQK4PNMGJR=installs-from-re-engagement-campaigns-in-my-ua-dashboard 01H890CZSY7TRCA4NVKSVPY7DB=note crossdevice-attribution::77a37a1f=cross-device-attribution 01H890CZSYS8QKEAF6799SBS8J=cross-device-attribution 01H890CZSY2Z3S6E9R5MYC1CHX=example-1 01H890CZSYDHZE4V0ZWTT8V0EJ=validation-rules-and-protect360 01H890CZSYCTQZCAYAZP9TCBBF=example-2 01H890CZSYVFPQP0SKNPWMPB1R=sdk-related-discrepancies h_01KA6NEZSRFSAJYZ5C4HJ4SKTQ=meta-probabilistic-modeling-aem-discrepancies-in-ios-apps" />
