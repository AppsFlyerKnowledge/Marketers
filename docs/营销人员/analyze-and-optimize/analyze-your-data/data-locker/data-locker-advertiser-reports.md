---
title: Data Locker中广告主可用的报告
metadata:
  keywords:
    - Advertisers
    - Premium Feature
    - Marketers
    - Data Locker
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Data Locker
  created_at: '2021-11-11T09:48:51Z'
  edited_at: '2026-10-14T10:15:13Z'
  id: 4410643856657
  locale: zh-cn
  section: Data Locker
  section_id: 6550945728657
  url: https://support.appsflyer.com/hc/zh-cn/articles/4410643856657
---
> **概要：** 广告主可以通过Data Locker获取各种汇总和原始数据报告。

## 广告主可通过Data Locker获取的报告

<table><colgroup><col/><col/><col/></colgroup><thead><tr><th>数据类型</th><th>报告分组</th><th>需要购买Data Locker</th></tr></thead><tbody><tr><td>原始数据</td><td>用户链路——原始数据</td><td>是（2）</td></tr><tr><td>原始数据</td><td>Protect360</td><td>是</td></tr><tr><td>原始数据</td><td>基于用户的归因（PBA） </td><td>否 </td></tr><tr><td>原始数据</td><td>增量分析</td><td>否 </td></tr><tr><td>原始数据</td><td>SKAN</td><td>否</td></tr><tr><td>原始数据</td><td>收入</td><td><p>购买了Data Locker套餐的广告主可查看次日最终版的广告收入报告。</p><p>购买了ROI360高阶套餐的广告主可查看所有其他报告。</p></td></tr><tr><td>原始数据</td><td>CTV、PC和主机端应用</td><td>是</td></tr><tr><td>汇总数据</td><td>群组分析</td><td>否</td></tr><tr><td>高级汇总数据</td><td>群组分析</td><td>否</td></tr><tr><td>汇总数据</td><td>素材优化</td><td><p>否</p><p>需购买素材优化高阶付费套餐。</p></td></tr><tr><td>汇总数据</td><td>SSOT</td><td>否</td></tr><tr><td colspan="3"><p>（1）没有Data Locker套餐的广告主必须提供其<a href="./data-locker-for-marketers#storage-options" target="_blank">自有的存储空间</a>，才能获取相关报告。</p><p>（2）跨平台的广告交互除外。</p><p>（3）购买了Data Locker套餐或数据分析API产品套件的广告主可获取相关数据。</p></td></tr></tbody></table>

<div id="data-freshness-explanations" />

<Accordion title="数据时效性说明">

下表解释了本文中提到的各类数据时效性。

| 时效 | 说明 |
| --- | --- |
| 1-3小时 | <ul><li>在此期间的报告可用性分布情况：<ul><li>95%的报告会在事件发生后的1小时内写入存储桶，可供使用。</li><li>99%的报告会在事件发生后的3小时内写入存储桶，可供使用。</li></ul></li></ul> |
| 每日更新-卸载 | <ul><li>卸载数据每天处理一次。</li><li>通常在UTC时间10:00-12:00之前可用。</li><li>通常写入h=2文件夹。也就是说h=2文件夹中包含前一天上报的卸载，但相关数据可能会被写入更后期的文件夹中，因此您在配置导入流程时须确保读取“uninstall”下所有文件夹的数据，即从h=1到h=24，以及h=late文件夹。举例来说，对于周一产生的数据，对应的报告会写入周二的h=2文件夹中。这些数据会在周二的UTC时间10:00之后可用。</li></ul> |
| 每日更新，次日可用 | 广告收入数据次日可用。举例来说，对于周一产生的数据，对应的报告会在周二UTC时间20:00之后写入周一的h=23文件夹中，可供使用。详情请见<Anchor target="_blank" href="/marketers/zh/docs/roi360-guide-ad-revenue-attribution#data-freshness">广告收入数据时效性</Anchor>。 |

</Accordion>

## 原始数据报告

<div id="user-journey" />

<Accordion title="用户链路">

