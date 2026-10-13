---
title: "Braze (formerly Appboy) integration with AppsFlyer"
excerpt: "Braze, an AppsFlyer integrated partner, offers a lifecycle engagement platform for marketing, growth, and engagement teams. The platform enables marketers to connect human-to-human, at scale, with their customers, driving deep engagement and ROI. The center of our platform is the holistic user profile, which provides a single view of the customer."
x-zendesk:
  id: 115001603343
  url: https://support.appsflyer.com/hc/en-us/articles/115001603343-Braze-formerly-Appboy-integration-with-AppsFlyer
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: 3rd-party platforms
  section_id: 6551199962257
  position: 5
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11085
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution, Ad Networks]
  labels: [Appboy, Advertisers, Ad Networks, Marketers, Localize, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2017-03-30T08:39:03Z'
  edited_at: '2026-08-14T15:06:14Z'
---
Learn more at [braze.com](https://www.braze.com/).

> 🚧 Important notes
>
> * [Some media sources](/docs/about-raw-data-identifier-restrictions#media-source-restrictions) restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.
> * Postbacks won't be sent if the source is organic.

## Integration overview

Follow the instructions below to configure the integration with Braze.

Minimum requirements - AppsFlyer SDK:

- [Android](/docs/sdk-integration-overview) (Android SDK – version 2.3.1.18 and above)
- [iOS](/docs/sdk-integration-overview)

On Android, integrating with Braze requires that the Braze [Device ID](https://www.braze.com/docs/partners/advertising_technologies/attribution/appsflyer/#integration) (Braze unique user identifier) is populated in AppsFlyer Android SDK. This parameter is sent with every postback and enables the identification of each user. To perform this you must insert the following strings to your app code:

> 🚧 Important Note
>
> Make sure the lines of code are inserted at the correct place – after Braze SDK is launched and before the initialization code for AppsFlyer SDK (see the Initializing the SDK section in our Android SDK Integration Guide).
**Android**

```java
JavaHashMap<String, Object> customData = new HashMap<String,Object>();
String deviceId =(Braze.getInstance(MyActivity.this).getDeviceId());
customData.put(