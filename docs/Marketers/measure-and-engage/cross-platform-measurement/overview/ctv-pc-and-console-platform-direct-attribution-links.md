---
title: CTV, PC, and console platform direct attribution links
metadata:
  keywords:
    - Advertiser
    - Marketers
    - CTV Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - CTV Attribution
  created_at: '2023-05-10T10:21:14Z'
  edited_at: '2026-10-16T08:45:49Z'
  id: 15199908310801
  locale: en-us
  section: Overview
  section_id: 15323084579345
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/15199908310801-CTV-PC-and-console-platform-direct-attribution-links
---
**At a glance:**  Learn about the AppsFlyer attribution link structure and parameters for CTV, PC, and console platforms. **Note**: For Android and iOS apps, including Android PC games, use <Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters">mobile attribution link instructions</Anchor>.

## Overview

CTV, PC, and console platform direct attribution links allow advertisers to redirect users and collect data following clicks. These direct attribution links are AppsFlyer links that support redirection and attribution **for a single destination app on a single platform at a time**. The redirection destination is the value of the af\_r parameter included in the link.

**Note**: For Android and iOS apps, including Android PC games, use <Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters">mobile attribution link instructions</Anchor>.

Attribution links can be directly created by you and placed behind ads. To create such links, follow the instructions in this article.

Alternatively, links can be created via S2S using the <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_click-app-platform-app-id">Engagements API</Anchor>. This requires some developer work. **Note**: Links created via S2S can also collect impression data.

### Attribution link

