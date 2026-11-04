---
title: SKAN汇总效果报告API
metadata:
  keywords:
    - Advertisers
    - SKAD
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2020-10-08T09:45:03Z'
  edited_at: '2026-10-14T10:07:05Z'
  id: 360014104157
  locale: zh-cn
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/zh-cn/articles/360014104157
---
> **概要：** 您可以使用该API获取数据点更充足、维度更丰富的SKAN效果数据。这些数据与SKAdNetwork面板中的数据类似，按激活日期或回传送达日期进行汇总。

<div id="skan-aggregated-performance-report-api" />

## SKAN汇总效果报告API（SKAN aggregated performance report API）

该API可返回由Apple SKAdNetwork上报的归因指标等数据点（真实数据），按激活日期或回传送达日期汇总。返回的报告结构与<Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">SKAN面板</Anchor>中的数据结构相同。

<div id="using-skan-aggregated-performance-report-api" />

<Accordion title="使用SKAN汇总效果报告API">

**如需使用SKAN汇总效果报告API，请按以下方式操作**：

1. 获取API token。只有相关账户的管理员才能获取该token。
2. 将该API token发送给您的开发人员，用于认证头（Authentication Header）中。
3. 将下表所列的相关参数发送给您的开发人员，让其在调用API时输入这些参数。这些参数用于界定报告的重点内容、信息梳理方式以及报告覆盖的时间范围。
4. 让您的开发人员按照开发者资源中心的<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/skan-agg-performance-report-api-get">SKAN汇总效果报告API指南</Anchor>进行操作。

<div id="parameters" />

#### 参数

