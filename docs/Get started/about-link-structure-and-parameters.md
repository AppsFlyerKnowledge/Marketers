---
title: "About link structure and parameters"
excerpt: "Learn about the AppsFlyer attribution link structure, parameters, and levels of data granularity."
---
**At a glance:** Learn about the AppsFlyer attribution link structure and parameters.

## Overview

Attribution links allow advertisers to collect data about user engagement with an ad. Attribution links are placed behind ads and notify AppsFlyer when users engage with an ad. The engagement can occur via a click on an ad or when a user views an ad impression. A copy of the attribution URL is sent to AppsFlyer.

Attribution links are generated using **OneLink** or a **single-platform link**.

|  | OneLink (multi-platform link) | Single-platform link |
| --- | --- | --- |
| Description and when to use | Use when:<br>- You want a single link for all platforms.<br>- Deep linking capabilities are required.<br>- You want to use Android App Links or iOS Universal Links to open the app.<br>[Learn more about OneLink](https://support.appsflyer.com/hc/articles/115005248543-OneLink-overview) | Use when:<br>- You only use a single platform. For example, Android and not iOS.<br>- You only use URI schemes to open the app.<br>[Learn more on how to set up an integrated partner](https://support.appsflyer.com/hc/articles/4410395957521#attribution-link-tab) |
| Prerequisites | [OneLink template](https://support.appsflyer.com/hc/articles/207032246-OneLink-templates) | None |
| Information to include | - [Media source](https://support.appsflyer.com/hc/articles/207447163-Attribution-link-structure-and-parameters#partner-id-pid-parameter)<br>- [Campaign](/docs/about-link-structure-and-parameters#c)<br>- [Site ID / Sub Site ID](https://support.appsflyer.com/hc/articles/207447163-Attribution-link-structure-and-parameters#site-id-parameter) | - [Media source](https://support.appsflyer.com/hc/articles/207447163-Attribution-link-structure-and-parameters#partner-id-pid-parameter)<br>- [Campaign](/docs/about-link-structure-and-parameters#c)<br>- [Site ID / Sub Site ID](https://support.appsflyer.com/hc/articles/207447163-Attribution-link-structure-and-parameters#site-id-parameter) |
| Base URL | {subdomain}.onelink.me | app.appsflyer.com |
| Unique identifier | Template ID | app\_id |
| URL structure | `https://{subdomain}.onelink.me/`<br>`{templateid}?pid={media_source}`<br>`&af_siteid={ApplicationID}`<br>`&c={CampaignName}` | `https://app.appsflyer.com/{app_id}?pid={media_source}&af_siteid={ApplicationID}&c={CampaignName}` |
| Example | `https://yourbrand.onelink.me/aAB1?pid=greatnetwork_int`<br>`&c=GreatCampaign&af_siteid=A1b1` | `https://app.appsflyer.com/com.greatapp?pid=greatnetwork_int&`<br>`c=GreatCampaign&af_siteid=A1b1` |

> ❗️ Important!
>
> AppsFlyer supports only the HTTPS protocol for incoming engagement traffic, i.e. clicks and impressions.

## Attribution link parameters

- The parameters listed are available for use in the attribution link.
- The value **field type** column is the character limit of the parameter value. Find more about limitations on the length of parameter values [here.](https://support.appsflyer.com/hc/articles/208387843)

### Attribution link parameters—UA and retargeting

The following table can be [downloaded as a `.csv` file](https://docs.google.com/spreadsheets/d/e/2PACX-1vTZQnoDdFo2NxBuWXBs5gGgvkGU2pr_hn58H9Dtf5uHBAHv4Io89Wd44rRtL24pRsOXHthnBitaOyfp/pub?gid=0&single=true&output=csv).

| Parameter | Display name in raw data | Description | Field type and length |
| --- | --- | --- | --- |
| pid | Media Source | Uniquely identifies an AppsFlyer integrated partner. Don't change it. [More details](https://support.appsflyer.com/hc/articles/207447163#partner-id-pid-parameter). | String 150 |
| c | Campaign | Provided by the advertiser or the publisher. See [limits on campaign names](https://support.appsflyer.com/hc/articles/207447163#what-limits-are-there-on-campaign-names). | String |
| af\_prt | Partner | - Agency Account Name enables attributing installs to the agency<br>- **Caution**: Don't use this parameter before ensuring that **Agency Permissions** are enabled | String 50 |
| af\_mp | N/A | - Enable sending postbacks to publisher marketing partners per install.<br>- **Note**: Currently, this parameter is relevant only for Pinterest Marketing Partners. |  |
| clickid | N/A | Ad network unique click identifier |  |
| af\_siteid | Site ID | - Unique ID that identifies the publisher that displays the ad. [Learn more](https://support.appsflyer.com/hc/articles/207447163-Attribution-link-structure-and-parameters#site-id-parameter) | String 24 |
| af\_sub\_siteid | Sub Site ID | - Ad sub-network/Publisher ID.<br>- If in addition to the main publisher (site ID), there is a sub-publisher, or you want to include additional info, such as ad type/placement within the app, like banner, interstitial, video, etc. use af\_sub\_siteid. For example: af\_sub\_siteid =ABCD\_4567 | String |
| af\_c\_id | Campaign ID | Provided by the advertiser/publisher | String 24 |
| af\_adset | Adset | - Provided by the advertiser/publisher.<br>- Adset is an intermediate level in the hierarchy between Campaign and Ad. [See more](https://support.appsflyer.com/hc/articles/207447163#levels-of-data-granularity) | String 100 |
| af\_adset\_id | Adset ID | Provided by the advertiser/publisher | String 24 |
| af\_ad | Ad | Ad Name ( [see more](https://support.appsflyer.com/hc/articles/207447163#levels-of-data-granularity)) provided by the advertiser/publisher | String 100 |
| af\_ad\_id | Ad ID | Provided by the advertiser/publisher | String 24 |
| af\_ad\_type | Ad type | Use the following naming conventions:<br>- **native**: Paid media designed to match the content of a media source. This media is designed to match the visual design and function of natural content, appearing in your feed of recommended videos.<br>- **banner**: Display ads that are typically small rectangular advertisements that appear at various locations of a web page or app interface.<br>- **interstitial**: Full-screen ads that cover the entire interface of the host app. These ads are designed to be placed between content and are typically displayed at transition points within the app flow, such as between activities or game levels, or while on pause.<br>- **rewarded\_video**: Ads that users can choose to view to completion in exchange for an in-app reward — such as watching a video for extra life in the game, access to an article, or entry to Wi-Fi at an airport. These “rewarded” ads engage users and offer a better overall app experience.<br>- **audio**: Ads in audio format delivered within online podcasts or music streaming platforms.<br>- **offerwall**: An in-app advertising unit that developers use to monetize their apps. It acts like a mini-store within the app, listing multiple “offers” that users can complete in exchange for an in-app reward. | String 24 |
| af\_ad\_format | Ad format | Use the following naming conventions:<br>- **text**: A text-based ad that usually appears as a brief snippet of text. It may include a headline, description, and a link or call-to-action designed to create interest and encourage a click-through to a website or landing page.<br>- **image**: A visual advertisement that showcases a product, service, or brand using graphics or photographs. It typically includes a captivating image along with concise text and may also incorporate a call to action.<br>- **video**: A digital ad that uses audiovisual content to convey a marketing message. It can vary in length and may appear as pre-roll, mid-roll, or post-roll within online video content or as standalone videos on various platforms.<br>- **playable**: An interactive ad allowing users to engage with a miniature version of a game or app before downloading or making a purchase. It grants users a hands-on taste of actual gameplay or app functionality.<br>- **interactive**: An engaging and dynamic advertisement encouraging users to interact or participate. It may involve quizzes, polls, or other interactive elements to capture users' attention and encourage active participation.<br>- **dynamic\_product**: A personalized ad format that dynamically populates product information and details based on user behavior, preferences, or browsing history. It lets advertisers display highly relevant and tailored product ads to individuals.<br>- **carousel**: An ad format consisting of multiple slides or cards within a single advertisement. Each card can include a different image, headline, and description, allowing advertisers to showcase multiple products or features in a single ad. |  |
| af\_click\_lookback | Attribution lookback window | - Lookback Window for Click Attribution. This window's duration is the maximum CTIT (Click Time to Install) for the new user to be attributed to the source displaying the ad/link.<br>- Configurable number of days for the lookback click attribution period. Available parameter values: 1d - 30d (days) OR 1h-23h (hours). The default value is 7d.<br>- The lookback window can be customized for [OneLinks and SRNs](https://support.appsflyer.com/hc/articles/208338403-Lookback-windows-explained#lookback-window-setup).<br>**Note**: Only affects click URLs and not impression URLs. | 3 char max |
| af\_viewthrough\_lookback | N/A | - Configurable number of hours for the lookback view-through attribution period. Available parameter values: 1h - 24h (hours). The default is 24h.<br>- The lookback window can be customized for [SRNs](https://support.appsflyer.com/hc/articles/208338403-Lookback-windows-explained#lookback-window-setup).<br>**Note**: Only affects impression URLs and not click URLs | 3 char max |
| af\_channel | Channel | The media source channel through which the ads are distributed, for example, UAC\_Search, UAC\_Display, Instagram, Meta Audience Network, etc. | Dynamic Enum. String 20 |
| af\_engagement\_destination | Engagement destination | Indicates the category of the destination linked from the ad, such as a **web** landing page, a **mobile** app (via a deep link or an app store), or other destination types such as **CTV**, **PC**, or **Console**. | String 50 |
| af\_keywords | Keywords | Keywords list for text-targeted campaigns | String 100 |
| af\_cost\_model | Cost model | - Cost model, CPI (default) is currently the only supported model when reporting cost by click, which populates [cost value in AppsFlyer aggregated data](https://support.appsflyer.com/hc/articles/207040526#cost-data-availability-and-reports) reports.<br>- Where possible, report cost by [API.](https://support.appsflyer.com/hc/articles/207040526-Ad-cost-measurement-guide#cost-aggregation-methods) In cases where cost is reported by on the link and by API - API has priority. | String 20 |
| af\_cost\_currency | Cost currency | - 3 letter currency code compliant with [ISO-4217.](https://support.appsflyer.com/hc/articles/207040526-Ad-cost-measurement-guide#cost-aggregation-methods) For example, USD, ZAR, EUR<br>- [Default]: USD | Enum. 3 char |
| af\_cost\_value | Cost value | - Cost value in using cost currency.<br>- Up to 4 digits after the decimal point.<br>- Set ONLY numerical digits (use a decimal point if needed) Example: "56", "2.85" | Numeric |
| af\_sub[n] <br>(n=1-5) example: af\_sub1 | Sub param [n] | Optional custom parameter defined by the advertiser. For more information about the usage of these parameters, check the [Traits and limitations](https://support.appsflyer.com/hc/articles/207447163#traits-and-limitations) section. | String 100 |
| af\_r | N/A | Used to redirect users to the specified URL in **all platforms** (Android, iOS, and desktop).<br>In multi-platform links (OneLink) this parameter:<br>- Overrides template-level redirection setup<br>- Is overridden by the following link-level parameters:<br>  - [`af_android_url`](https://support.appsflyer.com/hc/articles/207447163-Attribution-link-structure-and-parameters#af_android_url)<br>  - [`af_ios_url`](https://support.appsflyer.com/hc/articles/207447163-Attribution-link-structure-and-parameters#af_ios_url)<br>  - [`af_web_dp`](https://support.appsflyer.com/hc/articles/207447163-Attribution-link-structure-and-parameters#af_web_dp)<br>**Note:** See additional redirection parameter [traits and limitations](https://support.appsflyer.com/hc/articles/207447163-Attribution-link-structure-and-parameters#special-characters). |  |
| af\_web\_dp | N/A | URL to redirect desktop (for example, Windows or Mac) users to a different web page than configured in the OneLink template. Use this to keep attribution data of desktop users on other platforms (for example, Google Analytics or Omniture)<br>**Note:** See additional redirection parameter [traits and limitations](https://support.appsflyer.com/hc/articles/207447163-Attribution-link-structure-and-parameters#special-characters). |  |
| af\_dp | N/A | The URI scheme fallback value to launch the app, to be used if the Universal Link or Android App Link method fails, and for Android users below 6.0. It should only point to the [base path](https://support.appsflyer.com/hc/articles/208874366#deep-linking-and-deferred-deep-linking), i.e. the default activity.<br>**Note:** If you use a web URL value for this parameter (not recommended), be sure to review the redirection parameter [traits and limitations](https://support.appsflyer.com/hc/articles/207447163-Attribution-link-structure-and-parameters#special-characters). |  |
| af\_force\_deeplink | N/A | [Force deep linking](https://support.appsflyer.com/hc/articles/360014821438) into the activity specified in af\_dp value |  |
| af\_ref | N/A | Ad networks working with S2S clicks can send a unique referrer value using the following parameter: &af\_ref= **ReferrerValue**<br>The af\_ref value **must** consist of a unique value, structured as follows:<br>**NetworkName\_UniqueClickValueForEachClick**<br>Example: af\_ref=networkname\_123456789ABCDEF<br>The network name can be any valid string. It can be networkname\_int or just network name.<br>AppsFlyer may use this parameter for attribution in Android devices. AppsFlyer doesn't use this parameter for attribution in iOS or Windows devices. |  |
| is\_incentivized | N/A | Boolean: true/false<br>Incentivized or non-incentivized campaigns |  |
| af\_param\_forwarding | N/A | - When set to false, parameters that are on the attribution link are not forwarded to the redirected page.<br>- Use this for a cleaner looking URL in the redirected page, or if attribution link parameters might cause issues due to query parameter handling on the redirected page. |  |
| af\_base\_params\_forward | N/A | - When set to false, AppsFlyer PID and C parameters that are on the attribution link are not forwarded to the redirected page.<br>- Use this if the URL is going to be clicked from a desktop and you want essential CRM parameters to remain but the AppsFlyer PID and C parameters to be removed. This will avoid having multiple PIDs in the URL. |  |
| af\_partner\_account\_id | Network Account ID | Advertiser's account ID with the partner | String 100 |
| redirect | N/A | When`&redirect=false`, this parameter lets AppsFlyer know that this is an S2S click and that the partner is responsible for redirecting the user that clicked. |  |
| af\_ua | User-agent | Relevant for ad networks that send clicks and impressions [server-to-server (S2S)](https://support.appsflyer.com/hc/articles/360000807629).<br>**Important:** Don’t use `af_ua` in client-to-server (C2S) links. Using `af_ua` in a C2S link may affect attribution.<br>The user-agent string sent as:<br>1. URL parameter (URL-encoded)<br>2. HTTP request header (unencoded)<br>The User-Agent should be **identical in both the URL parameter and the HTTP header**.<br>**In Android**, the user-agent is sometimes reduced due to Client Hints. It should be sent regardless.<br>- **Example of full user-agent:**`Mozilla/5.0 (Linux; Android 12; Pixel 5) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/95.0.4638.16 Mobile Safari/537.36`<br>- **Example of reduced user-agent:**`Mozilla/5.0 (Linux; Android 10; K) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/95.0.0.0 Mobile Safari/537.36`<br>**In iOS**, starting iOS 26 the version is appended. <br>Here is:<br>- **An example of the appended part:**`Version/26.0.1 Mobile/15E148 Safari/604.1`<br>- **An example of the full user-agent:**<br> <br> `Mozilla/5.0 (iPhone; CPU iPhone OS 16_4_1 like Mac OS X) AppleWebKit/8615.1.26.10.24 (KHTML, like Gecko) Mobile/20E252 Version/26.0.1 Mobile/15E148 Safari/604.1` |  |
| af\_ip | IP | Relevant for ad networks that send clicks and impressions [server-to-server](https://support.appsflyer.com/hc/articles/360000807629).<br>**Important:** Don’t use `af_ip` in client-to-server (C2S) links. Using `af_ip` in a C2S link may affect attribution.<br>**Device IP address**<br>**Recommended**: If available, provide the device IP under the `af_ip` parameter.<br>**Next option**: If available, AppsFlyer will use the IP in X-Forwarded-For. |  |
| [Deprecated] af\_os | OS version | [For iOS only] The device operating system version.<br>This parameter is deprecated but still supported by AppsFlyer. Recommended: Use the af\_os\_version parameter instead. |  |
| af\_os\_version | OS version | - Relevant for ad networks that send clicks and impressions [server-to-server](https://support.appsflyer.com/hc/articles/360000807629).<br>- The device operating system version.<br>  - Android:<br>    - Example: 12<br>    - For reduced user-agent (due to browsers running on desktop or Android and using the Chrome 110+ engine), the ad network must use the [Client Hints API](https://web.dev/migrate-to-ua-ch/) to get this value.<br>    - For user-agent that **isn’t** reduced, use the following regex to extract the Android OS version from the user-agent string: `(\d+(?:\.\d+)*);(?:\s..-..;)?\s(.+?(?=\)|\s\w*\/))`.<br>  - iOS:<br>    - Include the full OS version for accurate attribution. For example: 18.6.2 |  |
| af\_model | Device model | - Relevant for ad networks that send clicks and impressions [server-to-server](https://support.appsflyer.com/hc/articles/360000807629).<br>- The device model.<br>  - Android:<br>    - Example: Pixel 5<br>    - For reduced user-agent (due to browsers running on desktop or Android and using the Chrome 110+ engine), the ad network must use the [Client Hints API](https://web.dev/migrate-to-ua-ch/) to get this value.<br>    - For user-agent that **isn’t** reduced, use the following regex to extract the Android model from the user-agent string: `(\d+(?:\.\d+)*);(?:\s..-..;)?\s(.+?(?=\)|\s\w*\/))`.<br>  - iOS:<br>    - Include the full device model identifier for accurate attribution. For example: `iphone15,1`or `ipad14,2`. |  |
| af\_media\_type | Media type | Placement of the ad carrying the link as follows:<br>- app: The link is available via an app<br>- web: The link is available within a mobile website |  |
| deep\_link\_sub1-10 | N/A | Additional deep link values. Developers implement the desired behavior of the values in the code. |  |
| deep\_link\_value | N/A | The name for the specific in-app content that users will be directed to. Developers implement the desired behavior of the deep\_link\_value in the code. |  |
| af\_og\_title | N/A | When a link is posted to social media, open graph (OG) title will generate a preview of the title. | String 40 |
| af\_og\_description | N/A | When a link is posted to social media, open graph (OG) description will generate a preview of the description. | String 300 |
| af\_og\_image | N/A | When a link is posted to social media, open graph (OG) image will generate a preview of the image. |  |

### Attribution link parameters—retargeting only

| Parameter | Display name in raw data | Description | Field type and width |
| --- | --- | --- | --- |
| is\_retargeting | Is Retargeting (campaign) | The click URL of all retargeting campaigns must include `&is_retargeting=true`.<br>If the parameter is not included or its value is "false," the campaign is considered as a regular user acquisition campaign. | Enum 5 char |
| af\_reengagement\_window | Re-engagement window | Change the [re-engagement attribution window](/docs/retargeting-attribution-guide#reengagement-rules-and-windows) by adding this parameter to the attribution link.<br>The possible window range options are:<br>- Days: 1-90 or Hours 1-36<br>- Lifetime: This means the re-engagement window is unlimited. Example:` &af_reengagement_window=lifetime`<br>Default value: 30 days<br>Example:` &af_reengagement_window=30d` sets the re-engagement window to 30 days. | N/A |

### Viewability parameters

Depending on the ad type, you can also send the relevant viewability parameter detailing the specifications of the engagement.

| Parameter | Value format | Description |
| --- | --- | --- |
| af\_video\_total\_length | seconds | The total possible duration of the video |
| af\_video\_played\_length | seconds | How much of the video was viewed |
| af\_playable\_played\_length | seconds | How long the playable element was played once fully loaded |
| af\_ad\_time\_viewed | seconds | How long the ad unit was visible on the screen |
| af\_ad\_displayed\_percent | % | The maximum percentage of the ad unit that was visible on the device screen |
| af\_audio\_total\_length | seconds | The total possible duration of the audio |
| af\_audio\_played\_length | seconds | How much of the audio was heard |

### Android-specific parameters

| Parameter | Display name in raw data | Description | Field type |
| --- | --- | --- | --- |
| advertising\_id | Advertising ID | Google Advertising ID - Requires ad network support | 40 char max |
| sha1\_advertising\_id | N/A | Google Advertising ID hashed with SHA1 - Requires ad network support |  |
| md5\_advertising\_id | N/A | Google Advertising ID hashed with MD5 - Requires ad network support | Supported with installs and re-attributions only |
| android\_id | Android ID | Device Android\_id - Requires ad network support | 20 char max |
| sha1\_android\_id | N/A | Device Android\_id hashed with SHA1 - Requires ad network support |  |
| md5\_android\_id | N/A | Device Android\_id hashed with MD5 - Requires ad network support | Supported with installs and re-attributions only |
| imei | IMEI | Device IMEI ID |  |
| sha1\_imei | N/A | Device IMEI ID hashed with SHA1 - Requires ad network support |  |
| md5\_imei | N/A | Device IMEI ID hashed with MD5 - Requires ad network support |  |
| oaid | OAID | Open Anonymous Device Identifier | Available as of Android SDK version 4.10.3 |
| sha1\_oaid | N/A | Open Anonymous Device Identifier hashed with SHA1 - Requires ad network support | Available as of Android SDK version 4.10.3 |
| md5\_oaid | N/A | Open Anonymous Device Identifier hashed with MD5 - Requires ad network support | Available as of Android SDK version 4.10.3 |
| af\_android\_url | N/A | Redirect Android users to a different URL than the app page on Google Play. Use for [third-party app stores](https://support.appsflyer.com/hc/articles/207447023#single-dashboard-vs-dashboard-per-store).<br>**Note:** See additional redirection parameter [traits and limitations](https://support.appsflyer.com/hc/articles/207447163-Attribution-link-structure-and-parameters#special-characters). |  |
| sha1\_el | N/A | Used for desktop to mobile attribution - email hashed with SHA1. Requires ad network support |  |
| fire\_advertising\_id | N/A | Amazon Fire Advertising ID |  |
| af\_android\_store\_csl | store\_product\_page | Custom store listing in Google Console | string |

### iOS-specific parameters

| Parameters | Display Name | Description |
| --- | --- | --- |
| idfa | IDFA | Use upper case. Requires ad network support<br>Field type: 40 char max |
| idfv | IDFV | Use upper case. |
| af\_ios\_url |  | Use this for landing page redirections to redirect iOS (iPhone or iPad) users to a different URL than the app page on iTunes<br>**Note:** See additional redirection parameter [traits and limitations](https://support.appsflyer.com/hc/articles/207447163-Attribution-link-structure-and-parameters#special-characters). |
| af\_ios\_store\_cpp | store\_product\_page | Custom product page ID (ppid)<br>**Note:** In raw data and aggregated reporting, the af\_ios\_store\_cpp (custom product page ID) parameter value is recorded for clicks but not for impressions. |
| af\_ios\_fallback [deprecated] | N/A | **Deprecated**: Users are redirected based on the [iOS URI scheme flow](https://support.appsflyer.com/hc/articles/115002366466). |
| sha1\_idfa | N/A | IDFA hashed with SHA1. Requires ad network support |
| sha1\_idfv | N/A | IDFV hashed with SHA1 |
| mac | N/A | Device mac address. Requires ad network support |
| md5\_idfa | N/A | IDFA hashed with MD5 |
| md5\_idfv | N/A | IDFV hashed with MD5 |
| sha1\_mac | N/A | Device mac address hashed with SHA1. Requires ad network support |

#### Example

```auto
Autohttps://app.appsflyer.com/{app_id}/?pid=airpush_int&c=RedBanner&
	  af_siteid={publisher_id}&af_sub1=1.5&af_sub2=USD&af_sub3=burst_campaign
```

All parameters are available in the [Install report](https://support.appsflyer.com/hc/articles/209680773) and the [Analytics, Reports, and APIs](https://support.appsflyer.com/hc/sections/6550976670225-Analytics-and-aggregate-reporting-APIs).

### Custom parameters

In addition to default Android-specific and iOS-specific parameters, you can also specify custom parameters. These custom parameters can help you if you wish to customize the user experience and content according to the attribution link that leads to an install.

You can append custom parameters to the attribution link in the format `parameter=value`. For example:

```auto
Autohttps://app.appsflyer.com/com.greatapp?pid=networkx_int&c=winter&af_adset=coats&af_ad=cashmere&my_custom_param=my_custom_value
```

Two important things to know about custom parameters:

- Custom parameters don't appear in raw data.
- Custom parameters can be retrieved from the [get conversion data SDK API](https://dev.appsflyer.com/hc/docs/conversion-data).

### Partner ID (PID) parameter

Among all available attribution link parameters, PID is mandatory. The PID is the unique identifier of the media source allocated by AppsFlyer.

Each [integrated partner](http://appsflyer.com/partners "AppsFlyer Active Integrations") has a unique PID value, which ends with the _\_int_ suffix. When using [OneLink links,](https://support.appsflyer.com/hc/articles/208874366) you can set the PID to any value you prefer, as long as it's not reserved by an integrated partner.

> 📘 Note
>
> AppsFlyer blocks attribution links that use reserved [SRN](/docs/self-reporting-networks-srns#srns-integrated-with-appsflyer) names as PID values in custom media sources, such as email and SMS. This restriction does **not** apply to ASRNs.

Examples of important integrated reserved publisher IDs: organic, googleadwords\_int (Google AdWords), facebook\_int (Meta ads), and twitter\_int (X Ads). You can use any name for non-integrated sources like email, SMS, or mail pigeons.

#### Avoid common PID issues:

- **Always include PID in your attribution links.** Without the PID on the attribution link, the user is automatically attributed to a "None" media source, and the original installation source is gone.
- **For each integrated source**, use only the designated PID for the correct attribution of its installs.
- **For Custom Sources, use non-integrated partner PIDs.** For any custom media source, such as email, SMS, or even viral unpaid posts on Facebook use other, non-integrated PID values. such as owned\_email, sms\_push, or other custom identifiers that do not match the names of integrated partners.
- **Use only legal characters.** If the PID parameter in the Attribution Link contains one of the following characters _**/<>\*&?\***_:
  - The click or install appears in the dashboard under _**af\_invalid\_param**_
  - Attribution links will not be attributed
  - Deep linking capabilities will not work on clicks

> 👍 Tip
>
> Avoid using white spaces in the PID value, or make sure to URL encode your attribution links before using them.

### Site ID parameter

The site ID is the unique identifier of the publisher serving the ad. In other words, the website or app displaying the ad. Ad networks allocate unique site IDs for each publisher.

This ID is included in the `af_siteid` parameter passed to AppsFlyer in the attribution link and is made available via the various dashboards, reporting options, and postbacks.

The site ID must be passed to AppsFlyer in the attribution link because it:

- Provides clarity and transparency about the publisher
- Is used by AppsFlyer to identify and eliminate fraudulent publishers, and other traffic clusters.

The site ID parameter only includes the ID of the publisher that serves the ad.

To include additional information, such as ad type, placement, or both within the app, for example, banner, interstitial, or video, use the sub-site ID parameter.

#### Example

The following attribution link includes:

- `af_siteid` (site ID): Publisher ID
- `af_sub_siteid` (sub-site ID): Additional ID info (in this case, an affiliate source and ad type placement)

`https://app.appsflyer.com/com.yourapp?pid=mediaName_int&clickid={clickid}&advertising_id={gaid}&af_siteid=1234&af_sub_siteid=ABCD_4567`

In the example link:

- 1234 = Publisher ID
- ABCD = Affiliate source (sub-publisher) that the publisher is working with
- 4567 = Ad type placement within the app, such as banner, interstitial, or video

#### **FAQ: Why does traffic result in many blocked installs?**

Blocked installs can be due to the following:

- **Missing site ID:** The `af_siteid` parameter is empty in the click URL. Engagements sent with an empty Site ID signify either a technical issue or an intentional attempt to bypass fraud detection mechanisms.
- **Multiple site IDs:** The same publisher is sent on multiple click URLs, using different site IDs. This is considered fraudulent behavior that masks the real publisher activity and is often associated with [click flooding](https://www.appsflyer.com/blog/click-flooding-detection-false-positive-challenge/).
- **Site ID formatted incorrectly:** Sending the wrong format, combined with other fraud indications, could result in blocking not only the specific publisher, but also of a higher cluster level, and might impact greater volumes of the partner activity.

To avoid blocked installs, make sure you send a single site ID parameter per publisher, as shown in the example.

## Levels of data granularity

You can use up to four URL parameters to deep dive into your ads' performance.

Using all 4 parameters on all your active attribution links enables you to:

- Attribute all user installs and events to specific ads
- Drill down and compare the performance of all your ads per ad set, per campaign, and per media source on aggregated reports to optimize on every level
- Compare all of your ads across all media sources on the raw data reports and [Pivot table](https://support.appsflyer.com/hc/articles/115001421846-AppsFlyer-Pivot-)

The parameters are:

- `Media source (pid=)`
- `campaign name (c=)`
- `Ad set (af_adset=)`
- `Ad name (af_ad=)`

#### Example

The following attribution link uses 4 levels of granularity to record the "cashmere" ad in the "coats" ad set in the "winter" campaign running on the integrated "network" media source.

```auto
Autohttps://app.appsflyer.com/com.greatapp?pid=networkx_int&c=winter&
af_adset=coats&af_ad=cashmere
```

## Frequently asked questions

<Accordion title="Should I use lower or upper case letters for parameters">

You can use either, but you must be consistent. If you set a custom parameter with upper or lower case characters, make sure always to use that parameter.

For example, if you set pid=MyMediaSource, make sure always to use it. If you use pid=MyMediaSource on one attribution link and pid=mymediasource on another, discrepancies in data might occur. The same goes for any other param that you set on the attribution link.

</Accordion>

<Accordion title="Is the AppsFlyer attribution link dynamic or static?">

Attribution links can be dynamic or static.

How can you tell if a link is dynamic or static?

If the **attribution link contains parameters**, it's a long pre-defined attribution link, and therefore **static**.

**Only short URLs**(for example, `yourbrand.onelink.me/HaT8/r5c2b371`), used for custom attribution links, **are dynamic**.

This means that once you start using an attribution link for an integrated partner, or a long URL for owned media, it would not change for any leads engaging with it, even if you change the attribution link values in the AppsFlyer dashboard. For the change to take place, you must use the new long URL going forward.

On the other hand, short URLs for owned media, don't directly contain parameters. When a lead engages with an AppsFlyer short URL, the lead is redirected to AppsFlyer and the current set parameters take place dynamically.

</Accordion>

<Accordion title="What is this Play Store error message?">

If you ever encounter the following error message in the Play Store after following an attribution Link:

![TL_error_message.png](https://files.readme.io/03e509d3cbe68aa0621bb0f43ab113c25a8427e70826c5af5258f1fc9e3f3d36-360000002485.png)

This is because the attribution link includes a # character. For example:

```auto
Autohttps://app.appsflyer.com/com.travelco?pid=globalwide_int&clickid=#reqid#
```

Usually, these characters are in the link because they are macros, and are dynamically replaced by a value, so it is not a really big problem and you can ignore the message.

</Accordion>

<Accordion title="What are subscriber parameters good for?">

The Subscriber Parameters, meaning af\_sub1, af\_sub2, ..., af\_sub\_5 can be used to record any useful KPIs. These parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.

#### Example

A hail ride app, Luber, has creatives with 3 color templates: blue, yellow, and red. Luber's mobile marketer, Linda, wants to test which color template brings in more installs. To do so she adds `&af_sub3=blue` in the attribution links of all the blue ads across ALL non-SRN media sources. The same is done for the yellow and red ads as well. With this information parsed and appearing in the raw data reports, Linda is able to analyze the success of the different colored ads and pick the best converting one.

</Accordion>

<Accordion title="What limits are there on campaign names?">

- The maximum length of a campaign name in the attribution link URL is limited to 100 characters. If exceeded, the campaign name is changed to: `c_name_exceeded_max_length`
- The campaign name shouldn't start from or end with a white space, as it may cause discrepancies in dashboards and reports

</Accordion>

## Traits and limitations

| Traits | Remarks |
| --- | --- |
| Special characters | The following special characters are not allowed in parameter keys and values (not applicable to redirect and af\_dp parameters): ;, \*, !, @, #, ?, $, ^, :, &, ~, \`, =, +, ’, >, <, /, {, }, %, ),( |
| Redirection parameters | - Make sure your redirection URL domains are added to your [redirect allowlist](/docs/set-up-your-domain-redirect-allowlist).<br>- The redirection value must be a full valid (and publically accessible) web URL (https://[domain][optional-path]) in accordance with [RFC 1738 standards](https://datatracker.ietf.org/doc/html/rfc1738);<br>- [URI Fragment identifiers](https://en.wikipedia.org/wiki/URI_fragment) **are not supported** in redirection URLs (e.g., #webpagesection which scrolls users down to a specific section in an article). |
| URL character limit | Total URL length must not exceed 2000 characters |
| Android social apps WebView deep linking redirection | See limitation details [here](https://support.appsflyer.com/hc/articles/208874366#android-social-apps-webview-deep-linking-redirection) |
| Deep linking is not supported in the Android Naver Blog app | Deep linking is not supported in the Android Naver Blog app. Users will be redirected to the Google Play Store or the web as defined by the link. |
| A pop-up appears when clicking on a URI scheme link from Chrome browser on iOS | Due to a change in Chrome iOS, whenever a user clicks a URI scheme link in Chrome on iOS, a pop-up is displayed, prompting the user to confirm opening the app or redirecting to the App Store. |
| URI Scheme validity requirements | We recommend using a valid URI scheme that complies with [RFC 3986](https://www.rfc-editor.org/rfc/rfc3986#section-3.1). Schemes that do not comply with the above may fail to open an app and produce an error when clicked from a web view or other web environments. |
| Telegram WebView attribution | See limitation details [here](https://support.appsflyer.com/hc/articles/208874366-Create-a-OneLink-link-for-your-campaigns#telegram-webview) |