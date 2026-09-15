---
title: "About raw data identifier restrictions"
excerpt: "Some partners require AppsFlyer to restrict certain fields in specific raw data reports, or request redaction of the media source when sharing postbacks with third-party platforms."
---
At a glance: Some partners require AppsFlyer to restrict certain fields in specific raw data reports. In other cases, partners may request redaction of the media source when sharing postbacks with third-party platforms. This article outlines these restrictions and their implications.

## Raw data restriction

AppsFlyer restricts access to certain raw data report fields based on the advertiser's [AAP (Aggregated Advanced Privacy)](https://support.appsflyer.com/hc/articles/360018515798) settings or the data-sharing policies of the ad networks providing the data. These restrictions vary depending on the type of report and the reason for the restriction.

### Media source restrictions

The following table lists restrictions per media source for conversions, clicks, and impressions.

> 📘 Note
>
> Aggregated attribution and analytics data are available without limitations. However, all postbacks and device-level reports are subject to the limitations outlined below.

[Postback restrictions on third-party platforms](https://support.appsflyer.com/hc/articles/19384888063249#postback-restrictions):

- The restrictions described in the table below apply to the events included in postbacks sent to third-party platforms, such as analytics and marketing platforms.
- Further postback restrictions may apply for other events.

| Media source | Attribution type restriction |
| --- | --- |
| Amazon Ads | Raw data from Amazon Ads is restricted on the AppsFlyer platform. As a result, the media source is reported as "restricted" and campaign details are null.<br>As with any SRN (Self-Reporting Network), clicks and impressions from Amazon aren't included in raw data reports. |
| Discord | Raw data from Discord is restricted on the AppsFlyer platform. <br>The following restrictions apply to view-through and click-through attribution:<br>- original\_url: restricted<br>- click\_id: restricted<br>Clicks and impressions from Discord aren't included in raw data reports. |
| Meta Ads | The following restrictions apply to Meta Ads raw data:<br>- By default, Meta Ads does not allow the distribution of device-level data with unrestricted attribution information. However, if you accept the Meta Advanced Mobile Measurement (AMM) Terms, you can access device-level attribution data for Meta Ads without restriction. See [Enable Meta ads device-level data](https://support.appsflyer.com/hc/articles/207033826-Meta-ads-integration-setup#enable-meta-ads-device-level-data).<br>- Data from the AEM deep link solution (iOS), as well as data from the Google Play Install Referrer and the Meta Install Referrer (Android), is available in device-level reports.<br>- Data from the Google Play Install Referrer and the Meta Install Referrer can only appear in install reports.<br>- Data from the AEM deep link solution (iOS) can only appear in re-engagement reports.<br>Clicks and impressions from Meta Ads aren't included in raw data reports. |
| Pinterest | Click-through and view-through attribution data is restricted.<br>Clicks and impressions from Pinterest aren't included in raw data reports. |
| Reddit | Clicks and impressions from Reddit aren't included in raw data reports.<br>**Reminder:** Data received about a Reddit campaign is subject to [Reddit Business Tool Terms](https://business.reddithelp.com/s/article/Reddit-Business-Tool-Terms), and includes, among other restrictions, a prohibition on using Reddit data to create profiles of any users. |
| Samsung DSP | Starting October 17, 2023:<br>Samsung view-through and click-through attribution is limited. The following are included in raw data delivery tools:<br>- Media source (samsungdsp\_int)<br>- Attributed touch type (impression/click)<br>- Attributed touch time is available<br>- Campaign details are available<br>Clicks and impressions from Samsung aren't included in raw data reports.<br>Starting August 30, 2025:<br>Samsung EMEA view-through and click-through attribution is limited, for engagements received with `af_data_restriction=attribution` on the URL. The following are included in raw data delivery tools:<br>- Media source: reported as restricted<br>- Attributed touch type (impression/click)<br>- Attributed touch time is available<br>- Campaign details are available<br>Clicks and impressions from Samsung aren't included in raw data reports. |
| Snapchat | The following restrictions apply to Snapchat raw data:<br>- Starting March 1, 2023, Snapchat uninstalls aren't included in the raw data reports.<br>- View-through attribution device-level data is limited. The following are **not** restricted in raw data delivery tools:<br>  - Media source (snapchat\_int)<br>  - Channel<br>  - Attributed touch type (impression)<br>  - Attributed touch time (reported as date only, "dd/mm/yyyy")<br>  - Campaign name and ID (starting December 15, 2025)<br>  - Ad set name and ID (starting December 15, 2025)<br>- The above restrictions do not apply to engaged views.<br>Clicks and impressions from Snapchat aren't included in raw data reports. |
| TikTok for Business | Until May 19, 2026, the following restrictions applied to view-through attribution:<br>- Media source was reported as `tiktokglobal_int`<br>- Channel was reported as TikTok / Pangle<br>- Attributed touch type was reported as impression<br>- Attributed touch time was reported as date only ("dd/mm/yyyy")<br>- Campaign, ad set, and ad information were reported as "restricted"<br>As of May 19, 2026, the following raw data tools were updated: Pull API, Data Locker, and the Raw Data Export page.<br>As of June 25, 2026, the following raw data tools were updated: Push API and the Get conversion data (GCD) API.<br>The changes are:<br>- Only the `original_url` field is restricted (empty)<br>- All other attribution fields are fully supported<br>The above restrictions don't apply to engaged views.<br>Clicks and impressions raw data reports via Data Locker from `tiktokglobal_int` are restricted. |
| Uber | The following restrictions apply to view-through and click-through attribution:<br>- Media source (uber\_int): available<br>- Campaign details: available<br>Clicks and impressions from Uber aren't included in raw data reports. |
| X Ads (formerly Twitter) | In some cases, based on user choices in X Ads, raw data may be restricted on the AppsFlyer platform.<br>**Until July 15, 2025:** Attributed events from X Ads didn't appear at all in raw data reports.<br>**As of July 15, 2025:** Attributed events are included in raw data reports, with the following restrictions:<br>- Media source (twitter): available<br>- Campaign details: reported as _restricted_<br>- Channel (Twitter): available<br>- Attributed touch type: available<br>- Attributed touch time: reported as date only (`dd/mm/yyyy`)<br>Clicks and impressions from X Ads aren't included in raw data reports.<br>Access to unrestricted raw data depends on participation in X Ads' **Advanced Mobile Measurement (AMM) program** and on end-user privacy settings:<br>- AMM not enabled: all clicks and impressions are sent with `af_data_restriction=attribution`. All resulting events are restricted.<br>- AMM enabled:<br>  - EU users: events are restricted if data sharing with business partners is not granted.<br>  - Users who did not agree to share data: events are restricted (`af_data_restriction=attribution`).<br>  - Users who agreed to share data with business partners: events are not restricted (`af_data_restriction=none`).<br>For more information, see the [X Ads setup guide, user privacy section](/docs/x-ads-formerly-twitter-ads-setup-guide-overview#twitter-user-privacy). |

### Raw data context

Field-level restriction of raw data depends on the context of the data, as listed in the table that follows.

| Restriction type | Reports impacted |
| --- | --- |
| [Restricted media source](https://support.appsflyer.com/hc/articles/360006868017#media-source-restrictions): Where the user came from | - Attribution: Installs, retargeting conversions, and uninstalls<br>- In-app events, sessions<br>- Protect360 reports |
| Fully restricted | - Clicks<br>- Impressions<br>- Blocked clicks (Protect360) |

### Delivery of raw data

User-level attribution data in AppsFlyer is available using the following raw data delivery tools:

- Data Locker
- Raw data Pull API
- Push API
- Dashboard export page
- Postbacks to networks
- [Get conversion data (GCD) API](https://dev.appsflyer.com/hc/docs/conversion-data) in the context of the client-side user-level data API

### Unavailable attribution fields

The following fields are unavailable when the media source is restricted:

| Display name | API name |
| --- | --- |
| Ad | af\_ad |
| Ad ID | af\_ad\_id |
| Ad type | af\_ad\_type |
| Adset | af\_adset |
| Adset ID | af\_adset\_id |
| Attribution lookback window | af\_attribution\_lookback |
| Campaign ID | af\_c\_id |
| Channel | af\_channel |
| Cost currency | af\_cost\_currency |
| Cost model | af\_cost\_model |
| Cost value | af\_cost\_value |
| Keywords | af\_keywords |
| Partner | af\_prt |
| Site ID | af\_siteid |
| Sub site ID | af\_sub\_siteid |
| Sub param [n] (n=1-5) | af\_sub[n] (n=1-5) |
| Attributed touch time | attributed\_touch\_time |
| Attributed touch type | attributed\_touch\_type |
| Campaign | campaign |
| Deeplink URL | deeplink\_url |
| HTTP referrer | http\_referrer |
| Install app store | install\_app\_store |
| Keyword ID | keyword\_id |
| Keyword match type | keyword\_match\_type |
| Match type | match\_type |
| Network account ID | network\_account\_id |
| Original URL | original\_url |
| Re-engagement window | af\_reengagement\_window |
| Store product page | store\_product\_page |

### Identifier restriction

When identifier restriction applies, the fields listed in the table that follows are the only fields available in the raw data reports.

| API name |
| --- |
| event\_time |
| event\_name |
| event\_revenue |
| event\_revenue\_currency |
| event\_revenue\_usd |
| af\_cost\_model |
| af\_cost\_value |
| af\_cost\_currency |
| event\_source |
| media\_source |
| af\_channel |
| campaign |
| af\_c\_id |
| af\_adset |
| af\_adset\_id |
| af\_ad |
| af\_ad\_id |
| af\_ad\_type |
| af\_siteid |
| af\_sub\_siteid |
| app\_id |
| app\_name |
| bundle\_id |
| is\_retargeting |
| retargeting\_conversion\_type |
| is\_primary\_attribution |
| af\_attribution\_lookback |
| af\_reengagement\_window |
| country\_code |
| blocked\_reason |
| blocked\_reason\_value |
| blocked\_reason\_rule |
| blocked\_sub\_reason |
| platform |
| is\_paid\_media |

## FAQ

<Accordion title="What events are restricted?">

Restricted events, as detailed in the [table above](https://support.appsflyer.com/hc/articles/360006868017-Raw-data-content-restriction-media-source-or-user-identifiers#media-source-restrictions), may include conversions (installs, re-engagements, and re-attributions) and associated in-app events to which the restricting ad network is attributed.

</Accordion>

<Accordion title="How does the restricted media source impact raw data reports?">

- The _media source_ field is populated with _restricted_.
- The attribution fields listed in this article are either empty or populated with _null_.

**Report example:** Installs [restricted raw data](https://docs.google.com/spreadsheets/d/e/2PACX-1vScXJznEex0WwdCy78Bm8LtrhbCk1jNy14O_t7etrq5ab5v4CIEiInfFD4B1EsZCE-_w-dVRAxl_cu4/pub?output=csv) in a CSV file. Other raw data reports are populated in a similar manner.

</Accordion>

<Accordion title="How does the restricted media source impact postbacks sent to partners?">

Postbacks sent to partners don't include attribution fields.

</Accordion>

<Accordion title="How do restricted events impact postbacks to third-party platforms?">

Postbacks for attributed ad networks listed in the [table above](/docs/about-raw-data-identifier-restrictions#media-source-restrictions) aren't sent to third-party platforms.

</Accordion>

<Accordion title="Do non-restricted events impact postbacks to third-party platforms?">

For events sent to third-party platforms such as analytics and marketing platforms, see the [postback restrictions on third-party platforms](https://support.appsflyer.com/hc/articles/19384888063249#postback-restrictions). In some cases, postbacks for non-restricted events don't include the media source. This means attribution is credited as organic.

</Accordion>

<Accordion title="What about the data of assists that form part of the attribution?">

Data related to assists is regarded as attribution data and isn't available.

</Accordion>

### See also

<Cards>
  <Card title="User-level data retention" href="/docs/user-level-data-retention">
    Learn more about user-level data retention policies and timelines.
  </Card>
</Cards>