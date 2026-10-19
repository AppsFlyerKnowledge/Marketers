---
title: About link structure and parameters
excerpt: Learn about the AppsFlyer attribution link structure and parameters.
metadata:
  keywords:
    - pid
    - Marketers
    - af_
    - af
    - c
    - af_mp
    - clickid
    - af_siteid
    - af_sub_siteid
    - af_c_id
    - af_adset_id
    - af_ad_type
    - af_viewthrough
    - af_cost_model
    - af_cost_value
    - af_web_dp
    - af_ref
    - af_ip
    - af_os_version
    - deep_link_sub
    - deep_link_value
    - af_og_title
    - af_og_description
    - af_og_image
    - af_prt
    - af_adset
    - af_ad
    - af_ad_id
    - af_channel
    - af_keywords
    - af_cost_currency
    - af_sub
    - af_r
    - af_dp
    - af_force_deeplink
    - is_incentivized
    - af_param_forwarding
    - af_partner_account_id
    - af_ua
    - af_os
    - af_model
    - af_media_type
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2015-12-24T11:50:00Z'
  edited_at: '2026-08-13T10:48:12Z'
  id: 207447163
  locale: en-us
  section: Attribution concepts
  section_id: 6551394235409
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/207447163-About-link-structure-and-parameters
---
## Overview

Attribution links allow advertisers to collect data about user engagement with an ad. Attribution links are placed behind ads and notify AppsFlyer when users engage with an ad. The engagement can occur via a click on an ad or when a user views an ad impression. A copy of the attribution URL is sent to AppsFlyer.

Attribution links are generated using **OneLink** or a **single-platform link**.

