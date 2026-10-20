---
title: Integrate the ROI360 ad revenue SDK API
excerpt: >-
  The AppsFlyer ad revenue SDK API works with ad networks to report ad revenue
  with impression-level granularity.
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
![mceclip1__1_.png](https://files.readme.io/202ded6950dfbf370bb48738876224936d28ecfae0c0aba09d1c49892b774cb5-31202279100177.png)

## Impression-level ad revenue reporting by SDK API

**Ad revenue reporting options**

Ad revenue is reported to AppsFlyer by either aggregate granularity (via API) or impression-level granularity (via SDK). Impression-level data via SDK:

* Has better data freshness and earlier availability in AppsFlyer.
* Supports SKAN.
* Is for AppsFlyer SDK V6.15+. For earlier SDK versions, an SDK connector is used instead of the API. Links for developers are included in this documentation where relevant.

**Note:**

* Ad revenue impressions are collected and processed in AppsFlyer, but aren't counted against your in-apps package.
* See the complete [list of SDK plugins that support the Ad Revenue SDK API](https://dev.appsflyer.com/hc/docs/gs-ad-revenue).

### Reporting ad revenue using the SDK API

**SDK principles of operation**

The ad revenue SDK API sends impression revenue data to the AppsFlyer SDK. These impression events are collected and processed in AppsFlyer, and ad revenue event, `af_ad_revenue` , is generated in the platform with the revenue attributed to the original UA source.

**Data display**

The `af_ad_revenue` event is used to identify ad revenue. This event is used throughout the platform including dashboards and other data delivery tools.

**Supported networks**

The list of supported ad revenue mediation and monetization networks that can send us data via the ad revenue SDK API is as follows:

* [Unity LevelPlay mediation](/docs/ironsource-campaign-configuration#ad-revenue-tab) (formerly ironSource)
* [Applovin Max](/docs/applovin-max-ad-revenue-configuration)
* [Google AdMob](/docs/google-admob-ad-revenue-attribution-configuration)
* [Fyber](/docs/fyber-campaign-configuration)
* [Appodeal](/docs/appodeal-campaign-configuration)
* Admost
* Topon
* Topon Pte.
* Tradplus
* [Yandex](/docs/yandex-direct-campaign-configuration)
* [Chartboost](/docs/chartboost-campaign-configuration)
* customMediation (when the mediation solution is not in the list of supported mediation partners)
* directMonetizationNetwork (when the app integrates directly with monetization networks without mediation)

**Data freshness**

The **SDK API sends the revenue data to the platform at the time the ad displays. For ROI360 premium customers, the data becomes available in:**

* **The DataLocker impression level topic at 1 AM and every 1 hour thereafter,**
* **The AppsFlyer Activity and Cohort reports at 5 AM UTC, and every 4 hours thereafter.**

## Implementing AppsFlyer ad revenue SDK API

**To implement the AppsFlyer ad revenue SDK API**:

1. [Enable SDK-level ad revenue in AppsFlyer](/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners) for the partner you want to connect. **Note**: This needs to be done for each app individually.
2. Tell your developer to integrate the AppsFlyer ad revenue SDK API using [these instructions](https://dev.appsflyer.com/hc/docs/gs-ad-revenue).
3. To record ad revenue in your SKAdNetwork dashboard, follow the [SKAN ad revenue instructions](/docs/skadnetwork-skan-solution-guide#recording-ad-revenue).
4. Test your integration: once integrated, verify that ad revenue events are being received using either of the following methods:
   * In the [Live Events viewer](/docs/testing-the-sdk-integration-for-marketers#view-live-events), check that ad revenue events appear in real time. Note that the Live Events viewer only displays events sent from registered test devices.
   * On the **Revenue Settings** page, edit the relevant ad revenue integration and click **Test Connection** to check whether any valid ad revenue events were recently processed. For more information, see [Connect to ad revenue integrated partners](/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners).

## Traits and limitations

| Trait | Remarks |
| --- | --- |
| Admob | <ul><li>To turn on iLTV for Admob, follow [this link](https://support.google.com/admob/answer/11322405#getstarted)</li><li>For Android and Unity, impression revenue is reported by the Admob iLTV SDK in [micro-units](https://developers.google.com/android/reference/com/google/android/gms/ads/AdValue#public-long-getvaluemicros). For the correct ad revenue amount in USD to display in AppsFlyer, before sending the ad revenue amount to AppsFlyer, divide the amount extracted from the iLTV event handler by 1 million.</li></ul> |
| Ad revenue value | Impression events with revenue values above $10 (and the equivalent in other currencies) aren't processed by the SDK API. |

<div data-zendesk-anchors="impressionlevel-ad-revenue-reporting-by-sdk-API=impression-level-ad-revenue-reporting-by-sdk-api 01H8HHAQHK6CDK8X2Y6N4GANNC=impression-level-ad-revenue-reporting-by-sdk-api reporting-ad-revenue-using-the-sdk-API=reporting-ad-revenue-using-the-sdk-api 01H8HHAQHKQ3H3R21Z1JYNJ2EE=reporting-ad-revenue-using-the-sdk-api implementing-generic-appsflyer-ad-revenue-sdk-API=implementing-appsflyer-ad-revenue-sdk-api 01H8HHAQHKCXKPJJE8EDT1J9CR=implementing-appsflyer-ad-revenue-sdk-api 01H8HHAQHMCSVQ2ZAT3G7XJKAN=traits-and-limitations" />
