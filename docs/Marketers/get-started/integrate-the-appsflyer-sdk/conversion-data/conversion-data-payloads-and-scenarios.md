---
title: "Conversion data payloads and scenarios"
excerpt: "Use conversion data to identify various conversion scenarios, customize user experience, and more."
---
## Overview

The following guide contains various user conversion scenarios and their corresponding conversion data payloads:

- [User Acquisition (UA)](#ua-conversion-data-with-srns)
- [Retargeting](#retargeting-conversion-data)

Conversion data is made available in the platform using any of the following:

- [Raw-data reports](https://support.appsflyer.com/hc/articles/360008613838)
- [Push API](https://support.appsflyer.com/hc/articles/207034356)
- [The AppsFlyer SDK](https://dev.appsflyer.com/hc/docs/conversion-data)

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

| Payload fields name | Raw-data field name | Remarks |
| --- | --- | --- |
| `af_channel` | Channel | SRNs populating this parameter:<br/>- AppLovin<br/>- Google Ads<br/>- Meta ads<br/>- Snapchat<br/>- TikTok for Business<br/>- X Ads<br/>Example: Facebook—Instagram, Google—YouTube |
| `orig_cost` |  | Note (1) |
| `cost_cents_USD` |  | Note (1) |
| `af_cpi` |  | Note (1) |

> 📘 Note
>
> (1) Cost fields are populated with values shared by the ad network. In order for the ad network to share cost data with AppsFlyer, you must enable cost integration on the [**Active integrations**](https://support.appsflyer.com/hc/articles/207040526#ad-networks-supporting-cost-api) page. Some SRNs support cost-sharing in bulk. In this case, event-level cost fields return as 0.

### Additional fields

- [AppsFlyer parameter list](https://support.appsflyer.com/hc/articles/207447163#attribution-link-parameters)
- You can add parameters to the attribution link, they are made available in the payload

See [raw-data fields dictionary](https://support.appsflyer.com/hc/articles/208387843#data-fields-dictionary) for additional information.

### Limitations

Custom parameter names

Custom parameters cannot be called `name` (lower case "n". `Name` is valid).

If a parameter is called `name`, it is removed from the payload.

* * *

## UA conversion data with SRNs

[Self-reporting networks](https://support.appsflyer.com/hc/articles/360001546905-Self-Reporting-Networks) (SRNs) are ad networks that implement their own attribution mechanisms, for example, Meta ads and Google.

SRNs don't use attribution links. It means that:

- Payload fields are predefined
- You can't add fields to the payload by appending parameters to an attribution link.

SRNs report conversions to AppsFlyer. The conversion data is made available in the app. The available fields vary by SRN and are detailed in the individual SRN tabs that follow.

> 📘 A note about Meta ads
>
> If you run campaigns on Meta ads and don't sign the Meta terms of service, AppsFlyer attributes the install. Report availability is limited as follows:
>
> - **Available:** Aggregate and analytics dashboards and reports
> - **Not available:** Raw data

<Tabs>
<Tab title="Meta ads">

### Meta ads conversion data

| Field name | Remarks | Data source |
| --- | --- | --- |
| `match_type` | `srn`, `gp_referrer`, `probabilistic` | AF |
| `media_source` | Always `Facebook Ads` | AF |
| `agency` | `null` or contains the agency name when [running Meta ads campaigns](https://support.appsflyer.com/hc/articles/207034106#srn-configurations) | Meta ads |
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
| `af_siteid` | **af\_siteid mapping:**<br/>_**publisher\_platform**_ → _**af\_siteid**_<br/>Facebook → ""<br/>Instagram → Instagram<br/>AudienceNetwork → AudienceNetwork<br/>Messenger → Messenger<br/>unknown → unknown<br/>"" \+ is\_instagram=true → Instagram<br/>"" \+ is\_external=true → AudienceNetwork | Meta ads |
| `af_sub[1-5]` | Always `null` | Advertiser |

> 📘 Note
>
> Cost-related fields are not available because Meta ads does not share cost data upon conversion. If [cost-sharing](https://support.appsflyer.com/hc/articles/207033826-Facebook-Ads-setup-guide#cost-clicks-and-impressions) is enabled, Meta ads shares cost data with AppsFlyer several times a day.

</Tab>

<Tab title="Google Ads">

### Google Ads conversion data

| Field name | Remarks |
| --- | --- |
| `match_type` | `srn`, `probabilistic` |
| `media_source` | Always `googleadwords_int` |
| `agency` | `none` or value of `af_prt` |
| `http_referrer` |  |
| `retargeting_conversion_type` |  |
| `af_channel` | Note (1) |
| `af_status` | Always `Non-organic` |
| `click_time` |  |
| `install_time` |  |
| `is_first_launch` | `true`, `false` |
| `adgroup_name` |  |
| `adset_id` | Always `null` |
| `campaign` | Note (3) |
| `campaign_id` |  |
| `adgroup` |  |
| `adgroup_id` |  |
| `adset` | Note (3) |
| `af_siteid` |  |
| `af_sub[1-5]` |  |
| `ad_event_id` |  |
| `af_ad` | Empty string |
| `af_ad_id` | Available in raw data when Google returns `creative_id` value. |
| `af_ad_type` | AdWords ad type |
| `af_adset` | Available in raw-data: Adset |
| `af_adset_id` | Available in raw-data: Adset ID |
| `af_c_id` | Available in raw-data: Campaign ID |
| `af_click_lookback` |  |
| `af_cpi` | Note (2) |
| `af_dp` | Only relevant to [Google App campaigns in Feeds](https://support.appsflyer.com/hc/articles/115002504686#using-deferred-deep-linking-in-app-campaigns). |
| `af_keywords` | Available in raw-data: Keywords |
| `af_prt` | `none` or value of `af_prt` |
| `af_reengagement_window` | Available in raw-data: Re-engagement Window |
| `af_viewthrough_lookback` | Available in raw-data: Lookback Window for View-through Attribution |
| `click_url` | Available in raw-data: HTTP Referrer |
| `click-timestamp` | Source: AppsFlyer |
| `cost_cents_USD` | Note (2) |
| `external_account_id` | AdWords account ID |
| `gclid` |  |
| `lat` |  |
| `network` | Note (1) |
| `orig_cost` | Note (2) |
| `video_id` | Always `null` |

> 📘 Notes
>
> (1) Google makes use of multiple ad networks. Use `af_channel` in conjunction with `network` to derive the install source.
> (2) These fields return as 0. If the advertiser enables cost-sharing, Google sends AppsFlyer cost data several times a day.
> (3) Use `campaign` and `af_adset` to personalize user content.

</Tab>

<Tab title="ASA">

### Apple Search Ads conversion data

| Field name | Remarks |
| --- | --- |
| `match_type` | Always `srn` |
| `media_source` | Always `Apple Search Ads` |
| `adset` | Note (2) |
| `adset_id` |  |
| `af_adset` | Note (2) |
| `af_adset_id` |  |
| `af_c_id` |  |
| `af_click_lookback` |  |
| `af_cpi` | Note (1) |
| `af_keywords` | Note (2)—Use keywords ID |
| `af_siteid` |  |
| `af_status` | Always `Non-organic` |
| `af_sub[1-5]` |  |
| `agency` | `null` or value of `af_prt` |
| `campaign` | Note (2) |
| `campaign_id` |  |
| `click_time` |  |
| `is_first_launch` | `true`, `false` |
| `cost_cents_USD` | Note (1) |
| `http_referrer` |  |
| `install_time` |  |
| `adgroup` |  |
| `adgroup_id` |  |
| `orig_cost` | Note (1) |
| `retargeting_conversion_type` |  |

> 📘 Notes
>
> (1) Apple Search Ads supports cost-sharing in bulk, not in conversion data.
> (2) Deprecated starting February 15, 2021, due to [Apple Search Ads adoption of the AdServices AP.](https://support.appsflyer.com/hc/articles/360016711377-Bulletin-Action-required-Apple-Search-Ads-integration#availability-of-campaign-names-and-other-identifiers)

</Tab>

<Tab title="Snapchat">

### Snapchat conversion data

| Field name | Remarks |
| --- | --- |
| `match_type` | `srn`, `gp_referrer`, `id_matching`, `probabilistic`<br/>As an Advanced SRN, all match types are supported. |
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

</Tab>

<Tab title="X Ads">

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

> 📘 Note
>
> Cost fields do not appear in the payload because X Ads doesn't support cost data sharing.

</Tab>

<Tab title="TikTok">

### TikTok for Business conversion data

| Field name | Remarks |
| --- | --- |
| `match_type` | `srn`, `gp_referrer`, `id_matching`, `probabilistic`<br/>As an Advanced SRN, all match types are supported. |
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

> 📘 Note
>
> Cost fields do not appear in the payload because TikTok doesn't support cost data sharing.

</Tab>

<Tab title="Oath">

### Oath Ad Platforms conversion data

| Field name | Remarks |
| --- | --- |
| `match_type` | Always `srn` |
| `media_source` | Always `yahoogemini_int` |
| `adset` |  |
| `adset_id` |  |
| `af_ad` |  |
| `af_ad_id` |  |
| `af_c_id` |  |
| `af_cpi` | Note (1) |
| `af_siteid` |  |
| `af_status` | Always `Non-organic` |
| `af_sub[1-5]` |  |
| `agency` |  |
| `campaign` |  |
| `campaign_id` |  |
| `campaign_type` |  |
| `click_time` |  |
| `cost_cents_USD` | Note (1) |
| `http_referrer` |  |
| `install_time` |  |
| `is_first_launch` |  |
| `adgroup` |  |
| `adgroup_id` |  |
| `orig_cost` | Note (1) |
| `retargeting_conversion_type` |  |

> 📘 Note
>
> (1) Oath supports cost-sharing but sends cost-related data in bulk, not in conversion data.

</Tab>
</Tabs>

## UA conversion with other ad networks

For other ad networks, the data in the payload is directly affected by the [parameters in the attribution link](https://support.appsflyer.com/hc/articles/207447163).

Examine the following JSON payloads.

> 📘 Note!
>
> Conversion data returns as a map-like data structure. The developer **does not** interact with raw JSON.

<Tabs>
<Tab title="Applovin">

#### Attribution link:

```auto
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

- Parameters in the attribution link appear as fields in the payload
- Other fields in the payload that are **not in the attribution link** appear with a value of null
- AppLovin supports ad cost-sharing but sends cost data to AppsFlyer in bulk. Cost-related fields return as 0.

</Tab>

<Tab title="ironSource">

#### Attribution link:

```auto
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

</Tab>
</Tabs>

## Retargeting conversion data

Retargeting includes two types of conversions, re-attribution or re-engagement.

> 👍 Tip
>
> Conversion data for retargeting doesn't always give a clear indication as to the type of conversion. See [alternative conversion data sources](#alternative-conversion-data-sources).

### Re-attribution with SRNs

When a user is re-attributed through an SRN, the conversion data payload doesn't indicate that this is a retargeting campaign. Since SRNs don't use attribution links, there is no way to set an `is_retargeting=true` parameter in the attribution link. For **SRNs that do support retargeting**, AppsFlyer determines whether the user should be re-attributed or not.

What this means is that there is no way to determine, on the SDK level, if an install comes from a retargeting campaign. The only way is to set the campaign name such that it indicates a retargeting campaign.

> 📘 Note
>
> Setting the campaign name such that it indicates retargeting **is not a foolproof method**. See [examples to learn more](#examples-of-mixed-user-acquisition-and-reattribution).

### Re-attribution with regular ad networks

Attribution to ad networks relies on attribution links. Whether regular attribution links or OneLink, with retargeting the attribution link always has the `is_retargeting=true` parameter set in it.

Retargeting campaign with Criteo

#### Attribution link

```auto
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

- `retargeting_conversion_type` parameter - this parameter indicates the type of retargeting. Can be either re-attribution, re-engagement, or none.
- `is_retargeting: true` parameter - this parameter indicates that the install is a re-attributed install
- `af_reengagement_window`: The re-engagement attribution window is the number of days in which an event can be attributed to a **re-engaged user**. Since this is a re-attribution conversion, this parameter is redundant.

### Re-attribution with deferred deep linking

Oftentimes, you want to deep link re-attributed users who, by definition of being re-attributed, don't have the app installed. For example, You set a campaign that aims to bring back users who uninstalled the app. The campaign promotes a product or service and you want to serve the users with content related to the product or service that you advertise.

This is referred to as Deferred Deep Linking. Conversion data payload for Deferred Deep Linking comes from the `onConversionDataSuccess` method.

Deferred deep linking with SRNs

Deep Link parameters defined in SRNs campaigns are not available outside of the SRN. This includes the `af_dp` parameter, which holds the scheme path in the app. The only exception to this is when using [Google App campaigns in Feeds](https://support.appsflyer.com/hc/articles/115002504686#using-deferred-deep-linking-in-app-campaigns). To implement deferred deep linking, additional logic must be applied for SRN campaigns. Use the data in `onConversionSuccess` response, such as campaign, adset, adgroup, to programmatically redirect your users.

#### Conversion data for deferred deep linking with Meta ads

<Tabs>
<Tab title="Android">

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

</Tab>

<Tab title="iOS">

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

</Tab>
</Tabs>

You can use the data in getConversionData response, such as campaign, adset, etc. to programmatically redirect your users and serve them with relevant content.

**Example**

The app is an eCommerce app that specializes in sportswear. A user who doesn't have the app installed engages with an ad and installs the app. Once the app launches, the SDK returns the conversion data. The developer makes the app open the **summer running shoe collection** (campaign) activity in the store and serves the **running shoes for women** category (adset).

Deferred deep linking with attribution links

There are three ways to deep link users:

#### URI schemes

When using URI Schemes, for both attribution links and OneLink, the attribution link and payload are as follows:

**Attribution Link**

```auto
http://app.appsflyer.com/com.appsflyer.nivisampleapp?pid=media_source_name
  &c=campaign_name&af_dp=superapp%3A%2F%2deeplink-activity
```

**OneLink**

```auto
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

- `af_deeplink: true` - when this parameter appears and is set to true, look for the `scheme` and `host` fields
- `scheme` and `host` - these fields come from the `af_dp` parameter in the attribution link and indicate the scheme and activity to which the user should be deep linked

#### iOS Universal links and Android app links

These are the other two out of the three ways for performing deep linking.

When using universal links or app links, the OneLink and payload are as follows:

**OneLink**

```auto
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

- `shortlink` field - this is the field that indicates the specific OneLink that the user comes from. It helps the developer know how to proceed in terms of launching an activity and serving content. Other fields like `campaign` can also be used for this purpose.

> ❗️ Important!
>
> The field `shortlink` does not appear in the payload when using the long OneLink.
>
> In both cases (short or long OneLink) we recommend adding a custom parameter that indicates the activity. For example `&deep_link_activity=shoes_cateogry`

> 📘 Note
>
> Using universal links and app links is only possible with OneLink.

### Re-engagement with SRNs

Much like with Re-Attribution campaigns, when a user is re-engaged through an SRN, the conversion data doesn't indicate that this is a re-engagement campaign. You can set the campaign name such that it indicates a re-engagement campaign.

### Re-engagement with regular ad networks

Here too, the conversion data payload doesn't indicate that the user comes from a re-engagement campaign. To overcome this limitation, you can set the campaign name to indicate a re-engagement.

### Re-engagement with deep linking

A major part of Re-Engagement is to send the user to a specific activity. For example, if you advertise some product or sale. In such cases, you want to send the users who click the ad straight to the app activity for this product or sale.

To do so, you use Deep Linking. The conversion data in Deep Linking is really important. It holds the information necessary for the developer to customize the user experience and send them to the correct activity.

Re-engagement: deep linking with SRNs

Conversion data is not available when a re-engaged user comes from an SRN. The developer needs to use the SRN methods to get it upon app launch.

Re-engagement: deep linking with ad networks

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

- The app developer can use such parameters, like `af_dp` and campaign name, to send the user to a specific activity and serve the relevant content.

> ❗️ Important!
>
> We recommend using the short version of OneLink. Click [here](https://support.appsflyer.com/hc/articles/360017132597) to learn more.
>
> Another reason to use the short version of OneLink is the conversion data structure that the long version returns. When using the long version, the conversion data is a map with a single field called `link` that holds the entire long OneLink.

```json
{
     "link": "https://abcd.onelink.me/12ab?pid=media_source&c=campaign_name&is_retargeting=true&af_dp=superapp%3A%2F%2FDeepLink"
  }
```

### Alternative conversion data sources

- Push API offers a detailed conversion payload that indicates re-attribution or re-engagement. Push API payloads include a field called `re_targeting_conversion_type`. This field indicates the type of conversion, either re-attribution or re-engagement. To learn more, see our [Push API guide](https://support.appsflyer.com/hc/articles/207034356-Push-APIs-Installation-and-Conversion-Notification-APIs).
- Raw Data Reports also contain indicators for the type of conversion. In the raw data report for retargeting conversions, there is a column called _**Event Name**_. The value in this column is either _**re-engagement**_ or _**re-attribution**_ according to the type of conversion.

### Examples of mixed user acquisition and re-attribution

**Example**

1. A user installs your app and then uninstalls it. The act of installation puts the user in a [re-attribution window](https://support.appsflyer.com/hc/articles/115002587066-Re-Attribution-Window). You set a user acquisition (not retargeting) campaign with Meta ads. You also set the AppsFlyer integration with Meta ads to allow retargeting.

While still in the re-attribution window, the user sees the ad, clicks on it, and reinstalls the app. As far as AppsFlyer sees it, the user is a re-attributed user.

This is due to two factors:

1. The configuration with Meta ads allows retargeting
2. The user is in the re-attribution window

In this case, the campaign name doesn't indicate re-attribution.

2. Let's take the same example, only this time the user is outside the re-attribution window. In this case, the install is a new non-organic install.
3. Let's look at another example. You set a retargeting campaign on Meta ads. Some users come across the campaign and install the app. However, these users install the app for the first time. Such users are not considered re-attributed users. Instead, AppsFlyer considers them as users that come from a user acquisition campaign.