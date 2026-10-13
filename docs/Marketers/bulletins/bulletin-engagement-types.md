---
title: "Bulletin: Engagement types"
excerpt: "Learn about the new engagement type fields added to AppsFlyer raw data reports, including preload, click-to-download, and engaged-view values."
table_of_contents: false
x-zendesk:
  id: 20161875390865
  url: https://support.appsflyer.com/hc/en-us/articles/20161875390865-Bulletin-Engagement-types
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Bulletins
  section_id: 6551161473041
  position: 28
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-moran-davida, Marketers, Mobile Attribution]
  labels: [Marketers, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2023-11-15T10:50:04Z'
  edited_at: '2026-08-13T13:34:31Z'
---
| Section | Description |
| --- | --- |
| **What's new** | New fields have been added to the raw data reports.<br /><br />* engagement\_type<br />* contributor1\_engagement\_type<br />* contributor2\_engagement\_type<br />* contributor3\_engagement\_type<br /><br />These parameters can return the following values: preload, click\_to\_download, click\_to\_app, engaged\_click, engaged\_view, view, listening, or if not reported it will be empty<br /><br />\|  \|  \|<br />\| --- \| --- \|<br />\| Engagement type \| Description \|<br />\| preload \| The app is preloaded by the OEM at the factory or by the provider the first time the device is activated. Alternatively, a wizard prompts users to download the app when the device is first activated. \|<br />\| click\_to\_download \| When the user engages with an ad, the app is automatically downloaded and installed on the device without redirecting to an app store. \|<br />\| click\_to\_app \| An ad click, QR code scan, deep link, or any other click that redirects the user to the app or to the relevant app store to download the app. \|<br />\| engaged\_click \| A click that keeps the user in the same context, engaging with the ad, and does NOT direct that user to the app store or to launch the app. \|<br />\| engaged\_view \| An engaged view is when a meaningful view takes place. Some examples are when a user watches at least 10 seconds or more of a skippable video ad or a video completion \|<br />\| view \| An ad view is when an ad is rendered, and an impression takes place. Some examples are banners, interstitials, or non-engaged videos. \|<br />\| listening \| Listening is when a user listens to an audio ad, such as a podcast ad. \| |
| Engagement type | Description |
| preload | The app is preloaded by the OEM at the factory or by the provider the first time the device is activated. Alternatively, a wizard prompts users to download the app when the device is first activated. |
| click\_to\_download | When the user engages with an ad, the app is automatically downloaded and installed on the device without redirecting to an app store. |
| click\_to\_app | An ad click, QR code scan, deep link, or any other click that redirects the user to the app or to the relevant app store to download the app. |
| engaged\_click | A click that keeps the user in the same context, engaging with the ad, and does NOT direct that user to the app store or to launch the app. |
| engaged\_view | An engaged view is when a meaningful view takes place. Some examples are when a user watches at least 10 seconds or more of a skippable video ad or a video completion |
| view | An ad view is when an ad is rendered, and an impression takes place. Some examples are banners, interstitials, or non-engaged videos. |
| listening | Listening is when a user listens to an audio ad, such as a podcast ad. |
| **Effective date** | January 17, 2024 |
| **What this impacts** | * Advertisers and agencies with access to raw data reports working with Ad networks who report these fields.<br />  * Preload and click\_to\_app for deep links will be populated by AppsFlyer regardless of whether the Ad networks report the fields.<br />* The raw data reports it affects are: Data Locker, Pull API, Export Page, and Push API.<br />  * These fields are not selected by default (with the exception of the select all in Push API), to use these fields you must manually select them in the raw data product. |