如需了解各类用户链路报告的具体内容，请参阅<Anchor target="_blank" href="/marketers/zh/docs/raw-data-reporting-overview">用户链路报告</Anchor>说明文档。

| 类别 | 报告类型（主题） | 数据时效性 | 自然/非自然 | 仅限Data Locker |
| --- | --- | --- | --- | --- |
| 用户获取 | 点击 | 1-3小时 | 不适用 | ✓ |
| 再营销 | 点击 | 1-3小时 | 不适用 | ✓ |
| 用户获取 | 展示 | 1-3小时 | 不适用 | ✓ |
| 再营销 | 展示 | 1-3小时 | 不适用 | ✓ |
| 用户获取 | 激活假量 | 1-3小时 | 两者皆有 |  |
| 用户获取 | 应用内事件 | 1-3小时 | 两者皆有 |  |
| 用户获取 | 记录到的变现收入 | 每日更新，次日可用 | 非自然量 |  |
| 用户获取 | 自然广告收入 | 每日更新，次日可用 | 自然量 |  |
| 再营销 | 再营销变现收入 | 每日更新，次日可用 | 非自然量 |  |
| 再营销 | 转化 | 1-3小时 | 非自然量 |  |
| 再营销 | 应用内事件 | 1-3小时 | 非自然量 |  |
| 再营销 | 应用打开（Sessions） | 1-3小时 | 两者皆有 | ✓ |
| 用户获取 | 应用打开（Sessions） | 1-3小时 | 两者皆有 | ✓ |
| 用户获取 | 卸载 | 每日更新-卸载 | 非自然量 |  |
| 用户获取 | 自然卸载 | 每日更新-卸载 | 自然量 |  |
| 重装激活 | 重装激活 | 1-3小时 | 非自然量 |  |
| 重装激活 | 自然重装 | 1-3小时 | 自然量 |  |
| 用户获取 | 跨平台广告交互 | 每小时更新一次 | 两者皆有 | ✓ |

</Accordion>

<div id="protect360" />

<Accordion title="Protect360">

详情请见<Anchor target="_blank" href="/marketers/zh/docs/protect360-raw-data-reports">Protect360报告</Anchor>说明。

| 报告类型（主题） | 数据时效性 |
| --- | --- |
| 已拦截的激活 | 1-3小时 |
| 已拦截的应用内事件 | 1-3小时 |
| 已拦截的点击 | 1-3小时 |
| 归因后判定的激活假量 | 每日更新<br /><br />对于归因后判定的激活假量，各天的报告中包含前一天上报的数据。举例来说，周一产生的数据会出现在周二的报告中。 |

</Accordion>

<div id="peoplebased-attribution" />

<Accordion title="基于用户的归因（PBA）">

**数据时效性**

PBA数据每日更新 ，并在前一天结束后的10-12小时后可用（UTC时间）。举例来说，周一接收到的数据会在当天结束后进行处理，并在UTC时间周二12:00点之前写入周一的h=23文件夹中。

**注意事项**

* AppsFlyer在提供相关账户下所有PBA品牌套件的数据时，总是忽略筛选条件中的应用选项。
* 无法按应用区分数据。

| 报告类型（主题） |
| --- |
| <Anchor target="_blank" href="/marketers/zh/docs/pba-raw-data-reports#website-visits-and-website-events">网页访问量</Anchor> |
| <Anchor target="_blank" href="/marketers/zh/docs/pba-raw-data-reports#website-visits-and-website-events">网页事件</Anchor> |
| <Anchor target="_blank" href="/marketers/zh/docs/pba-raw-data-reports#websiteassisted-installs::7e12586d">网页助攻激活</Anchor> |
| <Anchor target="_blank" href="/marketers/zh/docs/pba-raw-data-reports#conversion-paths">转化路径</Anchor> |

</Accordion>

<div id="incrementality" />

<Accordion title="增量分析">

详情请见<Anchor target="_blank" href="/marketers/zh/docs/incrementality-for-remarketing-overview#available-reports">增量分析报告</Anchor>说明。

</Accordion>

<div id="skan" />

<Accordion title="SKAN">

详情请见<Anchor target="_blank" href="/marketers/zh/docs/skan-raw-data-reports">SKAN原始数据报告</Anchor>说明。

