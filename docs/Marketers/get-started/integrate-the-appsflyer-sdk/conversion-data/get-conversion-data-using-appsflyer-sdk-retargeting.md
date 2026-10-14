---
title: "Get conversion data using AppsFlyer SDK–Retargeting"
excerpt: "Learn how re-attributions and re-engagements reflect in the conversion data for SRNs and non-SRN user journeys."
x-zendesk:
  id: 4410481260817
  url: https://support.appsflyer.com/hc/en-us/articles/4410481260817-Get-conversion-data-using-AppsFlyer-SDK-Retargeting
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Conversion data
  section_id: 6551287787537
  position: 4
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-guy-sarfatty, Marketers, Mobile Attribution]
  labels: [Developers, Marketers, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2021-11-09T10:17:47Z'
  edited_at: '2026-09-23T12:20:18Z'
---
## Retargeting conversion

Retargeting includes two types of conversions, re-attribution or re-engagement.

Conversion data for retargeting doesn't always give a clear indication as to the type of conversion. See [alternative conversion data sources](#alternative-conversion-data-sources).

## Re-attribution with SRNs

When a user is re-attributed through an SRN, the conversion data payload doesn't indicate that this is a retargeting campaign. Since SRNs don't use attribution links, there is no way to set an `is_retargeting=true` parameter in the attribution link. For **SRNs that do support retargeting**, AppsFlyer determines whether the user should be re-attributed or not.

What this means is that there is no way to determine, on the SDK level, if an install comes from a retargeting campaign.

Setting the campaign name such that it indicates retargeting **is not a foolproof method**. See [examples to learn more](#examples-of-mixed-user-acquisition-and-re-attribution).

## Re-attribution with regular ad networks

Attribution to ad networks relies on attribution links. Whether regular attribution links or OneLink, with retargeting the attribution link always has the `is_retargeting=true` parameter set in it.

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

## Re-attribution with deferred deep linking

Oftentimes, you want to deep link re-attributed users who, by definition of being re-attributed, don't have the app installed. For example, You set a campaign that aims to bring back users who uninstalled the app. The campaign promotes a product or service and you want to serve the users with content related to the product or service that you advertise.

This is referred to as Deferred Deep Linking. Conversion data payload for Deferred Deep Linking comes from the `onConversionDataSuccess` method.

<Accordion title="Deferred deep linking with SRNs">

To implement deferred deep linking with SRNs, additional logic
must
be applied for SRN campaigns. Use the data in
`onConversionSuccess` response, such as campaign,
adset,
adgroup, to programmatically redirect your users.

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

You can use the data in getConversionData response, such as campaign,
adset, etc. to programmatically redirect your users and serve
them
with relevant content.

The app is an eCommerce app that specializes in sportswear.
A
user who doesn't have the app installed engages with an ad
and
installs the app. Once the app launches, the SDK returns
the
conversion data. The developer makes the app open the
**summer running shoe collection** (campaign)
activity
in the store and serves the **running shoes for women**
category (adset).

</Accordion>

<Accordion title="Deferred deep linking with attribution links">

There are three ways to deep link users:

#### URI schemes

When using URI Schemes, for both attribution links and OneLink,
the
attribution link and payload are as follows:

**Attribution Link**

```
http://app.appsflyer.com/com.appsflyer.nivisampleapp?pid=media_source_name
  &c=campaign_name&af_dp=superapp%3A%2F%2deeplink-activity
```

**OneLink**

```
// short OneLink
  https://dhba.onelink.me/2rAD/71ba577e

  //long OneLink
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

* `af_deeplink: true` - when this parameter appears
  and is set to true, look for the `scheme` and
  `host` fields
* `scheme` and `host` - these fields
  come
  from the `af_dp` parameter in the attribution
  link
  and indicate the scheme and activity to which the user should
  be deep linked

#### iOS Universal links and Android app links

These are the other two out of the three ways for performing
deep
linking.

When using universal links or app links, the OneLink and payload
are as follows:

**OneLink**

```
// short OneLink
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

* `shortlink` field - this is the field that indicates
  the specific OneLink that the user comes from. It helps the
  developer
  know how to proceed in terms of launching an activity and
  serving
  content. Other fields like `campaign` can also
  be
  used for this purpose.

The field `shortlink` does not appear in the payload
when using the long OneLink.

In both cases (short or long OneLink) we recommend adding
a custom
parameter that indicates the activity. For example
`&deep_link_activity=shoes_cateogry`

Using universal links and app links is only possible with
OneLink.

</Accordion>

## Re-engagement with SRNs

Much like with Re-Attribution campaigns, when a user is re-engaged through an SRN, the conversion data doesn't indicate that this is a re-engagement campaign.

## Re-engagement with regular ad networks

Here too, the conversion data payload doesn't indicate that the user comes from a re-engagement campaign. To overcome this limitation, you can set the campaign name to indicate a re-engagement.

## Re-engagement with deep linking

A major part of Re-Engagement is to send the user to a specific activity. For example, if you advertise some product or sale. In such cases, you want to send the users who click the ad straight to the app activity for this product or sale.

To do so, you use Deep Linking. The conversion data in Deep Linking is really important. It holds the information necessary for the developer to customize the user experience and send them to the correct activity.

<Accordion title="Re-engagement: deep linking with SRNs">

Conversion data is not available when a re-engaged user comes from an SRN. The developer needs to use the SRN methods to get it upon app launch.

</Accordion>

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

We recommend using the short version of OneLink. Click [here](/docs/understand-onelink-short-vs-long-urls) to learn more.

Another reason to use the short version of OneLink is the conversion data structure that the long version returns. When using the long version, the conversion data is a map with a single field called `link` that holds the entire long OneLink.

```json
{
     "link": "https://abcd.onelink.me/12ab?pid=media_source&c=campaign_name&is_retargeting=true&af_dp=superapp%3A%2F%2FDeepLink"
  }
```

</Accordion>

## Alternative conversion data sources

* Push API offers a detailed conversion payload that indicates re-attribution or re-engagement. Push API payloads include a field called `re_targeting_conversion_type`. This field indicates the type of conversion, either re-attribution or re-engagement. To learn more, see our [Push API guide](/docs/push-api-streaming-raw-data).
* Raw Data Reports also contain indicators for the type of conversion. In the raw data report for retargeting conversions, there is a column called ***Event Name***. The value in this column is either ***re-engagemen*t** or ***re-attribution*** according to the type of conversion.

## Examples of mixed user acquisition and re-attribution

1. A user installs your app and then uninstalls it. The act of installation puts the user in a [re-attribution window](/docs/set-up-re-attribution-window). You set a user acquisition (not retargeting) campaign with Meta ads. You also set the AppsFlyer integration with Meta ads to allow retargeting.While still in the re-attribution window, the user sees the ad, clicks on it, and reinstalls the app. As far as AppsFlyer sees it, the user is a re-attributed user. This is due to two factors:

   1. The configuration with Meta ads allows retargeting
   2. The user is in the re-attribution window

   In this case, the campaign name doesn't indicate re-attribution.
2. Let's take the same example, only this time the user is outside the re-attribution window. In this case, the install is a new non-organic install.
3. Let's look at another example. You set a retargeting campaign on Meta ads. Some users come across the campaign and install the app. However, these users install the app for the first time. Such users are not considered re-attributed users. Instead, AppsFlyer considers them as users that come from a user acquisition campaign.