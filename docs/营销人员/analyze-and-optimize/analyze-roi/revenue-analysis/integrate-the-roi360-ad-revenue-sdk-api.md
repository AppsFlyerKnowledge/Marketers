---
title: ROI360中展示层级广告收入的SDK API对接指南
metadata:
  keywords:
    - ROI
    - ad revenue
    - Advertisers
    - Advertiser
    - Developer
    - Developers
    - ad revenue SDK
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2022-01-12T09:09:07Z'
  edited_at: '2026-10-14T10:13:03Z'
  id: 4416353506833
  locale: zh-cn
  section: Revenue analysis
  section_id: 6551069075089
  url: https://support.appsflyer.com/hc/zh-cn/articles/4416353506833
---
> **概要：** 广告主可使用AppsFlyer ad revenue SDK API获取广告平台上报的展示级别广告收入数据。

![mceclip1__1_.png](https://files.readme.io/202ded6950dfbf370bb48738876224936d28ecfae0c0aba09d1c49892b774cb5-31202279100177.png)

## 通过SDK API上报展示级别的广告收入数据

**广告收入的上报方式**

广告收入可通过以下两种方式上报到AppsFlyer：1）通过API上报汇总级别的数据，或2）通过SDK上报展示级别的数据。通过SDK上报展示级别数据时：

* 数据时效性更高，AppsFlyer可更快呈现数据
* 支持SKAN归因。
* 适用于已接入AppsFlyer SDK V6.15+的应用。如果您使用早前版本的SDK，则无法使用SDK API，但可以使用SDK connector（数据传输插件）。本文会在相关处提供开发人员专用的说明文档，供您参考。

**请注意：**

* 广告收入展示数据由AppsFlyer收集并处理，但不计入您的应用内事件套餐使用量。
* 详见<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad-revenue">支持Ad Revenue SDK API的SDK插件完整列表</Anchor>。

### 使用SDK API上报广告收入

**SDK的作用原理**

广告收入的SDK API用于向AppsFlyer SDK发送广告展示收入数据。AppsFlyer会收集并处理这些展示事件，并在本平台中生成广告收入事件`af_ad_revenue`，这些收入会归因到初始的UA渠道。

**数据呈现方式**

`af_ad_revenue`事件用于识别广告收入，适用于整个AppsFlyer平台，包括面板和其他各种数据传输工具。

**适配平台**

下列适配的聚合平台和变现平台可通过广告收入SDK API向AppsFlyer发送相关数据：

* <Anchor target="_blank" href="/marketers/zh/docs/ironsource-campaign-configuration#ad-revenue-tab">Unity LevelPlay聚合平台</Anchor>（前身为ironSource）
* <Anchor target="_blank" href="/marketers/zh/docs/applovin-max-ad-revenue-configuration">Applovin Max</Anchor>
* <Anchor target="_blank" href="/marketers/zh/docs/google-admob-ad-revenue-attribution-configuration">Google AdMob</Anchor>
* <Anchor target="_blank" href="/marketers/zh/docs/fyber-campaign-configuration">Fyber</Anchor>
* <Anchor target="_blank" href="/marketers/zh/docs/appodeal-campaign-configuration">Appodeal</Anchor>
* Admost
* Topon
* Topon Pte.
* Tradplus
* <Anchor target="_blank" href="/marketers/zh/docs/yandex-direct-campaign-configuration">Yandex</Anchor>
* <Anchor target="_blank" href="/marketers/zh/docs/chartboost-campaign-configuration">Chartboost</Anchor>
* customMediation：如果您使用的聚合平台不在此列表中，可以使用这个值作为聚合平台名称
* directMonetizationNetwork：如果相关应用与变现平台直接对接（即不通过聚合平台对接），请使用这个值作为聚合平台名称

**数据时效性**

**SDK API会在发生广告展示时向AppsFlyer平台发送相应的收入数据。 对于购买了ROI360高阶付费套餐的广告主，这些数据的时效性如下：**

* **在Data Locker展示级别的主题下，从1AM开始呈现数据，且每1小时更新一次；**
* **在AppsFlyer的活跃数据和群组报告中，从UTC时间5AM开始呈现数据，且每4小时更新一次。**

## AppsFlyer ad revenue SDK APII的部署方式

**请按以下方式部署AppsFlyer ad revenue SDK API**：

1. 从AppsFlyer面板进入相关渠道的对接页面，<Anchor target="_blank" href="/marketers/zh/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">启用SDK级别的广告收入对接</Anchor>。**请注意**：该操作需分应用单独完成。
2. 让您的开发人员按照<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad-revenue">相关说明</Anchor>部署AppsFlyer ad revenue SDK API。
3. 如需在SKAN面板中记录广告收入，请参照<Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-solution-guide#recording-ad-revenue">SKAN广告收入说明</Anchor>进行操作。

## 特点与局限性

| 特点 | 说明 |
| --- | --- |
| Admob | <ul><li>如需启用Admob的iLTV功能（Impression-level Lifetime Value Pingback，可实时发送广告展示的价值），请参照<Anchor target="_blank" href="https://support.google.com/admob/answer/11322405#getstarted">此文档</Anchor>中的说明进行操作。</li><li>在安卓和Unity中，Admob iLTV SDK使用<Anchor target="_blank" href="https://developers.google.com/android/reference/com/google/android/gms/ads/AdValue#public-long-getvaluemicros">微量单位</Anchor>（micro-units）上报展示收入。因此，为了确保AppsFlyer中以美元为单位的广告收入金额正确无误，请先将取自iLTV事件处理机制（handler）的金额除以1百万，然后再将结果发送到AppsFlyer。</li></ul> |
| 广告收入价值 | 该SDK API不处理收入价值超过10美元（或其他货币的等价金额）的展示事件。 |
| Channel | 流量入口维度（Channel）对于第三方商店中的应用不可用（Amazon除外）。 |

<div data-zendesk-anchors="impressionlevel-ad-revenue-reporting-by-sdk-API=%E9%80%9A%E8%BF%87sdk-api%E4%B8%8A%E6%8A%A5%E5%B1%95%E7%A4%BA%E7%BA%A7%E5%88%AB%E7%9A%84%E5%B9%BF%E5%91%8A%E6%94%B6%E5%85%A5%E6%95%B0%E6%8D%AE 01H8HHAQHK6CDK8X2Y6N4GANNC=%E9%80%9A%E8%BF%87sdk-api%E4%B8%8A%E6%8A%A5%E5%B1%95%E7%A4%BA%E7%BA%A7%E5%88%AB%E7%9A%84%E5%B9%BF%E5%91%8A%E6%94%B6%E5%85%A5%E6%95%B0%E6%8D%AE reporting-ad-revenue-using-the-sdk-API=%E4%BD%BF%E7%94%A8sdk-api%E4%B8%8A%E6%8A%A5%E5%B9%BF%E5%91%8A%E6%94%B6%E5%85%A5 01H8HHAQHKQ3H3R21Z1JYNJ2EE=%E4%BD%BF%E7%94%A8sdk-api%E4%B8%8A%E6%8A%A5%E5%B9%BF%E5%91%8A%E6%94%B6%E5%85%A5 implementing-generic-appsflyer-ad-revenue-sdk-API=appsflyer-ad-revenue-sdk-apii%E7%9A%84%E9%83%A8%E7%BD%B2%E6%96%B9%E5%BC%8F 01H8HHAQHKCXKPJJE8EDT1J9CR=appsflyer-ad-revenue-sdk-apii%E7%9A%84%E9%83%A8%E7%BD%B2%E6%96%B9%E5%BC%8F traits-and-limitations=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 01H8HHAQHMCSVQ2ZAT3G7XJKAN=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7" />
