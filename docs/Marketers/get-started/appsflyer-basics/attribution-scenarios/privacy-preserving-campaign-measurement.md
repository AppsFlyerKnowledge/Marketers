---
title: Privacy-preserving campaign measurement
excerpt: >-
  Get answers to common FAQ about privacy-preserving campaign measurement
  methods, the networks involved, and their implications on retargeting,
  view-through, and child-directed app limitations.
metadata:
  keywords:
    - Agencies
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2023-11-28T07:10:15Z'
  edited_at: '2026-04-19T12:18:41Z'
  id: 20489739742609
  locale: en-us
  section: Attribution scenarios
  section_id: 6551328497041
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/20489739742609-Privacy-preserving-campaign-measurement
---
## Overview

In today's privacy-conscious era, platforms and technologies are increasingly limiting the use of advertiser IDs, driving the industry toward measurement methods that align with privacy requirements while still enabling effective campaign measurement. For such cases, AppsFlyer supports multiple privacy-preserving campaign measurement methods for both SRN and non-SRN ad networks, as described below.

<div id="what-methods-of-attribution-dont-require-collecting-device-ids" />

<Accordion title="How does AppsFlyer measure campaign performance when advertiser IDs are unavailable?">

AppsFlyer provides the following measurement methods:

* [Install referrer matching](/docs/appsflyer-attribution-model#install-referrer-android-only) (for Android only)
* [Probabilistic modeling](/docs/appsflyer-attribution-model#probabilistic-modeling)
* [Deep linking](/docs/appsflyer-attribution-model#deep-link) (for retargeting only)

</Accordion>

<div id="what-networks-can-be-attributed-without-using-a-device-id" />

<Accordion title="What attribution methods do ad networks support?">

**Non-SRN ad networks** can be measured using the additional privacy-preserving attribution methods described in the [FAQ above](#what-methods-of-attribution-dont-require-collecting-device-ids).

**Most** [**SRNs**](/docs/self-reporting-networks-srns) require an advertising ID for measurement; however, a few, as specified below, support other privacy-preserving methods.

| SRN | Method |
| --- | --- |
| Advanced SRNs (such as Tiktok and Snapchat) | Based on clicks and impressions from the Advanced SRN |
| Meta ads | <ul><li>[Using AEM for iOS devices](/docs/meta-ads-integration-setup#aggregate-event-measurement-aem-for-ios)</li><li>[Using the following parameters for Android devices:](/docs/meta-ads-integration-setup#getting-userlevel-data-for-android-installs)<ul><li>`gp_referrer`</li><li>`fb_referrer`</li><li>`ig_referrer`</li></ul></li></ul> |
| Google Ads | Using the `gbraid` parameter for iOS devices |
| Apple Search Ads (ASA) | Using [ASA attribution](/docs/apple-ads-integration-setup#asa-attribution) |
| <ul><li>Google Ads</li><li>Meta Ads</li><li>Snapchat</li><li>TikTok</li><li>X ads</li><li>Yahoo! Japan</li></ul> | [SKAN](/docs/skadnetwork-skan-solution-guide) |

</Accordion>

<div id="can-i-measure-retargeting-without-using-the-device-id" />

<Accordion title="What retargeting measurement options does AppsFlyer support?">

Retargeting attribution can be used with the methods mentioned [above](#what-methods-of-attribution-dont-require-collecting-device-ids).   
**Note:** Install referrer attribution (for Android) is for re-attributions only, not for re-engagements.

</Accordion>

<div id="can-i-measure-viewthrough" />

<Accordion title="Is view-through measurement supported by the above methods?">

View-through is supported using [probabilistic modeling](/docs/appsflyer-attribution-model#probabilistic-modeling). Other methods, such as referrer and deep linking, support click measurement but not view-through.

Learn more about [view-through attribution](/docs/appsflyer-attribution-model#viewthrough-attribution).

</Accordion>

<div id="can-deep-linking-be-done-without-a-device-id" />

<Accordion title="Does deep linking require an advertising ID?">

Deep linking users from a campaign to a specific activity in your app can occur in different scenarios, depending on whether the app is already installed.

The availability of an advertising ID may affect deep linking behavior depending on the following scenarios:

* **Direct deep linking:** **no impact**.   
  The deep link sends existing users directly to a specific activity in your app. As specified in the [table of attribution methods](/docs/appsflyer-attribution-model#attribution-methods), attribution is done using details on the deep link URL, which is directly fed into the SDK.
* **Indirect deep linking:** **works only if attribution is successful**.   
  The deep link sends existing users to a specific activity in your app, but the app fails to open directly. When the user opens the app again later, a re-engagement is recorded, and **indirect deep linking is performed. However, this happens only if the attribution is successful** (using the attribution methods [described above](#what-methods-of-attribution-dont-require-collecting-device-ids)). Therefore, if attribution is successful, deep linking will also work.
* **Deferred deep linking:** **works only if attribution is successful**.  
  The deep link sends new users to the app store. After the install, the app opens at a specific activity. **This happens only if the attribution is successful** (using the attribution methods [described above](#what-methods-of-attribution-dont-require-collecting-device-ids)). Therefore, if the lack of an advertiser ID still allows attribution, deep linking will also work.

</Accordion>

<div id="what-are-the-implications-of-childdirected-app-limitations-on-attribution" />

<Accordion title="How does measurement differ when an advertising ID is unavailable?">

In certain privacy-restricted scenarios, measurement coverage may be more limited. AppsFlyer continues to provide meaningful campaign measurement while preserving user privacy.

</Accordion>

> 📘 **See also**
>
> * [Preserving user privacy](/docs/preserve-user-privacy)
> * [User privacy on the SDK level](/docs/additional-sdk-integration-guide#user-privacy)

<div data-zendesk-anchors="eeee=overview h_01HMBEZD0P31S8N9ZERB17ZHPT=overview h_01HGAC6QR6XJ20K92DE8KQ02P3=what-methods-of-attribution-dont-require-collecting-device-ids 01HMEBCTBWJX03WEHY3QTR3RAS=what-networks-can-be-attributed-without-using-a-device-id h_01HGAC6QR7VXFNPENAXTAV97Y7=can-i-measure-retargeting-without-using-the-device-id h_01HGAC6QR7E298ZTH8G4TTD7EC=can-i-measure-viewthrough h_01HMRHWVEQCHS7QBJHPZS3B8KZ=can-deep-linking-be-done-without-a-device-id h_01HGAC6QR752QPT4MSDQ7TWAXT=what-are-the-implications-of-childdirected-app-limitations-on-attribution h_01HGAC6QR7R4ZTWJEMSKHACNPF=see-also" />
