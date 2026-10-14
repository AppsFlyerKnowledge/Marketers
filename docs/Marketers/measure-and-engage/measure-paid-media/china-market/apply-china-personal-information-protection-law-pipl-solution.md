---
title: Apply China Personal Information Protection Law (PIPL) solution
excerpt: Improve flexibility while measuring with AppsFlyer and complying with PIPL.
metadata:
  keywords:
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2022-05-10T08:59:00Z'
  edited_at: '2025-08-11T12:06:31Z'
  id: 6031419375377
  locale: en-us
  section: China market
  section_id: 6552042145425
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/6031419375377-Apply-China-Personal-Information-Protection-Law-PIPL-solution
---
## Background

In late 2021, China passed the Personal Information Protection Laws (PIPL) which regulates the collection, use, and transfer of user personal data. To provide customers with additional flexibility while using AppsFlyer and to support PIPL compliance, follow the step-by-step instructions described in this article.  
The AppsFlyer PIPL solution is based on 3 principles:

* Prevent the SDK from collecting device IDs.
* Mask and hash IPs of SDK events, S2S events, and clicks and impressions.
* Enable auditing all app events on a relay server in China.

## Apply PIPL solution in AppsFlyer

The following section describes the actions you have to take to apply the AppsFlyer PIPL solution.

**To apply PIPL solution:**

1. Stop collecting device IDs by the SDK. Make sure to not send AppsFlyer the device IDs for both engagements and events.
   * For Android:
     * Set `setDisableAdvertisingIdentifiers` to true
     * Set [`setCollectIMEI`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectimei) to false
     * Set [`setCollectAndroidID`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectandroidid) to false
   * For iOS:
     * Set [`disableAdvertisingIdentifier`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disableadvertisingidentifier) to true
     * Set [`disableIDFVCollection`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disableidfvcollection) to true

   Note that configuring these methods affects identifier collection not only in China. To disable identifiers specifically for the Chinese market, you must implement custom logic.
2. Mask and hash clicks and impressions by using dedicated Chinese domains to pass these events to AppsFlyer.
   * Use the following Chinese domains for OneLink and attribution links:
     * For single platform clicks - **hclicks.aflink.com**, don't use click signing. Make sure to [exclude the app from click signing](https://dev.appsflyer.com/hc/reference/click-signing-config-excluded-apps-add).
     * For single platform impressions - **himpressions.aflink.com**
     * For OneLink clicks - **`{subdomain}`.onelnk.com**
   * Send your CSM a list of relevant app IDs and OneLink subdomains.
   * If you’re using smart banners:
     * [Send AppsFlyer the website key.](/docs/smart-banners-mobile-web-to-app-for-marketers#1-website-workplace-setup)
     * Use only `{subdomain}`.onelnk.com.
     * Note! Since PIPL requires masking and hashing of IP addresses, smart banners based on geolocation rules will not function as expected.
3. Mask and hash SDK and S2S events and transfer them through a relay server in China
   * **SDK Events:**  
     Set the domain for SDK events to **hevents.appsflyer-cn.com**. [Android instructions](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#sethost). [iOS instructions](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#sethost).  
     Using this domain ensures that the IP of all SDK events is masked and hashed.
   * **S2S Events:**  
     For S2S events, use the `api2.hevents.appsflyer-cn.com` domain to mask and hash IP events as follows:
     * The IP should be converted to binary, then the last 2 digits should be masked.
     * The masked binary IP should be converted to text and then hashed by the sha256 algorithm.

## Solution limitations

This section describes certain limitations the PIPL solution imposes.

* The S2S solution for OneLink API for short links creation isn’t supported.
* All device IDs, for all engagements, must be hashed.

<div data-zendesk-anchors="h_01HQ5Y1W7M46BBJGEZZ5VEYW3K=background h_01HQ5Y1W7MRYYGJWJNWY7ZSY9S=apply-pipl-solution-in-appsflyer h_01HQ5Y1W7M39XRY607H4G7X0X4=solution-limitations" />
