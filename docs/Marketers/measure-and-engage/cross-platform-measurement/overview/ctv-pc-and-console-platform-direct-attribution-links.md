---
title: "CTV, PC, and console platform direct attribution links"
excerpt: "Learn about the AppsFlyer attribution link structure and parameters for CTV, PC, and console platforms."
---
> 📘 Note
>
> For Android and iOS apps, including Android PC games, use [mobile attribution link instructions](https://support.appsflyer.com/hc/articles/207447163).

## Overview

CTV, PC, and console platform direct attribution links allow advertisers to redirect users and collect data following clicks. These direct attribution links are AppsFlyer links that support redirection and attribution **for a single destination app on a single platform at a time**. The redirection destination is the value of the af_r parameter included in the link.

> 📘 Note
>
> For Android and iOS apps, including Android PC games, use [mobile attribution link instructions](https://support.appsflyer.com/hc/articles/207447163).

Attribution links can be directly created by you and placed behind ads. To create such links, follow the instructions in this article.

Alternatively, links can be created via S2S using the [Engagements API](https://dev.appsflyer.com/hc/reference/get_click-app-platform-app-id). This requires some developer work. **Note**: Links created via S2S can also collect impression data.

### Attribution link

| Property | Values |
| --- | --- |
| Base URL | engagements.appsflyer.com/v1.0/c2s/click/app/ |
| Mandatory path parameters | - platform<br>  <br>  Example: steam<br>- app\_id<br>  <br>  Example: 123456 |
| Mandatory query parameters | - af\_media\_source<br>- af\_campaign\_id |
| Other parameters | [See all parameters](https://support.appsflyer.com/hc/articles/15199908310801#attribution-link-parameters) |
| URL structure | `https://engagements.appsflyer.com/v1.0/c2s/click/app/{platform}/{app_id}?af_media_source={media_source}&af_campaign_id={campaign_id}&af_r={app_store_url}` |
| Sample URL | `https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=aloha&af_campaign_id=1234&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello` |

### Parameters

| Parameter | Display name in Raw data export and Pull API | Description | Field type |
| --- | --- | --- | --- |
| platform | Platform | - Path param that specified the application platform.<br>- Possible values:<br>  - smartcast<br>  - tizen<br>  - roku<br>  - webos<br>  - vidaa<br>  - playstation<br>  - steam<br>  - quest<br>  - battlenet<br>  - epic<br>  - switch<br>  - xbox<br>  - nativepc | String |
| app\_id | App ID | - Path param that specifies the app ID of the app for which you are posting.<br>- Example: `ap123456`<br>- Do not add a platform prefix to the app ID value. For example, If the app ID is `ap123456`, and the platform is `platformX` , do not use `platformX_ap123456` as the `app_id` value. | String |
| af\_media\_source | Media Source | This is the unique partner identifier as defined on the AppsFlyer platform.<br>The following special characters are not allowed: ;, \
*, !, @, #, ?, $, ^, :, &, ~, \
`, =, +, ’, >, <, /, \{, \}, %. | String |
| af\_campaign | Campaign | Campaign name | String |
| af\_campaign\_id | Campaign ID | Campaign ID | String |
| af\_request\_id | N/A | An identifier that uniquely identifies a request by a partner. | String |
| af\_adset | Adset | Adset name | String |
| af\_adset\_id | Adset ID | Adset ID | String |
| af\_ad | Ad | Ad name | String |
| af\_ad\_id | Ad ID | Ad ID | String |
| af\_campaign\_type | Campaign Type | Either:<br>- user\_acquisition<br>- retargeting | String |
| af\_prt | Partner | - Agency account name that enables attributing installs to the agency<br>- **Caution**: Don't use this parameter before ensuring that **Agency Permissions** are enabled | String |
| af\_siteid | Site ID | Unique ID that identifies the publisher that displays the ad | String |
| af\_sub\_siteid | Sub Site ID | Ad sub-network/publisher ID | String |
| af\_click\_id | N/A | Ad network unique transaction identifier | String |
| af\_lookback\_window | N/A | - Configurable number of days/hours for the lookback window attribution period. Available parameter values: <br>  - Clicks: 1d-7d (days).<br>  - Impressions: 1d-7d (days) OR 1h-23h (hours).<br>- Validation: 3 char max, using the scheme above.<br>- Default value is 24 hours for impressions and 7 days for clicks. | String |
| af\_ad\_placement | N/A | Ad network unique transaction identifier | String |
| af\_ad\_type | Ad Type | - Ad type. Use the following naming convention:<br>  - **text:** an ad unit containing only text, for example a search result<br>  - **banner:** a basic format that appears at the top or bottom of the device screen<br>  - **interstitial:** a full-page ad that appears during breaks in the current experience<br>  - **video:** a standard video, that is non-rewarded<br>  - **rewarded\_video:** an ad unit offering in-app rewards in exchange for watching a video<br>  - **playable:** an ad unit containing an interactive preview of the app experience<br>  - **audio:** an audio ad<br>- Case-sensitivity enforcement. | String |
| af\_channel | Channel | The media source channel through which the ads are distributed, for example, UAC\_Search, UAC\_Display, Instagram, Meta Audience Network, etc. | String |
| af\_model | Device Model | Device model | String 64 |
| af\_os\_version | N/A | - Device OS version<br>- Only digits and dots allowed<br>- Example: 8.1.0 | String |
| af\_device\_id\_type | N/A | Device identifier type. Either:<br>- vida<br>- tifa<br>- rida<br>- lgudid<br>- fire<br>- advertising\_id<br>- fire<br>- custom | String |
| af\_device\_id\_value | N/A | Device identifier type | String |
| af\_r | N/A | - Contains the link to the correct app store or landing page<br>- Everything within the af\_r parameter needs to be encoded. This includes any UTM parameter values, if appended.<br>**Note:** Ensure that the URL domain for af\_r is included in your [redirect allowlist](/docs/set-up-your-domain-redirect-allowlist). | String |

## Traits and limitations

| | |
| --- | --- |
| Agency attribution | - CTV-PC-Console to mobile flow - agency attribution is supported.<br>- Mobile to CTV-PC-Console flow - agency attribution isn't supported. |