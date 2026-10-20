---
title: Conversion data payloads and scenarios
excerpt: >-
  Use conversion data to identify various conversion scenarios, customize user
  experience, and more.
metadata:
  keywords:
    - Conversion
    - Retargeting
    - Installs
    - Re-attribution
    - Re-engagement
    - Developers
    - SRN
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2018-12-31T13:05:33Z'
  edited_at: '2026-08-14T16:22:50Z'
  id: 360000726098
  locale: en-us
  section: Conversion data
  section_id: 6551287787537
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360000726098-Conversion-data-payloads-and-scenarios
---
## Overview

The following guide contains various user conversion scenarios and their corresponding conversion data payloads:

* [User Acquisition (UA)](#ua-conversion-data-with-srns)
* [Retargeting](#retargeting-conversion-data)

Conversion data is made available in the platform using any of the following:

* [Raw-data reports](/docs/raw-data-export-page)
* [Push API](/docs/push-api-streaming-raw-data)
* [The AppsFlyer SDK](https://dev.appsflyer.com/hc/docs/conversion-data)

Due to the accuracy/latency tradeoff, conversion data for the same device IDs might differ across APIs.

### Non-organic conversion data payload fields

#### Fields always available

The table that follows lists fields that always exist for **non-organic** conversions, irrespective of the conversion `media_source`.

| Payload field name | Raw-data field name | Remarks |
| --- | --- | --- |
| `media_source` | Media source | Attributed publisher. Equivalent to the `pid` parameter in attribution links |
| `install_time` | Install time |  |
| `click_time` | Attributed touch time | The time that a click or impression occurred in UTC |
| `is_first_launch` | N/A | `true`, `false` |
| `af_status` | Raw data is divided into separate reports: organic, non-organic | `"Non-organic"` |
| `af_siteid` | Site ID |  |
| `adgroup_id` | Ad ID |  |
| `adset` | Adset |  |
| `adset_id` | Adset ID |  |
| `agency` | Partner | `null`, or agency name (for campaigns run by agencies) |
| `campaign` | Campaign |  |
| `campaign_id` | Campaign ID |  |
| `http_referrer` | HTTP Referrer |  |
| `retargeting_conversion_type` | Retargeting Conversion Type | "none", or retargeting\_conversion\_type |
| `af_sub[n] (n=1—5)` | Sub Param [n] (n=1–5) |  |

#### Fields available in some cases

The fields in the table that follows are available in some cases, depending on how the SRN populates the individual event.

<table><thead><tr><th>Payload fields name</th><th>Raw-data field name</th><th>Remarks</th><th> </th></tr></thead><tbody><tr><td><code>af_channel</code></td><td>Channel</td><td><p>SRNs populating this parameter:</p><ul><li>AppLovin</li><li>Google Ads</li><li>Meta ads</li><li>Snapchat</li><li>TikTok for Business</li><li>X Ads</li></ul><p>Example: Facebook—Instagram, Google—YouTube </p></td><td> </td></tr><tr><td><code>orig_cost</code></td><td> </td><td>Note (1)</td><td> </td></tr><tr><td><code>cost_cents_USD</code></td><td> </td><td>Note (1)</td><td> </td></tr><tr><td><code>af_cpi</code></td><td> </td><td>Note (1)</td><td> </td></tr><tr><td colspan="4"><p><strong>Note</strong></p><p>(1) Cost fields are populated with values shared by the ad network. In order for the ad network to share cost data with AppsFlyer, you must enable cost integration on the <a href="./roi360-cost-aggregation-overview#ad-networks-supporting-cost-api"><strong>Active integrations</strong></a> page. Some SRNs support cost-sharing in bulk. In this case, event-level cost fields return as 0. </p></td></tr></tbody></table>

### Additional fields

* [AppsFlyer parameter list](/docs/about-link-structure-and-parameters#attribution-link-parameters)
* You can add parameters to the attribution link, they are made available in the payload

See [raw-data fields dictionary](/docs/raw-data-field-dictionary#data-fields-dictionary) for additional information.

### Limitations

<div id="custom-parameter-names" />

<Accordion title="Custom parameter names">

Custom parameters cannot be called `name` (lower case "n". `Name` is valid).

If a parameter is called `name`, it is removed from the payload.

</Accordion>

---

## UA conversion data with SRNs

[Self-reporting networks](/docs/self-reporting-networks-srns) (SRNs) are ad networks that implement their own attribution mechanisms, for example, Meta ads and Google.

SRNs don't use attribution links. It means that:

* Payload fields are predefined
* You can't add fields to the payload by appending parameters to an attribution link.

SRNs report conversions to AppsFlyer. The conversion data is made available in the app. The available fields vary by SRN and are detailed in the individual SRN tabs that follow.

#### A note about Meta ads

If you run campaigns on Meta ads and don't sign the Meta terms of service, AppsFlyer attributes the install. Report availability is limited as follows:

* **Available:** Aggregate and analytics dashboards and reports
* **Not available:** Raw data

<Accordion title="Meta ads">

### Meta ads conversion data

| Field name | Remarks | Data source |
| --- | --- | --- |
| `match_type` | `srn`, `gp_referrer`, `probabilistic` | AF |
| `media_source` | Always `Facebook Ads` | AF |
| `agency` | `null` or contains the agency name when [running Meta ads campaigns](/partners/docs/about-agency-accounts#srn-configurations) | Meta ads |
| `http_referrer` | Always `null` | Meta ads |
| `retargeting_conversion_type` |  | AF |
| `af_channel` |  | Meta ads (publisher\_platform) |
| `af_status` | Always `Non-organic` | AF |
| `ad_id` | For Meta ads internal use only. | Meta ads (ad\_id) |
| `click_time` |  | AF |
| `install_time` |  | AF |
| `is_first_launch` | `true`, `false` | Device |
| `adset_id` | Available in raw-data: Adset ID | Meta ads (campaign\_id) |
| `is_fb` | Always `true` | AF |
| `campaign` | Available in raw-data: Campaign Name | Meta ads (campaign\_group\_name) |
| `campaign_id` | Available in raw-data: Campaign ID | Meta ads (campaign\_group\_id) |
| `is_paid` | Always `true` | Meta ads |
| `adgroup` | Available in raw-data: Ad | Meta ads (adgroup\_name) |
| `adgroup_id` | Available in raw-data: Ad ID | Meta ads (adgroup\_id) |
| `adset` | Available in raw-data: Adset | Meta ads (campaign\_name) |
| `af_siteid` | **af\_siteid mapping:**  <br />  <br />***publisher\_platform***  → ***af\_siteid***  <br />Facebook → ""  <br />Instagram → Instagram  <br />AudienceNetwork → AudienceNetwork  <br />Messenger → Messenger  <br />unknown → unknown  <br />"" + is\_instagram=true → Instagram  <br />"" + is\_external=true → AudienceNetwork | Meta ads |
| `af_sub[1-5]` | Always `null` | Advertiser |

**Note:** Cost-related fields are not available because Meta ads does not share cost data upon conversion. If [cost-sharing](/docs/meta-ads-integration-setup#cost-clicks-and-impressions) is enabled, Meta ads shares cost data with AppsFlyer several times a day.

</Accordion>

<Accordion title="Google Ads">

### Google Ads conversion data

<table><thead><tr><th>Field name</th><th>Remarks</th></tr></thead><tbody><tr><td><code>match_type</code></td><td> <code>srn</code>, <code>probabilistic</code> </td></tr><tr><td><code>media_source</code></td><td>Always <code>googleadwords_int</code></td></tr><tr><td><code>agency</code></td><td><code>none</code> or value of <code>af_prt</code></td></tr><tr><td><code>http_referrer</code></td><td> </td></tr><tr><td><code>retargeting_conversion_type</code></td><td> </td></tr><tr><td><code>af_channel</code></td><td>Note (1)</td></tr><tr><td><code>af_status</code></td><td>Always <code>Non-organic</code></td></tr><tr><td><code>click_time</code></td><td> </td></tr><tr><td><code>install_time</code></td><td> </td></tr><tr><td><code>is_first_launch</code></td><td><code>true</code>, <code>false</code></td></tr><tr><td><code>adgroup_name</code></td><td> </td></tr><tr><td><code>adset_id</code></td><td>Always <code>null</code></td></tr><tr><td><code>campaign</code></td><td>Note (3)</td></tr><tr><td><code>campaign_id</code></td><td> </td></tr><tr><td><code>adgroup</code></td><td> </td></tr><tr><td><code>adgroup_id</code></td><td> </td></tr><tr><td><code>adset</code></td><td>Note (3)</td></tr><tr><td><code>af_siteid</code></td><td> </td></tr><tr><td><code>af_sub[1-5]</code></td><td> </td></tr><tr><td><code>ad_event_id</code></td><td> </td></tr><tr><td><code>af_ad</code></td><td>Empty string</td></tr><tr><td><code>af_ad_id</code></td><td>Available in raw data when Google returns <code>creative_id</code> value.</td></tr><tr><td><code>af_ad_type</code></td><td><span>AdWords ad type</span></td></tr><tr><td><code>af_adset</code></td><td>Available in raw-data: Adset</td></tr><tr><td><code>af_adset_id</code></td><td>Available in raw-data: Adset ID</td></tr><tr><td><code>af_c_id</code></td><td>Available in raw-data: Campaign ID</td></tr><tr><td><code>af_click_lookback</code></td><td> </td></tr><tr><td><code>af_cpi</code></td><td>Note (2)</td></tr><tr><td><code>af_dp</code></td><td>Only relevant to <a href="./google-ads-adwords-integration-setup-for-advertisers#using-deferred-deep-linking-in-app-campaigns">Google App campaigns in Feeds</a>.</td></tr><tr><td><code>af_keywords</code></td><td>Available in raw-data: Keywords</td></tr><tr><td><code>af_prt</code></td><td><code>none</code> or value of <code>af_prt</code></td></tr><tr><td><code>af_reengagement_window</code></td><td>Available in raw-data: Re-engagement Window </td></tr><tr><td><code>af_viewthrough_lookback</code></td><td>Available in raw-data: Lookback Window for View-through Attribution</td></tr><tr><td><code>click_url</code></td><td>Available in raw-data: HTTP Referrer</td></tr><tr><td><code>click-timestamp</code></td><td>Source: AppsFlyer</td></tr><tr><td><code>cost_cents_USD</code></td><td>Note (2)</td></tr><tr><td><code>external_account_id</code></td><td>AdWords account ID</td></tr><tr><td><code>gclid</code></td><td> </td></tr><tr><td><code>lat</code></td><td> </td></tr><tr><td><code>network</code></td><td>Note (1)</td></tr><tr><td><code>orig_cost</code></td><td>Note (2)</td></tr><tr><td><code>video_id</code></td><td>Always <code>null</code></td></tr><tr><td colspan="2"><strong>Notes</strong><br/>(1) Google makes use of multiple ad networks. Use <code>af_channel</code> in conjunction with <code>network</code> to derive the install source.<br/>(2) These fields return as 0. If the advertiser enables cost-sharing, Google sends AppsFlyer cost data several times a day.<br/>(3) Use <code>campaign</code> and <code>af_adset</code> to personalize user content.</td></tr></tbody></table>

</Accordion>

<Accordion title="ASA">

### Apple Search Ads conversion data

<table><thead><tr><th>Field name</th><th>Remarks</th></tr></thead><tbody><tr><td><code>match_type</code></td><td>Always <code>srn</code></td></tr><tr><td><code>media_source</code></td><td>Always <code>Apple Search Ads</code></td></tr><tr><td><code><del>adset</del></code></td><td>Note (2)</td></tr><tr><td><code>adset_id</code></td><td> </td></tr><tr><td><code><del>af_adset</del></code></td><td>Note (2)</td></tr><tr><td><code>af_adset_id</code></td><td> </td></tr><tr><td><code>af_c_id</code></td><td> </td></tr><tr><td><code>af_click_lookback</code></td><td> </td></tr><tr><td><code>af_cpi</code></td><td>Note (1)</td></tr><tr><td><code><del>af_keywords</del></code></td><td>Note (2)—Use keywords ID</td></tr><tr><td><code>af_siteid</code></td><td> </td></tr><tr><td><code>af_status</code></td><td>Always <code>Non-organic</code></td></tr><tr><td><code>af_sub[1-5]</code></td><td> </td></tr><tr><td><code>agency</code></td><td><code>null</code> or value of <code>af_prt</code></td></tr><tr><td><code><del>campaign</del></code></td><td>Note (2)</td></tr><tr><td><code>campaign_id</code></td><td> </td></tr><tr><td><code>click_time</code></td><td> </td></tr><tr><td><code>is_first_launch</code></td><td><code>true</code>, <code>false</code></td></tr><tr><td><code>cost_cents_USD</code></td><td>Note (1)</td></tr><tr><td><code>http_referrer</code></td><td> </td></tr><tr><td><code>install_time</code></td><td> </td></tr><tr><td><code>adgroup</code></td><td> </td></tr><tr><td><code>adgroup_id</code></td><td> </td></tr><tr><td><code>orig_cost</code></td><td>Note (1)</td></tr><tr><td><code>retargeting_conversion_type</code></td><td> </td></tr><tr><td colspan="3"><strong>Notes</strong><br/>(1) Apple Search Ads supports cost-sharing in bulk, not in conversion data.<br/>(2) Deprecated starting February 15, 2021, due to Apple Search Ads adoption of the AdServices AP.</td></tr></tbody></table>

</Accordion>

<Accordion title="Snapchat">

### Snapchat conversion data

| Field name | Remarks |
| --- | --- |
| `match_type` | `srn`, `gp_referrer`, `id_matching`, `probabilistic`   <br />As an Advanced SRN, all match types are supported. |
| `media_source` | `snapchat_int` |
| `adset` |  |
| `adset_id` |  |
| `af_ad` |  |
| `af_ad_id` |  |
| `af_adset` |  |
| `af_adset_id` |  |
| `af_c_id` |  |
| `af_channel` |  |
| `af_cpi` |  |
| `af_siteid` |  |
| `af_status` | Always `Non-organic` |
| `af_sub[1-5]` |  |
| `af_viewthrough_lookback` |  |
| `agency` |  |
| `campaign` |  |
| `campaign_id` |  |
| `click_time` |  |
| `cost_cents_USD` |  |
| `http_referrer` |  |
| `install_time` |  |
| `is_first_launch` |  |
| `adgroup` |  |
| `adgroup_id` |  |
| `orig_cost` |  |
| `retargeting_conversion_type` |  |

</Accordion>

<Accordion title="X Ads">

### X Ads conversion data

| Field name | Remarks |
| --- | --- |
| `match_type` | Always `srn` |
| `media_source` | Always `Twitter` |
| `af_ad` |  |
| `af_ad_id` |  |
| `af_adset` |  |
| `af_adset_id` |  |
| `af_channel` |  |
| `af_siteid` |  |
| `af_status` | Always `Non-organic` |
| `af_sub[1-5]` |  |
| `agency` | Always `null` |
| `campaign` |  |
| `campaign_id` | `null` or Campaign ID |
| `click_time` |  |
| `http_referrer` |  |
| `install_time` |  |
| `is_first_launch` | `true`, `false` |
| `adgroup` |  |
| `adgroup_id` |  |
| `retargeting_conversion_type` | Always `none` |

**Note:** Cost fields do not appear in the payload because X Ads doesn't support cost data sharing.

</Accordion>

<Accordion title="TikTok">

### TikTok for Business conversion data

| Field name | Remarks |
| --- | --- |
| `match_type` | `srn`, `gp_referrer`, `id_matching`, `probabilistic`   <br />As an Advanced SRN, all match types are supported. |
| `media_source` | `tiktokglobal_int` |
| `af_ad` |  |
| `af_ad_id` |  |
| `af_adset` |  |
| `af_adset_id` |  |
| `af_channel` | `tiktok`, `pangle` |
| `af_siteid` |  |
| `af_status` | Always `Non-organic` |
| `af_sub[1-5]` |  |
| `agency` |  |
| `campaign` |  |
| `campaign_id` |  |
| `click_time` |  |
| `http_referrer` |  |
| `install_time` |  |
| `is_first_launch` |  |
| `adgroup` |  |
| `adgroup_id` |  |
| `retargeting_conversion_type` |  |

**Note:** Cost fields do not appear in the payload because TikTok doesn't support cost data sharing.

</Accordion>

<Accordion title="Oath">

### Oath Ad Platforms conversion data

<table><thead><tr><th>Field name</th><th>Remarks</th></tr></thead><tbody><tr><td><code>match_type</code></td><td>Always <code>srn</code></td></tr><tr><td><code>media_source</code></td><td>Always <code>yahoogemini_int</code></td></tr><tr><td><code>adset</code></td><td> </td></tr><tr><td><code>adset_id</code></td><td> </td></tr><tr><td><code>af_ad</code></td><td> </td></tr><tr><td><code>af_ad_id</code></td><td> </td></tr><tr><td><code>af_c_id</code></td><td> </td></tr><tr><td><code>af_cpi</code></td><td>Note (1)</td></tr><tr><td><code>af_siteid</code></td><td> </td></tr><tr><td><code>af_status</code></td><td>Always <code>Non-organic</code></td></tr><tr><td><code>af_sub[1-5]</code></td><td> </td></tr><tr><td><code>agency</code></td><td> </td></tr><tr><td><code>campaign</code></td><td> </td></tr><tr><td><code>campaign_id</code></td><td> </td></tr><tr><td><code>campaign_type</code></td><td> </td></tr><tr><td><code>click_time</code></td><td> </td></tr><tr><td><code>cost_cents_USD</code></td><td>Note (1)</td></tr><tr><td><code>http_referrer</code></td><td> </td></tr><tr><td><code>install_time</code></td><td> </td></tr><tr><td><code>is_first_launch</code></td><td> </td></tr><tr><td><code>adgroup</code></td><td> </td></tr><tr><td><code>adgroup_id</code></td><td> </td></tr><tr><td><code>orig_cost</code></td><td>Note (1)</td></tr><tr><td><code>retargeting_conversion_type</code></td><td> </td></tr><tr><td colspan="2"><strong>Note</strong><br/>(1) Oath supports cost-sharing but sends cost-related data in bulk, not in conversion data.</td></tr></tbody></table>

</Accordion>

## UA conversion with other ad networks

For other ad networks, the data in the payload is directly affected by the [parameters in the attribution link](/docs/about-link-structure-and-parameters).

Examine the following JSON payloads.

**Note!** Conversion data returns as a map-like data structure. The developer **does not** interact with raw JSON.

<div id="applovin" />

<Accordion title="Applovin">

#### Attribution link:

```
https://app.appsflyer.com/com.company.app?af_ad=ad_name&af_ad_type=INTER
  &af_channel=video&af_siteid=123_site_id&af_c_id=b8******************************&
  af_adset=_DEFAULT&pid=applovin_int&c=campaign_name
  &af_click_lookback=7d&clickid=10****************
  &advertising_id=50********************************&af_ip=
```

#### Payload:

```json
{
      "adgroup": null,
      "campaign": "campaign_name",
      "media_source": "applovin_int",
      "retargeting_conversion_type": "none",
      "adset_id": null,
      "campaign_id": null,
      "install_time": "2018-12-30 23:49:54.186",
      "adgroup_id": null,
      "orig_cost": "0.0",
      "click_time": "2018-12-24 14:29:33.738",
      "agency": null,
      "cost_cents_USD": "0",
      "af_ad_type": "INTER",
      "af_c_id": "b8******************************",
      "adset": null,
      "advertising_id": "50********************************",
      "af_sub1": null,
      "clickid": "10****************",
      "af_click_lookback": "7d",
      "af_siteid": "123_site_id",
      "af_ad": "ad_name",
      "http_referrer": null,
      "af_channel": "video",
      "af_adset": "_DEFAULT",
      "af_sub5": null,
      "af_sub4": null,
      "af_cpi": null,
      "af_sub3": null,
      "af_sub2": null,
      "af_status": "Non-organic"
  }
```

* Parameters in the attribution link appear as fields in the payload
* Other fields in the payload that are **not in the attribution link** appear with a value of null
* AppLovin supports ad cost-sharing but sends cost data to AppsFlyer in bulk. Cost-related fields return as 0.

</Accordion>

<div id="ironsource" />

<Accordion title="ironSource">

#### Attribution link:

```
https://app.appsflyer.com/id123456789?
  af_ua=Mozilla/5.0+(iPhone;+CPU+iPhone+OS+12_1_2+like+Mac+OS+X)+AppleWebKit/605.1.15+(KHTML,+like+Gecko)+Mobile/16C101
  &clickid=ab***************&redirect=false
  &ua=Mozilla/5.0+(iPhone;+CPU+iPhone+OS+12_1_2+like+Mac+OS+X)+AppleWebKit/605.1.15+(KHTML,+like+Gecko)+Mobile/16C101
  &af_lang=pt&imei=&af_sub1=&advertising_id=&af_ip=192.168.0.1&pid=ironsource_int
  &device_ip=192.168.0.1&c=campaign_name
  &idfa=01**********************************&af_siteid=123_site_id&
  af_enc_data=cN*********************************************************************
```

#### Payload:

```json
{
      "adgroup": null,
      "af_enc_data": "cN*************************************************************************************",
      "campaign": "campaign_name",
      "media_source": "ironsource_int",
      "retargeting_conversion_type": "none",
      "adset_id": null,
      "campaign_id": null,
      "install_time": "2018-12-30 23:59:32.194",
      "adgroup_id": null,
      "redirect": "false",
      "orig_cost": "0.75",
      "click_time": "2018-12-30 23:58:54.517",
     "agency": null,
      "cost_cents_USD": "75",
      "adset": null,
      "advertising_id": "35****************************",
      "af_sub1": null,
      "af_ip": "192.168.0.1",
      "clickid": "ab*******************",
      "af_sub3": null,
      "af_cost_value": "0.75",
      "af_ref": "ironsource_5f******************************************",
      "af_siteid": "123_site_id",
      "http_referrer": null,
      "af_cost_model": "cpi",
      "af_ua": "Mozilla/5.0 (Linux; Android 8.0.0; SM-N950F Build/R16NW; wv) AppleWebKit/537.36 (KHTML, like Gecko) Version/4.0 Chrome/71.0.3578.99 Mobile Safari/537.36",
      "af_cost_currency": "USD",
      "af_sub5": null,
      "af_sub4": null,
      "af_lang": "en",
      "af_cpi": null,
      "af_click_lookback": "7d",
      "af_sub2": null,
      "af_status": "Non-organic"
  }
```

ironSource shares cost-related data with AppsFlyer upon conversion using the `orig_cost`, `cost_cents_USD`, and `af_cost_value` fields.

However, cost-related data **does not appear in the attribution link**. ironSource encrypts cost data and stores it in the `af_enc_data` field.

</Accordion>

## Retargeting conversion data

Retargeting includes two types of conversions, re-attribution or re-engagement.

**Tip**

Conversion data for retargeting doesn't always give a clear indication as to the type of conversion. See [alternative conversion data sources](#alternative-conversion-data-sources).

### Re-attribution with SRNs

When a user is re-attributed through an SRN, the conversion data payload doesn't indicate that this is a retargeting campaign. Since SRNs don't use attribution links, there is no way to set an `is_retargeting=true` parameter in the attribution link. For **SRNs that do support retargeting**, AppsFlyer determines whether the user should be re-attributed or not.

What this means is that there is no way to determine, on the SDK level, if an install comes from a retargeting campaign. The only way is to set the campaign name such that it indicates a retargeting campaign.

**Note**

Setting the campaign name such that it indicates retargeting **is not a foolproof method**. See [examples to learn more](#examples-of-mixed-user-acquisition-and-re-attribution).

### Re-attribution with regular ad networks

Attribution to ad networks relies on attribution links. Whether regular attribution links or OneLink, with retargeting the attribution link always has the `is_retargeting=true` parameter set in it.

<div id="retargeting-campaign-with-criteo" />

<Accordion title="Retargeting campaign with Criteo">

#### Attribution link

```
https://app.appsflyer.com/id1234567895?pid=criteo_int&af_click_lookback=30d&
  c=campaign_name&is_retargeting=true&redirect=false&idfa=68**********************************
  &af_reengagement_window=30d
```

#### Conversion data payload

```json
{
      "adgroup": null,
      "campaign": "campaign_name",
      "media_source": "criteo_int",
      "retargeting_conversion_type": "re-attribution",
      "adset_id": null,
      "campaign_id": null,
      "af_reengagement_window": "30d",
      "install_time": "2018-12-01 23:13:03.126",
      "adgroup_id": null,
      "redirect": "false",
      "af_sub5": null,
      "click_time": "2018-11-18 20:02:31.559",
      "agency": null,
      "cost_cents_USD": "0",
      "is_retargeting": "true",
      "af_cpi": null,
      "af_click_lookback": "30d",
      "af_siteid": null,
      "idfa": "68**********************************",
      "http_referrer": null,
      "orig_cost": "0.0",
      "af_sub4": null,
      "adset": null,
      "af_sub1": null,
      "af_sub3": null,
      "af_sub2": null,
      "af_status": "Non-organic"
  }
```

* `retargeting_conversion_type` parameter - this parameter indicates the type of retargeting. Can be either re-attribution, re-engagement, or none.
* `is_retargeting: true` parameter - this parameter indicates that the install is a re-attributed install
* `af_reengagement_window`: The re-engagement attribution window is the number of days in which an event can be attributed to a **re-engaged user**. Since this is a re-attribution conversion, this parameter is redundant.

</Accordion>

### Re-attribution with deferred deep linking

Oftentimes, you want to deep link re-attributed users who, by definition of being re-attributed, don't have the app installed. For example, You set a campaign that aims to bring back users who uninstalled the app. The campaign promotes a product or service and you want to serve the users with content related to the product or service that you advertise.

This is referred to as Deferred Deep Linking. Conversion data payload for Deferred Deep Linking comes from the `onConversionDataSuccess` method.

<div id="deferred-deep-linking-with-srns" />

<Accordion title="Deferred deep linking with SRNs">

Deep Link parameters defined in SRNs campaigns are not available outside of the SRN. This includes the `af_dp` parameter, which holds the scheme path in the app. The only exception to this is when using [Google App campaigns in Feeds](/docs/google-ads-adwords-integration-setup-for-advertisers#using-deferred-deep-linking-in-app-campaigns). To implement deferred deep linking, additional logic must be applied for SRN campaigns. Use the data in `onConversionSuccess` response, such as campaign, adset, adgroup, to programmatically redirect your users.

#### Conversion data for deferred deep linking with Meta ads

<Accordion title="Android">

```json
{
     "adset":"Adidas Running Shoes Women",
       "adgroup": null,
     "campaign_id":"6**********",
     "af_status":"Non-organic",
     "retargeting_conversion_type": "none",
     "agency":null,
     "af_sub3":null,
     "af_siteid":null,
     "adset_id":"6**********",
     "is_fb":true,
     "is_first_launch":true,
     "click_time":"2017-07-18 12:55:05",
     "iscache":false,
     "ad_id":"6**********",
     "af_sub1":null,
     "campaign":"running shoes summer collection",
     "is_paid":true,
     "af_sub4":null,
     "adgroup_id":"6**********",
     "is_mobile_data_terms_signed":true,
     "af_channel":"Facebook",
     "af_sub5":null,
     "media_source":"Meta ads",
     "install_time":"2017-07-19 08:06:56.189",
     "af_sub2":null
  }
```

</Accordion>

<Accordion title="iOS">

```json
  {
     "media_source":"Meta ads",
     "campaign":"running shoes summer collection",
     "adset":"Running Shoes Women",
     "adgroup":null,
     "campaign_id":"6**********",
     "retargeting_conversion_type": "none",
     "af_status":"Non-organic",
     "agency":null,
     "af_sub3":null,
     "af_siteid":null,
     "adset_id":"6**********",
     "is_fb":true,
   "is_first_launch":true,
     "click_time":"2017-07-17 16:23:18",
     "iscache":false,
     "ad_id":"6**********",
     "af_sub1":null,
     "is_paid":true,
     "af_sub4":null,
     "adgroup_id":"6**********",
     "is_mobile_data_terms_signed":true,
     "af_channel":"Facebook",
     "af_sub5":null,
     "install_time":"2017-07-18 15:10:50.190",
     "af_sub2":null
  }
```

</Accordion>

You can use the data in getConversionData response, such as campaign, adset, etc. to programmatically redirect your users and serve them with relevant content.

**Example**

The app is an eCommerce app that specializes in sportswear. A user who doesn't have the app installed engages with an ad and installs the app. Once the app launches, the SDK returns the conversion data. The developer makes the app open the **summer running shoe collection** (campaign) activity in the store and serves the **running shoes for women** category (adset).

</Accordion>

<div id="deferred-deep-linking-with-attribution-links" />

<Accordion title="Deferred deep linking with attribution links">

There are three ways to deep link users:

#### URI schemes

When using URI Schemes, for both attribution links and OneLink, the attribution link and payload are as follows:

**Attribution Link**

```
http://app.appsflyer.com/com.appsflyer.nivisampleapp?pid=media_source_name
  &c=campaign_name&af_dp=superapp%3A%2F%2deeplink-activity
```

**OneLink**

```
/ short OneLink
  https://dhba.onelink.me/2rAD/71ba577e

  / /long OneLink
  https://dhba.onelink.me/2rAD?pid=media_source_name&c=campaign_name
  &is_retargeting=true&af_dp=superapp%3A%2F%2deeplink-activity
```

**Payload**

```json
{
      "af_deeplink": true,
      "campaign": "campaign_name",
      "media_source": "media_source_name",
      "retargeting_conversion_type": "none",
      "adset_id": null,
      "campaign_id": null,
      "orig_cost": "0.0",
      "click_time": "2018-12-30 23:59:09",
      "install_time": "2018-12-30 23:59:39.330",
      "agency": null,
      "cost_cents_USD": "0",
      "adset": "AD_SET_NAME",
      "ad_id": "AD_ID",
      "af_siteid": null,
      "http_referrer": null,
      "af_cpi": null,
      "af_sub5": null,
      "af_sub4": null,
      "af_sub1": null,
      "af_sub3": null,
      "af_sub2": null,
      "af_status": "Non-organic",
      "scheme": "superapp",
      "host": "deeplink_activity"
  }
```

* `af_deeplink: true` - when this parameter appears and is set to true, look for the `scheme` and `host` fields
* `scheme` and `host` - these fields come from the `af_dp` parameter in the attribution link and indicate the scheme and activity to which the user should be deep linked

#### iOS Universal links and Android app links

These are the other two out of the three ways for performing deep linking.

When using universal links or app links, the OneLink and payload are as follows:

**OneLink**

```
/ short OneLink
  https://dhba.onelink.me/2rAD/71ba577e

  //long OneLink
  https://dhba.onelink.me/2rAD?pid=media_source_name&c=campaign_name
  &is_retargeting=true
```

**Payload**

```json
{
      "install_time": "2019-01-08 16:24:49.853",
      "cost_cents_USD": "0",
      "campaign": "campaign_name",
      "retargeting_conversion_type": "none",
      "is_first_launch": true,
      "click_time": "2019-01-08 16:24:14.322",
      "af_click_lookback": "7d",
      "orig_cost": "0.0",
      "af_status": "Non-organic",
      "iscache": "true",
      "shortlink": "71ba577e",
      "media_source": "media_source_name",
      "is_retargeting": true
  }
```

* `shortlink` field - this is the field that indicates the specific OneLink that the user comes from. It helps the developer know how to proceed in terms of launching an activity and serving content. Other fields like `campaign` can also be used for this purpose.

  **Important!**

  The field `shortlink` does not appear in the payload when using the long OneLink.

  In both cases (short or long OneLink) we recommend adding a custom parameter that indicates the activity. For example `&deep_link_activity=shoes_cateogry`

**Note**

Using universal links and app links is only possible with OneLink.

</Accordion>

### Re-engagement with SRNs

Much like with Re-Attribution campaigns, when a user is re-engaged through an SRN, the conversion data doesn't indicate that this is a re-engagement campaign. You can set the campaign name such that it indicates a re-engagement campaign.

### Re-engagement with regular ad networks

Here too, the conversion data payload doesn't indicate that the user comes from a re-engagement campaign. To overcome this limitation, you can set the campaign name to indicate a re-engagement.

### Re-engagement with deep linking

A major part of Re-Engagement is to send the user to a specific activity. For example, if you advertise some product or sale. In such cases, you want to send the users who click the ad straight to the app activity for this product or sale.

To do so, you use Deep Linking. The conversion data in Deep Linking is really important. It holds the information necessary for the developer to customize the user experience and send them to the correct activity.

<div id="reengagement-deep-linking-with-srns" />

<Accordion title="Re-engagement: deep linking with SRNs">

Conversion data is not available when a re-engaged user comes from an SRN. The developer needs to use the SRN methods to get it upon app launch.

</Accordion>

<div id="reengagement-deep-linking-with-ad-networks" />

<Accordion title="Re-engagement: deep linking with ad networks">

When a user is re-engaged and the app launches, the following conversion data is available in the `onAppOpenAttribution` method:

For both iOS and Android, when using the short version of OneLink, the conversion data is a structured map of all the parameters on the link:

Example:

```json
{
     af_dp: "superapp://Deeplink",
     pid: "media_source_name"
     c: "campaign_name",
     link: "https://abcd.onelink.me/12ab/12ab34c"
     is_retargeting: true
  }
```

* The app developer can use such parameters, like `af_dp` and campaign name, to send the user to a specific activity and serve the relevant content.

**Important!**

We recommend using the short version of OneLink. Click [here](/docs/understand-onelink-short-vs-long-urls) to learn more.

Another reason to use the short version of OneLink is the conversion data structure that the long version returns. When using the long version, the conversion data is a map with a single field called `link` that holds the entire long OneLink.

```json
{
     "link": "https://abcd.onelink.me/12ab?pid=media_source&c=campaign_name&is_retargeting=true&af_dp=superapp%3A%2F%2FDeepLink"
  }
```

</Accordion>

### Alternative conversion data sources

* Push API offers a detailed conversion payload that indicates re-attribution or re-engagement. Push API payloads include a field called `re_targeting_conversion_type`. This field indicates the type of conversion, either re-attribution or re-engagement. To learn more, see our [Push API guide](/docs/push-api-streaming-raw-data).
* Raw Data Reports also contain indicators for the type of conversion. In the raw data report for retargeting conversions, there is a column called ***Event Name***. The value in this column is either ***re-engagemen*t** or ***re-attribution*** according to the type of conversion.

### Examples of mixed user acquisition and re-attribution

**Example**

1. A user installs your app and then uninstalls it. The act of installation puts the user in a [re-attribution window](/docs/set-up-re-attribution-window). You set a user acquisition (not retargeting) campaign with Meta ads. You also set the AppsFlyer integration with Meta ads to allow retargeting.  
     
   While still in the re-attribution window, the user sees the ad, clicks on it, and reinstalls the app. As far as AppsFlyer sees it, the user is a re-attributed user.  
     
   This is due to two factors:

   1. The configuration with Meta ads allows retargeting
   2. The user is in the re-attribution window

   In this case, the campaign name doesn't indicate re-attribution.
2. Let's take the same example, only this time the user is outside the re-attribution window. In this case, the install is a new non-organic install.
3. Let's look at another example. You set a retargeting campaign on Meta ads. Some users come across the campaign and install the app. However, these users install the app for the first time. Such users are not considered re-attributed users. Instead, AppsFlyer considers them as users that come from a user acquisition campaign.

<div data-zendesk-anchors="h_01HCY86CKDJK9TNHPAZB0QX2ZX=overview nonorganic-conversion-data-payload-fields=non-organic-conversion-data-payload-fields h_01HCY86CKDEMB3428YHCNJQA5R=non-organic-conversion-data-payload-fields h_01HCY86CKDBQRGAY7GHNBJE4WK=fields-always-available h_01HCY86CKDYQMYB9BQ4MXWP8A5=fields-available-in-some-cases h_01HCY86CKD47M85AZVEA5C4JH7=additional-fields h_01HCY86CKEFX646H9BSKSFGZ36=limitations h_01HCY86CKEZ2483XB461M2C9EC=custom-parameter-names h_01EGKTQN6XDYHA60P2WKHBBVFT=ua-conversion-data-with-srns a-note-about-facebook=a-note-about-meta-ads h_01HCY86CKENFEGX53G9G4SGPSK=a-note-about-meta-ads facebook-conversion-data=meta-ads-conversion-data h_01HCY86CKE658H36F3VJQMATQK=meta-ads-conversion-data h_01HCY86CKF6FY96PAWB5Y7YXSQ=google-ads-conversion-data h_01HCY86CKFMNNNJZTPGK4870YN=apple-search-ads-conversion-data h_01HCY86CKF26JRT64JR9JZEAKJ=snapchat-conversion-data twitter-conversion-data=x-ads-conversion-data h_01HCY86CKFM94SQWYARCM0GEJ9=x-ads-conversion-data tiktok-conversion-data=tiktok-for-business-conversion-data h_01HSQRQSK8W9K6871K0EWHDF76=tiktok-for-business-conversion-data h_01HCY86CKFS5SJBECSY42VRJWP=oath-ad-platforms-conversion-data h_01HCY86CKFB0GEJRTYSXN9YZ08=ua-conversion-with-other-ad-networks h_01HCY86CKFY787RD4BHQDVEVFV=applovin h_01HCY86CKFXM5XXJZSPXPB6397=attribution-link h_01HCY86CKFDDXWT2KKFTKKBGHM=payload h_01HCY86CKFV55GYY7C51D7F72S=ironsource attribution-link::a45a1b4a=attribution-link-1 h_01HCY86CKFYGEYR2TRPSD87KDA=attribution-link-1 payload::81867f5c=payload-1 h_01HCY86CKFKKFQDG1P42R1FSDJ=payload-1 h_01EHQ74JS84509GT6M93SZA4HX=retargeting-conversion-data reattribution-with-srns=re-attribution-with-srns h_01HCY86CKFAVWP1W0ZNEN5P30A=re-attribution-with-srns reattribution-with-regular-ad-networks=re-attribution-with-regular-ad-networks h_01HCY86CKF1PV8MRR902RAHQGW=re-attribution-with-regular-ad-networks h_01HCY86CKF1RGK01VTV3EEHQVM=retargeting-campaign-with-criteo attribution-link::c16e96bb=attribution-link-2 h_01HCY86CKFSKBBMFKA8NN8XTPC=attribution-link-2 h_01HCY86CKG2YQQC629SC3RAFKE=conversion-data-payload reattribution-with-deferred-deep-linking=re-attribution-with-deferred-deep-linking h_01HCY86CKGXV50H79R0YH1GB2C=re-attribution-with-deferred-deep-linking h_01HCY86CKG12YRGFEEJ27DQART=deferred-deep-linking-with-srns conversion-data-for-deferred-deep-linking-with-facebook=conversion-data-for-deferred-deep-linking-with-meta-ads h_01HCY86CKGX9VHSV3ASKXMFM0X=conversion-data-for-deferred-deep-linking-with-meta-ads h_01HCY86CKG3XWM4X0YH7WYCEH4=deferred-deep-linking-with-attribution-links h_01HCY86CKGDM2NE1FCRC92K8R0=uri-schemes h_01HCY86CKGY1NE4214DES0Y2AV=ios-universal-links-and-android-app-links reengagement-with-srns=re-engagement-with-srns h_01HCY86CKG4TRYR6TWYYVB0FJE=re-engagement-with-srns reengagement-with-regular-ad-networks=re-engagement-with-regular-ad-networks h_01HCY86CKGM2JS7C9T71R6GPH1=re-engagement-with-regular-ad-networks reengagement-with-deep-linking=re-engagement-with-deep-linking h_01HCY86CKG0NPQAA2ZRWWNKGQD=re-engagement-with-deep-linking h_01HCY86CKGEBHQVFRGJH96KDFJ=reengagement-deep-linking-with-srns h_01HCY86CKGJ9HG7AGB5MFP33RK=reengagement-deep-linking-with-ad-networks h_01HCY86CKG3N6ZXV70G4VMZ0X5=alternative-conversion-data-sources examples-of-mixed-user-acquisition-and-reattribution=examples-of-mixed-user-acquisition-and-re-attribution h_01HCY86CKGK9DVVB7T6CVNB8ZN=examples-of-mixed-user-acquisition-and-re-attribution" />