| 参数名称 | 格式 | 必须配置 |
| --- | --- | --- |
| `date_type` | 日期范围中使用的日期类型取决于`start_date`（起始日期）和`end_date`（截止日期）<br /><br />可用值如下：<ul><li>【默认】`install`：AppsFlyer根据回传送达时间及衡量周期推算得出的激活日期。</li><li>`arrival`：回传送达时间。请注意：在自然激活指标中，该参数值显示为“N/A”。</li></ul>Google Ads数据：由于Google Ads数据上报机制的关系，Google Ads数据的激活日期和回传送达日期相同。 | 否 |
| `start_date` | 激活日期的范围通过start\_date（起始日期）和end\_date（截止日期）设置。请注意：激活日期区别于回传送达日期。<ul><li>激活日期范围的起始日期，格式为YYYY-MM-DD</li><li>可以使用的最早日期：2020-11-01<br />示例：`2020-11-05`</li></ul> | 是 |
| `end_date` | <ul><li>激活日期范围的截止日期，格式为YYYY-MM-DD</li><li>每次调用最多可查询的天数：90天</li><li>示例：`2020-11-12`</li></ul> | 是 |
| `view_type` | 您可以按以下视图类型筛选激活数据：<ul><li>`acquisition`：新增激活</li><li>`retargeting`：重新下载（Redownloads）</li><li>`unified`：新增激活和重新下载的总和。</li><li>【默认】`unified`</li><li>`view_type=unified`时返回成本、点击和展示指标</li></ul> | 否 |
| `modeled_conversion_values` | <ul><li>仅V2及以上版本提供该数据</li><li>可用值为`true`或`false`</li><li>如果该参数值为“true”，则AppsFlyer在填充解析指标字段时，会在回传数据中加入模型推算的数据。另请参考[可用字段列表](/docs/skan-aggregated-performance-report-api#report-structure-and-example)</li><li>如果该参数的值为`false`，则回传中仅根据原始的SKAN回传数据按原样呈现解析数据，不包含模型推算的数据。</li><li>默认值为`false` 。</li></ul> | 否 |

</Accordion>

<div id="report-structure-and-example" />

<Accordion title="报告结构及示例">

该API会返回一个CSV格式的文件。

* 下表列出了报告中可用的字段和指标。
* 部分指标（收入、广告交互、转化）取决于SKAN<Anchor target="_blank" href="/marketers/zh/docs/skan-conversion-studio">广告效果衡量的设置方式</Anchor>。
* 报告中仅包含用户在数据上报周期内完成的应用内事件，因此每个报告中应用内事件字段的数量和顺序可能有所不同。基于这个因素，请不要按照字段顺序来设计您的数据导入流程。
* 示例： [V1](https://docs.google.com/spreadsheets/d/e/2PACX-1vSmnyUITQjRxNp6-rz8Xzscu-Rr4Kn2DW1du2VppS-QrpyQSZ0GKQ_qZdWNdNoLuwJAmgh2O-bWiuU3/pub?gid=0&single=true&output=csv) | <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQogLd4w3xgrjQBmEiHLfcvz1e9dtWez_Rdg1OxV8bSRHRE-wxZJItfT6azLr4iZAgsW2Vxr_WVmEYo/pub?gid=0&single=true&output=csv">V2</Anchor>

<div id="report-fields" />

#### 报告字段

| 字段名称 | 维度或指标 | API V1 token中是否可用 | API V2 token中是否可用 | API V2 token中是否可用（针对SKAN 4） | 是否可使用“仅显示模型推算数据”的筛选条件 |
| --- | --- | --- | --- | --- | --- |
| Date<br /><br />根据选定的日期类型（date\_type）呈现数据 | 维度 | N | Y | Y | Y |
| Media Source (pid) | 维度 | Y | Y | Y | Y |
| Campaign (c) | 维度 | Y | Y | Y | Y |
| Campaign ID | 维度 | Y | Y | Y | Y |
| Site ID | 维度 | Y | Y | Y | N |
| Adset | 维度 | N | Y | Y | Y |
| 即广告组的ID | 维度 | N | Y | Y | Y |
| Ad | 维度 | N | Y | Y | N |
| 即相关广告的ID | 维度 | N | Y | Y | N |
| Country | 维度 | Y | Y | Y | N |
| AF Attribution Flag<br /><br />详情请见<Anchor target="_blank" href="/marketers/zh/docs/single-source-of-truth-ssot-guide-for-ios-attribution">SSOT指南</Anchor> | 维度 | N | Y | Y | Y |
| Postback sequence index | 维度 | N | N | Y | Y |
| Creative | 维度 | N | N | Y | N |
| 流量入口（Channel） | 维度 | N | N | Y | N |
| Impressions | 指标 | Y | Y | Y | Y |
| Clicks | 指标 | Y | Y | Y | Y |
| CTR | 指标 | Y | Y | Y | Y |
| Installs | 指标 | Y | Y | Y | Y |
| Click Through Installs（fidelity\_type = 1） | 指标 | Y | Y | Y | Y |
| View Through Installs<br /><br />(fidelity\_type = 0) | 指标 | Y | Y | Y | Y |
| Null Conversion Value Rate<br /><br />【2022年1月23日起可用】 | 指标 | N | Y | Y | Y |
| Conversion Rate | 指标 | Y | Y | Y | Y |
| Converted Users | 指标 | Y | Y | Y | Y |
| Converted Users/Installs | 指标 | Y | Y | Y | Y |
| Total Revenue | 收入指标 | Y | Y | Y | Y |
| Total Cost | 指标 | Y | Y | Y | Y |
| ROI | 收入指标 | Y | Y | Y | Y |
| ARPU | 收入指标 | Y | Y | Y | Y |
| Average eCPI | 指标 | Y | Y | Y | Y |
| `{af_skad_revenue}`（独立用户数） | 收入指标 | Y | Y | Y | Y |
| `{af_skad_revenue}`（事件数量） | 收入指标 | Y | Y | Y | Y |
| `{应用内事件名称}`（独立用户数） | 指标 | Y | Y | Y | Y |
| `{应用内事件名称}`（事件数量） | 指标 | Y | Y | Y | Y |

</Accordion>

<div id="specifications-and-limitations" />

<Accordion title="特点与局限性">

| 特点 | 说明 |
| --- | --- |
| 数据时效性 | 数据可用性取决于<Anchor target="_blank" href="/marketers/zh/docs/about-data-freshness-and-timezone-support#skan">SKAN</Anchor>数据的更新频次。 |
| 日期范围 | <ul><li>日期范围中最近的日期应设置为当天日期减3天（按UTC时间计算）。举例来说，假设当前日期为3月31日，则最近的日期应设置为3月28日。</li><li>可查询范围内最早的日期：2020年11月1日</li><li>最多可查询90天</li></ul> |
| 频次限制 | <ul><li>最多可返回25万行数据</li><li>每分钟最多可调用10次</li></ul> |
| SRN | <ul><li>Meta ads数据可用。</li><li>Google Ads：由于Google点击时间机制的影响，激活后的45天内都可能会记录到激活。如果您每天都查询最近45天的Google数据，就可以全面覆盖对Google SKAN数据的需求。</li></ul> |
| 渠道权限 | 如果贵司是数据分析平台，请让相关广告主为您开放权限。 |
| 代理访问权限 | 不可用 |
| 应用层级的指定时区 | 不支持，仅限UTC |
| 应用配置中的指定货币 | 不支持，仅限USD |
| 自然量数据 | 计算方式：由SDK直接上报给AF的总体数据减去由SKAN回传上报的非自然量数据 |
| 非自然量数据 | 根据AppsFlyer接收到的SKAN回传计算 |
| 历史数据 | 转化数据（激活或再营销）的最早可查询日期：2020年11月1日 |
| 相关账户下的用户权限 | 账户管理员可以在面板中获取授权token。 |
| Total Cost | 如果常规归因（即常规数据总览）中粒度最细的SKAN投放数据（如具体广告、国家或子渠道ID等）行数超过5万行，则SKAN API不返回总成本指标。 |

</Accordion>

<div data-zendesk-anchors="skadnetwork-postback-arrival-date-aggregation-reporting-api=skan%E6%B1%87%E6%80%BB%E6%95%88%E6%9E%9C%E6%8A%A5%E5%91%8Aapiskan-aggregated-performance-report-api h_01HH9WHP1SDQ3TJPZ931R9KWKH=skan%E6%B1%87%E6%80%BB%E6%95%88%E6%9E%9C%E6%8A%A5%E5%91%8Aapiskan-aggregated-performance-report-api h_01HH9WHP1S7PWJHKAKHN434G7Y=using-skan-aggregated-performance-report-api parameters=%E5%8F%82%E6%95%B0 h_01HH9WHP1SZQZGSZ4WEPAAFNV7=%E5%8F%82%E6%95%B0 h_01HH9WHP1SYEHGJBBWSMS2XQP0=report-structure-and-example skadnetwork-aggregate-report-structure=%E6%8A%A5%E5%91%8A%E5%AD%97%E6%AE%B5 h_01HH9WHP1STYNJK3DRESDF23DG=%E6%8A%A5%E5%91%8A%E5%AD%97%E6%AE%B5 h_01HH9WHP1T4NEMW56XVYKM3KHM=specifications-and-limitations" />
