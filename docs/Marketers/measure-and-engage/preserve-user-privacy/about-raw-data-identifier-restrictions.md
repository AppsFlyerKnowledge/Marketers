---
title: About raw data identifier restrictions
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Agencies
    - Raw Reports
  created_at: '2020-03-23T08:29:01Z'
  edited_at: '2026-11-02T08:39:16Z'
  id: 360006868017
  locale: en-us
  section: Preserve user privacy
  section_id: 6551440878097
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360006868017-About-raw-data-identifier-restrictions
---
> **At a glance:** Some partners require AppsFlyer to restrict certain fields in specific raw data reports. In other cases, partners may request redaction of the media source when sharing postbacks with third-party platforms. This article outlines these restrictions and their implications.

## Raw data restriction

AppsFlyer restricts access to certain raw data report fields based on the advertiser's <Anchor target="_blank" href="/marketers/docs/apply-aggregated-advanced-privacy-framework">AAP (Aggregated Advanced Privacy)</Anchor> settings or the data-sharing policies of the ad networks providing the data. These restrictions vary depending on the type of report and the reason for the restriction.

### Media source restrictions

The following table lists restrictions per media source for conversions, clicks, and impressions.

> 📘 **Note**
>
> Aggregated attribution and analytics data are available without limitations. However, all postbacks and device-level reports are subject to the limitations outlined below.
>
> <Anchor target="_blank" href="/marketers/docs/discrepancies-between-appsflyer-and-third-party-platforms#postback-restrictions-on-third-party-platforms">Postback restrictions on third-party platforms</Anchor>:
>
> * The restrictions described in the table below apply to the events included in postbacks sent to third-party platforms, such as analytics and marketing platforms.
> * Further postback restrictions may apply for other events.

