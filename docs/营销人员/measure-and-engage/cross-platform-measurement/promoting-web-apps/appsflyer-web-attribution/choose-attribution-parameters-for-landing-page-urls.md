---
title: 选择着陆页URL的归因参数
metadata:
  keywords:
    - Agencies
    - Web Attribution
    - Web Attribution SDK
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Web Attribution
    - Agencies
  created_at: '2026-02-04T16:46:08Z'
  edited_at: '2026-10-14T10:00:21Z'
  id: 43525434385809
  locale: zh-cn
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/zh-cn/articles/43525434385809
---
> **概览：** 在网站着陆页链接中添加完整、一致的URL参数，在确保网页端效果衡量准确归因的同时，获得最精细的广告系列数据。

## URL归因参数类别简介

AppsFlyer会读取着陆页URL（即用户点击的链接）中的广告系列参数，并据此将会话和事件归因到正确的**媒体渠道**、**广告系列**，以及**广告组**和**广告**等更细的层级（如有）。

您添加的参数会直接影响广告系列的衡量结果。换言之，即使使用相同的着陆页，添加的参数不同，也可能产生截然不同的衡量结果。

URL参数分为两类：PID和UTM。

* PID类包括AppsFlyer URL参数。
* UTM类包括标准UTM参数。

如需详细了解网页端效果衡量如何处理URL参数，请参阅<Anchor target="_blank" href="/marketers/zh/docs/about-traffic-source-resolution">流量来源识别简介</Anchor>。

### 支持的PID和UTM参数

网页端效果衡量支持以下参数。

| # | 参数 | 用途 | 参数类别 | 面板中是否可用 | 原始数据字段 |
| --- | --- | --- | --- | --- | --- |
| 1 | `pid` | 媒体渠道 | PID | 是 | `media_source` |
| 2 | `c` | 广告系列名称 | PID | 是 | `campaign_name` |
| 3 | `af_c_id` | 广告系列ID | PID | 是 | `campaign_id` |
| 4 | `af_adset` | 广告组名称 | PID | 是 | `adset_name` |
| 5 | `af_adset_id` | Ad set ID（广告组ID） | PID | 是 | `adset_id` |
| 6 | `af_ad` | Ad name（广告名称） | PID | 是 | `ad_name` |
| 7 | `af_ad_id` | 广告ID | PID | 是 | `ad_id` |
| 8 | `utm_source` | 媒体渠道 | UTM | 是 | `media_source` |
| 9 | `utm_medium` | 媒体类型 | UTM | 否 | `media_type` |
| 10 | `utm_campaign` | 广告系列名称 | UTM | 是 | `campaign_name` |

## 选择合适的归因参数

AppsFlyer会按照特定的优先级顺序，分别检查各报表字段（如媒体渠道或广告系列）对应的URL参数。因此，您可以在同一URL中同时使用**PID类参数**（AppsFlyer原生参数）和**UTM类参数**（标准营销参数），既满足AppsFlyer归因需求，又兼容Google Analytics等其他工具。

网页端效果衡量会分别按照各字段的优先级顺序检查参数。如果某个字段没有优先级较高的PID类参数，系统会自动回退至对应的UTM类参数，以确定该字段的正确值。

<div id="scenario-a-url-with-pid-class-only-appsflyer-reporting" />

<Accordion title="场景A：URL仅包含PID类参数（AppsFlyer报表）">

如果主要使用AppsFlyer报表，请选择PID类参数。

#### 示例

```http
www.website.com?pid=facebook_int&c={{campaign.name}}&af_c_id={{campaign.id}}
```

**结果：** AppsFlyer根据`pid`识别媒体渠道，并根据`c`识别广告系列。

</Accordion>

<div id="scenario-b-url-with-utm-class-only-fallback" />

<Accordion title="场景B：URL仅包含UTM类参数（回退）">

如果缺少`pid`，AppsFlyer会回退至UTM类参数。

#### 示例

```http
 www.website.com?utm_source=facebook&utm_medium=paidsocial&utm_campaign={{campaign.name}}
```

**结果：** AppsFlyer根据`utm_source`识别媒体渠道，并根据`utm_campaign`识别广告系列。

</Accordion>

<div id="scenario-c-url-with-both-pid-and-utm-classes" />

<Accordion title="场景C：URL同时包含PID和UTM类参数">

同一URL中可以包含不同类别的参数（如PID和UTM）。如果既要使用AppsFlyer归因，又要兼容Google Analytics等其他分析工具或内部衡量系统，可以采用这种方式。

AppsFlyer会分别处理媒体渠道和广告系列等归因字段。对于每个字段，系统会按照优先级顺序确定要记录的值。通常，对于同一字段，**PID类参数**的优先级高于**UTM类参数**。

#### 示例1：同一字段包含两类参数

```http
www.website.com?pid=facebook_ads&c=summer_sale&utm_source=facebook&utm_campaign=seasonal_promo
```

* **媒体渠道：** AppsFlyer同时识别到`pid`和`utm_source`。根据该字段的参数优先级，AppsFlyer会记录`facebook_ads`。
* **广告系列：** AppsFlyer同时识别到`c`和`utm_campaign`。根据该字段的参数优先级，AppsFlyer会记录`summer_sale`。
* **结果：** AppsFlyer采用优先级较高的PID类参数值，其他工具仍可读取UTM参数值。

#### 示例2：混合使用不同类别的参数

```http
www.website.com?utm_source=facebook&c=summer_sale
```

