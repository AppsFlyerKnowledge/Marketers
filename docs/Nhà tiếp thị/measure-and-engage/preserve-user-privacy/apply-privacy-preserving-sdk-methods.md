---
title: Apply privacy-preserving SDK methods
metadata:
  keywords:
    - Advertisers
    - coppa
    - opt-out
    - opt out
    - consent management
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2018-08-20T11:14:36Z'
  edited_at: '2026-08-14T16:22:41Z'
  id: 360001422989
  locale: en-us
  section: Preserve user privacy
  section_id: 6551440878097
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360001422989-Apply-privacy-preserving-SDK-methods
---
> **At a glance:** Preserve the privacy of your users with one or more of the methods available through the AppsFlyer SDK.

> 📘 **Note**
>
> The information presented in this article is intended solely to provide insight into the methods available to app developers for controlling the sharing of user-related data with app owners, ad networks, and social networks. **This article does not include or constitute guidance on compliance with privacy regulations such as COPPA or GDPR or any specific privacy-preserving regulations.**

The AppsFlyer SDK offers app owners several methods to protect user privacy and control data. In this article, we will explore these methods and assess how they impact user data and how to use them to preserve user privacy while still permitting attribution.

After considering which options you want to use, share the implementation information in our Dev Hub with your developers.

Let's discuss each method.

## Use start and stop methods

The SDK sends installs and in-app events to AppsFlyer only after the `start` method is called. Any event preceding the `start` call will not be reported by the SDK. In a similar manner, if the `start` call is subsequently reversed by invoking the `stop` method, no events will be sent thereafter.

### Impact on attribution

Attribution does **not** occur when:

* the `start` method is not called.
* the `stop` method is called to reverse a previous start.

### Common use cases

| Use case | Description |
| --- | --- |
| Opt-in or opt-out on launch | Call `start` after the user consents to share data on the first launch.  <br />If the user does not consent to share data, don’t call  <br />`start` at all. |
| Session opt-out | In every app session, ask for consent and call or do not call `start` accordingly. |
| One-time opt-out (When a user opts-in and then decides to opt-out). | Call `stop` to stop the SDK from sending further events. |

### Developer reference

Developer reference and documentation on how to use the start and stop methods see:

<Tabs>
<Tab title="Android">