| Media source | Attribution type restriction |
| --- | --- |
| <span id="amazon-ads"></span>Amazon Ads | Raw data from Amazon Ads is restricted on the AppsFlyer platform. As a result, the media source is reported as "restricted" and campaign details are null.<br /><br />As with any SRN (Self-Reporting Network), clicks and impressions from Amazon aren't included in raw data reports. |
| <span id="discord"></span>Discord | Raw data from Discord is restricted on the AppsFlyer platform.<br /><br />The following restrictions apply to view-through and click-through attribution:<ul><li>original\_url: restricted</li><li>click\_id: restricted</li></ul>Clicks and impressions from Discord aren't included in raw data reports. |
| <span id="meta-ads"></span>Meta Ads | The following restrictions apply to Meta Ads raw data:<ul><li>By default, Meta Ads does not allow the distribution of device-level data with unrestricted attribution information. However, if you accept the Meta Advanced Mobile Measurement (AMM) Terms, you can access device-level attribution data for Meta Ads without restriction. See <Anchor target="_blank" href="/marketers/docs/meta-ads-integration-setup#enable-meta-ads-device-level-data">Enable Meta ads device-level data</Anchor>.</li><li>Data from the AEM deep link solution (iOS), as well as data from the Google Play Install Referrer and the Meta Install Referrer (Android), is available in device-level reports.</li><li>Data from the Google Play Install Referrer and the Meta Install Referrer can only appear in install reports.</li><li>Data from the AEM deep link solution (iOS) can only appear in re-engagement reports.</li></ul>Clicks and impressions from Meta Ads aren't included in raw data reports. |
| <span id="pinterest"></span>Pinterest | Pinterest manages the raw data restriction logic for each event and communicates it to AppsFlyer through the integration. This logic can apply to both click-through and view-through attribution data.<br /><br />When an event has raw data restrictions, you can’t access its click-through and view-through attribution data, including all attribution fields, such as media source, campaign, adset, ad, touch type, engagement type, and touch time.<br /><br />In all cases, raw data reports don’t include clicks and impressions from Pinterest. |
| <span id="reddit"></span>Reddit | Clicks and impressions from Reddit aren't included in raw data reports.<br /><br />**Reminder:** Data received about a Reddit campaign is subject to <Anchor target="_blank" href="https://business.reddithelp.com/s/article/Reddit-Business-Tool-Terms">Reddit Business Tool Terms</Anchor>, and includes, among other restrictions, a prohibition on using Reddit data to create profiles of any users. |
| <span id="samsung-dsp"></span>Samsung DSP | Starting October 17, 2023:<br /><br />Samsung view-through and click-through attribution is limited. The following are included in raw data delivery tools:<ul><li>Media source (samsungdsp\_int)</li><li>Attributed touch type (impression/click)</li><li>Attributed touch time is available</li><li>Campaign details are available</li></ul>Clicks and impressions from Samsung aren't included in raw data reports.<br /><br />Starting August 30, 2025:<br /><br />Samsung EMEA view-through and click-through attribution is limited, for engagements received with `af_data_restriction=attribution` on the URL. The following are included in raw data delivery tools:<ul><li>Media source: reported as restricted</li><li>Attributed touch type (impression/click)</li><li>Attributed touch time is available</li><li>Campaign details are available</li></ul>Clicks and impressions from Samsung aren't included in raw data reports. |
| <span id="snapchat"></span>Snapchat | The following restrictions apply to Snapchat raw data:<ul><li>Starting March 1, 2023, Snapchat uninstalls aren't included in the raw data reports.</li><li>View-through attribution device-level data is limited in some cases. The logic of the raw data restrictions is managed on the Snapchat side, per event, and is communicated to AppsFlyer via the integration.</li><li>When the event has raw data restrictions, the following are **not** restricted in raw data delivery tools:</li></ul><ul><li>Media source (snapchat\_int)</li><li>Channel</li><li>Attributed touch type (impression)</li><li>Attributed touch time (reported as date only, "dd/mm/yyyy")</li><li>Campaign name and ID (starting December 15, 2025)</li><li>Ad set name and ID (starting December 15, 2025)</li></ul><ul><li>The above restrictions do not apply to engaged views.</li></ul>Clicks and impressions from Snapchat aren't included in raw data reports. |
| <span id="tiktok-for-business"></span>TikTok for Business | Until May 19, 2026, the following restrictions applied to view-through attribution:<ul><li>Media source was reported as `tiktokglobal_int`</li><li>Channel was reported as TikTok / Pangle</li><li>Attributed touch type was reported as impression</li><li>Attributed touch time was reported as date only ("dd/mm/yyyy")</li><li>Campaign, ad set, and ad information were reported as "restricted"</li></ul>As of May 19, 2026, the following raw data tools were updated: Pull API, Data Locker, and the Raw Data Export page.<br /><br />As of June 25, 2026, the following raw data tools were updated: Push API and the Get conversion data (GCD) API.<br /><br />The changes are:<ul><li>Only the `original_url` field is restricted (empty)</li><li>All other attribution fields are fully supported</li></ul>The above restrictions don't apply to engaged views.<br /><br />Clicks and impressions raw data reports via Data Locker from `tiktokglobal_int` are restricted. |
| <span id="uber"></span>Uber | The following restrictions apply to view-through and click-through attribution:<ul><li>Media source (uber\_int): available</li><li>Campaign details: available</li></ul>Clicks and impressions from Uber aren't included in raw data reports. |
| <span id="x-ads-formerly-twitter"></span>X Ads (formerly Twitter) | In some cases, based on user choices in X Ads, raw data may be restricted on the AppsFlyer platform.<br /><br />**Until July 15, 2025:** Attributed events from X Ads didn't appear at all in raw data reports.<br /><br />**As of July 15, 2025:** Attributed events are included in raw data reports, with the following restrictions:<ul><li>Media source (twitter): available</li><li>Campaign details: reported as *restricted*</li><li>Channel (Twitter): available</li><li>Attributed touch type: available</li><li>Attributed touch time: reported as date only (`dd/mm/yyyy`)</li></ul>Clicks and impressions from X Ads aren't included in raw data reports.<br /><br />Access to unrestricted raw data depends on participation in X Ads' **Advanced Mobile Measurement (AMM) program** and on end-user privacy settings:<ul><li>AMM not enabled: all clicks and impressions are sent with `af_data_restriction=attribution`. All resulting events are restricted.</li><li>AMM enabled:<ul><li>EU users: events are restricted if data sharing with business partners is not granted.</li><li>Users who did not agree to share data: events are restricted (`af_data_restriction=attribution`).</li><li>Users who agreed to share data with business partners: events are not restricted (`af_data_restriction=none`).</li></ul></li></ul>For more information, see the <Anchor target="_blank" href="/marketers/docs/x-ads-formerly-twitter-ads-setup-guide-overview#x-ads-user-privacy">X Ads setup guide, user privacy section</Anchor>. |
| Walmart | The following restrictions apply to view-through and click-through attribution:<ul><li>`original_url` : restricted</li></ul>Clicks and impressions from Walmart aren't included in raw data reports. |

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
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data">Get conversion data (GCD) API</Anchor> in the context of the client-side user-level data API

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
| <span id="event_time"></span>event\_time |
| <span id="event_name"></span>event\_name |
| <span id="event_revenue"></span>event\_revenue |
| <span id="event_revenue_currency"></span>event\_revenue\_currency |
| <span id="event_revenue_usd"></span>event\_revenue\_usd |
| <span id="af_cost_model"></span>af\_cost\_model |
| <span id="af_cost_value"></span>af\_cost\_value |
| <span id="af_cost_currency"></span>af\_cost\_currency |
| <span id="event_source"></span>event\_source |
| <span id="media_source"></span>media\_source |
| <span id="af_channel"></span>af\_channel |
| <span id="campaign"></span>campaign |
| <span id="af_c_id"></span>af\_c\_id |
| <span id="af_adset"></span>af\_adset |
| <span id="af_adset_id"></span>af\_adset\_id |
| <span id="af_ad"></span>af\_ad |
| <span id="af_ad_id"></span>af\_ad\_id |
| <span id="af_ad_type"></span>af\_ad\_type |
| <span id="af_siteid"></span>af\_siteid |
| <span id="af_sub_siteid"></span>af\_sub\_siteid |
| <span id="app_id"></span>app\_id |
| <span id="app_name"></span>app\_name |
| <span id="bundle_id"></span>bundle\_id |
| <span id="is_retargeting"></span>is\_retargeting |
| <span id="retargeting_conversion_type"></span>retargeting\_conversion\_type |
| <span id="is_primary_attribution"></span>is\_primary\_attribution |
| <span id="af_attribution_lookback"></span>af\_attribution\_lookback |
| <span id="af_reengagement_window"></span>af\_reengagement\_window |
| <span id="country_code"></span>country\_code |
| <span id="blocked_reason"></span>blocked\_reason |
| <span id="blocked_reason_value"></span>blocked\_reason\_value |
| <span id="blocked_reason_rule"></span>blocked\_reason\_rule |
| <span id="blocked_sub_reason"></span>blocked\_sub\_reason |
| <span id="platform"></span>platform |
| <span id="is_paid_media"></span>is\_paid\_media |

</Accordion>

## FAQ

<div id="what-events-are-restricted" />

<Accordion title="What events are restricted?">

Restricted events, as detailed in the [table above](/docs/about-raw-data-identifier-restrictions#media-source-restrictions), may include conversions (installs, re-engagements, and re-attributions) and associated in-app events to which the restricting ad network is attributed.

</Accordion>

<div id="how-does-the-restricted-media-source-impact-raw-data-reports" />

<Accordion title="How does the restricted media source impact raw data reports?">

* The *media source* field is populated with *restricted*.
* The attribution fields listed in this article are either empty or populated with *null*.

**Report example:** Installs <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vScXJznEex0WwdCy78Bm8LtrhbCk1jNy14O_t7etrq5ab5v4CIEiInfFD4B1EsZCE-_w-dVRAxl_cu4/pub?output=csv">restricted raw data</Anchor> in a CSV file. Other raw data reports are populated in a similar manner.

</Accordion>

<div id="how-does-the-restricted-media-source-impact-postbacks-sent-to-partners" />

<Accordion title="How does the restricted media source impact postbacks sent to partners?">

Postbacks sent to partners don't include attribution fields.

</Accordion>

<div id="how-do-restricted-events-impact-postbacks-to-thirdparty-platforms" />

<Accordion title="How do restricted events impact postbacks to third-party platforms?">

Postbacks for attributed ad networks listed in the [table above](#media-source-restrictions) aren't sent to third-party platforms.

</Accordion>

<div id="do-nonrestricted-events-impact-postbacks-to-thirdparty-platforms" />

<Accordion title="Do non-restricted events impact postbacks to third-party platforms?">

For events sent to third-party platforms such as analytics and marketing platforms, see the <Anchor target="_blank" href="/marketers/docs/discrepancies-between-appsflyer-and-third-party-platforms#postback-restrictions-on-third-party-platforms">postback restrictions on third-party platforms</Anchor>. In some cases, postbacks for non-restricted events don't include the media source. This means attribution is credited as organic.

</Accordion>

<div id="what-about-the-data-of-assists-that-form-part-of-the-attribution" />

<Accordion title="What about the data of assists that form part of the attribution?">

Data related to assists is regarded as attribution data and isn't available.

</Accordion>

> 📄 **See also**
>
> <Anchor target="_blank" href="/marketers/docs/user-level-data-retention">User-level data retention</Anchor>

<div data-zendesk-anchors="01H7WQHTV9RM2JF2BV45XF626H=raw-data-restriction 01H7WQHTV9HJEHHH1N8VN6APX6=media-source-restrictions 01H7WQHTV90YFRP3Z9AEP7ACRD=note 01H7WQHTVA8H9FTBJ1FB6BJQ2A=raw-data-context 01H7WQHTVA0XP6B2H95EEM7EYD=unavailable-attribution-fields 01H7WQHTVA7ERWW1PC3DF5H0NP=identifier-restriction 01H7WQHTVA5439QPE6GNXNKJ63=faq h_01HDBND48E05P1WV51ZJGD072N=what-events-are-restricted 01H7WQHTVAHCK7QDZ5P25YRQ2D=how-does-the-restricted-media-source-impact-raw-data-reports 01H7WQHTVABKATP6B6XN4NRC54=how-does-the-restricted-media-source-impact-postbacks-sent-to-partners h_01HDBND48EDTAFBFXTADGWJADM=how-do-restricted-events-impact-postbacks-to-thirdparty-platforms h_01HE5TK3WSNBPM6W5D1Y9S6PDX=do-nonrestricted-events-impact-postbacks-to-thirdparty-platforms 01H7WQHTVA60PWZ017WJMRTKVP=what-about-the-data-of-assists-that-form-part-of-the-attribution h_01HE7SCVN3VJ4Y6KF2QZSNBEMZ=see-also" />
