---
title: Pull API汇总数据
metadata:
  keywords:
    - Performance
    - raw data
    - Pull API
    - Reports
    - API
    - Parameters
    - API Policy
    - Advertisers
    - facebook rawdata
    - facebook raw data
    - Developers
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Raw Reports
  created_at: '2013-04-24T15:08:25Z'
  edited_at: '2026-10-14T10:15:01Z'
  id: 207034346
  locale: zh-cn
  section: Data delivery tools
  section_id: 6550995484561
  url: https://support.appsflyer.com/hc/zh-cn/articles/207034346
---
> **概要：** 概要：本文重点讲解了如何使用Pull API来拉取CSV格式的AppsFlyer汇总报告。

[![PullAPIAverage_us-en.png](https://files.readme.io/fb9be34d49394086b37e71d2553d6f926829928a3e1f6cd2ec3e95943ecaa503-360008811078.png)](https://files.readme.io/fb9be34d49394086b37e71d2553d6f926829928a3e1f6cd2ec3e95943ecaa503-360008811078.png)

<div id="looking-for-pull-api-raw-data" />

> 👍 **需要Pull API原始数据？**
>
> 请参考<Anchor target="_blank" href="/marketers/zh/docs/pull-api-raw-data">此文档</Anchor>。

<div id="pull-api-aggregate-data" />

## Pull API汇总数据

* Pull API能够帮助您拉取到CSV格式的用户获取（UA）和再营销汇总数据报告。
* <Anchor target="_blank" href="/marketers/zh/docs/about-data-freshness-and-timezone-support#data-freshness-rates-and-timezone-support">数据更新频次</Anchor>与数据总览面板的导出数据页中对应报告的更新频次一致。请注意成本更新会有数小时延迟，具体取决于提供成本数据的渠道。
* 可用的筛选条件包括：
* Pull API的其他功能包括：
  * 添加归因触点类型
  * 选择时区

<div id="aggregate-performance-reports-available-via-pull-api" />

#### 可通过Pull API拉取的汇总效果报告

<table><tbody><tr><th>类别</th><th> UA（用户获取）</th><th>再营销\*</th></tr><tr><td>分渠道报告</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><p>分渠道每日报告</p></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><p>每日更新</p></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><p>国家/地区</p></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><p>按日期和地域汇总的报告</p></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td colspan="3"></td></tr></tbody></table>

<div id="using-pull-api-aggregate-data" />

<Accordion title="使用Pull API拉取汇总数据">

**Pull API汇总数据的拉取方式：**

1. ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)获取API token。只有相关账户的管理员才能获取该token。
2. 将该API token发送给您的开发人员，用于认证头（Authentication Header）中。
3. 将下表所列的相关[参数](/docs/pull-api-aggregate-data#parameters)发送给您的开发人员，让其在调用API时输入这些参数。这些参数用于界定报告的重点内容、信息梳理方式以及报告覆盖的时间范围。
4. 让您的开发人员按照开发者资源中心的<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-11">Pull API汇总数据指南</Anchor>进行操作。

</Accordion>

<div id="parameters" />

<Accordion title="参数">

| 参数 | 说明 |
| --- | --- |
| app\_id | 应用ID |
| from | <ul><li>日期范围包含一个`from`和`to`参数，</li><li>格式：</li><li>比如2010-01-01</li></ul> |
| to | 表示截至日期，与`from`相对 |
| media\_source | 用于按具体的媒体渠道筛选结果。<ul><li>示例：`media_source=facebook`</li></ul> |
| attribution\_touch\_type | 请根据示例来设置该参数，从而拉取[浏览型归因](/docs/pull-api-aggregate-data)（VTA）指标。<br /><br />例如： `attribution_touch_type=impression`<br /><br />点击、展示、成本等部分VTA指标没有对应的值，因此在报告中显示为N/A。 |
| currency | 收入和成本的货币币种。<br /><br />汇总Pull API报告按应用层级的指定货币显示相关值。 |
| reattr | 用于拉取再营销转化数据。<ul><li>【默认】如果该参数为false，就会拉取到用户获取（UA）的投放数据。</li><li>如果该参数的值为true，就会拉取到再营销转化数据。</li><li>**示例**：`reattr=true`</li></ul> |
| timezone | 【默认】数据以UTC时间显示。<ul><li>URI模板中的时区参数以应用层级的指定时区填充。</li><li>【默认】如果不发送该参数，报告会按UTC时间显示数据。</li></ul>选择时区时的注意事项<ul><li>Joda-Time时区格式会自动根据夏令时进行调整。</li><li>时区设置完成后产生的数据会根据指定时区来显示，但在设置时区前产生的数据仍以UTC时间显示。</li></ul> |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="特点与局限性">

| 特点 | 注意事项 |
| --- | --- |
| 规定的API密钥类型 | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)<Anchor target="_blank" href="/marketers/zh/docs/managing-appsflyer-tokens">V2.0 token</Anchor> |
| 渠道权限 | N |
| 代理访问权限 | Y |
| 代理数据透明化 | Y |
| 应用配置中的指定货币 | Y |
| 应用层级指定时区 | Y |
| 成本 | 成本数据仅限UA广告；再营销广告或无转化广告（未带来任何激活的广告）是没有成本数据的。 |
| 数据时效性 | <Anchor target="_blank" href="/marketers/zh/docs/about-data-freshness-and-timezone-support#continuous-aka-realtime">持续滚动</Anchor> |
| 历史数据 | 5年 |
| 非自然量数据 | Y |
| 自然量数据 | Y |
| 频次限制 | <Anchor target="_blank" href="/marketers/zh/docs/report-generation-quotas-rate-limitations">局限性</Anchor> |
| 大小限制 | <ul><li>调用API最多可拉取20万条数据。<ul><li>如果报告中的数据条数正好是20万条，基本可以判定数据有缺失。</li><li>出现这种情况时，请进行多次调用，每次在from/to时间范围中指定某一天的具体时间。</li></ul></li></ul> |
| 广告系列名称变更 | Pull API报告不支持广告系列名称变更 |

</Accordion>

<div id="see-also" />

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/aggregated-and-analytics-reporting-overview">汇总报告说明及示例</Anchor>
> * <Anchor target="_blank" href="/marketers/zh/docs/aggregated-and-analytics-reporting-overview">如何选择合适的数据传输工具来获取汇总数据</Anchor>

<div data-zendesk-anchors="h_01HE0YP82966QHRAEW979ABCTP=%E9%9C%80%E8%A6%81pull-api%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE pull-api-aggregate-data=pull-api%E6%B1%87%E6%80%BB%E6%95%B0%E6%8D%AE h_01HE0YP829WD5TDFHTPYAV30QN=pull-api%E6%B1%87%E6%80%BB%E6%95%B0%E6%8D%AE aggregate-performance-reports-available-via-pull-api=%E5%8F%AF%E9%80%9A%E8%BF%87pull-api%E6%8B%89%E5%8F%96%E7%9A%84%E6%B1%87%E6%80%BB%E6%95%88%E6%9E%9C%E6%8A%A5%E5%91%8A h_01HE0YP829EQ7N6CST352X917H=%E5%8F%AF%E9%80%9A%E8%BF%87pull-api%E6%8B%89%E5%8F%96%E7%9A%84%E6%B1%87%E6%80%BB%E6%95%88%E6%9E%9C%E6%8A%A5%E5%91%8A h_01HE0YP82954F1ACVR2K4AFD5W=using-pull-api-aggregate-data h_01HE0YP8292131Q2561A4E1GYZ=parameters h_01HE0YP829ZPJAPHPDR9H4HMRT=traits-and-limitations h_01HE0Y2KTXS06WHN57MQ91AD09=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />
