---
title: ROI360—成本汇总解决方案
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Premium
    - Premium Feature
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Marketers
    - Agencies
    - ROI360
  created_at: '2015-12-24T10:45:16Z'
  edited_at: '2026-10-14T10:00:24Z'
  id: 207040526
  locale: zh-cn
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/zh-cn/articles/207040526
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概览：** 本文重点介绍了汇总和查看营销成本数据的各种方法。

## 成本数据汇总

**ROI360**：

* 提供汇总广告成本数据和与成本相关的LTV（生命周期价值）绩效指标。以及与成本相关的LTV效果指标。成本相关指标包括过去一段时间内的ROI、ROAS、点击、展示、广告系列ROI以及平均有效激活成本（eCPI）。
* 覆盖所有平台，包括移动应用、网页浏览器、CTV、PC 和主机端
* 支持渠道使用的各种成本模型，如CPI、CPA、CPC和CPM等。
* 支持分API的广告成本数据、成本导入（CSV文件上传）以及<Anchor target="_blank" href="/marketers/zh/docs/view-aggregated-cost-data-for-attribution-links">通过归因链接上报成本</Anchor>。
* 广告主购买ROI360套餐后，代理就可以访问广告主的ROI360成本数据。

套餐中没有ROI360的广告主可以使用以下指标：

* <Anchor target="_blank" href="/marketers/zh/docs/view-aggregated-cost-data-for-attribution-links">通过归因链接上报的成本数据</Anchor>
* SRN（自报告网络）点击和展示数据，通过SRN集成合作伙伴配置 **费用** Tab。

## 成本数据汇总的原则

本节介绍了广告成本数据汇总的主要原则。

<div id="cost-aggregation-methods" />

<Accordion title="成本汇总方法">

渠道侧的成本数据可以通过一种或多种方法上报。如果成本数据通过多种方式上报，AF会通过[成本优先级排序机制](/docs/roi360-cost-aggregation-overview#cost-prioritization-mechanism)判断数据的取舍，以防最终结果虚高。

AppsFlyer处理数据后，会显示在UTC时区（默认时间）或根据你的情况 <Anchor target="_blank" href="/marketers/zh/docs/changing-app-time-zone-settings">应用专用时区</Anchor> 设定。

<table><thead><tr><th>成本汇总方法</th><th>支持的成本模型</th><th>数据颗粒度</th><th>数据时效性</th><th>说明</th></tr></thead><tbody><tr><td> <a href="./set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api" target="_blank">API</a>\*</td><td>所有</td><td>数据颗粒度取决于对接配置</td><td><a href="./about-data-freshness-and-timezone-support#intraday-during-the-day" target="_blank">一天多次</a></td><td>在成本事件发生后，成本数据可能会随着7天的数据回滚（具体取决于媒体渠道）发生变化，这使我们能够考虑媒体来源所做的追溯性变更。</td></tr><tr><td><a href="./import-cost-data" target="_blank">成本导入（文件上传）</a></td><td>所有</td><td>数据颗粒度取决于上传的文件</td><td>数据导入后的4小时内</td><td>报告的成本可以被撤销，修正后的数据可提交最长90天。</td></tr><tr><td><a href="./view-aggregated-cost-data-for-attribution-links" target="_blank">通过归因链接获取成本数据</a></td><td>CPI</td><td>用户层级数据</td><td><p>最低限度：实时</p><p>最慢：点击链接后最多4小时</p></td><td>不可更改</td></tr><tr><td colspan="5">\* 渠道与AppsFlyer之间通过Cost API或InCost API实现API对接（不会两者并用）。所用API和提供的数据粒度取决于合作伙伴。</td></tr></tbody></table>

</Accordion>

<div id="cost-data-availability-and-reports" />

<Accordion title="可用的成本数据和报告">

下表列出了各种可用的成本数据。

为了便于理解，请在查阅下表时参考以下说明（表格中另有备注之处则以表中备注为准）：

#### 获客视图中的成本

系统会根据广告系列在成本上报日期（激活日期）及其前后10天内是否记录了至少一次激活、点击或展示，将广告系列成本数据归类到用户获取（UA）中。系统会根据媒体渠道、广告系列ID和代理机构进行匹配。

#### 统一视图中的成本

统一视图会包含所选应用下所有广告系列的成本数据，无论在成本上报日期（激活日期）及其前后10天内是否存在激活、点击或展示。

#### 示例

* 如果广告系列X的成本上报日期为3月10日，且广告系列X在3月1日至3月20日期间至少有一次点击或激活，则3月10日的成本会同时显示在UA视图和统一视图中。

  * 如果该时间窗口内没有任何活跃数据，则3月10日的成本**只会**显示在统一视图中。
* 如果报告不支持更改广告系列名称，则会同时显示新旧两个名称，其中一个带有归因数据，另一个带有成本数据。任一名称下都不会单独显示完整的数据。

#### 可用的成本数据和报告

| 报告方式 | 视图/数据类型 | 是否支持更改广告系列名称 | 说明 |
| --- | --- | --- | --- |
| 数据总览面板 | <ul><li>UA（用户获取）</li><li>统一</li></ul> | 是 | 再营销视图中不显示成本数据。请在统一视图中查看再营销成本。 |
| 活跃数据面板 | UA（用户获取） | 是 |  |
| 群组面板 | <ul><li>UA（用户获取）</li><li>统一</li></ul> | 是 | <ul><li>再营销视图中不显示成本数据。</li><li>此统一数据仅适用于在成本上报日期（激活日期）及其前后10天内至少记录了一次激活、点击或展示的广告系列。</li></ul> |
| 群组报告API | <ul><li>UA（用户获取）</li><li>统一</li></ul> | 是 | 此统一数据仅适用于在成本上报日期（激活日期）及其前后10天内至少记录了一次激活、点击或展示的广告系列。 |
| SKAN面板 | SKAN | 否 | **显示SKAN激活以及所有激活（包括非SKAN激活）的成本数据。** |
| SKAN Aggregated Performance API | SKAN | 否 | **显示SKAN激活以及所有激活（包括非SKAN激活）的成本数据。** |
| 数据透视表 | UA（用户获取） | 否 |  |
| Master API | UA（用户获取） | 否 |  |
| 自定义面板 | UA（用户获取） | 否 |  |
| Cost ETL | 统一 | 是 | 显示所有可用成本数据。 |
| Pull API汇总数据 | UA（用户获取） | 否 |  |
| Push API | 原始点击数据（非汇总） | 不相关 |  |
| Pull API原始数据 | 原始点击数据（非汇总） | 不相关 |  |
| Data Locker | 原始点击数据（非汇总） | 不相关 | Data Locker的群组报告不支持成本数据。 |

**请注意**：

* 数据的细度会因仪表盘/报表类型而异。<Anchor target="_blank" href="/marketers/zh/docs/set-up-and-use-roi360-cost-etl-reports">Cost ETL</Anchor>报告工具可拉取完整的数据集，包括各广告层级的详细信息（媒体渠道、广告系列名称、广告组以及媒体渠道提供的数据维度，如地理位置、流量入口、子渠道、关键词等等）。
* 您可以在原始数据报告中查看通过归因链接上报的成本数据。

</Accordion>

<div id="cost-prioritization-mechanism" />

<Accordion title="成本优先级排序机制">

![](https://files.readme.io/8dbea1b8561d67f77d27cad85ab109e5203930273f32d2a9b04900b810c46ec2-25433450962577.png)

一个渠道的成本数据可以通过多种方式进行上报。为了避免后台的成本数据虚高，AF会通过广告成本优先级排序机制来判断数据的取舍。这一机制按汇总方式对数据进行优先级排序，从高到低依次为：通过归因链接上报成本 > Cost API > 成本导入

成本优先级机制会影响汇总数据报告和面板，原始数据报告中的归因链接成本数据不受该机制影响。

**注意事项**：

* 优先级机制会在广告系列层级生效，也就是说，如果您的同一个广告系列同时使用了两种方式上报成本，则优先级更高的方式胜出，并对整个广告系列生效。
  * 在给定的任何一天中，如果您通过Cost API了获取了某个具体应用和媒体渠道（或代理）的成本数据，AF就会忽略通过归因链接上报的成本。
* 如果您更改了成本汇总方式，相关数据会发生回滚更新，以往的汇总成本数据会发生变化。
* 成本汇总方式的变更也会对代理流量产生上述影响，无论相关代理的数据是否透明。

> 📄 **示例：**
>
> 某媒体渠道通过归因链接上报成本，但您决定使用该渠道的Cost API。
>
> **结果：** 成本是从归因链接和成本API中汇总的。由于成本API具有优先权，归因链接的成本会被忽略。

</Accordion>

<div id="closed-beta--cost-split" />

<Accordion title="成本分摊">

部分广告平台上报广告系列成本数据时，不会关联应用ID。遇到这种情况时，AppsFlyer会根据广告交互和归因数据补全应用ID。

AppsFlyer会基于上报成本日期前后10天内，与该广告系列的点击、展示和转化相关联的应用进行匹配。

如果应用补全流程匹配到多个应用，AppsFlyer会按照以下方式在这些应用之间分摊广告系列成本：

#### 按比例拆分（按转化量）

如果在报告成本日期有转化（安装、重新归属和再参与）存在，成本将根据每个应用的转化次数按比例分配。

**示例：** 如果第1天的总成本为 **$100**，且该广告系列分别带来**60次iOS激活**和**40次Android激活**，则：

* iOS: **$60**
* Android: **$40**

#### 平均拆分（无转化）

如果上报成本日期当天没有转化，系统会在匹配到的应用之间平均拆分成本。

**示例：** 如果第1天的总成本为**100美**元，且该广告系列在该日期有展示但没有转化，则：

* iOS: **$50**
* Android: **$50**

> 📘 **注意**
>
> 只有当归因中的转化细度与广告网络报告的成本数据精确匹配时，比例（基于转化）分配才适用。当两者仅部分匹配时，AppsFlyer 无法将成本映射到每个应用的转化率，因此会将成本平均分配到匹配的应用中。

#### 局限性

* 该功能支持Google、TikTok和DV360跨平台及Web-to-App（W2A）活动（活动目标与移动/应用不同）。
* **谷歌性能最大化（PMAX）广告活动**:按比例（基于转化率）的分配不适用。Google 的 API 不会报告 PMAX 广告活动的 Ad ID 或 Geo 细度，因此转化细度只能部分匹配，且成本无法映射到每个应用的安装、重新归属和再互动。因此，成本会在匹配的应用中平均分摊，无论每个应用的转化次数多少。在活动层面，当仪表盘中选择所有平台（iOS、Android等）时，总成本仍与谷歌报告的相同。

</Accordion>

## 补充信息

<div id="ad-networks-supporting-cost-api" />

<Accordion title="支持成本API的媒体渠道列表">

以下可下载表格列出了所有支持Cost API的媒体渠道，及其在以下各方面的数据颗粒度：

* 维度
* 支持的功能及其特征
* 指标（由媒体渠道上报）

下载文件：[CSV](https://docs.google.com/spreadsheets/d/e/2PACX-1vQT0acJlUFIwS5NUuD8tJ5MA7OmL0N9a55qLp4ib5FYL_eat1H4IWNW9ZCtAEeDa1kTZK5bRD2ez-ee/pub?output=csv)、<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQT0acJlUFIwS5NUuD8tJ5MA7OmL0N9a55qLp4ib5FYL_eat1H4IWNW9ZCtAEeDa1kTZK5bRD2ez-ee/pub?output=xlsx">XLS</Anchor>

</Accordion>

<div id="changing-campaign-names" />

<Accordion title="更改广告系列名称">

AppsFlyer显示广告系列数据时以广告系列ID为标识。

为避免显示异常，请确保：

* 每个战役都有独特的战役ID。
* 请勿对同一个广告系列名称使用不同的广告系列ID。

<Anchor target="_blank" href="/marketers/zh/docs/campaign-name-changes">进一步了解广告系列名称的变更方式</Anchor>

</Accordion>

<div id="costs-without-installs" />

<Accordion title="不带有激活的成本数据">

<strong>为什么会出现不带激活的成本数据？</strong>当成本在层级较高层级（例如广告活动层面）提供，而绩效信息（点击和安装量）则在广告层级较低层级（例如广告集）时，就会发生这种情况。

AppsFlyer会在较高的广告层级上补齐缺失维度的成本数据，这是为了更全面地呈现各层级的成本数据，并减少内部的数据差异。

> 📄 **示例**
>
> 广告主投放广告，其广告层级如下：
>
> * **媒体渠道**：media\_eg
> * **广告系列**：campaign\_eg
> * **广告组**：**adset1**、**adset2**
>
> 显示的媒体渠道信息如下：
>
> 显示层级：所有媒体渠道 > media\_eg
>
>
>
> | Campaign | 成本 | 激活假量 |
> | --- | --- | --- |
> | campaign\_eg | $100 | 100 |
> | campaign\_yy | $200 | 1000 |
> | campaign\_zz | $300 | 2000 |
>
>
>
> 切入到campaign\_eg，可以看到广告组层级的数据。
>
> 显示层级：所有媒体渠道 > media\_eg > campaign\_eg
>
>
>
> | Adset | 成本 | 激活假量 |
> | --- | --- | --- |
> | 无 | $100 |  |
> | adset\_1 | 不适用 | 30 |
> | adset\_2 | 不适用 | 70 |
>
>
>
> 据以上信息可知，广告平台提供的是广告系列层级的成本数据，campaign\_eg的成本为100美元。再向下切入到广告组层级时，成本数据无法进一步细分。
>
> 为解决这个问题，AppsFlyer会直接沿用广告系列层级的成本数据，并单开一行显示。在上述场景中，有消耗数据的广告组名称会显示为None，激活栏则为空。

</Accordion>

<div id="cost-currency-conversion" />

<Accordion title="成本货币换算">

如果媒体渠道的成本货币不同于您在AF后台的应用配置中设定的货币，AF会把成本换算到应用层级的指定货币，方法如下：

* AppsFlyer从<Anchor target="_blank" href="https://openexchangerates.org/">openexchangerates.org</Anchor>获取汇率信息。
* 汇率每小时更新一次，每次更新最多覆盖近7天的数据。
* AppsFlyer会根据已知的最新汇率进行货币换算。

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="特点与局限性">

| 特性 | 说明 |
| --- | --- |
| 代理 | <ul><li>广告主购买ROI360套餐后，代理就可以访问广告主的ROI360成本数据。</li><li>当透明代理机构开展活动时，广告主可以在仪表盘和报告中看到成本，提供统一视图。[了解详情](/docs/roi360-cost-aggregation-overview#cost-data-availability-and-reports)</li><li>如果广告主终止了与代理机构的合作关系，但代理机构仍为该应用配置了成本对接，那么即使广告主在应用层级停用了代理机构权限，成本数据仍会继续拉取。为避免这种情况，广告主必须先要求代理机构在AppsFlyer中停用成本对接，然后再停用代理机构权限。</li><li>部分媒体渠道要求代理必须联系广告主，让广告主激活对接，而且AppsFlyer面板中也会弹出相应的提示信息。对于这些广告平台，代理机构和广告主必须确保媒体渠道发送数据时包含相关`af_prt`参数；该参数是代理机构成本归因所必需的。</li><li>X Ads中，如果投放的广告系列只有SKAN激活而没有常规激活，则其成本数据对代理不可用。成本对接必须由广告主设置，且相关数据仅限广告主可以查看。</li></ul> |
| API数据数据时效性 | <ul><li><Anchor target="_blank" href="/marketers/zh/docs/about-data-freshness-and-timezone-support#intraday-during-the-day">一天更新多次</Anchor>（Moloco除外）</li><li>Mintegral数据可在次日通过API获取，通常在前一天结束约4小时后可用。也就是说，假设在第一天发生了某个事件，则广告主可在第二天凌晨4:00左右通过API拉取到该事件的成本数据。</li></ul> |
| 广告系列名称变更 | 广告消耗数据会显示在最近一次上报的广告系列名称下。**请注意**：这是用来显示汇总数据，而不是原始数据本身。 |
| 时区 | 如果媒体渠道仅支持一个时区，且该时区与您应用设置中的时区不一致，则以媒体渠道支持的时区为准。 |
| CTV、PC和主机平台 | 对于这些平台中的应用，必须通过邮件<Anchor target="_blank" href="/marketers/zh/docs/import-cost-data">上传</Anchor>的方式来发送成本数据。 |
| 跨平台 | 跨平台点击和展示的成本数据不可得，这意味着展示/点击可能发生在一个平台，应用安装在另一个平台。 |
| 第三方商店中的应用 | 对于第三方商店中的应用（即在Google Play和App Store以外的其他平台中上架的应用），来自Mintegral的成本数据不可用。 |
| 地理位置 | Mistplay上成套的广告系列（bundled campaigns，即投放到多个国家的广告系列）无法使用国家/地区维度进行细分。这类广告系列的国家/地区显示为N/A。 |
| Smadex | 如果Smadex在子渠道ID值中提供了其他信息（比如库存ID等），当Smadex在站点ID值中包含额外元素（如库存ID）时，就会发生这种情况。 |
| apple\_search\_ads.png | 对于仅SKAN报表，SKAN面板或Pull API中不提供ASA成本数据，因为Apple不会在SKAN回传中包含广告系列层级数据。不过，您仍可通过我们的传统对接，在SSOT报告中查看成本数据。 |
| 成本数据维度字符限制 | 以下列出的网络尺寸不得超过指定字符长度。如超出限制，相关数值将无法在报告中显示。<ul><li>`app_id` &lt;=100</li><li>`publisher` &lt;=250</li><li>`partner` &lt;=250</li><li>`campaign` &lt;=250</li><li>`campaign_id` &lt;=250</li><li>`adset` &lt;=250</li><li>`adset_id` &lt;=250</li><li>`ad` &lt;=250</li><li>`ad_id` &lt;=250</li><li>`site_id` &lt;=250</li><li>`site_name` &lt;=250</li><li>`channel` &lt;=250</li><li>`ad_account` &lt;=250</li><li>`ad_account_name` &lt;=250</li></ul>这些限制仅适用于以下网络：<ul><li>mintegral\_int</li><li>moloco\_int</li><li>applovin\_int</li><li>liftoff\_int</li><li>aura\_int</li><li>tiktokglobal\_int,</li><li>pinterest\_int</li><li>vungle\_int,</li><li>iossearchads\_int</li></ul> |
| API成本数据可用性 | 仅当客户拥有有效的ROI360资产时，API成本数据才会显示。如果ROI360已停用，来自API渠道的成本数据将不再可用，面板中仅会显示基于CPI的成本数据。 |
| Mintegral：广告层级粒度 | 如需获取Mintegral广告层级粒度的成本报告，每个广告账户都需要具备以下广告平台权限：**Sub/Package×Creative维度**。 |

</Accordion>

> 📄 **另请参阅**
>
> * Xpend—成本汇总概述
> * <Anchor target="_blank" href="/marketers/zh/docs/view-aggregated-cost-data-for-attribution-links">通过归因链接获取成本数据</Anchor>
> * <Anchor target="_blank" href="/marketers/zh/docs/about-data-freshness-and-timezone-support">数据新鲜度与时区支持</Anchor>
> * <Anchor target="_blank" href="/marketers/zh/docs/campaign-name-changes">广告系列名称变更</Anchor>

<div data-zendesk-anchors="cost-aggregation=%E6%88%90%E6%9C%AC%E6%95%B0%E6%8D%AE%E6%B1%87%E6%80%BB h_01HC7K2Y627P56F5JH9QT47GB2=%E6%88%90%E6%9C%AC%E6%95%B0%E6%8D%AE%E6%B1%87%E6%80%BB principles-of-cost-data-aggregation=%E6%88%90%E6%9C%AC%E6%95%B0%E6%8D%AE%E6%B1%87%E6%80%BB%E7%9A%84%E5%8E%9F%E5%88%99 h_01HC7K2Y62ZC932EDX00YP7DAW=%E6%88%90%E6%9C%AC%E6%95%B0%E6%8D%AE%E6%B1%87%E6%80%BB%E7%9A%84%E5%8E%9F%E5%88%99 h_01HC7K2Y62K78M02ZN034N99T0=cost-aggregation-methods h_01HC7K2Y62YPM3A6Z0HBY58J00=cost-data-availability-and-reports cost-in-the-ua-view=%E8%8E%B7%E5%AE%A2%E8%A7%86%E5%9B%BE%E4%B8%AD%E7%9A%84%E6%88%90%E6%9C%AC h_01KGS7NM964HW175AW2CF59P5K=%E8%8E%B7%E5%AE%A2%E8%A7%86%E5%9B%BE%E4%B8%AD%E7%9A%84%E6%88%90%E6%9C%AC cost-in-unified-view=%E7%BB%9F%E4%B8%80%E8%A7%86%E5%9B%BE%E4%B8%AD%E7%9A%84%E6%88%90%E6%9C%AC h_01KGS7QG5GNKG1YVACWQKCQFZ4=%E7%BB%9F%E4%B8%80%E8%A7%86%E5%9B%BE%E4%B8%AD%E7%9A%84%E6%88%90%E6%9C%AC example=%E7%A4%BA%E4%BE%8B h_01KGS7R5SJ3NSVJAHG3BM922VS=%E7%A4%BA%E4%BE%8B cost-data-availability-and-reports::865c5bcd=%E5%8F%AF%E7%94%A8%E7%9A%84%E6%88%90%E6%9C%AC%E6%95%B0%E6%8D%AE%E5%92%8C%E6%8A%A5%E5%91%8A h_01HC7K2Y62ZY6HWG5TJDEPHZKH=%E5%8F%AF%E7%94%A8%E7%9A%84%E6%88%90%E6%9C%AC%E6%95%B0%E6%8D%AE%E5%92%8C%E6%8A%A5%E5%91%8A h_01HC7K2Y62112X308A0Y7DDDRM=cost-prioritization-mechanism h_01HC7K2Y62SZKXD4W0EJGYF6RS=%E7%A4%BA%E4%BE%8B-1 %5Bclosed-beta%5D-cost-split=closed-beta--cost-split h_01KHR3PQTNF5XP7J4HZEYVRK95=closed-beta--cost-split proportional-split-by-conversions=%E6%8C%89%E6%AF%94%E4%BE%8B%E6%8B%86%E5%88%86%E6%8C%89%E8%BD%AC%E5%8C%96%E9%87%8F h_01KHR3PQTNMDX8AGM1C73N7SMK=%E6%8C%89%E6%AF%94%E4%BE%8B%E6%8B%86%E5%88%86%E6%8C%89%E8%BD%AC%E5%8C%96%E9%87%8F equal-split-no-conversions=%E5%B9%B3%E5%9D%87%E6%8B%86%E5%88%86%E6%97%A0%E8%BD%AC%E5%8C%96 h_01KHR3PQTPG8GTHV64MFCM628H=%E5%B9%B3%E5%9D%87%E6%8B%86%E5%88%86%E6%97%A0%E8%BD%AC%E5%8C%96 h_01KZ8TMT06KNYFZ7VBX1GY07JB=%E6%B3%A8%E6%84%8F limitations=%E5%B1%80%E9%99%90%E6%80%A7 h_01KHR3PQTPPJYKXRYKNHM4W95A=%E5%B1%80%E9%99%90%E6%80%A7 list-of-ad-networks=%E8%A1%A5%E5%85%85%E4%BF%A1%E6%81%AF h_01HC7K2Y63T9GK0WW95YM39B5C=%E8%A1%A5%E5%85%85%E4%BF%A1%E6%81%AF h_01HC7K2Y63MG10M4Z66VHY5WYW=ad-networks-supporting-cost-api h_01HE0T3TGPZFB2ZBHFGGWXY6AP=changing-campaign-names h_01HE0T3TGQGK6135KM7AYJ7S1G=costs-without-installs h_01HE0T3TGQMK285N8RV48KG8N9=%E7%A4%BA%E4%BE%8B-2 h_01HE0T3TGQ7MSSB09GFNPYFKR1=cost-currency-conversion h_01HJ10FMTJKH48CEXM0G40Y9J1=traits-and-limitations h_01KZB8X752XR3PB8ZACZE4QWTC=%E5%8F%A6%E8%AF%B7%E5%8F%82%E9%98%85" />