| Property | Values |
| --- | --- |
| Base URL | engagements.appsflyer.com/v1.0/c2s/click/app/ |
| Mandatory path parameters | <ul><li>platform<br />Example: steam</li><li>app\_id<br />Example: 123456</li></ul> |
| Mandatory query parameters | <ul><li>af\_media\_source</li><li>af\_campaign\_id</li></ul> |
| Other parameters | [See all parameters](/docs/ctv-pc-and-console-platform-direct-attribution-links#parameters) |
| URL structure | `https://engagements.appsflyer.com/v1.0/c2s/click/app/{platform}/{app_id}?af_media_source={media_source}&af_campaign_id={campaign_id}&af_r={app_store_url}` |
| Sample URL | `https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=aloha&af_campaign_id=1234&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello` |

### Parameters

| Parameter | Display name in Raw data export and Pull API | Description | Field type |
| --- | --- | --- | --- |
| platform | Platform | <ul><li>Path param that specified the application platform.</li><li>Possible values:<ul><li>smartcast</li><li>tizen</li><li>roku</li><li>webos</li><li>vidaa</li><li>playstation</li><li>steam</li><li>quest</li><li>battlenet</li><li>epic</li><li>switch</li><li>xbox</li><li>nativepc</li></ul></li></ul> | String |
| app\_id | App ID | <ul><li>Path param that specifies the app ID of the app for which you are posting.</li><li>Example: `ap123456`</li><li>Do not add a platform prefix to the app ID value. For example, If the app ID is `ap123456`, and the platform is `platformX` , do not use `platformX_ap123456` as the `app_id` value.</li></ul> | String |
| af\_media\_source | Media Source | This is the unique partner identifier as defined on the AppsFlyer platform.  <br />The following special characters are not allowed: ;, *, !, @, #, ?, $, ^, :, &, ~, \`, =, +, ’, >, &lt;, /, \{, \}, %. | String |
| af\_campaign | Campaign | Campaign name | String |
| af\_campaign\_id | Campaign ID | Campaign ID | String |
| af\_request\_id | N/A | An identifier that uniquely identifies a request by a partner. | String |
| af\_adset | Adset | Adset name | String |
| af\_adset\_id | Adset ID | Adset ID | String |
| af\_ad | Ad | Ad name | String |
| af\_ad\_id | Ad ID | Ad ID | String |
| af\_campaign\_type | Campaign Type | Either:<ul><li>user\_acquisition</li><li>retargeting</li></ul> | String |
| af\_prt | Partner | <ul><li>Agency account name that enables attributing installs to the agency</li><li>**Caution**: Don't use this parameter before ensuring that **Agency Permissions** are enabled</li></ul> | String |
| af\_siteid | Site ID | <span id="query-getImpressionAppPlatformApp_id_af_siteid__description"></span>Unique ID that identifies the publisher that displays the ad | String |
| af\_sub\_siteid | Sub Site ID | <span id="query-getImpressionAppPlatformApp_id_af_sub_siteid__description"></span>Ad sub-network/publisher ID | String |
| af\_click\_id | N/A | <span id="query-getImpressionAppPlatformApp_id_af_click_id__description"></span>Ad network unique transaction identifier | String |
| af\_lookback\_window | N/A | <ul><li>Configurable number of days/hours for the lookback window attribution period. Available parameter values:<ul><li>Clicks: 1d-7d (days).</li><li>Impressions: 1d-7d (days) OR 1h-23h (hours).</li></ul></li><li>Validation: 3 char max, using the scheme above.</li><li>Default value is 24 hours for impressions and 7 days for clicks.</li></ul> | String |
| af\_ad\_placement | N/A | <span id="query-getImpressionAppPlatformApp_id_af_ad_placement__description"></span>Ad network unique transaction identifier | String |
| af\_ad\_type | Ad Type | <ul><li>Ad type. Use the following naming convention:<ul><li>**text:** an ad unit containing only text, for example a search result</li><li>**banner:** a basic format that appears at the top or bottom of the device screen</li><li>**interstitial:** a full-page ad that appears during breaks in the current experience</li><li>**video:** a standard video, that is non-rewarded</li><li>**rewarded\_video:** an ad unit offering in-app rewards in exchange for watching a video</li><li>**playable:** an ad unit containing an interactive preview of the app experience</li><li>**audio:** an audio ad</li></ul></li><li>Case-sensitivity enforcement.</li></ul> | String |
| af\_channel | Channel | <span id="query-getImpressionAppPlatformApp_id_af_channel__description"></span>The media source channel through which the ads are distributed, for example, UAC\_Search, UAC\_Display, Instagram, Meta Audience Network, etc. | String |
| af\_model | Device Model | Device model | String 64 |
| af\_os\_version | N/A | <ul><li>Device OS version</li><li>Only digits and dots allowed</li><li>Example: 8.1.0</li></ul> | String |
| af\_device\_id\_type | N/A | <span id="query-getImpressionAppPlatformApp_id_af_device_id_type__description"></span>Device identifier type. Either:<ul><li>vida</li><li>tifa</li><li>rida</li><li>lgudid</li><li>fire</li><li>advertising\_id</li><li>fire</li><li>custom</li></ul> | String |
| af\_device\_id\_value | N/A | <span id="query-getImpressionAppPlatformApp_id_af_device_id_value__description"></span>Device identifier type | String |
| af\_r | N/A | <ul><li>Contains the link to the correct app store or landing page</li><li>Everything within the af\_r parameter needs to be encoded. This includes any UTM parameter values, if appended.</li></ul>**Note:** Ensure that the URL domain for af\_r is included in your <Anchor target="_blank" href="/marketers/docs/set-up-your-domain-redirect-allowlist">redirect allowlist</Anchor>. | String |

## Traits and limitations

| Trait | Remarks |
| --- | --- |
| Agency attribution | <ul><li>CTV-PC-Console to mobile flow - agency attribution is supported.</li><li>Mobile to CTV-PC-Console flow - agency attribution isn't supported.</li></ul> |

<div data-zendesk-anchors="01H7Z1003GTTMRY072BXWDFNP0=overview 01H7Z1003G0WYBCK3530064WM1=attribution-link attribution-link-parameters=parameters 01H7Z1003GNC551PDCKKFQMPVN=parameters h_01HVED5DJPFR5XCWYDSYCHMCR6=traits-and-limitations" />