**数据时效性**

* 数据最早可用时间：AppsFlyer通过回传或API接收到相关数据后的第二天
* 数据存储位置：以AppsFlyer接收到相关数据的日期为准，写入该日期文件夹下的h=23文件夹。举例来说，举例来说，假设AF在周一接收到回传，并在当天结束后处理相关数据。处理完毕后，会在UTC时间的周二12:00之前将数据写入周一的h=23文件夹下。

| 报告类型（主题） |
| --- |
| 数据回传 |
| 回传备份（由iOS直接发送到AppsFlyer）。 |
| 激活假量 |
| 重新下载（Redownloads） |
| 应用内事件 |
| SRN广告维度 |

</Accordion>

<div id="ad-revenue" />

<Accordion title="收入">

详情请见<Anchor target="_blank" href="/marketers/zh/docs/revenue-etl-reports">Data Locker中的Revenue ETL报告</Anchor>。

详情请见<Anchor target="_blank" href="/marketers/zh/docs/roi360-guide-ad-revenue-attribution#ad-revenue-raw-data">广告收入原始数据</Anchor>

</Accordion>

<div id="ctv" />

<Accordion title="CTV、PC和主机端数据">

详情请见<Anchor target="_blank" href="/marketers/zh/docs/ctv-pc-and-console-data-via-data-locker">通过Data Locker拉取CTV、PC和主机平台数据</Anchor>

</Accordion>

## 高级原始数据报告（测试版）

高级报告引入了一代新的原始数据报告，旨在提供结构化、经过验证的和**AI准备好的数据集**。它们能够使用仅三个报告来摄取和分析**整个用户旅程，从第一次接触到转化和安装后的活动**。  
这些报告采用**类型化字段**、**精炼的字段命名**以及所有数据集的一致模式，确保清晰、准确和易于使用。统一结构简化了数据集之间的连接，**减少了ETL和下游处理的复杂性**，并提供支持高级分析的数据，使您能够根据需要灵活地处理数据。

<div id="advanced-reports" />

<Accordion title="原始互动报告">

原始互动报告整合了来自移动和连接电视（CTV）平台的用户获取和重定向活动的点击和展示数据。通过提供用户与广告互动的统一视图，该报告使得对漏斗顶部表现的深入分析成为可能，并帮助营销人员识别哪些创意和渠道驱动了有意义的互动。它还支持在互动层面的成本和覆盖优化，为评估营销曝光和流量质量提供了坚实的基础。

| 类别 | 报告类型（主题） | 数据时效性 | 仅限Data Locker |
| --- | --- | --- | --- |
| 用户获取和重新定向指南 | 点击和展示 | 1–24小时 | ✅ |

</Accordion>

<div id="conversion-report" />

<Accordion title="转化报告">

转化报告提供了所有应用安装的完整视图，包括来自移动和连接电视（CTV）平台的有机和非有机来源。通过集中转化数据，营销人员可以使用单一、简化的数据集进行全面的增长分析。使用此报告精确测量和优化营销表现。

使用此报告进行营销表现的精确测量。

| 类别 | 报告类型（主题） | 数据时效性 | 仅限Data Locker |
| --- | --- | --- | --- |
| 用户获取和重新定向指南 | 转化 | 1–24小时 | ✅ |

> 📘 **注意**
>
> 此报告不包括重新安装。

</Accordion>

<div id="h_01K9CROSSPLATFORMREPORT" />

<Accordion title="最终用户事件报告">

最终用户事件报告捕获详细的应用内事件数据，包括会话、购买、注册和关卡完成，涵盖移动和CTV平台。每个事件都附带完整的归因上下文，使得对用户行为、留存和生命周期价值的详细分析成为可能，同时确保完整的归因可追溯性。

| 类别 | 报告类型（主题） | 数据时效性 | 仅限Data Locker |
| --- | --- | --- | --- |
| 用户获取和重新定向指南 | 最终用户事件 | 1–24小时 | ✅ |

</Accordion>

## 汇总报告

<div id="cohort-analytics" />

<Accordion title="群组分析">

