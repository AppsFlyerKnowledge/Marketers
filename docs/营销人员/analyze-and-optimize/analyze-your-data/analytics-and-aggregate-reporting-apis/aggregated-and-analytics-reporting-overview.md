---
title: 数据汇总及分析功能简介
metadata:
  keywords:
    - Agencies
    - Ad Networks
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
    - Agencies
    - Ad Networks
  created_at: '2020-02-04T09:38:14Z'
  edited_at: '2026-10-14T10:07:40Z'
  id: 360005437257
  locale: zh-cn
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/zh-cn/articles/360005437257
---
> **概要：** 本文分别介绍并对比了用于归因数据汇总和分析的报告、工具和API。

## 投放效果数据的汇总和分析工具简介

AppsFlyer中的数据汇总和分析工具能为广告主提供各种指标，让其全面了解相关应用、广告和用户的表现。

不同的工具会以不同的方式呈现数据。比如数据总览面板用于查看LTV维度的投放指标，而群组面板则用于分析长期的用户互动情况。

本文介绍的工具适用于可从AF平台中导出的数据。下表列出了各种工具的特性对比，帮助您理解这些工具的主要功能和差异。

<div id="toolapi-comparison" />

<Accordion title="数据上报方式对比">

下表说明了用于获取汇总数据的各种数据上报方式和面板。