|  | OneLink (multi-platform link) | Single-platform link |
| --- | --- | --- |
| Description and when to use | Use when:<ul><li>You want a single link for all platforms.</li><li>Deep linking capabilities are required.</li><li>You want to use Android App Links or iOS Universal Links to open the app.</li></ul>[Learn more about OneLink](/docs/onelink-guide) | Use when:<ul><li>You only use a single platform. For example, Android and not iOS.</li><li>You only use URI schemes to open the app.</li></ul>[Learn more on how to set up an integrated partner](/docs/set-up-an-integrated-partner#attribution-link-tab) |
| Prerequisites | [OneLink template](/docs/create-a-onelink-template) | None |
| Information to include | <ul><li>[Media source](/docs/about-link-structure-and-parameters#partner-id-pid-parameter)</li><li>[Campaign](#c)</li><li>[Site ID / Sub Site ID](/docs/about-link-structure-and-parameters#site-id-parameter)</li></ul> | <ul><li>[Media source](/docs/about-link-structure-and-parameters#partner-id-pid-parameter)</li><li>[Campaign](#c)</li><li>[Site ID / Sub Site ID](/docs/about-link-structure-and-parameters#site-id-parameter)</li></ul> |
| Base URL | `{subdomain}`.onelink.me | app.appsflyer.com |
| Unique identifier | Template ID | app\_id |
| URL structure | `https://{subdomain}.onelink.me/``{templateid}?pid={media_source}``&af_siteid={ApplicationID}``&c={CampaignName}` | `https://app.appsflyer.com/{app_id}?pid={media_source}&af_siteid={ApplicationID}&c={CampaignName}` |
| Example | `https://yourbrand.onelink.me/aAB1?pid=greatnetwork_int``&c=GreatCampaign&af_siteid=A1b1` | `https://app.appsflyer.com/com.greatapp?pid=greatnetwork_int&``c=GreatCampaign&af_siteid=A1b1` |

> 📘 **Important!**
>
> AppsFlyer supports only the HTTPS protocol for incoming engagement traffic, i.e. clicks and impressions.

## Attribution link parameters

* The parameters listed are available for use in the attribution link.
* The value **field type** column is the character limit of the parameter value. Find more about limitations on the length of parameter values [here.](/docs/raw-data-field-dictionary)

### Attribution link parameters—UA and retargeting

The following table can be [downloaded as a `.csv` file](https://docs.google.com/spreadsheets/d/e/2PACX-1vTZQnoDdFo2NxBuWXBs5gGgvkGU2pr_hn58H9Dtf5uHBAHv4Io89Wd44rRtL24pRsOXHthnBitaOyfp/pub?gid=0&single=true&output=csv).

<div id="attribution-parameters" />

| Parameter | Display name in raw data | Description | Field type and length |
| --- | --- | --- | --- |
| <span id="pid"></span>pid | Media Source | Uniquely identifies an AppsFlyer integrated partner. Don't change it. [More details](/docs/about-link-structure-and-parameters#partner-id-pid-parameter). | <span id="PID"></span>String 150 |
| <span id="c"></span>c | Campaign | Provided by the advertiser or the publisher. See [limits on campaign names](/docs/about-link-structure-and-parameters#what-limits-are-there-on-campaign-names). | <span id="Campaign"></span>String |
| <span id="af_prt"></span>af\_prt | Partner | <ul><li>Agency Account Name enables attributing installs to the agency</li><li>**Caution**: Don't use this parameter before ensuring that **Agency Permissions** are enabled</li></ul> | String 50 |
| <span id="af_mp"></span>af\_mp | N/A | <ul><li>Enable sending postbacks to publisher marketing partners per install.</li><li>**Note**: Currently, this parameter is relevant only for Pinterest Marketing Partners.</li></ul> |  |
| <span id="clickid"></span>clickid | N/A | Ad network unique click identifier |  |
| <span id="af_siteid"></span>af\_siteid | Site ID | <ul><li>Unique ID that identifies the publisher that displays the ad. [Learn more](/docs/about-link-structure-and-parameters#site-id-parameter)</li></ul> | <span id="Site_id"></span>String 24 |
| <span id="af_sub_siteid"></span>af\_sub\_siteid | Sub Site ID | <ul><li>Ad sub-network/Publisher ID.</li><li>If in addition to the main publisher (site ID), there is a sub-publisher, or you want to include additional info, such as ad type/placement within the app, like banner, interstitial, video, etc. use af\_sub\_siteid. For example: af\_sub\_siteid =ABCD\_4567</li></ul> | String |
| <span id="af_c_id"></span>af\_c\_id | Campaign ID | Provided by the advertiser/publisher | String 24 |
| <span id="af_adset"></span>af\_adset | Adset | <ul><li>Provided by the advertiser/publisher.</li><li>Adset is an intermediate level in the hierarchy between Campaign and Ad. [See more](/docs/about-link-structure-and-parameters#levels-of-data-granularity)</li></ul> | String 100 |
| <span id="af_adset_id"></span>af\_adset\_id | Adset ID | Provided by the advertiser/publisher | String 24 |
| <span id="af_ad"></span>af\_ad | Ad | Ad Name ([see more](/docs/about-link-structure-and-parameters#levels-of-data-granularity)) provided by the advertiser/publisher | String 100 |
| <span id="af_ad_id"></span>af\_ad\_id | Ad ID | Provided by the advertiser/publisher | String 24 |
| <span id="af_ad_type"></span>af\_ad\_type | Ad type | Use the following naming conventions:<ul><li>**native**: Paid media designed to match the content of a media source. This media is designed to match the visual design and function of natural content, appearing in your feed of recommended videos.</li><li>**banner**: Display ads that are typically small rectangular advertisements that appear at various locations of a web page or app interface.</li><li>**interstitial**: Full-screen ads that cover the entire interface of the host app. These ads are designed to be placed between content and are typically displayed at transition points within the app flow, such as between activities or game levels, or while on pause.</li><li>**rewarded\_video**: Ads that users can choose to view to completion in exchange for an in-app reward — such as watching a video for extra life in the game, access to an article, or entry to Wi-Fi at an airport. These “rewarded” ads engage users and offer a better overall app experience.</li><li>**audio**: Ads in audio format delivered within online podcasts or music streaming platforms.</li><li>**offerwall**: An in-app advertising unit that developers use to monetize their apps. It acts like a mini-store within the app, listing multiple “offers” that users can complete in exchange for an in-app reward.</li></ul> | String 24 |
| <span id="af_ad_format"></span>af\_ad\_format | Ad format | Use the following naming conventions:<ul><li>**text**: A text-based ad that usually appears as a brief snippet of text. It may include a headline, description, and a link or call-to-action designed to create interest and encourage a click-through to a website or landing page.</li><li>**image**: A visual advertisement that showcases a product, service, or brand using graphics or photographs. It typically includes a captivating image along with concise text and may also incorporate a call to action.</li><li>**video**: A digital ad that uses audiovisual content to convey a marketing message. It can vary in length and may appear as pre-roll, mid-roll, or post-roll within online video content or as standalone videos on various platforms.</li><li>**playable**: An interactive ad allowing users to engage with a miniature version of a game or app before downloading or making a purchase. It grants users a hands-on taste of actual gameplay or app functionality.</li><li>**interactive**: An engaging and dynamic advertisement encouraging users to interact or participate. It may involve quizzes, polls, or other interactive elements to capture users' attention and encourage active participation.</li><li>**dynamic\_product**: A personalized ad format that dynamically populates product information and details based on user behavior, preferences, or browsing history. It lets advertisers display highly relevant and tailored product ads to individuals.</li><li>**carousel**: An ad format consisting of multiple slides or cards within a single advertisement. Each card can include a different image, headline, and description, allowing advertisers to showcase multiple products or features in a single ad.</li></ul> |  |
| <span id="af_click_lookback"></span>af\_click\_lookback | Attribution lookback window | <ul><li>Lookback Window for Click Attribution. This window's duration is the maximum CTIT (Click Time to Install) for the new user to be attributed to the source displaying the ad/link.</li><li>Configurable number of days for the lookback click attribution period. Available parameter values: 1d - 30d (days) OR 1h-23h (hours). The default value is 7d.</li><li>The lookback window can be customized for [OneLinks and SRNs](/docs/set-up-lookback-windows#lookback-window-setup).</li></ul>**Note**: Only affects click URLs and not impression URLs. | 3 char max |
| <span id="af_viewthrough_lookback"></span>af\_viewthrough\_lookback | N/A | <ul><li>Configurable number of hours for the lookback view-through attribution period. Available parameter values: 1h - 24h (hours). The default is 24h.</li><li>The lookback window can be customized for [SRNs](/docs/set-up-lookback-windows#lookback-window-setup).</li></ul>**Note**: Only affects impression URLs and not click URLs | 3 char max |
| <span id="af_channel"></span>af\_channel | Channel | The media source channel through which the ads are distributed, for example, UAC\_Search, UAC\_Display, Instagram, Meta Audience Network, etc. | Dynamic Enum. String 20 |
| <span id="af_engagement_destination"></span>af\_engagement\_destination | Engagement destination | Indicates the category of the destination linked from the ad, such as a **web** landing page, a **mobile** app (via a deep link or an app store), or other destination types such as **CTV**, **PC**, or **Console**. | String 50 |
| <span id="af_keywords"></span>af\_keywords | Keywords | Keywords list for text-targeted campaigns | String 100 |
| <span id="af_cost_model"></span>af\_cost\_model | Cost model | <ul><li>Cost model, CPI (default) is currently the only supported model when reporting cost by click, which populates [cost value in AppsFlyer aggregated data](/docs/roi360-cost-aggregation-overview#cost-data-availability-and-reports) reports.</li><li>Where possible, report cost by [API.](/docs/roi360-cost-aggregation-overview#cost-aggregation-methods) In cases where cost is reported by on the link and by API - API has priority.</li></ul> | String 20 |
| <span id="af_cost_currency"></span>af\_cost\_currency | Cost currency | <ul><li>3 letter currency code compliant with [ISO-4217.](/docs/roi360-cost-aggregation-overview#cost-aggregation-methods) For example, USD, ZAR, EUR</li><li>[Default]: USD</li></ul> | Enum. 3 char |
| <span id="af_cost_value"></span>af\_cost\_value | Cost value | <ul><li>Cost value in using cost currency.</li><li>Up to 4 digits after the decimal point.</li><li>Set ONLY numerical digits (use a decimal point if needed) Example: "56", "2.85"</li></ul> | Numeric |
| <span id="af_sub-n-n15-example-af_sub1"></span>af\_sub[n]<br /><br />(n=1-5) example: af\_sub1 | Sub param [n] | Optional custom parameter defined by the advertiser. For more information about the usage of these parameters, check the [Traits and limitations](/docs/about-link-structure-and-parameters#traits-and-limitations) section. | String 100 |
| <span id="af_r"></span>af\_r | N/A | Used to redirect users to the specified URL in **all platforms** (Android, iOS, and desktop).<br /><br />In multi-platform links (OneLink) this parameter:<ul><li>Overrides template-level redirection setup</li><li>Is overridden by the following link-level parameters:<ul><li>[`af_android_url`](/docs/about-link-structure-and-parameters#af_android_url)</li><li>[`af_ios_url`](/docs/about-link-structure-and-parameters#af_ios_url)</li><li>[`af_web_dp`](/docs/about-link-structure-and-parameters#af_web_dp)</li></ul></li></ul>**Note:** See additional redirection parameter [traits and limitations](/docs/about-link-structure-and-parameters#special-characters). |  |
| <span id="af_web_dp"></span>af\_web\_dp | N/A | URL to redirect desktop (for example, Windows or Mac) users to a different web page than configured in the OneLink template. Use this to keep attribution data of desktop users on other platforms (for example, Google Analytics or Omniture)<br /><br />**Note:** See additional redirection parameter [traits and limitations](/docs/about-link-structure-and-parameters#special-characters). |  |
| <span id="af_dp"></span>af\_dp | N/A | The URI scheme fallback value to launch the app, to be used if the Universal Link or Android App Link method fails, and for Android users below 6.0. It should only point to the [base path](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking), i.e. the default activity.<br /><br />**Note:** If you use a web URL value for this parameter (not recommended), be sure to review the redirection parameter [traits and limitations](/docs/about-link-structure-and-parameters#special-characters). |  |
| <span id="af_force_deeplink"></span>af\_force\_deeplink | N/A | [Force deep linking](/docs/onelink-troubleshooting-and-faq) into the activity specified in af\_dp value |  |
| <span id="af_ref"></span>af\_ref | N/A | Ad networks working with S2S clicks can send a unique referrer value using the following parameter: &af\_ref=**ReferrerValue**<br /><br />The af\_ref value **must** consist of a unique value, structured as follows:<br /><br />**NetworkName\_UniqueClickValueForEachClick**<br /><br />Example: af\_ref=networkname\_123456789ABCDEF<br /><br />The network name can be any valid string. It can be networkname\_int or just network name.<br /><br />AppsFlyer may use this parameter for attribution in Android devices. AppsFlyer doesn't use this parameter for attribution in iOS or Windows devices. |  |
| <span id="is_incentivized"></span>is\_incentivized | N/A | Boolean: true/false<br /><br />Incentivized or non-incentivized campaigns |  |
| <span id="af_param_forwarding"></span>af\_param\_forwarding | N/A | <ul><li>When set to false, parameters that are on the attribution link are not forwarded to the redirected page.</li><li>Use this for a cleaner looking URL in the redirected page, or if attribution link parameters might cause issues due to query parameter handling on the redirected page.</li></ul> |  |
| <span id="af_base_params_forward"></span>af\_base\_params\_forward | N/A | <ul><li>When set to false, AppsFlyer PID and C parameters that are on the attribution link are not forwarded to the redirected page.</li><li>Use this if the URL is going to be clicked from a desktop and you want essential CRM parameters to remain but the AppsFlyer PID and C parameters to be removed. This will avoid having multiple PIDs in the URL.</li></ul> |  |
| <span id="af_partner_account_id"></span>af\_partner\_account\_id | Network Account ID | Advertiser's account ID with the partner | String 100 |
| <span id="af_redirect"></span>redirect | N/A | When`&redirect=false`, this parameter lets AppsFlyer know that this is an S2S click and that the partner is responsible for redirecting the user that clicked. |  |
| <span id="af_ua"></span>af\_ua | User-agent | Relevant for ad networks that send clicks and impressions [server-to-server (S2S)](/partners/docs/redirecting-users-to-the-app-store).<br /><br />**Important:** Don’t use `af_ua` in client-to-server (C2S) links. Using `af_ua` in a C2S link may affect attribution.<br /><br />The user-agent string sent as:<ol><li>URL parameter (URL-encoded)</li><li>HTTP request header (unencoded)</li></ol>The User-Agent should be **identical in both the URL parameter and the HTTP header**.<br /><br />**In Android**, the user-agent is sometimes reduced due to Client Hints. It should be sent regardless.<ul><li>**Example of full user-agent:** `Mozilla/5.0 (Linux; Android 12; Pixel 5) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/95.0.4638.16 Mobile Safari/537.36`</li><li>**Example of reduced user-agent:** `Mozilla/5.0 (Linux; Android 10; K) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/95.0.0.0 Mobile Safari/537.36`</li></ul>**In iOS**, starting iOS 26 the version is appended.<br />Here is:<ul><li>**An example of the appended part:** `Version/26.0.1 Mobile/15E148 Safari/604.1`</li><li>**An example of the full user-agent:**<br />`Mozilla/5.0 (iPhone; CPU iPhone OS 16_4_1 like Mac OS X) AppleWebKit/8615.1.26.10.24 (KHTML, like Gecko) Mobile/20E252 Version/26.0.1 Mobile/15E148 Safari/604.1`</li></ul> |  |
| <span id="af_ip"></span>af\_ip | IP | Relevant for ad networks that send clicks and impressions [server-to-server](/partners/docs/redirecting-users-to-the-app-store).<br /><br />**Important:** Don’t use `af_ip` in client-to-server (C2S) links. Using `af_ip` in a C2S link may affect attribution.<br /><br />**Device IP address**<br /><br />**Recommended**: If available, provide the device IP under the `af_ip` parameter.<br /><br />**Next option**: If available, AppsFlyer will use the IP in X-Forwarded-For. |  |
| <span id="deprecated--af_os"></span>[Deprecated] af\_os | OS version | [For iOS only] The device operating system version.<br /><br />This parameter is deprecated but still supported by AppsFlyer. Recommended: Use the af\_os\_version parameter instead. |  |
| <span id="af_os_version"></span>af\_os\_version | OS version | <ul><li>Relevant for ad networks that send clicks and impressions [server-to-server](/partners/docs/redirecting-users-to-the-app-store).</li><li>The device operating system version.<ul><li>Android:<ul><li>Example: 12</li><li>For reduced user-agent (due to browsers running on desktop or Android and using the Chrome 110+ engine), the ad network must use the [Client Hints API](https://web.dev/migrate-to-ua-ch/) to get this value.</li><li>For user-agent that **isn’t** reduced, use the following regex to extract the Android OS version from the user-agent string: `(\d+(?:\.\d+)*);(?:\s..-..;)?\s(.+?(?=\)\|\s\w*\/))`.</li></ul></li><li>iOS:<ul><li>Include the full OS version for accurate attribution. For example: 18.6.2</li></ul></li></ul></li></ul> |  |
| <span id="af_model"></span>af\_model | Device model | <ul><li>Relevant for ad networks that send clicks and impressions [server-to-server](/partners/docs/redirecting-users-to-the-app-store).</li><li>The device model.<ul><li>Android:<ul><li>Example: Pixel 5</li><li>For reduced user-agent (due to browsers running on desktop or Android and using the Chrome 110+ engine), the ad network must use the [Client Hints API](https://web.dev/migrate-to-ua-ch/) to get this value.</li><li>For user-agent that **isn’t** reduced, use the following regex to extract the Android model from the user-agent string: `(\d+(?:\.\d+)*);(?:\s..-..;)?\s(.+?(?=\)\|\s\w*\/))`.</li></ul></li><li>iOS:<ul><li>Include the full device model identifier for accurate attribution. For example: `iphone15,1`or `ipad14,2`.</li></ul></li></ul></li></ul> |  |
| <span id="af_media_type"></span>af\_media\_type | Media type | Placement of the ad carrying the link as follows:<ul><li>app: The link is available via an app</li><li>web: The link is available within a mobile website</li></ul> |  |
| <span id="deep_link_sub110"></span>deep\_link\_sub1-10 | N/A | Additional deep link values. Developers implement the desired behavior of the values in the code. |  |
| <span id="deep_link_value"></span>deep\_link\_value | N/A | The name for the specific in-app content that users will be directed to. Developers implement the desired behavior of the deep\_link\_value in the code. |  |
| <span id="af_og_title"></span>af\_og\_title | N/A | When a link is posted to social media, open graph (OG) title will generate a preview of the title. | String 40 |
| <span id="af_og_description"></span>af\_og\_description | N/A | When a link is posted to social media, open graph (OG) description will generate a preview of the description. | String 300 |
| <span id="af_og_image"></span>af\_og\_image | N/A | When a link is posted to social media, open graph (OG) image will generate a preview of the image. |  |

### Attribution link parameters—retargeting only

| Parameter | Display name in raw data | Description | Field type and width |
| --- | --- | --- | --- |
| <span id="is_retargeting"></span>is\_retargeting | Is Retargeting (campaign) | The click URL of all retargeting campaigns must include `&is_retargeting=true`.  <br />If the parameter is not included or its value is "false," the campaign is considered as a regular user acquisition campaign. | Enum 5 char |
| <span id="af_reengagement_window"></span>af\_reengagement\_window | Re-engagement window | Change the [re-engagement attribution window](/docs/retargeting-attribution-guide#reengagement-rules-and-windows) by adding this parameter to the attribution link.<br /><br />The possible window range options are:<ul><li>Days: 1-90 or Hours 1-36</li><li>Lifetime: This means the re-engagement window is unlimited. Example:`&af_reengagement_window=lifetime`</li></ul>Default value: 30 days<br /><br />Example:`&af_reengagement_window=30d` sets the re-engagement window to 30 days. | N/A |

### Viewability parameters

Depending on the ad type, you can also send the relevant viewability parameter detailing the specifications of the engagement.

| Parameter | Value format | Description |
| --- | --- | --- |
| <span id="af_video_total_length"></span>af\_video\_total\_length | seconds | The total possible duration of the video |
| <span id="af_video_played_length"></span>af\_video\_played\_length | seconds | How much of the video was viewed |
| <span id="af_playable_played_length"></span>af\_playable\_played\_length | seconds | How long the playable element was played once fully loaded |
| <span id="af_ad_time_viewed"></span>af\_ad\_time\_viewed | seconds | How long the ad unit was visible on the screen |
| <span id="af_ad_displayed_percent"></span>af\_ad\_displayed\_percent | % | The maximum percentage of the ad unit that was visible on the device screen |
| <span id="af_audio_total_length"></span>af\_audio\_total\_length | seconds | The total possible duration of the audio |
| <span id="af_audio_played_length"></span>af\_audio\_played\_length | seconds | How much of the audio was heard |

### Android-specific parameters

| Parameter | Display name in raw data | Description | Field type |
| --- | --- | --- | --- |
| <span id="advertising_id"></span>advertising\_id | Advertising ID | Google Advertising ID - Requires ad network support | 40 char max |
| <span id="sha1_advertising_id"></span>sha1\_advertising\_id | N/A | Google Advertising ID hashed with SHA1 - Requires ad network support |  |
| <span id="md5_advertising_id"></span>md5\_advertising\_id | N/A | Google Advertising ID hashed with MD5 - Requires ad network support | Supported with installs and re-attributions only |
| <span id="android_id"></span>android\_id | Android ID | Device Android\_id - Requires ad network support | 20 char max |
| <span id="sha1_android_id"></span>sha1\_android\_id | N/A | Device Android\_id hashed with SHA1 - Requires ad network support |  |
| <span id="md5_android_id"></span>md5\_android\_id | N/A | Device Android\_id hashed with MD5 - Requires ad network support | Supported with installs and re-attributions only |
| <span id="imei"></span>imei | IMEI | Device IMEI ID |  |
| <span id="sha1_imei"></span>sha1\_imei | N/A | Device IMEI ID hashed with SHA1 - Requires ad network support |  |
| <span id="md5_imei"></span>md5\_imei | N/A | Device IMEI ID hashed with MD5 - Requires ad network support |  |
| <span id="oaid"></span>oaid | OAID | Open Anonymous Device Identifier | Available as of Android SDK version 4.10.3 |
| <span id="sha1_oaid"></span>sha1\_oaid | N/A | Open Anonymous Device Identifier hashed with SHA1 - Requires ad network support | Available as of Android SDK version 4.10.3 |
| <span id="md5_oaid"></span>md5\_oaid | N/A | Open Anonymous Device Identifier hashed with MD5 - Requires ad network support | Available as of Android SDK version 4.10.3 |
| <span id="af_android_url"></span>af\_android\_url | N/A | Redirect Android users to a different URL than the app page on Google Play. Use for [third-party app stores](/docs/set-up-multi-store-android-attribution#single-dashboard-vs-dashboard-per-store).<br /><br />**Note:** See additional redirection parameter [traits and limitations](/docs/about-link-structure-and-parameters#special-characters). |  |
| <span id="sha1_el"></span>sha1\_el | N/A | Used for desktop to mobile attribution - email hashed with SHA1. Requires ad network support |  |
| <span id="fire_advertising_id"></span>fire\_advertising\_id | N/A | Amazon Fire Advertising ID |  |
| <span id="af_android_store_csl"></span>af\_android\_store\_csl | store\_product\_page | Custom store listing in Google Console | string |

### iOS-specific parameters

| Parameters | Display Name | Description |
| --- | --- | --- |
| <span id="idfa"></span>idfa | IDFA | Use upper case. Requires ad network support<br /><br />Field type: 40 char max |
| <span id="idfv"></span>idfv | IDFV | Use upper case. |
| <span id="af_ios_url"></span>af\_ios\_url |  | Use this for landing page redirections to redirect iOS (iPhone or iPad) users to a different URL than the app page on iTunes<br /><br />**Note:** See additional redirection parameter [traits and limitations](/docs/about-link-structure-and-parameters#special-characters). |
| <span id="af_ios_store_cpp"></span>af\_ios\_store\_cpp | store\_product\_page | Custom product page ID (ppid)<br /><br />**Note:** In raw data and aggregated reporting, the af\_ios\_store\_cpp (custom product page ID) parameter value is recorded for clicks but not for impressions. |
| <span id="af_ios_fallback--deprecated"></span>af\_ios\_fallback [deprecated] | N/A | **Deprecated**: Users are redirected based on the [iOS URI scheme flow](/docs/uri-scheme-fallback-for-ios). |
| <span id="sha1_idfa"></span>sha1\_idfa | N/A | IDFA hashed with SHA1. Requires ad network support |
| <span id="sha1_idfv"></span>sha1\_idfv | N/A | IDFV hashed with SHA1 |
| <span id="mac"></span>mac | N/A | Device mac address. Requires ad network support |
| <span id="md5_idfa"></span>md5\_idfa | N/A | IDFA hashed with MD5 |
| <span id="md5_idfv"></span>md5\_idfv | N/A | IDFV hashed with MD5 |
| <span id="sha1_mac"></span>sha1\_mac | N/A | Device mac address hashed with SHA1. Requires ad network support |

> 📘 **Example**
>
> ```
> https://app.appsflyer.com/`{app_id}`/?pid=airpush_int&c=RedBanner&
> 	  af_siteid=`{publisher_id}`&af_sub1=1.5&af_sub2=USD&af_sub3=burst_campaign
> ```

All parameters are available in the [Install report](/docs/raw-data-reporting-overview) and the [Analytics, Reports, and APIs](/docs/analytics-and-aggregate-reporting-apis).

### Custom parameters

In addition to default Android-specific and iOS-specific parameters, you can also specify custom parameters. These custom parameters can help you if you wish to customize the user experience and content according to the attribution link that leads to an install.

You can append custom parameters to the attribution link in the format `parameter=value`. For example:

```
https://app.appsflyer.com/com.greatapp?pid=networkx_int&c=winter&af_adset=coats&af_ad=cashmere&my_custom_param=my_custom_value
```

Two important things to know about custom parameters:

* Custom parameters don't appear in raw data.
* Custom parameters can be retrieved from the [get conversion data SDK API](https://dev.appsflyer.com/hc/docs/conversion-data).

<div id="partner-id-pid-parameter" />

<Accordion title="Partner ID (PID) parameter">

Among all available attribution link parameters, PID is mandatory.
The PID is the unique identifier of the media source allocated
by
AppsFlyer.

Each
[integrated partner](http://appsflyer.com/partners "AppsFlyer Active Integrations")
has a unique PID value, which ends with the *\_int* suffix.
When using
[OneLink links,](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink)
you can set the PID to any value you prefer, as long as it's
not
reserved by an integrated partner.

> 📘 **Note**
>
> AppsFlyer blocks attribution links that use reserved
> [SRN](/docs/self-reporting-networks-srns#srns-integrated-with-appsflyer)
> names as PID values in custom media sources, such as email
> and SMS.
> This restriction does **not** apply to ASRNs.

Examples of important integrated reserved publisher IDs: organic,
googleadwords\_int (Google AdWords), facebook\_int (Meta ads),
and
twitter\_int (X Ads). You can use any name for non-integrated
sources
like email, SMS, or mail pigeons.

#### Avoid common PID issues:

* **Always include PID in your attribution links.**
  Without the PID on the attribution link, the user is automatically
  attributed to a "None" media source, and the original installation
  source is gone.
* **For each integrated source**, use only the
  designated
  PID for the correct attribution of its installs.
* **For Custom Sources, use non-integrated partner PIDs.**
   For any custom media source, such as email, SMS, or
  even
  viral unpaid posts on Facebook use other, non-integrated
  PID
  values. such as owned\_email,
  sms\_push, or other custom
  identifiers
  that do not match the names of integrated partners.
* **Use only legal characters.** If the PID parameter
  in the Attribution Link contains one of the following characters
  ***/&lt;>*&?\***
  * The click or install appears in the dashboard under
    ***af\_invalid\_param***
  * Attribution links will not be attributed
  * Deep linking capabilities will not work on clicks

> 📘 **Tip**
>
> Avoid using white spaces in the PID value, or make sure to
> URL
> encode your attribution links before using them.

</Accordion>

<div id="site-id-parameter" />

<Accordion title="Site ID parameter">

The site ID is the unique identifier of the publisher serving
the
ad. In other words, the website or app displaying the ad. Ad
networks
allocate unique site IDs for each publisher.

This ID is included in the `af_siteid` parameter passed
to AppsFlyer in the attribution link and is made available via
the
various dashboards, reporting options, and postbacks.

The site ID must be passed to AppsFlyer in the attribution link
because
it:

* Provides clarity and transparency about the publisher
* Is used by AppsFlyer to identify and eliminate fraudulent
  publishers,
  and other traffic clusters.

The site ID parameter only includes the ID of the publisher that
serves the ad.

To include additional information, such as ad type, placement,
or
both within the app, for example, banner, interstitial, or video,
use the sub-site ID parameter.

> 📘 **Example**
>
> The following attribution link includes:
>
> * `af_siteid` (site ID): Publisher ID
> * `af_sub_siteid` (sub-site ID): Additional
>   ID info (in this case, an affiliate source and ad type
>   placement)
>
> `https://app.appsflyer.com/com.yourapp?pid=mediaName_int&clickid={clickid}&advertising_id={gaid}&af_siteid=1234&af_sub_siteid=ABCD_4567`
>
> In the example link:
>
> * 1234 = Publisher ID
> * ABCD = Affiliate source (sub-publisher) that the publisher
>   is working with
> * 4567 = Ad type placement within the app, such as banner,
>   interstitial, or video

#### **FAQ: Why does traffic result in many blocked installs?**

Blocked installs can be due to the following:

* **Missing site ID:** The `af_siteid`
  parameter is empty in the click URL. Engagements sent with
  an
  empty Site ID signify either a technical issue or an intentional
  attempt to bypass fraud detection mechanisms.
* **Multiple site IDs:** The same publisher is
  sent
  on multiple click URLs, using different site IDs. This is
  considered
  fraudulent behavior that masks the real publisher activity
  and
  is often associated with
  [click flooding](https://www.appsflyer.com/blog/click-flooding-detection-false-positive-challenge/).
* **Site ID formatted incorrectly:** Sending the
  wrong
  format, combined with other fraud indications, could result
  in
  blocking not only the specific publisher, but also of a higher
  cluster level, and might impact greater volumes of the partner
  activity.

To avoid blocked installs, make sure you send a single site ID
parameter
per publisher, as shown in the example.

</Accordion>

## Levels of data granularity

You can use up to four URL parameters to deep dive into your ads' performance.

Using all 4 parameters on all your active attribution links enables you to:

* Attribute all user installs and events to specific ads
* Drill down and compare the performance of all your ads per ad set, per campaign, and per media source on aggregated reports to optimize on every level
* Compare all of your ads across all media sources on the raw data reports and [Pivot table](/docs/pivot-table-user-metrics)

The parameters are:

* `Media source (pid=)`
* `campaign name (c=)`
* `Ad set (af_adset=)`
* `Ad name (af_ad=)`

> 📘 **Example**
>
> The following attribution link uses 4 levels of granularity to record the "cashmere" ad in the "coats" ad set in the "winter" campaign running on the integrated "network" media source.
>
> ```
> https://app.appsflyer.com/com.greatapp?pid=networkx_int&c=winter&
> af_adset=coats&af_ad=cashmere
> ```

## Frequently asked questions

<div id="should-i-use-lower-or-upper-case-letters-for-parameters" />

<Accordion title="Should I use lower or upper case letters for parameters">

You can use either, but you must be consistent. If you set a custom parameter with upper or lower case characters, make sure always to use that parameter.

For example, if you set pid=MyMediaSource, make sure always to use it. If you use pid=MyMediaSource on one attribution link and pid=mymediasource on another, discrepancies in data might occur. The same goes for any other param that you set on the attribution link.

</Accordion>

<div id="is-the-appsflyer-attribution-link-dynamic-or-static" />

<Accordion title="Is the AppsFlyer attribution link dynamic or static?">

Attribution links can be dynamic or static.  
How can you tell if a link is dynamic or static?  
If the **attribution link contains parameters**, it's a long pre-defined attribution link, and therefore **static**.  
**Only short URLs** (for example, `yourbrand.onelink.me/HaT8/r5c2b371`), used for custom attribution links, **are dynamic**.  
This means that once you start using an attribution link for an integrated partner, or a long URL for owned media, it would not change for any leads engaging with it, even if you change the attribution link values in the AppsFlyer dashboard. For the change to take place, you must use the new long URL going forward.  
On the other hand, short URLs for owned media, don't directly contain parameters. When a lead engages with an AppsFlyer short URL, the lead is redirected to AppsFlyer and the current set parameters take place dynamically.

</Accordion>

<div id="what-is-this-play-store-error-message" />

<Accordion title="What is this Play Store error message?">

If you ever encounter the following error message in the Play Store after following an attribution Link:

![TL_error_message.png](https://files.readme.io/03e509d3cbe68aa0621bb0f43ab113c25a8427e70826c5af5258f1fc9e3f3d36-360000002485.png)

This is because the attribution link includes a # character. For example:

```
https://app.appsflyer.com/com.travelco?pid=globalwide_int&clickid=#reqid#
```

Usually, these characters are in the link because they are macros, and are dynamically replaced by a value, so it is not a really big problem and you can ignore the message.

</Accordion>

<div id="what-are-subscriber-parameters-good-for" />

<Accordion title="What are subscriber parameters good for?">

The Subscriber Parameters, meaning af\_sub1, af\_sub2, ..., af\_sub\_5 can be used to record any useful KPIs. These parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.

> 📘 **Example**
>
> A hail ride app, Luber, has creatives with 3 color templates: blue, yellow, and red. Luber's mobile marketer, Linda, wants to test which color template brings in more installs. To do so she adds `&af_sub3=blue` in the attribution links of all the blue ads across ALL non-SRN media sources. The same is done for the yellow and red ads as well. With this information parsed and appearing in the raw data reports, Linda is able to analyze the success of the different colored ads and pick the best converting one.

</Accordion>

<div id="what-limits-are-there-on-campaign-names" />

<Accordion title="What limits are there on campaign names?">

* The maximum length of a campaign name in the attribution link URL is limited to 100 characters. If exceeded, the campaign name is changed to: `c_name_exceeded_max_length`
* The campaign name shouldn't start from or end with a white space, as it may cause discrepancies in dashboards and reports

</Accordion>

## Traits and limitations

| Traits | Remarks |
| --- | --- |
| <span id="special-characters"></span>Special characters | The following special characters are not allowed in parameter keys and values (not applicable to redirect and af\_dp parameters):  ;, *, !, @, #, ?, $, ^, :, &, ~, \`, =, +, ’, >, &lt;, /, \{, \}, %, ),( |
| <span id="redirection-parameters"></span>Redirection parameters | <ul><li>Make sure your redirection URL domains are added to your [redirect allowlist](/docs/set-up-your-domain-redirect-allowlist).</li><li>The redirection value must be a full valid (and publically accessible) web URL (https://[domain][optional-path]) in accordance with [RFC 1738 standards](https://datatracker.ietf.org/doc/html/rfc1738);</li><li>[URI Fragment identifiers](https://en.wikipedia.org/wiki/URI_fragment) **are not supported** in redirection URLs (e.g., #webpagesection which scrolls users down to a specific section in an article).</li></ul> |
| <span id="url-characteravailable"></span>URL character limit | Total URL length must not exceed 2000 characters |
| <span id="agencies"></span>Android social apps WebView deep linking redirection | See limitation details [here](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#android-social-apps-webview-deep-linking-redirection) |
| <span id="deep-linking-is-not-supported-in-the-android-naver-blog-app"></span>Deep linking is not supported in the Android Naver Blog app | Deep linking is not supported in the Android Naver Blog app. Users will be redirected to the Google Play Store or the web as defined by the link. |
| <span id="a-popup-appears-when-clicking-on-a-uri-scheme-link-from-chrome-browser-on-ios"></span>A pop-up appears when clicking on a URI scheme link from Chrome browser on iOS | Due to a change in Chrome iOS, whenever a user clicks a URI scheme link in Chrome on iOS, a pop-up is displayed, prompting the user to confirm opening the app or redirecting to the App Store. |
| <span id="uri-scheme-validity-requirements"></span>URI Scheme validity requirements | We recommend using a valid URI scheme that complies with [RFC 3986](https://www.rfc-editor.org/rfc/rfc3986#section-3.1). Schemes that do not comply with the above may fail to open an app and produce an error when clicked from a web view or other web environments. |
| <span id="telegram-webview-attribution"></span>Telegram WebView attribution | See limitation details [here](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#telegram-webview) |

<div data-zendesk-anchors="01H8GN1XXC5T2ENFHBK0G4WQ1P=overview 01JENAANV4KTRF882JMEM5N91A=important 01H8GN1XXDX1XMQ1GJTHCP425D=attribution-link-parameters attribution-link-parameters%E2%80%94ua-and-retargeting=attribution-link-parametersua-and-retargeting 01H8GN1XXDEWPB2MPP3KJVPRJV=attribution-link-parametersua-and-retargeting af_sub%5Bn%5D%C2%A0%0An15-example-af_sub1=af_sub-n-n15-example-af_sub1 %5Bdeprecated%5D-af_os=deprecated--af_os attribution-link-parameters%E2%80%94retargeting-only=attribution-link-parametersretargeting-only 01H8GN1XXD9X7CWZJN43PSS94R=attribution-link-parametersretargeting-only 01H8GN1XXETQEYT39F05ZYX4E2=viewability-parameters androidspecific-parameters=android-specific-parameters 01H8GN1XXEE9RGSB1H72H025Z4=android-specific-parameters iosspecific-parameters=ios-specific-parameters 01H8GN1XXESJ9VE3W8CYKRFFYX=ios-specific-parameters af_ios_fallback-%5Bdeprecated%5D=af_ios_fallback--deprecated 01H8GN1XXEFRSQSERTB6ARC773=example 01H8GN1XXEB58JN4SV9HX1ZV6S=custom-parameters 01H8GN1XXE8EXMMKDZMJ2WNNH5=partner-id-pid-parameter h_01JRX48BX8W9V9XWPB1DSG4H8Y=note 01H8GN1XXEXTGC4M8AMJ256Q9G=avoid-common-pid-issues 01H8GN1XXEGNVX9GM5JYBMBGCF=tip 01H8GN1XXEVG65YP782CM37RES=site-id-parameter 01H8GN1XXED2MVSNRXN11KZ955=example-1 01H8GN1XXEK0G9TDW8WHWM17HK=faq-why-does-traffic-result-in-many-blocked-installs 01H8GN1XXE4RF9J0APAAKD1WEG=levels-of-data-granularity 01H8GN1XXEHPFKX7V0RRW2MH2G=example-2 h_01HN0JW166VHR33T8VVVY47F9P=frequently-asked-questions 01H8GN1XXEND9X8YVRQE1YFA5W=should-i-use-lower-or-upper-case-letters-for-parameters 01H8GN1XXER749PH4Z14A7AJ0F=is-the-appsflyer-attribution-link-dynamic-or-static 01H8GN1XXEPQTY0XNW6EZSA9ZN=what-is-this-play-store-error-message 01H8GN1XXFYAFYFX9MNBP6D35B=what-are-subscriber-parameters-good-for 01H8GN1XXFEFA498J22GRF5F8G=example-3 01H8GN1XXFS1DFS3HAHVTVG93A=what-limits-are-there-on-campaign-names h_01HN0JW166WH76A5SM293PGKX6=traits-and-limitations" />