**数据时效性**

报告一般会在UTC时间12:00之前呈现在前一天的文件夹中。举例来说，如果相关数据在UTC时间周二12:00之前处理完毕，那么这些数据会被写入周一的文件夹下。

| 报告类型（主题） |
| --- |
| <Anchor target="_blank" href="/marketers/zh/docs/cohort-analytics-via-data-locker">群组 - 统一</Anchor> |
| <Anchor target="_blank" href="/marketers/zh/docs/cohort-analytics-via-data-locker">群组 - 用户获取</Anchor> |
| <Anchor target="_blank" href="/marketers/zh/docs/cohort-analytics-via-data-locker">群组 - 再营销</Anchor> |

</Accordion>

<div id="advanced-aggregated-reports" />

<Accordion title="高级汇总报告">

Data Locker中的高级汇总报告具有最高的时效性和准确性，可呈现颗粒度最细的数据，且对数据量没有限制。<Anchor target="_blank" href="/marketers/zh/docs/advanced-aggregated-reports-in-data-locker">详情请见此处说明。</Anchor>

</Accordion>

<div id="creative-optimization-etl" />

<Accordion title="素材优化ETL">

素材优化ETL（Creative Optimization ETL）报告能让您的数据分析专员获得所有必要信息，帮助其完成素材效果分析。该工具提供素材资产层级的完整数据，包括所有投放KPI、浅层及深层漏斗KPI、归因数据以及素材资产数据。<Anchor target="_blank" href="/marketers/zh/docs/creative-optimization-etl-reporting">详情请见此处说明。</Anchor>

</Accordion>

<div data-zendesk-anchors="reports-available-via-data-locker-for-advertisers=%E5%B9%BF%E5%91%8A%E4%B8%BB%E5%8F%AF%E9%80%9A%E8%BF%87data-locker%E8%8E%B7%E5%8F%96%E7%9A%84%E6%8A%A5%E5%91%8A 01H7WFZN6P1S49NYX8Q0W55P0B=%E5%B9%BF%E5%91%8A%E4%B8%BB%E5%8F%AF%E9%80%9A%E8%BF%87data-locker%E8%8E%B7%E5%8F%96%E7%9A%84%E6%8A%A5%E5%91%8A 01H7WFZN6PQWASTMXM9V72QZER=data-freshness-explanations raw-data-reports=%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%91%8A 01H7WFZN6P94YW1V79NT3HV5G4=%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%91%8A 01H7WFZN6PD75S557PDB5PSFFR=user-journey 01H7WFZN6QY2GV69N464EE196M=protect360 01H7WFZN6QW72FDBTMW2ZD7NZQ=peoplebased-attribution 01H7WFZN6QZ1B7BS6E59RVAF30=incrementality 01H7WFZN6Q0P99DCFA7MZQTVSX=skan 01H7WFZN6Q717F9Z1HG38JVBG3=ad-revenue 01H7WFZN6QMJGSAJR00MHYJB6Z=ctv Unified%20raw-data-reports=%E9%AB%98%E7%BA%A7%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%91%8A%E6%B5%8B%E8%AF%95%E7%89%88 h_01JX9T0PGE93JNJ3S4NDP0C2YW=%E9%AB%98%E7%BA%A7%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%91%8A%E6%B5%8B%E8%AF%95%E7%89%88 h_01K85EE8DA4E8D4SVHYV2PE42E=conversion-report h_01K85EE8DAWY52B7RJQ33MJ59B=%E6%B3%A8%E6%84%8F cross-platform-end-user-events-report=h_01K9CROSSPLATFORMREPORT aggregated-reports=%E6%B1%87%E6%80%BB%E6%8A%A5%E5%91%8A 01H7WFZN6Q90AT8N0VY5PKQ407=%E6%B1%87%E6%80%BB%E6%8A%A5%E5%91%8A 01H7WFZN6QNKXTRM7G6VFANSZ7=cohort-analytics h_01J0K1MEKEEAQBXF1YRZTG8V0X=advanced-aggregated-reports h_01J0TQ88VNSFZJ27T3E2P3MVE6=creative-optimization-etl" />
