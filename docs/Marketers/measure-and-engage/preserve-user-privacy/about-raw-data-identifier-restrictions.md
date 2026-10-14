---
title: "About raw data identifier restrictions"
excerpt: "Some partners require AppsFlyer to restrict certain fields in specific raw data reports. In other cases, partners may request redaction of the media source when sharing postbacks with third-party platforms. This article outlines these restrictions and their implications."
x-zendesk:
  id: 360006868017
  url: https://support.appsflyer.com/hc/en-us/articles/360006868017-About-raw-data-identifier-restrictions
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Preserve user privacy
  section_id: 6551440878097
  position: 6
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-rona-einat, Marketers, Agencies, Raw Reports]
  labels: [Advertisers, Agencies, Marketers, Loc In Prog]
  promoted: false
  comments_disabled: true
  created_at: '2020-03-23T08:29:01Z'
  edited_at: '2026-10-07T08:17:07Z'
---
## Raw data restriction

AppsFlyer restricts access to certain raw data report fields based on the advertiser's [AAP (Aggregated Advanced Privacy)](/docs/apply-aggregated-advanced-privacy-framework) settings or the data-sharing policies of the ad networks providing the data. These restrictions vary depending on the type of report and the reason for the restriction.

### Media source restrictions

The following table lists restrictions per media source for conversions, clicks, and impressions.