[Use start to share only the install event](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-android#use-start-to-share-only-the-install-event)

</Tab>

<Tab title="iOS">

[Use start to share only the install event](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-ios#use-start-to-share-only-the-install-event)

</Tab>
</Tabs>

## Prevent sharing data with networks

At the time of integration with an ad network or Self-Reporting Network (SRN), you can elect to share or not share user-level information with that partner. In the SDK, you can further filter data sharing with all or some partners **according to end-user preferences** by using the `setSharingFilterForPartners` method.

When you use this method, AppsFlyer will disable the sharing of user data with the excluded partner by any means, including postbacks, APIs, raw data reports, etc.

### Impact on attribution

* Installs **from excluded ad networks** **(non-SRNs)** are attributed in AppsFlyer, but the ad networks will not be notified in any form or manner.
* Installs **from excluded SRNs** are not attributed, and their data is not shared with your integrated partners. This does not apply to **Advanced SRNs**, where attribution is still possible; however, installs, re-engagements, and in-app events will not be shared back due to the sharing filter.

  > 📘 **Note**
  >
  > AppsFlyer cannot attribute engagement data for any SRNs excluded from getting your data.


### Developer reference

Developer reference and documentation on how to prevent sharing data with third parties see:

<Tabs>
<Tab title="Android">

[Prevent sharing data with third parties](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-android#prevent-sharing-data-with-third-parties)

</Tab>

<Tab title="iOS">

[Prevent sharing data with third parties](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-ios#prevent-sharing-data-with-third-parties)

</Tab>
</Tabs>

## Anonymize user information

You can configure the SDK to instruct AppsFlyer to remove all user-identifying information by using the `anonymizeUser` method. In this case, the SDK sends install and in-app events to AppsFlyer, where all identifying information is then deleted or hashed:

* **Deleted:** personal identifiers (GAID, IDFA, IDFV, and CUID)
* **Hashed:** AppsFlyer ID and IP address

The following image shows an example row of raw data after anonymization (deletion and hashing).

![Example row of raw data showing deleted and hashed fields after anonymization](https://files.readme.io/5cae15ee0e38c84b2f9876d0dca2145543e83e624933ca138017da5206e7a834-35847868223633.png)

### Impact on attribution

If you call `anonymizeUser` before calling `start`, attribution can't use device identifiers or the device IP address. As a result, standard attribution methods based on these identifiers don't take place.

However, attribution can still occur using the following methods, which don't rely on device identifiers:

* <Anchor target="_blank" href="/marketers/vi/docs/self-reporting-networks-srns#phân-bổ">Self-reporting network (SRN) attribution</Anchor>
* <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-attribution-model#probabilistic-modeling">Probabilistic modeling (PMOD)</Anchor>
* <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-attribution-model#install-referrer-android-only">Referrer-based attribution</Anchor>

To attribute the install event using standard identifiers, call `anonymizeUser` **only after the SDK confirms that the install event was sent to AppsFlyer**.

This flow ensures that:

* The install event can be attributed normally.
* Any in-app events that occur after `anonymizeUser` is called are sent **without identifiers**.

As a result, these in-app events are either counted as **organic** or **disregarded**, depending on the reporting method.

> 📘 **Note**
>
> <Anchor target="_blank" href="/marketers/vi/docs/self-reporting-networks-srns#phân-bổ">SRN</Anchor>, <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-attribution-model#probabilistic-modeling">PMOD (probabilistic)</Anchor>, and <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-attribution-model#install-referrer-android-only">Referrer-based attribution</Anchor> are supported in anonymized mode. This includes <Anchor target="_blank" href="/marketers/vi/docs/basic-sdk-integration-guide#người-giới-thiệu-cài-đặt-google-play">Google Play Install Referrer</Anchor>, other store referrers (such as <Anchor target="_blank" href="/marketers/vi/docs/set-up-multi-store-android-attribution#referrer-implementation-thirdparty-android-app-stores">Xiaomi, Huawei,</Anchor> <Anchor target="_blank" href="/marketers/vi/docs/set-up-appsflyer-preload-referrer-attribution#samsung-preload-referrer">and Samsung</Anchor>), and <Anchor target="_blank" href="/marketers/vi/docs/set-up-appsflyer-preload-referrer-attribution?utm_source=chatgpt.com">AppsFlyer preload referrer</Anchor>

### Developer reference

Developer reference and documentation on how to anonymize user information see:

<Tabs>
<Tab title="Android">

[Anonymize user information](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-android#anonymize-user-information)

</Tab>

<Tab title="iOS">

[Anonymize user information](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-ios#anonymize-user-information)

</Tab>
</Tabs>

## Remove specific device identifiers

You can prevent the SDK from collecting and sending specific device identifiers to AppsFlyer. In contrast to using the `anonymizeUser` method, disabling specific identifiers lets you decide on the identifiers you want to keep.

The SDK API includes the following methods to disable identifiers.

### Android identifiers

| Method | Identifiers disabled |
| --- | --- |
| [`setdisableadvertisingIdentifiers`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setdisableadvertisingidentifiers) | <ul><li>Google Advertising ID (GAID)</li><li>Open Anonymous Device Identifier (OAID)</li><li>Amazon Advertising ID (AAID)</li></ul> |
| [`setcollectoaid`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectoaid) | Open Anonymous Device Identifier (OAID) |

### iOS identifiers

| Method | Identifier disabled |
| --- | --- |
| [`disableAdvertisingIdentifier`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disableadvertisingidentifier) | IDFA (iOS 13 and below) |
| [`disableIDFVCollection`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disableidfvcollection) | IDFV |

### Developer reference

Developer reference and documentation on how to remove specific device identifiers see:

<Tabs>
<Tab title="Android">

[Disable IDs](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-android#disable-ids)

</Tab>

<Tab title="iOS">

[Disable IDs](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-ios#disable-ids)

</Tab>
</Tabs>

> 📘 **Note**
>
> **Questions about AppsFlyer privacy?**
>
> The privacy relationship between you and AppsFlyer is governed by the [AppsFlyer Statement on Data Processing](https://www.appsflyer.com/legal/processing-customer-data/). For questions relating to this statement or to contact our data protection officer, send an email to [dpo@appsflyer.com](mailto:dpo@appsflyer.com).

<div data-zendesk-anchors="h_01HKD1N2C8V0SP1NG8W2EJPRQZ=use-start-and-stop-methods h_01HKD1N2C80QAJSNE83SD45DJA=impact-on-attribution h_01HKD1N2C8YHWYARRAGX1TD6DM=common-use-cases h_01HKM6VNJFCW77F2268XXDF65Q=developer-reference h_01HKD1N2C8ASV10XWY33R972MC=prevent-sharing-data-with-networks impact-on-attribution::aa0a9f9e=impact-on-attribution-1 h_01HKD1N2C8RA34M4TSWYCW3A9F=impact-on-attribution-1 developer-reference::f2007ab7=developer-reference-1 h_01HKM6VNJFP8C7KCFSV1046H0B=developer-reference-1 h_01HKD1N2C8CWSWK0VSXZ39MQ3D=anonymize-user-information anonymize-impact=impact-on-attribution-2 h_01KK93D18X4QYG87CFMZWNHSBA=impact-on-attribution-2 developer-reference::e4cacf1f=developer-reference-2 h_01HKM6VNJF7XPZ9ME61JG4KM9Z=developer-reference-2 h_01HKD1N2C8S3Y73AZ9J7JFDKQE=remove-specific-device-identifiers h_01HKD1N2C8HZ61XHMBC0JNTK7S=android-identifiers h_01HKD1N2C8AHK4EYANG6N6ST06=ios-identifiers developer-reference::4e0971d1=developer-reference-3 h_01HKM6VNJFV0YJWV8KT23VTKKH=developer-reference-3" />