* **媒体渠道：** AppsFlyer识别到`utm_source`。由于没有对应的PID类参数（`pid`），AppsFlyer会记录UTM类参数中的`facebook`。
* **广告系列：** AppsFlyer识别到`c`。由于没有对应的UTM类参数（`utm_campaign`），AppsFlyer会记录PID类参数中的`summer_sale`。
* **结果：** 由于系统会分别识别各字段的值，AppsFlyer可以结合两类参数的值，成功完成事件归因。

</Accordion>

## 其他最佳实践

<div id="keep-parameter-values-in-a-consistent-case" />

<Accordion title="统一参数值的大小写格式">

参数值**区分大小写**。例如，系统会将`utm_source=channel1`和`utm_source=CHANNEL1`视为**不同的媒体渠道**。

最佳实践：制定统一的大小写规则（通常使用小写），并应用于所有URL。

</Accordion>

<div id="use-question-marks-only-once" />

<Accordion title="URL中只使用一个问号">

规则：

* URL中的查询参数前只能使用**一个**问号（`?`）。
* 不要在URL中添加其他问号。

正确：

* `www.website.com?parameters`

错误：

* `www.website.com??parameters`
* `www.website.com?parameter1?parameter2`

</Accordion>

<div id="don-t-use-anchor-signs" />

<Accordion title="不要使用锚点符号（#）">

不要在URL中使用锚点符号（`#`）。

原因：`#`之后的参数可能无法加载，网页端SDK也可能无法记录这些参数。

</Accordion>

<div data-zendesk-anchors="about-website-attribution-urls=url%E5%BD%92%E5%9B%A0%E5%8F%82%E6%95%B0%E7%B1%BB%E5%88%AB%E7%AE%80%E4%BB%8B h_01KGMRXNWGXQ3CH5XGSREV6Z3R=url%E5%BD%92%E5%9B%A0%E5%8F%82%E6%95%B0%E7%B1%BB%E5%88%AB%E7%AE%80%E4%BB%8B supported-pid-and-utm-parameters=%E6%94%AF%E6%8C%81%E7%9A%84pid%E5%92%8Cutm%E5%8F%82%E6%95%B0 h_01KGMRXNWG88REW1CVJ4XMYFHQ=%E6%94%AF%E6%8C%81%E7%9A%84pid%E5%92%8Cutm%E5%8F%82%E6%95%B0 choose-the-right-attribution-parameters=%E9%80%89%E6%8B%A9%E5%90%88%E9%80%82%E7%9A%84%E5%BD%92%E5%9B%A0%E5%8F%82%E6%95%B0 h_01KGMRXNWGP1SFBWE3KG6VRZ9V=%E9%80%89%E6%8B%A9%E5%90%88%E9%80%82%E7%9A%84%E5%BD%92%E5%9B%A0%E5%8F%82%E6%95%B0 h_01KGMRXNWGT9MS799QH9EP29XR=scenario-a-url-with-pid-class-only-appsflyer-reporting example=%E7%A4%BA%E4%BE%8B h_01KGMS1RMN3F1D0Q7HDZMGG19E=%E7%A4%BA%E4%BE%8B h_01KGMRXNWG0T3YCK0RPKX4B3BT=scenario-b-url-with-utm-class-only-fallback example::4f5c28b5=%E7%A4%BA%E4%BE%8B-1 h_01KGMS215ARDSY6NFQ8VEF6C2Y=%E7%A4%BA%E4%BE%8B-1 h_01KGMRXNWGZH2ZBP9XR8C8TNFN=scenario-c-url-with-both-pid-and-utm-classes example-1-overlapping-parameters=%E7%A4%BA%E4%BE%8B1%E5%90%8C%E4%B8%80%E5%AD%97%E6%AE%B5%E5%8C%85%E5%90%AB%E4%B8%A4%E7%B1%BB%E5%8F%82%E6%95%B0 h_01KGMS10B1QCRJ5N28FBNEEKR2=%E7%A4%BA%E4%BE%8B1%E5%90%8C%E4%B8%80%E5%AD%97%E6%AE%B5%E5%8C%85%E5%90%AB%E4%B8%A4%E7%B1%BB%E5%8F%82%E6%95%B0 example-2-mixed-parameter-classes=%E7%A4%BA%E4%BE%8B2%E6%B7%B7%E5%90%88%E4%BD%BF%E7%94%A8%E4%B8%8D%E5%90%8C%E7%B1%BB%E5%88%AB%E7%9A%84%E5%8F%82%E6%95%B0 h_01KGMS17B500RPGHSKJ1AJSYH8=%E7%A4%BA%E4%BE%8B2%E6%B7%B7%E5%90%88%E4%BD%BF%E7%94%A8%E4%B8%8D%E5%90%8C%E7%B1%BB%E5%88%AB%E7%9A%84%E5%8F%82%E6%95%B0 other-best-practices=%E5%85%B6%E4%BB%96%E6%9C%80%E4%BD%B3%E5%AE%9E%E8%B7%B5 h_01KGMRXNWGVJY55M83FVMKBP1X=%E5%85%B6%E4%BB%96%E6%9C%80%E4%BD%B3%E5%AE%9E%E8%B7%B5 h_01KGMRXNWG9S03GGBDXPN34DDM=keep-parameter-values-in-a-consistent-case h_01KGMRXNWGEF9D0ZH5M81RP0PH=use-question-marks-only-once don%E2%80%99t-use-anchor-signs-=don-t-use-anchor-signs h_01KGMRXNWGX6HA0R9X3VC2WFXV=don-t-use-anchor-signs" />