> 📘 **Note**
>
> Aggregated attribution and analytics data are available without limitations. However, all postbacks and device-level reports are subject to the limitations outlined below.
>
> [Postback restrictions on third-party platforms](/docs/discrepancies-between-appsflyer-and-third-party-platforms#postback-restrictions-on-third-party-platforms):
>
> * The restrictions described in the table below apply to the events included in postbacks sent to third-party platforms, such as analytics and marketing platforms.
> * Further postback restrictions may apply for other events.

| Media source | Attribution type restriction |
| --- | --- |
| Amazon Ads | Raw data from Amazon Ads is restricted on the AppsFlyer platform. As a result, the media source is reported as "restricted" and campaign details are null.<br /><br />As with any SRN (Self-Reporting Network), clicks and impressions from Amazon aren't included in raw data reports. |
| Discord | Raw data from Discord is restricted on the AppsFlyer platform.<br /><br />The following restrictions apply to view-through and click-through attribution:<ul><li>original\_url: restricted</li><li>click\_id: restricted</li></ul>Clicks and impressions from Discord aren't included in raw data reports. |
| <span id="meta-ads"></span>Meta Ads | The following restrictions apply to Meta Ads raw data:<ul><li>By default, Meta Ads does not allow the distribution of device-level data with unrestricted attribution information. However, if you accept the Meta Advanced Mobile Measurement (AMM) Terms, you can access device-level attribution data for Meta Ads without restriction. See [Enable Meta ads device-level data](/docs/meta-ads-integration-setup#enable-meta-ads-device-level-data).</li><li>Data from the AEM deep link solution (iOS), as well as data from the Google Play Install Referrer and the Meta Install Referrer (Android), is available in device-level reports.</li><li>Data from the Google Play Install Referrer and the Meta Install Referrer can only appear in install reports.</li><li>Data from the AEM deep link solution (iOS) can only appear in re-engagement reports.</li></ul>Clicks and impressions from Meta Ads aren't included in raw data reports. |
| Pinterest | Click-through and view-through attribution data is restricted.<br /><br />Clicks and impressions from Pinterest aren't included in raw data reports. |
| Reddit | Clicks and impressions from Reddit aren't included in raw data reports.<br /><br />**Reminder:** Data received about a Reddit campaign is subject to [Reddit Business Tool Terms](https://business.reddithelp.com/s/article/Reddit-Business-Tool-Terms), and includes, among other restrictions, a prohibition on using Reddit data to create profiles of any users. |
| Samsung DSP | Starting October 17, 2023:<br /><br />Samsung view-through and click-through attribution is limited. The following are included in raw data delivery tools:<br /><br />* Media source (samsungdsp\_int)<br />* Attributed touch type (impression/click)<br />* Attributed touch time is available<br />* Campaign details are available<br /><br />Clicks and impressions from Samsung aren't included in raw data reports.<br /><br />Starting August 30, 2025:<br /><br />Samsung EMEA view-through and click-through attribution is limited, for engagements received with `af_data_restriction=attribution` on the URL. The following are included in raw data delivery tools:<br /><br />* Media source: reported as restricted<br />* Attributed touch type (impression/click)<br />* Attributed touch time is available<br />* Campaign details are available<br /><br />Clicks and impressions from Samsung aren't included in raw data reports. |
| Snapchat | The following restrictions apply to Snapchat raw data:<ul><li>Starting March 1, 2023, Snapchat uninstalls aren't included in the raw data reports.</li><li>View-through attribution device-level data is limited in some cases. The logic of the raw data restrictions is managed on the Snapchat side, per event, and is communicated to AppsFlyer via the integration.</li><li>When the event has raw data restrictions, the following are **not** restricted in raw data delivery tools:</li></ul><ul><li>Media source (snapchat\_int)</li><li>Channel</li><li>Attributed touch type (impression)</li><li>Attributed touch time (reported as date only, "dd/mm/yyyy")</li><li>Campaign name and ID (starting December 15, 2025)</li><li>Ad set name and ID (starting December 15, 2025)</li></ul><ul><li>The above restrictions do not apply to engaged views.</li></ul>Clicks and impressions from Snapchat aren't included in raw data reports. |
| TikTok for Business | Until May 19, 2026, the following restrictions applied to view-through attribution:<br /><br />* Media source was reported as `tiktokglobal_int`<br />* Channel was reported as TikTok / Pangle<br />* Attributed touch type was reported as impression<br />* Attributed touch time was reported as date only ("dd/mm/yyyy")<br />* Campaign, ad set, and ad information were reported as "restricted"<br /><br />As of May 19, 2026, the following raw data tools were updated: Pull API, Data Locker, and the Raw Data Export page.<br /><br />As of June 25, 2026, the following raw data tools were updated: Push API and the Get conversion data (GCD) API.<br /><br />The changes are:<br /><br />* Only the `original_url` field is restricted (empty)<br />* All other attribution fields are fully supported<br /><br />The above restrictions don't apply to engaged views.<br /><br />Clicks and impressions raw data reports via Data Locker from `tiktokglobal_int` are restricted. |
| Uber | The following restrictions apply to view-through and click-through attribution:<ul><li>Media source (uber\_int): available</li><li>Campaign details: available</li></ul>Clicks and impressions from Uber aren't included in raw data reports. |
| <span id="x-ads-formerly-twitter"></span>X Ads (formerly Twitter) | In some cases, based on user choices in X Ads, raw data may be restricted on the AppsFlyer platform.<br /><br />**Until July 15, 2025:** Attributed events from X Ads didn't appear at all in raw data reports.<br /><br />**As of July 15, 2025:** Attributed events are included in raw data reports, with the following restrictions:<br /><br />* Media source (twitter): available<br />* Campaign details: reported as *restricted*<br />* Channel (Twitter): available<br />* Attributed touch type: available<br />* Attributed touch time: reported as date only (`dd/mm/yyyy`)<br /><br />Clicks and impressions from X Ads aren't included in raw data reports.<br /><br />Access to unrestricted raw data depends on participation in X Ads' **Advanced Mobile Measurement (AMM) program** and on end-user privacy settings:<br /><br />* AMM not enabled: all clicks and impressions are sent with `af_data_restriction=attribution`. All resulting events are restricted.<br />* AMM enabled:<br />  * EU users: events are restricted if data sharing with business partners is not granted.<br />  * Users who did not agree to share data: events are restricted (`af_data_restriction=attribution`).<br />  * Users who agreed to share data with business partners: events are not restricted (`af_data_restriction=none`).<br /><br />For more information, see the [X Ads setup guide, user privacy section](/docs/x-ads-formerly-twitter-ads-setup-guide-overview#x-ads-user-privacy). |

### Raw data context

Field-level restriction of raw data depends on the context of the data, as listed in the table that follows.

| Restriction type | Reports impacted |
| --- | --- |
| [Restricted media source](/docs/about-raw-data-identifier-restrictions#media-source-restrictions): Where the user came from | <ul><li>Attribution: Installs, retargeting conversions, and uninstalls</li><li>In-app events, sessions</li><li>Protect360 reports</li></ul> |
| Fully restricted | <ul><li>Clicks</li><li>Impressions</li><li>Blocked clicks (Protect360)</li></ul> |

### Delivery of raw data

User-level attribution data in AppsFlyer is available using the following raw data delivery tools:

* Data Locker
* Raw data Pull API
* Push API
* Dashboard export page
* Postbacks to networks
* [Get conversion data (GCD) API](https://dev.appsflyer.com/hc/docs/conversion-data) in the context of the client-side user-level data API

<div id="unavailable-attribution-fields" />

<Accordion title="Unavailable attribution fields">

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

</Accordion>

<div id="identifier-restriction" />

<Accordion title="Identifier restriction">

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

</Accordion>

## FAQ

<Accordion title="What events are restricted?">

Restricted events, as detailed in the [table above](/docs/about-raw-data-identifier-restrictions#media-source-restrictions), may include conversions (installs, re-engagements, and re-attributions) and associated in-app events to which the restricting ad network is attributed.

</Accordion>

<Accordion title="How does the restricted media source impact raw data reports?">

* The *media source* field is populated with *restricted*.
* The attribution fields listed in this article are either empty or populated with *null*.

**Report example:** Installs [restricted raw data](https://docs.google.com/spreadsheets/d/e/2PACX-1vScXJznEex0WwdCy78Bm8LtrhbCk1jNy14O_t7etrq5ab5v4CIEiInfFD4B1EsZCE-_w-dVRAxl_cu4/pub?output=csv) in a CSV file. Other raw data reports are populated in a similar manner.

</Accordion>

<Accordion title="How does the restricted media source impact postbacks sent to partners?">

Postbacks sent to partners don't include attribution fields.

</Accordion>

<Accordion title="How do restricted events impact postbacks to third-party platforms?">

Postbacks for attributed ad networks listed in the [table above](#media-source-restrictions) aren't sent to third-party platforms.

</Accordion>

<Accordion title="Do non-restricted events impact postbacks to third-party platforms?">

For events sent to third-party platforms such as analytics and marketing platforms, see the [postback restrictions on third-party platforms](/docs/discrepancies-between-appsflyer-and-third-party-platforms#postback-restrictions-on-third-party-platforms). In some cases, postbacks for non-restricted events don't include the media source. This means attribution is credited as organic.

</Accordion>

<Accordion title="What about the data of assists that form part of the attribution?">

Data related to assists is regarded as attribution data and isn't available.

</Accordion>

> 📘 **See also**
>
> [User-level data retention](/docs/user-level-data-retention)