---
title: "Self-reporting networks (SRNs)"
excerpt: "Learn about self-reporting networks (SRNs)—attribution, deep linking, iOS implications, and FAQ."
---
## SRNs integrated with AppsFlyer

| **SRN** | **Logo** |
| --- | --- |
| [Amazon Ads](https://support.appsflyer.com/hc/articles/11904659502737-Amazon-DSP-Advanced-SRN-integration) | ![amazon-ads-logo.png](https://files.readme.io/da898ff008f7fe6f9a6f845f7c170746c36bd88293632555c2a2c3db13b47414-32259457808145.png) |
| [Apple Ads](https://support.appsflyer.com/hc/articles/213747963-Apple-Search-Ads-guide) | ! |
| [Google Ads](https://support.appsflyer.com/hc/articles/115002504686-Google-Ads-AdWords-Integration-Configuration-New-API) | ! |
| [Google Marketing Platform (DV360)](https://support.appsflyer.com/hc/articles/360017595598) | ! |
| [Meta ads](https://support.appsflyer.com/hc/articles/207033826-Facebook-Ads-Setup-Guide) | ! |
| [Roku](/docs/roku-integration-with-appsflyer) | ![roku.png](https://files.readme.io/4909a45e611700e5c2a69f94710226e65e10faf620e3a7939a2c038bea1736ca-33565070184337.png) |
| [Snapchat—Advanced SRN](https://support.appsflyer.com/hc/articles/211011983-How-to-Configure-a-Campaign-with-Snapchat) | ![snapchat_logo.png](https://files.readme.io/c9b62d55d5c1497011d7411a21dca6f1668308bbe2806ab238b71742c421b182-32259457816209.png) |
| [Tencent Social Ads](https://support.appsflyer.com/hc/articles/360000264689) | ![blobid0.jpg](https://files.readme.io/0cc402a1637148cf154188286d4939af73ad83fdaecfd813eb1ae7e17ce5830f-32259428927505.png) |
| [TikTok for Business—Advanced SRN](https://support.appsflyer.com/hc/articles/6722785184913) | ![TTFB_logo__4C_horizontal_black.png](https://files.readme.io/caa8c9e02b161eea10740cb79f26d04d3324e87b9cfd929281374d2d7936ef2e-32259428903953.png) |
| [X Ads](https://support.appsflyer.com/hc/articles/4410464316049) | ![X Ads logo.png](https://files.readme.io/be88359054dba353a15beeafc13d590f5296a721b206be3f768fa606592249e6-32259428909841.png) |
| [Yahoo (Oath: Ad Platforms / Yahoo Gemini)](https://support.appsflyer.com/hc/articles/212067546-Yahoo-campaign-configuration) | ![verizonmedia.png](https://files.readme.io/36291ff556d07a5dbf2ae8ff693ea33d21dae9e0518a94b251202634a24049cf-32259428916369.png) |
| [Yahoo! Search Ads](/docs/yahoo-japan-search-ads-campaign-configuration) | ! |

> 📘 Note
>
> SRNs have [user-level data use and retention restrictions.](https://support.appsflyer.com/hc/articles/360006091197)

## Attribution

Unlike non-SRNs (ad networks), which use attribution links to report events to AppsFlyer, SRNs self-attribute using the device ID when notified of an install by AppsFlyer. For iOS apps, [SKAN](https://support.appsflyer.com/hc/articles/360011420698) and the [Aggregated Advanced Privacy framework](https://support.appsflyer.com/hc/articles/360018515798) are used for attribution.

AppsFlyer attribution for both SRNs and non-SRNs is based on:

- Last-touch and multi-touch methodologies.
- AppsFlyer standard attribution logic to sequence the relevant impression and click data.

### How does attribution work with SRNs?

SRNs report events, such as new installs and in-app events, to AppsFlyer in the following way:

- Using APIs to communicate with attribution and measurement providers.
- When third-party attribution providers detect an install, they query the network using the advertising ID.
- Reporting details of any relevant ad clicks or impressions.

After AppsFlyer performs the attribution, the customer sends in-app postbacks to the SRN for the duration of the [partner data retention period](https://support.appsflyer.com/hc/articles/360006091197-User-level-data-retention-and-sharing-limitations-of-partners#partner-data-retention-periods).

### How does attribution work with Advanced SRNs?

Advanced SRNs support the same attribution methods as standard SRNs. In addition, advanced SRNs support measurement through the [Aggregated Advanced Privacy](https://support.appsflyer.com/hc/articles/360000732237-AppsFlyer-Help-Center-glossary#aggregated-advancedprivacy) framework. Depending on the network, this may include attribution based on advertising ID where dual consent has been obtained, or campaign measurement modeling based on click and impression data.

### Install attribution

Potential app users see and interact with multiple ads before they install an app. In general, attribution providers offer last-touch attribution, which assigns an install to the last click before the actual install.

When an app is first launched:

- AppsFlyer checks that:
  - The app is set to receive traffic from SRNs.
  - The user has an advertising ID.
- If both conditions are true, AppsFlyer queries SRNs using the advertising ID.
- AppsFlyer performs attribution after considering SRN claims.

#### Install attribution examples

<Tabs>
<Tab title="Example A: Assisted attribution">

![SRN_1.png](https://files.readme.io/8e244c99f54b36a4e88b03bf05bb7ca0da2db5c7c601882ea9f68c191c38981b-32259428920337.png)

**Monday:** Network A reports a user click.

**Tuesday:** Network B reports a video engagement.

**Wednesday:** Network C reports a click on a playable ad and, 30 minutes later, there is an install.

**AppsFlyer** attributes the install to Network C and gives Networks A and B credit for assisting with the install.

AppsFlyer gives advertisers assist data (unattributed engagements that occur before an install). This lets advertisers customize their multi-touch or fractional attribution models. For more information, see [Assisted installs explained](https://support.appsflyer.com/hc/articles/207040506).

</Tab>
<Tab title="Example B: Last click attribution">

![SRN_2.png](https://files.readme.io/6817d8235acfdbbb5324d07ea8a31ace21cf2306e8e099129d9802e3e0d58b0c-32259457863825.png)

**Network D** (SRN) reports a click a few minutes before Network C.

**Network C** uses standard attribution integration.

**AppsFlyer** attributes the install to Network C as they had the last click.

</Tab>
</Tabs>

### Attribution windows

Attribution windows include lookback and view-through. Some SRNs charge advertisers for an install based on Cost per Impression (CPM) and Cost per Action (CPA)—these are based on clicks or impressions that occur within a 1-28 day period.

**AppsFlyer** attributes install, activity, Effective Cost per Install (eCPI), and Effective Cost per Action (eCPA) based on an advertiser’s preferred attribution methodology and lookback windows.

**Advertisers** may have to pay for installs based on SRN attribution lookback windows and view-through models.

- Advertisers expect the AppsFlyer third-party universal attribution methodology to optimize and allocate their ad spend.
- Why? Because AppsFlyer reports actual eCPI and eCPA based on advertiser-defined terms.
- SRNs may benefit in the short term as they often define their own payment terms. But, advertisers correct this by using third-party attribution providers.

## Deep linking with SRNs

For users to open your app when the link is clicked, you just need to set up App Links/Universal Links/URI scheme. However, to perform deep or deferred deep linking to a specific page or activity in your app, SRNs use their own methods—without involving AppsFlyer's deep linking method.

So how can you deep link your users and get the relevant data from SRNs?

### Direct deep linking

When a user device performs deep linking, direct deep linking with SRNs is done without calling the AppsFlyer deep linking method. In the example below, existing users clicking an ad are redirected to the activity directly using Facebook's methods, while new users get the same experience using AppsFlyer's conversion data. Learn how [Meta ads uses OneLink for deep linking](https://support.appsflyer.com/hc/articles/4410472805649#who-needs-facebooks-sdk)

#### Example

Jill, the mobile marketer of "greatapp", decides to run a deep linking campaign on Meta ads, targeted at general audiences. The campaign redirects any clicking users to a "bonus" activity.

Jack, the mobile developer, adds this logic after getting the conversion data:

1. Is it Facebook-originated ("is\_fb=true")?
2. If true, get the value of the ad group parameter.
3. If the value contains the word "bonus", send the user to the "bonus" activity.

### Deferred deep linking

In contrast to deep linking, deferred deep linking with SRNs is possible using the AppsFlyer GCD API. AppsFlyer receives the conversion data and makes it available to the app on the first launch. Using the conversion data, new users who install after clicking on a deep linking/retargeting campaign on an SRN can be redirected within the app upon launch.

Deferred deep linking is supported for Google Ads, Meta (provided that the FB SDK is installed on the app), Snapchat, and TikTok for Business using the actual deep link value, which can be queried via GCD using the `af_dp` field. In the case of TikTok for Business, this value can also be accessed from the `deep_link_value` field.

However, with other SRNs, the regular AppsFlyer deep linking parameters aren't present as part of the deep link data. To use this data within the app, the developer needs to employ further logic based on available parameters, such as campaign, ad set, or single ad names.

## iOS implications

Most SRNs support SKAdNetwork and have the necessary integration with AppsFlyer.

### iOS 14.5 SRN attribution

Starting iOS 14.5, when users give ATT consent in both the advertiser and publisher apps ([dual consent](https://support.appsflyer.com/hc/articles/360000732237-AppsFlyer-Help-Center-glossary#dual-consent)), SRN installs, which are recorded in the [SKAdNetwork dashboard](https://support.appsflyer.com/hc/articles/360011307357), are also shown in the traditional dashboards.

> 📘 Note
>
> - The traditional dashboard shows a reduction in installs attributed to SRNs. When considering SRN performance, use the [SKAdNetwork dashboard](https://support.appsflyer.com/hc/articles/360011307357). Overall expect a decrease in SRN attributions of installs, with a matching increase in organic installs. However, for advanced SRNs, the impact is lower, as they also support measurement via the [Aggregated Advanced Privacy](https://support.appsflyer.com/hc/articles/360018515798) framework and other privacy-preserving methods.
- The [SKAdNetwork dashboard](https://support.appsflyer.com/hc/articles/360011307357) updates with a lag of 48-72 hours after installs.
- Installs brought by Apple Ads (ASA) aren't attributed in the SKAdNetwork dashboard.

### Sending event postbacks to SRNs

SRNs receiving event postbacks rely on the device ID being included in the postback. This enables SRNs to self-attribute reported user actions. Many iOS 14 users are non-consenting, meaning they don't allow access to their device ID (IDFA). In this case, you should expect:

- A decrease in the number of event postbacks sent to SRNs
- Discrepancies in the number of event postbacks between SRNs and AppsFlyer, which log all events.

> 📘 Note
>
> - If an advertising ID is not available, postbacks for installs, app opens, or in-app events are not sent to SRNs. [However, in some cases, limited postbacks may still be sent to SRNs even when an advertiser ID is unavailable](https://support.appsflyer.com/hc/articles/360001546905#does-appsflyer-send-postbacks-for-missing-advertising-ids-idfagaid) [.](https://support.appsflyer.com/hc/articles/360001546905#does-appsflyer-send-postbacks-for-missing-advertising-ids-idfagaid)
- Click ad networks are not affected, as they use their own transaction IDs rather than device IDs to self-attribute event postback information.

## FAQ

<Accordion title="How does retargeting work with SRNs?">

Retargeting clicks from non-SRNs are easily identifiable by the existence of the `is_retargeting=true` parameter in the retargeting attribution link.

With SRNs, there is no similar indication. Instead, to enable attributing re-engagements from SRNs, AppsFlyer uses another logic:

- Pre-requisites:
  - On the **App Settings** page, turn on **Enable retargeting.**
  - In the **Active Integrations** page, select the SRN, and turn on **Retargeting**.
- With each app launch, AppsFlyer queries the SRN about recent engagements of the device ID with campaign ads for the app.
  - If the SRN responds back with engagement details, AppsFlyer validates the engagement is within the lookback window and beyond the minimum time between re-engagements.
  - Validated engagements are recorded as re-engagements and attributed to the SRN.

</Accordion>

<Accordion title="What is SRN mistargeting?">

SRN campaigns should target a specific audience, but this doesn't always happen: Non-users in user-acquisition campaigns and existing users in retargeting campaigns.

If one SRN is used to run both user acquisition and retargeting campaigns, this can lead to user mistargeting. As a result, you pay for unintended traffic.

**Scenario:** An SRN in the AppsFlyer platform is enabled for a user-acquisition campaign.

- After each app launch, AppsFlyer queries the SRN to check if the advertising ID (user) had a recent engagement.
- If yes,
  - SRN replies with the campaign name.
  - AppsFlyer determines if it was the first launch (or not) and attributes accordingly:

    **First launch**: A new install is attributed to the campaign.

    **Second or later launch**: A retargeting event is attributed to the campaign.

**Conclusion:** It is wasteful to get retargeting events from a user acquisition campaign.

#### Is mistargeting a problem?

AppsFlyer data analysts checked Meta ads **user acquisition** campaigns during a given month.

- Retargeting was enabled.
- In 30% of campaigns, at least 15% of targeted users were existing app users.
- In 5% of campaigns, at least 40% were existing app users.
- **Conclusion: In SRN user-acquisition campaigns, 1 in 10 targeted users is already an existing user.**

![mistargeted_users.png](https://files.readme.io/40a58e1fb6fb9aa01c19f82fdb9d1974c9ad243f69a791757517b977c8ea79e9-32259428927505.png)

#### Solving the mistargeting problem

**Basic solution:** Don't include existing app users in a user acquisition campaign.

- SRN will only target potential new users.
- **Maximizes new user acquisition results for the same budget**.
- Periodically (and manually) update the campaign, for example, once a month.
- However, time gaps mean that existing users may be targeted in user-acquisition campaigns during the first month after they install an app.

[**Audiences**](https://support.appsflyer.com/hc/articles/115002689186), an AppsFlyer premium feature, lets you automatically send, on a daily basis, any segment of your user base to dozens of ad networks.

AppsFlyer research shows that solving mistargeting can have a dramatic impact on your marketing and user acquisition efforts.

</Accordion>

<Accordion title="Why is the Original URL field empty in raw data reports?">

Click is performed in the SRN environment but without an AppsFlyer attribution link. Therefore, the click's associated Original URL data is not available to AppsFlyer.

</Accordion>

<Accordion title="Dashboard doesn't show SRN clicks and impressions">

Click is performed in the SRN environment but without an AppsFlyer attribution link. Therefore, some SRNs don't give click and impression data to AppsFlyer.

[Meta Ads](https://support.appsflyer.com/hc/articles/207033826-Facebook-Ads-setup-guide#cost-clicks-and-impressions) and [Google](https://support.appsflyer.com/hc/articles/4417309205521) provide aggregated data to AppsFlyer.

</Accordion>

<Accordion title="Can agencies configure SRN campaigns?">

Yes, [see here about SRN configuration by Agencies](https://support.appsflyer.com/hc/articles/207034106-Agency-Accounts-All-You-Need-To-Know#selfreporting-ad-networks).

</Accordion>

<Accordion title="Can postbacks be sent when the advertising ID is not available?">

When advertising IDs contain an empty string (“”) or show the value ‘00000000-0000-0000-0000-000000000000’ (zeroed IDFAs), postbacks for installs, app opens, or in-app events are not sent, except for the following scenarios:

- Google Ads: As part of the integration for remarketing measurement with Google Ads, when double consent is not obtained, and a user performs an app open or in-app event, `gbraid` and event info is sent to Google Ads (for the `additional_data_json` event).
- Google Ads: On Android, when there’s no device ID, but the referrer value contains a `gclid` (for installs) or a re-engagement event contains a deep link with the `gclid` parameter, the `gclid` and event info is sent to Google Ads.
- Meta: Facebook cookie or campaign IDs (on deep link or previous re-engagement) or AEM toggle enabled.
- Snapchat and [TikTok for Business—Advanced SRN](https://support.appsflyer.com/hc/articles/6722785184913): If an install is attributed to Snapchat or TikTok via probabilistic modeling and an in-app event tied to that install arrives, the postback is sent.

**Google Ads** `gbraid` **parameter:** An aggregated identifier generated by Google that identifies a group of devices and is referenced by the deep link.

**Google Click ID (** `gclid` **parameter):** A parameter passed in the URL with ad clicks, that identifies the campaign and other click attributes that are associated with the ad. This is used for ad tracking and campaign attribution.

</Accordion>

<Accordion title="Are clicks and impressions from SRNs available in raw data reports?">

No, clicks and impressions from SRNs are not shared in raw data reports. While SRN data is used for attribution, raw clicks and impressions are not included in reports. This applies to all SRNs, including TikTok, Snap, Meta, and Google.

</Accordion>