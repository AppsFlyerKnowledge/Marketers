---
title: 'Bulletin: Apple Ads now supports SKAN attribution'
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2025-04-15T08:21:59Z'
  edited_at: '2026-05-04T09:15:30Z'
  id: 34395758837137
  locale: en-us
  section: Bulletins
  section_id: 6551161473041
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/34395758837137-Bulletin-Apple-Ads-now-supports-SKAN-attribution
---
| **What's new** | Apple Ads (AA) SKAN postbacks are now fully ingested, processed and reported by AppsFlyer, giving marketers the same privacy-safe measurement already available for other networks. |
| --- | --- |
| **Update date** | 10/04/2025 |
| **What you need to know** | Starting with **iOS 26.2**, Apple Ads postbacks are signed and sent using **AdAttributionKit (AAK)** instead of **SKAdNetwork (SKAN)**.<br /><br />For **iOS 26.1 and earlier**, Apple Ads postbacks continue to use SKAdNetwork.<br /><br />To ensure AppsFlyer receives all Apple Ads postbacks, configure your app to send **both SKAdNetwork and AdAttributionKit postback copies** to AppsFlyer, as described in the Apple developer documentation.<br /><br />**<span id="where-to-find-aa-skan-data"></span>Where to find AA SKAN data**<ul><li>**Apr 10 2025 – May 26 2025:** Data can be found in the report <Anchor target="_blank" href="/marketers/docs/skan-raw-data-reports#postback::315d5a62">SKAN raw postback copies report</Anchor> (Data Locker).</li><li>**From May 27 2025:** Data is available in all SKAN dashboards, APIs, Data Locker exports, and SSOT.</li></ul>**Attribution changes**: AA may now receive credit for installs previously attributed to other networks under SKAN.<br /><br />**<span id="data-granularity"></span>Data granularity:**<ul><li>SKAN postbacks contain only standard SKAN fields. Campaign, adset, ad, geo and creative enrichment fields are **NULL**.</li><li>**Placement mapping (via** **skad\_campaign\_id**):</li><li>10 -> Search Results</li><li>20 -> Search Tab</li><li>30 -> Today Tab</li><li>40 -> Product Pages</li></ul>**<span id="h_01JXYJ6B8FP8N79CVF84VNYQCR"></span>Note**<br />Apple will only share information about the placement of the ad. They'll use the Campaign ID field in SKAN Postbacks to reflect the four available different placements (Search Results, Search Tab, Today Tab, and Product Pages). This means actual Campaign ID and Campaign Level Reporting will not be available.<ul><li>media\_source is **Apple Search Ads** and skad\_ad\_network\_id is **com.apple.ads**.</li></ul>**<span id="skan-versions-supported"></span>SKAN versions supported:**<ul><li>AA supports **SKAN 1.0–3.0**, with **click-through attribution** only.</li><li>Starting from iOS 26.2, AdAttributionKit (AAK) is used.</li><li>View-through is currently not supported.</li></ul>**SSOT impact**: No changes to deduplication logic. AA postbacks not already attributed by AppsFlyer classic methods are included, the rest are deduplicated in SSOT. |
| **What you need to do** | To activate AA SKAN data in AppsFlyer, ensure your app is configured to <Anchor target="_blank" href="/marketers/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">forward SKAN and Ad Attribtution postbacks directly from Apple to AppsFlyer</Anchor>.<ul><li>If your app is already configured, no further action is required.</li></ul>Note: Apps must be running iOS 15 or later for this to work. According to Apple, over 95% of users meet this requirement​. |

<div data-zendesk-anchors="h_01JXYJ7NFNJP83Z2J43841ZENJ=where-to-find-aa-skan-data h_01JXYJ7S61RSK8SV11Y7QGQ9XE=data-granularity h_01JXYJ7Z0ERWPH70A291CEFMH6=skan-versions-supported" />
