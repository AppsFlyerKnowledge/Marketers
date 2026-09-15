---
title: "Bulletin: Engagement types"
excerpt: "Learn about the new engagement type fields added to AppsFlyer raw data reports, including preload, click-to-download, and engaged-view values."
---
## What's new

New fields have been added to the raw data reports.

- engagement_type
- contributor1_engagement_type
- contributor2_engagement_type
- contributor3_engagement_type

These parameters can return the following values: preload, click_to_download, click_to_app, engaged_click, engaged_view, view, listening, or if not reported it will be empty

| Engagement type | Description |
| --- | --- |
| preload | The app is preloaded by the OEM at the factory or by the provider the first time the device is activated. Alternatively, a wizard prompts users to download the app when the device is first activated. |
| click_to_download | When the user engages with an ad, the app is automatically downloaded and installed on the device without redirecting to an app store. |
| click_to_app | An ad click, QR code scan, deep link, or any other click that redirects the user to the app or to the relevant app store to download the app. |
| engaged_click | A click that keeps the user in the same context, engaging with the ad, and does NOT direct that user to the app store or to launch the app. |
| engaged_view | An engaged view is when a meaningful view takes place. Some examples are when a user watches at least 10 seconds or more of a skippable video ad or a video completion |
| view | An ad view is when an ad is rendered, and an impression takes place. Some examples are banners, interstitials, or non-engaged videos. |
| listening | Listening is when a user listens to an audio ad, such as a podcast ad. |

## Effective date

January 17, 2024

## What this impacts

- Advertisers and agencies with access to raw data reports working with Ad networks who report these fields.
- Preload and click_to_app for deep links will be populated by AppsFlyer regardless of whether the Ad networks report the fields.
- The raw data reports it affects are: Data Locker, Pull API, Export Page, and Push API.
- These fields are not selected by default (with the exception of the select all in Push API), to use these fields you must manually select them in the raw data product.