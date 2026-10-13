---
title: "SKAN integrated partners list"
excerpt: "Lists of ad network partners having SKAN integration with AppsFlyer, and ad network Apple SKAdNetwork IDs."
x-zendesk:
  id: 360012640377
  url: https://support.appsflyer.com/hc/en-us/articles/360012640377-SKAN-integrated-partners-list
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: SKAN interoperation
  section_id: 6552115163153
  position: 0
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-gil-or, Marketers, SKAdNetwork (SKAN)]
  labels: [Advertisers, Marketers, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2020-09-01T20:45:57Z'
  edited_at: '2026-04-28T09:55:09Z'
---
**At a glance:** Lists of ad network partners having SKAN integration with AppsFlyer, Ad network Apple SKAdNewtork IDs.

## AppsFlyer SKAN partners

The partners listed are integrated with AppsFlyer and forward iOS SKAN postbacks to AppsFlyer.

Partners listed send AppsFlyer the SKAN postbacks they receive from iOS devices. In addition, they add to the postbacks supplement fields based on their advertising hierarchy and reporting systems. These supplement fields enrich the postback with more data and help to better understand the performance of your SKAN campaigns.

Note that SKAN postbacks are reflected in the SKAN overview dashboard regardless of the state of **Activate partner** toggle in the partner Integration tab.

The following enrichment fields are available:

* **Location**: Reported by the attributed ad network using the country code.
* **Enrichment Campaign ID**: This ID is distinct from the SKAN campaign ID reported in the iOS postback **which is always available**.
* **Enrichment Campaign name**: Displays in reports and dashboards.
* **Enrichment Adset ID**: Displays in reports and dashboards.
* **Enrichment Adset name**: Displays in reports and dashboards.
* **Enrichment Ad ID**: Displays in reports and dashboards.
* **Enrichment Ad name**: Displays in reports and dashboards.
* **Enrichment cost**: Displays in reports and dashboards.
* **View-through attribution support:** This field isn't enriched by the ad network, but rather indicates if VTA is available through SKAN postbacks.
* **Redownloads:** Available as part of the SKAN 2.0 postback for non-SRNs.  
  All SRNs send all install data in SKAN postbacks. Note that some SRNs choose to not distinguish between new installs and redownloads, meaning redownload data (for some SRNs) is not displayed in SKAN dashboard.

[List of SKAN networks](/docs/skan-integrated-partners-list#skan-enrichment-fields-supported-in-srn-integrations).

### SKAN SRN integrations and enrichment fields

| Partner name | Supported feature | Enrichment fields | | | | | | | | | | |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| *SKAN 4  (data received) | Location | Camp. ID | Camp. name | Adset ID | Adset Name | Ad ID | Ad Name | Site ID | Cost | VTA+ | Re-down- loads |
| [Meta Ads](/docs/skadnetwork-skan-interoperation-with-meta-ads) | **✓** | - | **✓** | **✓** | **-** | **-** | **-** | **-** | - | **✓** | **✓** | **✓***** |
| [Google Ads](/docs/get-skan-postback-data-from-google-ads) | - | - | **✓**** | **✓** | **-** | **-** | **-** | **-** | **✓** | **✓** | **✓** | **✓** |
| [Snapchat](/docs/skan-interoperation-with-snapchat) | - | - | **✓** | **✓** | **✓** | **✓** | **-** | **-** | **✓** | **✓** | **✓** | **-** |
| [TikTok for Business](/docs/skan-interoperation-with-tiktok-for-business) | **✓** | - | **✓** | **✓** | **✓** | **✓** | **✓** | **✓** | **✓** | **✓** | **✓** | **✓** |
| [X Ads](/docs/x-ads-formerly-twitter-ads-setup-guide-overview#twitter-ads-and-appsflyer-skan-interoperation) | **✓** | - | **✓**** | **✓** | **✓** | **✓** | **-** | **-** | **✓** | **✓** | **✓** | **✓** |
| [Yahoo! Japan](/docs/yahoo-japan-search-ads-campaign-configuration) | **✓** | - | **✓** | **✓** | **-** | **-** | **-** | **-** | - | - | - | **✓** |
| [Amazon Ads](/docs/beta-skan-interoperation-with-amazon) | **✓** | - | **✓** | **✓** | **-** | **-** | **✓** | **✓** | **✓** | - | **✓** | **✓** |
| [Apple Ads (Search Ads)](/docs/get-skan-postback-data-from-google-ads) | SKAN 1-3 | - | - | - | **-** | **-** | - | - | - | **✓++** | - | - |

*Ad networks with more than 10% of their SKAN traffic from version 4

**skan\_campaign\_id is not reported

*** Available for SKAN postbacks version 4 and above

^ Aggregated with click-through

+ View-through attribution

++ Cost is not available in the SKAN dashboard or SKAN Pull API due to the lack of campaign-level data in SKAN postbacks. Cost data is available in SSOT reports via classic ASA integration.

### SKAN non-SRN integrations and enrichment fields

| Partner name | Supported feature | | Enrichment fields | | | | | | | | |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| *SKAN 4  (data received) | View-through attribution | Location | Camp. ID | Camp. name | Adset ID | Adset Name | Ad ID | Ad Name | Site ID | Cost |
| RZR (formerly Aarki) | **✓** | **✓** | - | **✓** | **✓** | **-** | **-** | **-** | **-** | - | **✓** |
| AdColony | - | **✓** | - | **✓** | **✓** | **✓** | **✓** | **-** | **-** | - | **✓** |
| AdzMedia | - | - | - | **✓** | **✓** | **-** | **-** | **-** | **-** | - | - |
| Appier | **✓** | **✓** | - | - | - | - | - | - | - | - | - |
| Applovin | - | **✓** | **✓** | **✓** | **✓** | **-** | **-** | **-** | **-** | - | **✓** |
| Appreciate | - | **✓** | - | **✓** | **✓** | **-** | **-** | **-** | **-** | - | - |
| BigaBid | - | **✓** | - | **✓** | **✓** | **-** | **-** | **-** | **-** | - | - |
| BoomBit | - | **✓** | - | **✓** | **✓** | **✓** | **✓** | **✓** | **✓** | - | - |
| [TikTok for Business](/docs/skan-interoperation-with-tiktok-for-business) | - | **✓** | - | **✓** | **✓** | **✓** | **✓** | **-** | **-** | - | **✓** |
| Chart-boost | - | **✓** | - | - | - | - | - | - | - | - | - |
| Dataseat | **✓** | **✓** | - | **✓** | **✓** | **-** | **-** | **-** | **-** | - | **✓** |
| Edge Solutions | - | **✓** | - | **-** | **-** | **-** | **-** | **-** | **-** | - |  |
| InMobi | - | - | - | **✓** | **✓** | **-** | **-** | **-** | **-** | - | **✓** |
| InMobi DSP | - | **✓** | - | **✓** | **✓** | **-** | **-** | **-** | **-** | - | **-** |
| ironSource | **-** | **✓** | - | **✓** | **✓** | **-** | **-** | **-** | **-** | **✓** | **✓** |
| Jampp, an Affle company | **✓** | **✓** | - | **✓** | **✓** | **-** | **-** | **-** | **-** | - | **✓** |
| Kaden | - | **✓** | - | **✓** | **✓** | **✓** | **✓** | **✓** | **✓** | - |  |
| Kayzen | - | - | - | **✓** | **✓** | **-** | **-** | **-** | **-** | - | - |
| King | - | - | - | **✓** | **✓** | **-** | **-** | **-** | **-** | - | - |
| Kismet | - | **✓** | - | **✓** | **✓** | **-** | **-** | **-** | **-** | **✓** |  |
| Lifestreet | - | **✓** | - | **✓** | - | - | - | - | - | - | **✓** |
| Liftoff | **✓** | **✓** | **✓** | **✓** | **✓** | **-** | **-** | **-** | **-** | - | **✓** |
| Mapendo | - | **✓** | **✓** | **✓** | **✓** | **-** | **-** | **-** | **-** | - |  |
| Mintegral Inter-national Limited | **✓** | **✓** | - | **✓** | **✓** | **-** | **-** | **-** | **-** | - | **✓** |
| Moloco | **✓** | **✓** | **✓** | **✓** | **✓** | **-** | **-** | **-** | **-** | - | - |
| MoPub Acquire | - | - | - | **✓** | **✓** | **-** | **-** | **-** | **-** | - | **✓** |
| Myappfree | - | - | - | **✓** | **✓** | **-** | **-** | **-** | **-** | - |  |
| myTarget (Mail.ru) | - | **✓** | **✓** | **✓** | **✓** | **✓** | **-** | **✓** | **✓** | - |  |
| nend | - | **✓** | - | **✓** | **✓** | **-** | **-** | **-** | **-** | - |  |
| Outbrain | - | - | - | **✓** | **✓** | **-** | **-** | **-** | **-** | - | - |
| Persona.ly RTB | - | **✓** | - | **✓** | **✓** | **-** | **-** | **-** | **-** | - | - |
| Reddit | **✓** | **✓** | - | **✓** | **✓** | **✓** | **✓** | **✓** | **✓** | - | **✓** |
| Remerge | - | - | - | **✓** | **✓** | **-** | **-** | **-** | **-** | - | - |
| Simeji | - | **✓** | - | - | - | - | - | - | - | - | - |
| Smadex | **✓** | **✓** | - | **✓** | **✓** | **-** | **-** | **-** | **-** | - | **✓** |
| SmartNews | **✓** | **✓** | - | **✓** | **✓** | **-** | **-** | **-** | - | - | **-** |
| Tapjoy | - | - | - | **✓** | **✓** | **✓** | **✓** | **-** | **-** | - | - |
| TD Media | - | - | - | **-** | **-** | **-** | **-** | **-** | **-** | - |  |
| Tencent AMS | - | - | - | - | - | - | - | - | - | - | - |
| TheTradeDesk | **✓** | **✓** | - | **✓** | **✓** | - | - | - | - | - | **✓** |
| Unicorn | **✓** | - | - | **✓** | **✓** | **-** | **-** | **-** | **-** | - | - |
| Unity Ads | **✓** | **✓** | - | **✓** | **✓** | **-** | **-** | **-** | **-** | **✓** | **✓** |
| Vungle | - | **✓** | - | **✓** | **✓** | **-** | **-** | **✓** | **✓** | - | **✓** |
| Yandex Direct | - | **✓** | - | **✓** | **✓** | **-** | **-** | **-** | **-** | - | - |
| ZinkAds | - | - | - | **✓** | - | - | - | - | - | - | - |

*Ad networks with more than 10% of their SKAN traffic from version 4

## Apple SKAdNetwork IDs of ad networks

The table that follows contains the list of Apple SKAdNetwork IDs to populate your app [*Info.plist*](https://developer.apple.com/documentation/storekit/skadnetwork/configuring_a_source_app).

<Embed title="SKAN integrated partners list" typeOfEmbed="oembed" url="https://docs.google.com/spreadsheets/d/e/2PACX-1vSqwIBW3FzbrXKqluDQ2hEec7zcvVrxQ02ivWsHnGQTvLMeFmHHjGz1R5TVy6_cqAIVh0pAy4Yud7Qx/pubhtml?widget=true&amp;headers=false" providerUrl="https://docs.google.com" />

[Download CSV file](https://docs.google.com/spreadsheets/d/e/2PACX-1vSqwIBW3FzbrXKqluDQ2hEec7zcvVrxQ02ivWsHnGQTvLMeFmHHjGz1R5TVy6_cqAIVh0pAy4Yud7Qx/pub?gid=0&single=true&output=csv)

In accordance with [Apple guidance](https://developer.apple.com/forums/thread/663032) IDs must be in lowercase

> 📘 **See also**
>
> * [AppsFlyer SKAN solution guide](/docs/skadnetwork-skan-solution-guide)
> * [SKAN Conversion Studio: Configuring performance measurement](/docs/skan-conversion-studio)
> * [SKAN Overview dashboard](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer)
> * [Send iOS postbacks directly to AppsFlyer](/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15) (iOS 15+)