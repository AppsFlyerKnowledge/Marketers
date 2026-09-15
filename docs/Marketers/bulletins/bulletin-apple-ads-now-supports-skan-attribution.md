---
title: "Bulletin: Apple Ads now supports SKAN attribution"
excerpt: "Apple Ads SKAN postbacks are now fully ingested, processed, and reported by AppsFlyer, providing privacy-safe measurement for your campaigns."
---
Apple Ads (AA) SKAN postbacks are now fully ingested, processed and reported by AppsFlyer, giving marketers the same privacy-safe measurement already available for other networks.

* **Update date**: 10/04/2025

> 📘 What you need to know
>
> Starting with **iOS 26.2**, Apple Ads postbacks are signed and sent using **AdAttributionKit (AAK)** instead of **SKAdNetwork (SKAN)**.
> 
> For **iOS 26.1 and earlier**, Apple Ads postbacks continue to use SKAdNetwork.
> 
> To ensure AppsFlyer receives all Apple Ads postbacks, configure your app to send **both SKAdNetwork and AdAttributionKit postback copies** to AppsFlyer, as described in the Apple developer documentation.

## Where to find AA SKAN data

* **Apr 10 2025 – May 26 2025:** Data can be found in the report [SKAN raw postback copies report](/docs/skan-raw-data-reports#postback::315d5a62) (Data Locker).
* **From May 27 2025:** Data is available in all SKAN dashboards, APIs, Data Locker exports, and SSOT.

**Attribution changes**: AA may now receive credit for installs previously attributed to other networks under SKAN.

## Data granularity

* SKAN postbacks contain only standard SKAN fields. Campaign, adset, ad, geo and creative enrichment fields are **NULL**.
* **Placement mapping (via `skad_campaign_id`):**
  * 10 -> Search Results
  * 20 -> Search Tab
  * 30 -> Today Tab
  * 40 -> Product Pages

> 📘 Note
>
> Apple will only share information about the placement of the ad. They'll use the Campaign ID field in SKAN Postbacks to reflect the four available different placements (Search Results, Search Tab, Today Tab, and Product Pages). This means actual Campaign ID and Campaign Level Reporting will not be available.

* `media_source` is **Apple Search Ads** and `skad_ad_network_id` is **com.apple.ads**.

## SKAN versions supported

* AA supports **SKAN 1.0–3.0**, with **click-through attribution** only. 
* Starting from iOS 26.2, AdAttributionKit (AAK) is used.
* View-through is currently not supported.

**SSOT impact**: No changes to deduplication logic. AA postbacks not already attributed by AppsFlyer classic methods are included, the rest are deduplicated in SSOT.

## What you need to do

To activate AA SKAN data in AppsFlyer, ensure your app is configured to [forward SKAN and Ad Attribution postbacks directly from Apple to AppsFlyer](https://support.appsflyer.com/hc/articles/4402320969617-Send-SKAN-postback-copies-directly-to-AppsFlyer-iOS-15). 

* If your app is already configured, no further action is required.

> 📘 Note
>
> Apps must be running iOS 15 or later for this to work. According to Apple, over 95% of users meet this requirement​.