---
title: 使用AppsFlyer SDK获取转化数据——再营销
metadata:
  keywords:
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T10:17:47Z'
  edited_at: '2026-10-14T09:59:34Z'
  id: 4410481260817
  locale: zh-cn
  section: Conversion data
  section_id: 6551287787537
  url: https://support.appsflyer.com/hc/zh-cn/articles/4410481260817
---
> **概要：** 本文介绍了SRN和非SRN用户链路中的再归因和再互动在转化数据中的呈现方式。

<div id="retargeting-conversion" />

## 再营销转化

再营销转化分为再归因和再互动两种类型。

<div id="tip" />

> 👍 **提示**
>
> 某些情况下，您可能无法通过再营销转化数据明确地判断转化类型，具体请参考[其他的转化数据来源](#转化数据的其他来源)说明。

<div id="re-attribution-with-srns" />

## SRN带来的再归因

如果某个用户通过SRN完成了再归因，其转化数据的payload中不会说明该流量来自再营销广告。这是因为SRN不使用归因链接，因此无法在链接中设置`is_retargeting=true`参数。对于**支持再营销的SRN**，AppsFlyer会判断是否将相关用户记录为再归因流量。

这种情况下，AppsFlyer无法在SDK层级确定某个激活是否来自再营销广告，只能通过广告系列名称来识别再营销广告带来的流量。

<div id="note" />

> 📘 **注意事项**
>
> 即使您在广告系列名称中标识出再营销也**无法确保**一定能识别出再营销广告。详情请见[示例](#用户获取与再归因混合场景)部分的说明。

<div id="re-attribution-with-regular-ad-networks" />

## 常规广告平台带来的再归因

非SRN广告平台的归因一般通过归因链接完成。不论您通过常规归因链接还是OneLink投放再营销广告，其链接中总是包含`is_retargeting=true`参数。

<div id="retargeting-campaign-with-criteo" />

<Accordion title="Criteo上的再营销广告">

<div id="attribution-link" />

#### 归因链接

```http
https://app.appsflyer.com/id1234567895?pid=criteo_int&af_click_lookback=30d&
  c=campaign_name&is_retargeting=true&redirect=false&idfa=68**********************************
  &af_reengagement_window=30d
```

<div id="conversion-data-payload" />

#### 转化数据payload

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

* `retargeting_conversion_type`参数——该参数用于说明再营销转化的类型。可能出现的参数值为re-attribution（再归因）、re-engagement（再互动）或none（无）。
* `is_retargeting: true`参数——该参数用于标识相关激活是否为再归因。
* `af_reengagement_window`：用于说明再互动归因窗口期。用户与再营销广告互动后，仅在该窗口期所限定的天数内发生的事件才能归因为**再互动**。当转化类型为再归因时，可忽略该参数。

</Accordion>

<div id="re-attribution-with-deferred-deep-linking" />

## 延迟深度链接带来的再归因

您可能经常需要为再归因（即卸载后重新安装相关应用）的用户部署深度链接。假设您为了召回已卸载的流失用户而投放广告，在广告中推广某个产品或服务，并让用户在重新安装并打开应用后直接进入该产品或服务的页面。

用于实现这种场景的技术叫做“延迟深度链接”（Deferred Deep Linking）。您可以使用`onConversionDataSuccess`方法来获取延迟深度链接的转化数据payload。

<div id="deferred-deep-linking-with-srns" />

<Accordion title="在SRN中使用延迟深度链接">

SRN广告中设定的深度链接参数在SRN之外不可用，其中包括含有应用内scheme路径的`af_dp`参数。因此，如需在SRN广告中使用延迟深度链接，您必须在其中添加额外的逻辑。您可以使用`onConversionSuccess`响应中的数据，如广告系列、广告组（adset、adgroup）等，以程序化的方式实现用户跳转。

<div id="conversion-data-for-deferred-deep-linking-with-meta-ads" />

#### Meta ads中延迟深度链接的转化数据

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

您可以使用getConversionData响应中的数据，如广告系列、广告组等，以程序化的方式为用户实现跳转，并向其展示相关内容。

<div id="note-1" />

> 📄 **示例**
>
> 假设您有一个运动服装类电商应用。有一个未安装该应用的用户与某个广告互动后激活了应用。在应用首次启动时，SDK会返回相应的转化数据。开发人员让该应用打开店铺中的**夏季跑鞋系列**页面（与广告系列对应），并展示**女士跑鞋**类别（与广告组对应）。

</Accordion>

<div id="deferred-deep-linking-with-attribution-links" />

<Accordion title="通过归因链接实现延迟深度链接">

深度链接的实现方式共有以下三种：

<div id="uri-schemes" />

#### URI scheme

在归因链接和OneLink中使用URI scheme时，相关归因链接和payload如下：

**归因链接**

```http
http://app.appsflyer.com/com.appsflyer.nivisampleapp?pid=media_source_name
  &c=campaign_name&af_dp=superapp%3A%2F%2deeplink-activity
```

**OneLink**

```http
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

* `af_deeplink: true`——出现该参数且参数值为true时，请查看`scheme`和`host`字段
* `scheme`和`host`——这两个字段来自归因链接中的`af_dp`参数，用于说明相关scheme以及通过深度链接向用户展示的页面

<div id="ios-universal-links-and-android-app-links" />

#### iOS Universal Link和安卓App Link

这两种方式也可以实现深度链接。

使用Universal Link或App Link时，相关的OneLink和payload如下：

**OneLink**

```http
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

* `shortlink`字段用于说明带来用户的具体OneLink。开发人员可根据此信息设置应用打开后跳转的页面和展示的内容。`campaign`等其他字段也具有此用途。

  <div id="important" />

  > 🚧 **注意事项！**
  >
  > 使用OneLink长链时，payload中不会出现`shortlink`字段。
  >
  > 不管您使用长链还是短链，都建议您添加一个自定义参数来说明相关的跳转内容，例如：`&deep_link_activity=shoes_cateogry`。


<div id="note-2" />

> 📘 **注意**
>
> 只有在OneLink场景中才能使用Universal Link和App Link。

</Accordion>

<div id="re-engagement-with-srns" />

## SRN带来的再互动

与再归因相同，当用户通过SRN上的广告再次打开应用（即完成再互动）时，转化数据无法体现该流量是否来自再互动广告。如需解决此问题，您可以在广告系列名称中标识出再互动广告类型。

<div id="re-engagement-with-regular-ad-networks" />

## 常规广告平台带来的再互动

在该场景中，转化数据payload也无法体现出该流量是否来自再归因广告。如需解决此问题，您可以在广告系列名称中标识出再互动广告类型。

<div id="re-engagement-with-deep-linking" />

## 深度链接带来的再互动

大部分的再互动广告会让用户跳转到应用中的某个具体页面。举例来说，假设您投放广告宣传某个商品或优惠活动，并希望点击广告的用户能直接进入应用中与该商品或活动相关的页面。

这时您就要用到深度链接。开发人员需要根据深度链接中的转化数据定制用户体验，并将用户引导到对应的页面。

<div id="reengagement-deep-linking-with-srns" />

<Accordion title="再互动：在SRN中使用深度链接">

来自SRN的再互动用户没有可用的转化数据。开发人员需要使用相关SRN提供的方法在应用打开时获取转化数据。

</Accordion>

<div id="reengagement-deep-linking-with-ad-networks" />

<Accordion title="再互动：在广告平台中使用深度链接">

沉睡用户被唤醒并打开应用时，您可以通过`onAppOpenAttribution`方法获取以下转化数据：

在iOS和安卓平台上使用OneLink短链时，转化数据是链接中所有参数的结构化映射：

举例来说，

```json
{
     af_dp: "superapp://Deeplink",
     pid: "media_source_name"
     c: "campaign_name",
     link: "https://abcd.onelink.me/12ab/12ab34c"
     is_retargeting: true
  }
```

* 应用开发人员可以根据`af_dp`和广告系列名称等参数将用户引导到应用内的具体页面并向其展示相关内容。

<div id="important-1" />

> 🚧 **注意事项！**
>
> 建议使用OneLink短链。详情请见<Anchor target="_blank" href="/marketers/zh/docs/understand-onelink-short-vs-long-urls">此文档</Anchor>。

建议使用OneLink短链的另一个原因是长链返回的转化数据结构较为复杂。使用长链时，转化数据仅通过一个`link`字段进行映射，该字段中包含整条OneLink长链。

```json
{
     "link": "https://abcd.onelink.me/12ab?pid=media_source&c=campaign_name&is_retargeting=true&af_dp=superapp%3A%2F%2FDeepLink"
  }
```

</Accordion>

<div id="alternative-conversion-data-sources" />

## 转化数据的其他来源

* Push API可提供详细的转化数据payload，其中会标识出再归因和再互动。Push API的payload中包含`re_targeting_conversion_type`字段，该字段可说明转化类型，即再归因或再互动。详情请见<Anchor target="_blank" href="/marketers/zh/docs/push-api-streaming-raw-data">Push API指南</Anchor>。
* 原始数据报告也会标识出转化类型。再营销转化的原始数据报告中包含***Event Name***（事件名称）字段，该字段中可能出现的值为**re-engagement**（再互动）或***re-attribution*** （再归因），用于说明转化类型。

<div id="examples-of-mixed-user-acquisition-and-re-attribution" />

## 用户获取与再归因混合场景

<div id="note-3" />

> 📄 **示例**
>
> 1. 某个用户激活您的应用后将其卸载。其激活行为触发了<Anchor target="_blank" href="/marketers/zh/docs/set-up-re-attribution-window">再归因窗口期</Anchor>。您在Meta ads上投放拉新广告（非再营销广告），同时在AppsFlyer后台的Meta ads对接中启用再营销衡量。
>
>    该用户在再归因窗口期内看到并点击该广告，随后重新安装并激活了您的应用。AppsFlyer会将其记录为一次再归因。
>
>    该归因结果基于以下两个因素得出：
>
>    1. Meta ads对接中启用了再营销
>    2. 用户仍处于再归因窗口期内
>    在该场景中，广告系列名称中并未标识出再营销。
> 2. 沿用以上示例，但这次假设该用户在再归因窗口期之后点击广告并重新激活应用。这时AppsFlyer会将其记录为一次新增非自然激活。
> 3. 再以另外一种场景为例，假设您在Meta ads上投放了再营销广告，一部分从未安装过应用的用户与该广告互动后激活了应用。AppsFlyer不会将这些用户记录为再归因，而是将其视为来自拉新广告的用户。

<div data-zendesk-anchors="retargeting-conversion=%E5%86%8D%E8%90%A5%E9%94%80%E8%BD%AC%E5%8C%96 h_01EHQ74JS84509GT6M93SZA4HX=%E5%86%8D%E8%90%A5%E9%94%80%E8%BD%AC%E5%8C%96 reattribution-with-srns=srn%E5%B8%A6%E6%9D%A5%E7%9A%84%E5%86%8D%E5%BD%92%E5%9B%A0 reattribution-with-regular-ad-networks=%E5%B8%B8%E8%A7%84%E5%B9%BF%E5%91%8A%E5%B9%B3%E5%8F%B0%E5%B8%A6%E6%9D%A5%E7%9A%84%E5%86%8D%E5%BD%92%E5%9B%A0 attribution-link=%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5 conversion-data-payload=%E8%BD%AC%E5%8C%96%E6%95%B0%E6%8D%AEpayload reattribution-with-deferred-deep-linking=%E5%BB%B6%E8%BF%9F%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5%E5%B8%A6%E6%9D%A5%E7%9A%84%E5%86%8D%E5%BD%92%E5%9B%A0 conversion-data-for-deferred-deep-linking-with-facebook=meta-ads%E4%B8%AD%E5%BB%B6%E8%BF%9F%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5%E7%9A%84%E8%BD%AC%E5%8C%96%E6%95%B0%E6%8D%AE uri-schemes=uri-scheme ios-universal-links-and-android-app-links=ios-universal-link%E5%92%8C%E5%AE%89%E5%8D%93app-link reengagement-with-srns=srn%E5%B8%A6%E6%9D%A5%E7%9A%84%E5%86%8D%E4%BA%92%E5%8A%A8 reengagement-with-regular-ad-networks=%E5%B8%B8%E8%A7%84%E5%B9%BF%E5%91%8A%E5%B9%B3%E5%8F%B0%E5%B8%A6%E6%9D%A5%E7%9A%84%E5%86%8D%E4%BA%92%E5%8A%A8 reengagement-with-deep-linking=%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5%E5%B8%A6%E6%9D%A5%E7%9A%84%E5%86%8D%E4%BA%92%E5%8A%A8 alternative-conversion-data-sources=%E8%BD%AC%E5%8C%96%E6%95%B0%E6%8D%AE%E7%9A%84%E5%85%B6%E4%BB%96%E6%9D%A5%E6%BA%90 examples-of-mixed-user-acquisition-and-reattribution=%E7%94%A8%E6%88%B7%E8%8E%B7%E5%8F%96%E4%B8%8E%E5%86%8D%E5%BD%92%E5%9B%A0%E6%B7%B7%E5%90%88%E5%9C%BA%E6%99%AF" />