您可以[**下载CSV格式的表格**](https://docs.google.com/spreadsheets/d/e/2PACX-1vSICicxcvD0996RT59fTLDJvdGUKxqPqr47f5SMD8BmsbZtrWIoxRxJEo7tAXTBBmnIbiH097VtK6L9/pub?output=xlsx)**，其中更详细地说明了各种规格和限制，帮助您选取最合适的数据上报方式。**

可下载的CSV表格中包括以下额外说明字段：

* <Anchor target="_blank" href="/marketers/zh/docs/about-data-freshness-and-timezone-support">数据时效性</Anchor>（Data freshness）：在相关数据上报方式中，从事件发生到数据处理完毕所需要的时间。
* <Anchor target="_blank" href="/marketers/zh/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">LTV/活跃数据</Anchor>（LTV/activity）：用于说明相关数据是LTV维度还是活跃维度。
* <Anchor target="_blank" href="/marketers/zh/docs/retargeting-attribution-guide">再营销</Anchor>（Retargeting）：用于说明相关上报方式是否呈现再营销（即再互动和再归因）数据。
* <Anchor target="_blank" href="/marketers/zh/docs/measure-reinstalls#attributed-to-the-first-install">重装激活后的事件归因到初次激活</Anchor>（Re-install events attribution to first install）：用于说明重装激活后发生的事件是否可归因到初始激活。
* <Anchor target="_blank" href="/partners/zh/docs/about-agency-accounts#代理数据透明化">代理数据透明化</Anchor>（Agency transparency）：用于说明带来代理流量的原始媒体渠道对营销人员是否可见。
* <Anchor target="_blank" href="/marketers/zh/docs/about-data-freshness-and-timezone-support#date-and-timezone-principles">时区</Anchor>（Timezone）：用于说明相关上报方式呈现数据所用的时区（UTC或应用配置中设定的时区）。
* <Anchor target="_blank" href="/marketers/zh/docs/measure-reinstalls#unattributed-organic-inapps">未归因的事件</Anchor>（Unattributed events）：用于说明相关上报方式是否呈现重装激活后未归因的事件。
* <Anchor target="_blank" href="/marketers/zh/docs/campaign-name-changes?">广告系列名称变更</Anchor>（Campaign name changes）：用于说明是否可在不创建副本的情况下更改广告系列名称。

| 报告方式 | 说明 |
| --- | --- |
| 数据总览面板 | 在选定日期范围内完成激活、再互动或再归因的用户的生命周期价值（LTV）。 |
| <Anchor target="_blank" href="/marketers/zh/docs/master-api-user-acquisition-metrics-via-api">Master API</Anchor>  <br />（高阶付费功能） | 通过该API获取指定的LTV、活跃、群组、Protect360、和留存等维度的投放效果指标（CSV或JSON格式）。 |
| <Anchor target="_blank" href="/marketers/zh/docs/pull-api-aggregate-data">Pull API汇总报告</Anchor> | 完成激活、再互动或再归因的用户的生命周期价值（LTV），以CSV文件的形式呈现。UA和再营销数据是分开单独呈现的，不支持统一规格的数据。 |
| <Anchor target="_blank" href="/marketers/zh/docs/aggregated-data-export-page">导出数据页面——汇总报告</Anchor> | 完成激活、再互动或再归因的用户的生命周期价值（LTV），以CSV文件的形式呈现。UA和再营销数据是分开单独呈现的，不支持统一规格的数据。 |
| <Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">SKAN</Anchor>  <br /><Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">数据总览</Anchor> | 通过iOS SKAN回传上报的指标以及在最初的用户衡量窗口期内获得的其他数据。 |
| <Anchor target="_blank" href="/marketers/zh/docs/skan-aggregated-performance-report-api">SKAN</Anchor>  <br /><Anchor target="_blank" href="/marketers/zh/docs/skan-aggregated-performance-report-api">汇总数据API</Anchor> | 通过iOS SKAN回传上报的指标以及在最初的用户衡量窗口期内获得的其他数据。 |
| <Anchor target="_blank" href="/marketers/zh/docs/protect360-dashboard">Protect360面板</Anchor> | 与假量相关的指标和关键信息。  <br />LTV维度激活数据以及活跃维度的应用内事件数据。 |
| <Anchor target="_blank" href="/marketers/zh/docs/activity-dashboard">活跃数据面板</Anchor> | 选定日期范围内的应用使用情况、互动以及应用内事件指标。 |
| 事件面板 | 对于在选定日期范围内激活应用的用户，呈现不同媒体渠道的LTV维度应用内事件效果指标数据。 |
| 留存面板 | 独立用户在激活后每一天的互动（session）指标。 |
| <Anchor target="_blank" href="/marketers/zh/docs/cohort-and-retention-dashboard">群组面板</Anchor> | 激活后每一天的群组化LTV用户指标。 |
| <Anchor target="_blank" href="/marketers/zh/docs/cohort-api">群组报告API</Anchor>  <br />（高阶付费功能） | 激活后每一天的群组化LTV用户指标。 |
| <Anchor target="_blank" href="/marketers/zh/docs/cohort-analytics-via-data-locker">Cohort Data Locker</Anchor>  <br />（高阶付费功能） | 激活后每一天的群组化LTV用户指标。 |
| <Anchor target="_blank" href="/marketers/zh/docs/advanced-aggregated-reports-in-data-locker">高级汇总报告</Anchor>  <br />（高阶付费功能） | 版本化的汇总数据报告。LTV维度。 |
| <Anchor target="_blank" href="/marketers/zh/docs/custom-dashboards">自定义面板</Anchor> | 带有LTV用户获取指标的自定义面板。 |
| <Anchor target="_blank" href="/marketers/zh/docs/pivot-table-user-metrics">数据透视报告</Anchor>  <br />（高阶付费功能） | 指定的LTV、活跃、Protect360和留存等维度的投放效果指标，在面板或CSV文件中呈现。 |
| <Anchor target="_blank" href="/marketers/zh/docs/set-up-and-use-roi360-cost-etl-reports">Cost ETL</Anchor> | 分媒体渠道的投放成本数据，提供可用范围内最细的颗粒度。 |
| 使用情况报告 | 综合呈现AppsFlyer平台中所有按使用量计费的功能，这些功能的使用情况会影响计费周期内AppsFlyer所提供的服务。 |
| <Anchor target="_blank" href="/marketers/zh/docs/creative-optimization-guide">素材优化面板</Anchor> | 针对广告素材提供LTV维度的效果数据。也就是说，该面板中的指标与相关素材在选定时间段内产生的转化有关。 |

</Accordion>

<div id="cohort-flavors" />

<Accordion title="群组数据的传输方式">

AppsFlyer通过以下多种方式提供群组数据：<Anchor target="_blank" href="/marketers/zh/docs/cohort-and-retention-dashboard">群组面板</Anchor>、<Anchor target="_blank" href="/marketers/zh/docs/cohort-api">Cohort API</Anchor>和<Anchor target="_blank" href="/marketers/zh/docs/cohort-analytics-via-data-locker">写入Data Locker的群组分析数据。</Anchor>下表列出了各种形式之间的差异。

| 主要特点 | Data Locker中的群组分析报告 | Data Locker中的高级汇总报告 | 群组面板 | 群组报告API |
| --- | --- | --- | --- | --- |
| 多应用/单应用 | 多应用。按应用对数据分组，可在单个文件中呈现，或将各应用的数据分别呈现在不同的文件中。 | 多应用。按应用对数据分组，可在单个文件中呈现，或将各应用的数据分别呈现在不同的文件中。 | 多应用。可将多个应用的效果数据合并呈现，或按应用分组。 | 单应用 |
| 分组 | 所有广告层级和事件名称。约有20个分组维度。 | 所有广告层级和事件名称。约有20个分组维度。 | 4个分组维度 | 7个分组维度 |
| 可用指标 | 所有指标 | 所有指标 | 每种视图1个自选指标和3个固定指标 | 每次调用1个自选指标和3个固定指标 |
| 数据可用范围（群组天数） | 365 | 1095 | 180 | 180 |
| 数据导出限制 | 整个数据集可用 | 整个数据集可用 | 手动下载并设置 | 拉取频次和数据量有限制 |
| 自定义请求 | 否 | 否 | 是 | 是 |

群组数据不同传输方式之间的差异

</Accordion>

### 用户链路报告

本节介绍的报告可通过导出数据页或Pull API获取。

这些报告是<Anchor target="_blank" href="/marketers/zh/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">LTV维度</Anchor>的，因此

* 最早的数据上报日期是应用的首次归因日期。
* 数据上报日期范围与归因日期相关联，具体如下：
  * 用户获取和Protect360报告的激活日期
  * 再营销报告中的再归因或再互动日期

<div id="ua-ltv-aggregate-data-reports-containing-nonorganic-and-organic-users" />

<Accordion title="LTV维度的UA汇总数据报告包含自然量和非自然量数据。">

<table><thead><tr><th>报告名称</th><th>分组维度：</th></tr></thead><tbody><tr><td>合作伙伴（媒体渠道）</td><td>代理、媒体渠道、广告系列</td></tr><tr><td>分渠道每日报告</td><td>日期、代理、媒体渠道、广告系列</td></tr><tr><td>日常行为</td><td>日期、代理、媒体渠道、广告系列</td></tr><tr><td>国家/地区</td><td>国家、代理、媒体渠道、广告系列</td></tr><tr><td>国家/地区+每日汇总</td><td>日期、国家、代理、媒体渠道、广告系列</td></tr><tr><td>浏览型归因（VTA）的KPI</td><td><a href="./pull-api-aggregate-data" target="_blank">VTA报告可通过Pull API拉取</a></td></tr><tr><td colspan="2"> <strong>请注意</strong>：如果您选择了Meta ads作为<em>媒体渠道</em>，则报告中会增加以下字段：Adgroup ID、Adgroup name、Adset ID、Adset name</td></tr></tbody></table>

CSV文件中的日期字段格式为yyyy-mm-dd。当您在Excel中打开CSV文件时，日期字段将使用您计算机日期和时间格式设置。因此请确保在<Anchor target="_blank" href="https://support.office.com/en-us/article/format-a-date-the-way-you-want-8e10019e-d5d8-47a1-ba95-db95123d273e#ID0EAACAAA=Windows">Excel</Anchor>中选择合适的日期显示格式。

#### 汇总报告示例

[Excel格式的报告示例](https://docs.google.com/spreadsheets/d/e/2PACX-1vQmzRons779Dk5QWVoPsOF8E7yJLwNPB1IF87shZr6rcMJLjszlSNIbAMVcdeQLysr8Bc4QAby5QB4u/pub?output=xlsx)

#### UA汇总报告中的字段

<table><colgroup><col/><col/><col/><col/><col/><col/><col/></colgroup><thead><tr><th rowspan="2">字段</th><th rowspan="2">说明</th><th colspan="5"><strong>报告名称</strong></th></tr><tr><th><strong>分渠道报告</strong></th><th><strong>分渠道每日报告</strong></th><th><strong>每日更新</strong></th><th><strong>国家/地区</strong></th><th><strong>国家/地区+每日汇总</strong></th></tr></thead><tbody><tr><td>Country</td><td>激活发生的国家</td><td> </td><td> </td><td> </td><td>✓</td><td> ✓</td></tr><tr><td>Date</td><td>归因日期</td><td> </td><td>✓</td><td> </td><td> </td><td>✓</td></tr><tr><td>Agency/PMD (af_prt)</td><td>代理/渠道名称</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Media Source (pid)</td><td>带来用户的媒体渠道（pid=媒体渠道）</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Campaign</td><td><p>Campaign name（广告系列名称）</p><p>（c=广告系列名称）</p></td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Campaign ID</td><td>Meta广告系列ID </td><td>仅限Meta ads</td><td>仅限Meta ads</td><td>仅限Meta ads</td><td>仅限Meta ads</td><td>仅限Meta ads</td></tr><tr><td>Adgroup ID</td><td>Meta ad group ID或Ad ID</td><td>仅限Meta ads</td><td>仅限Meta ads</td><td>仅限Meta ads</td><td>仅限Meta ads</td><td>仅限Meta ads</td></tr><tr><td>Adgroup Name</td><td>Meta ad group（即单个广告）</td><td>仅限Meta ads</td><td>仅限Meta ads</td><td>仅限Meta ads</td><td>仅限Meta ads</td><td>仅限Meta ads</td></tr><tr><td>Adset ID</td><td>Meta广告组ID</td><td>仅限Meta ads</td><td>仅限Meta ads</td><td>仅限Meta ads</td><td>仅限Meta ads</td><td>仅限Meta ads</td></tr><tr><td>Adset Name</td><td>Meta广告组名称</td><td>仅限Meta ads</td><td>仅限Meta ads</td><td>仅限Meta ads</td><td>仅限Meta ads</td><td>仅限Meta ads</td></tr><tr><td>ARPU</td><td>每用户平均收入</td><td>✓</td><td>✓</td><td> </td><td>✓</td><td>✓</td></tr><tr><td>Average eCPI</td><td>Average eCPI</td><td> </td><td>✓</td><td> </td><td> </td><td> </td></tr><tr><td>Clicks</td><td>点击数量</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Conversion Rate</td><td>激活数量/点击数量</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>CTR</td><td>点击至激活率</td><td> </td><td>✓</td><td>✓</td><td> </td><td> </td></tr><tr><td>`{your event name}(Unique users)</td><td>完成相关事件的独立用户数</td><td>✓</td><td>✓</td><td> </td><td>✓</td><td>✓</td></tr><tr><td>{your event name} (Event counter)</td><td>事件数量</td><td>✓</td><td>✓</td><td> </td><td>✓</td><td>✓</td></tr><tr><td>{your event name}` (Sales in XXX)</td><td>按XXX计算的销售额，其中XXX代表您在应用配置中指定的货币</td><td>✓</td><td>✓</td><td> </td><td>✓</td><td>✓</td></tr><tr><td>Impressions</td><td>展示次数</td><td>✓</td><td>✓</td><td> </td><td>✓</td><td>✓</td></tr><tr><td>Installs</td><td>激活数量</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Loyal Users</td><td>【默认】打开应用超过3次的用户</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Loyal Users/Installs</td><td>忠实用户率</td><td>✓</td><td>✓</td><td> </td><td> </td><td> </td></tr><tr><td>ROI</td><td>投资回报率</td><td>✓</td><td>✓</td><td> </td><td> </td><td> </td></tr><tr><td>Sessions</td><td><ul><li>非自然的应用打开次数</li><li>应用打开（session）的自然和非自然量数据可在群组分析报告中查看</li></ul></td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Total Cost</td><td>-</td><td>✓</td><td>✓</td><td> </td><td> </td><td> </td></tr><tr><td>Total revenue</td><td>具体渠道和广告系列所产生的总体收入</td><td>✓</td><td>✓</td><td> </td><td>✓</td><td>✓</td></tr><tr><td colspan="7"> <strong>请注意：</strong>若您选择了Meta ads作为唯一的媒体渠道，则报告中会包含“Meta ads only”（仅限Meta ads）的字段。</td></tr></tbody></table>

</Accordion>

<div id="retargeting" />

<Accordion title="再营销的汇总数据报告">

再营销报告中的用户与<Anchor target="_blank" href="/marketers/zh/docs/retargeting-attribution-guide#retargeting-reports-and-raw-data">再营销广告</Anchor>互动后完成了一次再互动或再归因。

再营销报告不区分自然用户与非自然用户。

如需通过Pull API拉取再营销报告，请在效果报告的URI末尾添加*&reattr=true*参数。

#### LTV维度的再营销汇总报告

| 报告名称 | 分组维度： |
| --- | --- |
| 合作伙伴（媒体渠道） | 代理、媒体渠道、广告系列 |
| 分渠道每日报告 | 日期、代理、媒体渠道、广告系列 |
| 分日期的用户行为 | 日期、代理、媒体渠道、广告系列 |
| 国家 | 国家、代理、媒体渠道、广告系列 |
| 分日期的国家数据 | 日期、国家、代理、媒体渠道、广告系列 |

#### LTV维度的再营销汇总报告

| 字段 | 说明 | 渠道 | 每日更新 | 分渠道每日报告 | 国家/地区+每日汇总 | 国家/地区 |
| --- | --- | --- | --- | --- | --- | --- |
| Date | 转化日期 | - | - | ✓ | ✓ | - |
| Country |  | - | ✓ |  | ✓ | ✓ |
| Agency/PMD (af\_prt) | 代理/渠道名称 | ✓ | ✓ | ✓ | ✓ | ✓ |
| Media Source (pid) |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Campaign (c) |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Clicks |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Conversions |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Conversion Type | 再归因或再互动 | ✓ | ✓ | ✓ | ✓ | ✓ |
| Conversion Rate | 转化量/点击量 | ✓ | ✓ | ✓ | ✓ | ✓ |
| Sessions |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Loyal Users |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Loyal Users/Installs |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Total Cost |  | - | - | - | - | - |
| Average eCPI |  | - | - | - | - | - |
| Total Revenue |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| ROI |  | - | - | - | - | - |
| ARPU |  | ✓ | ✓ | ✓ | - | ✓ |

</Accordion>

## 功能报告

<div id="skadnetwork" />

<Accordion title="SKAdNetwork">

<Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-solution-guide#reporting-options">SKAN汇总报告</Anchor>

</Accordion>

<div id="protect360-blocked-fraud" />

<Accordion title="Protect360—已拦截的假量">

![](https://theme.zdassets.com/theme_assets/245528/ffbbc473bb0e74b9fb636ed735f69e9af6a25a18.png)

已拦截的假量汇总报告中包含通过<Anchor target="_blank" href="/marketers/zh/docs/protect360-anti-fraud-guide">Protect360</Anchor>功能拦截的事件信息。

您可通过Pull API拉取这些报告，但无法在导出数据页中获取相关数据。

日期范围以激活日期为准。

#### 可通过Pull API拉取的Protect360报告

| 报告名称 |
| --- |
| 合作伙伴（媒体渠道） |
| 分渠道每日报告 |
| 国家/地区 |
| 国家/地区+每日汇总 |
| 渠道投放报告 |

**局限性：** 即使真正的拦截原因为**应用版本**或**CUID缺失**，报告中的拦截原因仍会显示为**Bots**。

</Accordion>

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/configuring-meta-campaign-management-partners">Meta投放管理平台配置说明</Anchor>
> * <Anchor target="_blank" href="/marketers/zh/docs/raw-data-reporting-overview">原始数据报告概览</Anchor>

<div data-zendesk-anchors="aggregated-and-analytics-performance-reporting%E2%80%94tools-and-reports=%E6%8A%95%E6%94%BE%E6%95%88%E6%9E%9C%E6%95%B0%E6%8D%AE%E7%9A%84%E6%B1%87%E6%80%BB%E5%92%8C%E5%88%86%E6%9E%90%E5%B7%A5%E5%85%B7%E7%AE%80%E4%BB%8B 01EWA9VQ2HH93525BMK6WN0P6S=%E6%8A%95%E6%94%BE%E6%95%88%E6%9E%9C%E6%95%B0%E6%8D%AE%E7%9A%84%E6%B1%87%E6%80%BB%E5%92%8C%E5%88%86%E6%9E%90%E5%B7%A5%E5%85%B7%E7%AE%80%E4%BB%8B 01ED4D7W8B53Q81G7PXQH8ADE2=toolapi-comparison h_01HDNYFR9KBX2KP75K1FAZC2Q7=cohort-flavors user-journey-reports=%E7%94%A8%E6%88%B7%E9%93%BE%E8%B7%AF%E6%8A%A5%E5%91%8A 01ED4D7W8CVAQ9V2GCEX1G6KD7=%E7%94%A8%E6%88%B7%E9%93%BE%E8%B7%AF%E6%8A%A5%E5%91%8A h_01HDNYFR9KBMWAFXDNNJN8VA2X=ua-ltv-aggregate-data-reports-containing-nonorganic-and-organic-users examples-of-aggregate-reports=%E6%B1%87%E6%80%BB%E6%8A%A5%E5%91%8A%E7%A4%BA%E4%BE%8B 01ED4D7W8C3ZNBYR3CMHJF3QSE=%E6%B1%87%E6%80%BB%E6%8A%A5%E5%91%8A%E7%A4%BA%E4%BE%8B fields-in-ua-aggregate-reports=ua%E6%B1%87%E6%80%BB%E6%8A%A5%E5%91%8A%E4%B8%AD%E7%9A%84%E5%AD%97%E6%AE%B5 h_01HDNYFR9KTQ7ZF35C7E7M7AF1=ua%E6%B1%87%E6%80%BB%E6%8A%A5%E5%91%8A%E4%B8%AD%E7%9A%84%E5%AD%97%E6%AE%B5 h_01J3YNA04FEF0MHPAFF39ZJYC2=retargeting aggregate-ltv-retargeting-reports=ltv%E7%BB%B4%E5%BA%A6%E7%9A%84%E5%86%8D%E8%90%A5%E9%94%80%E6%B1%87%E6%80%BB%E6%8A%A5%E5%91%8A h_01HDNYFR9MSJWCP3JA4M1WXN1H=ltv%E7%BB%B4%E5%BA%A6%E7%9A%84%E5%86%8D%E8%90%A5%E9%94%80%E6%B1%87%E6%80%BB%E6%8A%A5%E5%91%8A aggregate-ltv-retargeting-reports::b2093953=ltv%E7%BB%B4%E5%BA%A6%E7%9A%84%E5%86%8D%E8%90%A5%E9%94%80%E6%B1%87%E6%80%BB%E6%8A%A5%E5%91%8A-1 h_01HDNYFR9MSK9VQQ0Q889Z55TN=ltv%E7%BB%B4%E5%BA%A6%E7%9A%84%E5%86%8D%E8%90%A5%E9%94%80%E6%B1%87%E6%80%BB%E6%8A%A5%E5%91%8A-1 feature-reports=%E5%8A%9F%E8%83%BD%E6%8A%A5%E5%91%8A h_01HDNYFR9MYXVZ5BA9FDZ6D82M=%E5%8A%9F%E8%83%BD%E6%8A%A5%E5%91%8A 01ED4D7W8CBH7Q8D31VX5313WP=skadnetwork protect360%E2%80%94blocked-fraud=protect360-blocked-fraud h_01HDNYFR9MJNKGR7XFCACVP6KT=protect360-blocked-fraud aggregate-protect360-reports-available-via-pull-api=%E5%8F%AF%E9%80%9A%E8%BF%87pull-api%E6%8B%89%E5%8F%96%E7%9A%84protect360%E6%8A%A5%E5%91%8A h_01HDNYFR9MSZ9K8F283J0WBHCZ=%E5%8F%AF%E9%80%9A%E8%BF%87pull-api%E6%8B%89%E5%8F%96%E7%9A%84protect360%E6%8A%A5%E5%91%8A h_01HDNYYJXVY9XHX87K06NXYQNS=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />
