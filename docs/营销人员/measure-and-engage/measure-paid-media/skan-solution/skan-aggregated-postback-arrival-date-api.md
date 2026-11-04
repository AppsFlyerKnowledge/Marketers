---
title: SKAN回传接收日期汇总报告API
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2020-12-21T09:03:09Z'
  edited_at: '2026-10-14T10:14:19Z'
  id: 360016646557
  locale: zh-cn
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/zh-cn/articles/360016646557
---
> **概要：** 这些数据是按回传接收日期来汇总的。

<div id="skan-aggregated-postback-arrival-date-api" />

## SKAN回传接收日期汇总报告API

该API会按回传数据的接收日期，返回汇总的SKAN回传数据。

**请注意**：注意：回传接收日期与SKAN面板和报告中的激活日期不同。

<div id="using-skan-aggregated-performance-report-api" />

<Accordion title="SKAN回传接收日期汇总报告API">

SKAN回传接收日期汇总报告API

1. 获取API token。只有相关账户的管理员才能获取该token。
2. 将该API token发送给您的开发人员，用于认证头（Authentication Header）中。
3. 将下表所列的相关参数发送给您的开发人员，让其在调用API时输入这些参数。这些参数用于界定报告的重点内容、信息梳理方式以及报告覆盖的时间范围。

<div id="parameters" />

#### 参数

| 参数名称 | 说明 | 必须配置 |
| --- | --- | --- |
| `start_date` | 回传接收日期的范围是通过start\_date（开始日期）和end\_date（截止日期）来设置的。请注意：回传接收日期与SKAN面板和报告中的激活日期不同。<ul><li>YYYY-MM-DD</li><li>可以使用的最早日期：2020-11-01<br />示例：`2020-11-05`</li></ul> | 是 |
| `end_date` | <ul><li>YYYY-MM-DD</li><li>每次调用最多可查询的天数：60天</li><li>示例：`2020-11-12`</li></ul> | 是 |
| `ad_network_name` | 按媒体渠道筛选数据 | 否 |
| `geo` | 按ISO 3166的二位国家代码筛选数据。`US`比如 | 否 |
| `skad_redownload` |  | 否 |
| `skad_source_app_id` | 按流量侧应用ID（Source App ID）筛选数据 | 否 |
| `ad_network_campaign_id` | 按广告平台的广告系列ID筛选数据。<br /><br />**请注意**：注意：这不是SKAN上报的广告系列ID。 | 否 |
| `modeled_conversion_values` | <ul><li>仅V2及以上版本的API支持该参数</li><li>可用值为`true`或`false`</li><li>如果该参数的值为false，回传数据中显示的转化值以及报告结构中所有可用字段（见下文）的值都是实际接收到的值，不包含模型推算数据。</li><li>默认值为`false` 。</li></ul> | 否 |

</Accordion>

<div id="report-structure-and-example" />

<Accordion title="报告结构及示例">

该API会返回一个CSV格式的文件。

下表列出了可用的字段和指标。

如 <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRXgsWlkyvMS20HgZuOQnH1YC8QQcRhOMYIOxyj_fcgikfDfmW6wNAMHO6alPWVA1j_KZwtqowohqrK/pub?gid=0&single=true&output=csv">V1</Anchor> | <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRMFEELm8JCAQBBAIJqAc1eE5YdN0kOcSVkOPd_Ki2ngnX61wHL4sXypVouOhto8u-JCQmdIYY_5UG6/pub?gid=219191499&single=true&output=csv">V2</Anchor>

| 字段名称 | 字段属性（分组维度或统计结果） | API V1 token中是否可用 | API V2 token中是否可用 | API V2 token中是否可用（针对SKAN 4） | 是否可使用“仅显示模型推算数据”的筛选条件 |
| --- | --- | --- | --- | --- | --- |
| skad\_postback\_sequence\_index | 分组维度 | N | N | Y | Y |
| skad\_conversion\_value | 分组维度 | Y | Y | Y | Y |
| skad\_coarse\_conversion\_value | 分组维度 | N | N | Y | Y |
| skad\_ad\_network\_id<br /><br />部分SRN不会将其ID分享给AF。在这种情况下，该字段为空，并会显示ad\_network\_name（广告平台名称）。 | 分组维度 | Y | Y | Y | Y |
| ad\_network\_name<br /><br />目前该字段一般为空，但在SRN不发送skad\_ad\_network\_id时我们会填充这个字段。 | 分组维度 | Y | Y | Y | Y |
| skad\_source\_identifier | 分组维度 | N | N | Y | Y |
| skad\_campaign\_id | 分组维度 | Y | Y | Y | Y |
| ad\_network\_campaign\_id | 分组维度 | Y | Y | Y | Y |
| ad\_network\_campaign\_name | 分组维度 | Y | Y | Y | Y |
| ad\_network\_adset\_id | 分组维度 | N | Y | Y | Y |
| ad\_network\_adset\_name | 分组维度 | N | Y | Y | Y |
| ad\_network\_ad\_id | 分组维度 | N | Y | Y | N |
| ad\_network\_ad\_name | 分组维度 | N | Y | Y | N |
| ad\_network\_creative | 分组维度 | N | N | Y | N |
| ad\_network\_channel | 分组维度 | N | N | Y | N |
| skad\_version | 分组维度 | Y | Y | Y | N |
| skad\_redownload | 分组维度 | Y | Y | Y | N |
| skad\_source\_app\_id | 分组维度 | Y | Y | Y | N |
| skad\_source\_domain | 分组维度 | N | N | Y | Y |
| skad\_fidelity\_type | 分组维度 | N | Y | Y | N |
| geo | 分组维度 | Y | Y | Y | N |
| arrival\_date | 分组维度 | Y | Y | Y | Y |
| count | 统计结果 | Y | Y | Y | Y |

</Accordion>

<div id="specifications-and-limitations" />

<Accordion title="特点与局限性">

| 特点 | 说明 |
| --- | --- |
| 数据时效性 | 该报告<Anchor target="_blank" href="/marketers/zh/docs/about-data-freshness-and-timezone-support#eod">每天</Anchor>更新一次。<br /><br />数据可用性取决于<Anchor target="_blank" href="/marketers/zh/docs/about-data-freshness-and-timezone-support#skan">SKAN</Anchor>数据的更新频次。 |
| 日期范围 | <ul><li>可查询范围内最早的日期：2020年11月1日</li><li>最多可查询60天</li></ul> |
| 比率限制 | <ul><li>最多可返回20万行数据</li><li>每分钟最多可调用60次</li></ul> |
| SRN | Google Ads：Google Ads：回传接收日期是通过Google上报的末次点击时间推算得出的。 |
| 渠道权限 | 在广告主开放相关权限的情况下，数据分析平台可以使用该API。 |
| 代理访问权限 | 不可用 |
| 应用层级的指定时区 | 不支持，仅限UTC |
| 应用配置中的指定货币 | 不支持，仅限USD |
| 自然量数据 | 该API中不可用 |
| 非自然量数据 | 根据AppsFlyer接收到的SKAN回传计算 |
| 历史数据 | 转化数据（激活或再营销）的最早可查询日期：2020年11月1日 |
| 相关账户下的用户权限 | 账户管理员可以在面板中获取授权token。 |

</Accordion>

<div id="see-also" />

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/skan-aggregated-performance-report-api">SKAN汇总效果报告API（SKAN aggregated performance report API）</Anchor>

<div data-zendesk-anchors="skadnetwork-postback-arrival-date-aggregation-reporting-api=skan%E5%9B%9E%E4%BC%A0%E6%8E%A5%E6%94%B6%E6%97%A5%E6%9C%9F%E6%B1%87%E6%80%BB%E6%8A%A5%E5%91%8Aapi h_01HDNZKFEHWET0FPX9WN136MB2=skan%E5%9B%9E%E4%BC%A0%E6%8E%A5%E6%94%B6%E6%97%A5%E6%9C%9F%E6%B1%87%E6%80%BB%E6%8A%A5%E5%91%8Aapi h_01HDNZKFEH76Y06091QS6Y5K1Z=using-skan-aggregated-performance-report-api parameters=%E5%8F%82%E6%95%B0 h_01HDNZKFEHA6N6EE4RMG0HGABA=%E5%8F%82%E6%95%B0 h_01HDNZKFEHM2D7GS3RMSRCKZY7=report-structure-and-example h_01HDNZKFEJ5P3245V1R99DGAQW=specifications-and-limitations h_01HDNZP87CWGVJ3G1BDXAR1WN0=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />
