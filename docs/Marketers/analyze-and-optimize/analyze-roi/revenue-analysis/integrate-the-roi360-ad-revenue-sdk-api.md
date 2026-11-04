---
title: Integrate the ROI360 ad revenue SDK API
metadata:
  keywords:
    - ROI
    - ad revenue
    - Advertisers
    - Advertiser
    - Developer
    - Developers
    - ad revenue SDK
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2022-01-12T09:09:07Z'
  edited_at: '2026-06-25T15:09:37Z'
  id: 4416353506833
  locale: en-us
  section: Revenue analysis
  section_id: 6551069075089
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/4416353506833-Integrate-the-ROI360-ad-revenue-SDK-API
---
> **At a glance:** The AppsFlyer ad revenue SDK API works with ad networks to report ad revenue with impression-level granularity.

![mceclip1__1_.png](https://files.readme.io/202ded6950dfbf370bb48738876224936d28ecfae0c0aba09d1c49892b774cb5-31202279100177.png)

<div id="impression-level-ad-revenue-reporting-by-sdk-api" />

## Impression-level ad revenue reporting by SDK API

**Ad revenue reporting options**

Ad revenue is reported to AppsFlyer by either aggregate granularity (via API) or impression-level granularity (via SDK). Impression-level data via SDK:

* Has better data freshness and earlier availability in AppsFlyer.
* Supports SKAN.
* Is for AppsFlyer SDK V6.15+. For earlier SDK versions, an SDK connector is used instead of the API. Links for developers are included in this documentation where relevant.

**Note:**

* Ad revenue impressions are collected and processed in AppsFlyer, but aren't counted against your in-apps package.
* See the complete <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/gs-ad-revenue">list of SDK plugins that support the Ad Revenue SDK API</Anchor>.

<div id="reporting-ad-revenue-using-the-sdk-api" />

### Reporting ad revenue using the SDK API

**SDK principles of operation**

The ad revenue SDK API sends impression revenue data to the AppsFlyer SDK. These impression events are collected and processed in AppsFlyer, and ad revenue event, `af_ad_revenue` , is generated in the platform with the revenue attributed to the original UA source.

**Data display**

The `af_ad_revenue` event is used to identify ad revenue. This event is used throughout the platform including dashboards and other data delivery tools.

**Supported networks**

The list of supported ad revenue mediation and monetization networks that can send us data via the ad revenue SDK API is as follows:

* <Anchor target="_blank" href="/marketers/docs/ironsource-campaign-configuration#ad-revenue-tab">Unity LevelPlay mediation</Anchor> (formerly ironSource)
* <Anchor target="_blank" href="/marketers/docs/applovin-max-ad-revenue-configuration">Applovin Max</Anchor>
* <Anchor target="_blank" href="/marketers/docs/google-admob-ad-revenue-attribution-configuration">Google AdMob</Anchor>
* <Anchor target="_blank" href="/marketers/docs/fyber-campaign-configuration">Fyber</Anchor>
* <Anchor target="_blank" href="/marketers/docs/appodeal-campaign-configuration">Appodeal</Anchor>
* Admost
* Topon
* Topon Pte.
* Tradplus
* <Anchor target="_blank" href="/marketers/docs/yandex-direct-campaign-configuration">Yandex</Anchor>
* <Anchor target="_blank" href="/marketers/docs/chartboost-campaign-configuration">Chartboost</Anchor>
* customMediation (when the mediation solution is not in the list of supported mediation partners)
* directMonetizationNetwork (when the app integrates directly with monetization networks without mediation)

**Data freshness**

The **SDK API sends the revenue data to the platform at the time the ad displays. For ROI360 premium customers, the data becomes available in:**

* **The DataLocker impression level topic at 1 AM and every 1 hour thereafter,**
* **The AppsFlyer Activity and Cohort reports at 5 AM UTC, and every 4 hours thereafter.**

<div id="implementing-appsflyer-ad-revenue-sdk-api" />

## Implementing AppsFlyer ad revenue SDK API

**To implement the AppsFlyer ad revenue SDK API**:

1. <Anchor target="_blank" href="/marketers/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">Enable SDK-level ad revenue in AppsFlyer</Anchor> for the partner you want to connect. **Note**: This needs to be done for each app individually.
2. Tell your developer to integrate the AppsFlyer ad revenue SDK API using <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/gs-ad-revenue">these instructions</Anchor>.
3. To record ad revenue in your SKAdNetwork dashboard, follow the <Anchor target="_blank" href="/marketers/docs/skadnetwork-skan-solution-guide#recording-ad-revenue">SKAN ad revenue instructions</Anchor>.
4. Test your integration: once integrated, verify that ad revenue events are being received using either of the following methods:
   * In the <Anchor target="_blank" href="/marketers/docs/testing-the-sdk-integration-for-marketers#view-live-events">Live Events viewer</Anchor>, check that ad revenue events appear in real time. Note that the Live Events viewer only displays events sent from registered test devices.
   * On the **Revenue Settings** page, edit the relevant ad revenue integration and click **Test Connection** to check whether any valid ad revenue events were recently processed. For more information, see <Anchor target="_blank" href="/marketers/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">Connect to ad revenue integrated partners</Anchor>.

<div id="traits-and-limitations" />

## Traits and limitations

| Trait | Remarks |
| --- | --- |
| Admob | <ul><li>To turn on iLTV for Admob, follow <Anchor target="_blank" href="https://support.google.com/admob/answer/11322405#getstarted">this link</Anchor></li><li>For Android and Unity, impression revenue is reported by the Admob iLTV SDK in <Anchor target="_blank" href="https://developers.google.com/android/reference/com/google/android/gms/ads/AdValue#public-long-getvaluemicros">micro-units</Anchor>. For the correct ad revenue amount in USD to display in AppsFlyer, before sending the ad revenue amount to AppsFlyer, divide the amount extracted from the iLTV event handler by 1 million.</li></ul> |
| Ad revenue value | Impression events with revenue values above $10 (and the equivalent in other currencies) aren't processed by the SDK API. |

<div data-zendesk-anchors="impressionlevel-ad-revenue-reporting-by-sdk-API=impression-level-ad-revenue-reporting-by-sdk-api 01H8HHAQHK6CDK8X2Y6N4GANNC=impression-level-ad-revenue-reporting-by-sdk-api reporting-ad-revenue-using-the-sdk-API=reporting-ad-revenue-using-the-sdk-api 01H8HHAQHKQ3H3R21Z1JYNJ2EE=reporting-ad-revenue-using-the-sdk-api implementing-generic-appsflyer-ad-revenue-sdk-API=implementing-appsflyer-ad-revenue-sdk-api 01H8HHAQHKCXKPJJE8EDT1J9CR=implementing-appsflyer-ad-revenue-sdk-api 01H8HHAQHMCSVQ2ZAT3G7XJKAN=traits-and-limitations" />
