---
title: iOS归因的单一可信数据源（SSOT）指南
metadata:
  keywords:
    - iOS
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
  created_at: '2021-11-11T09:28:42Z'
  edited_at: '2026-10-14T10:10:25Z'
  id: 4410634145425
  locale: zh-cn
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/zh-cn/articles/4410634145425
---
> **概要**：对于iOS 14+系统，AppsFlyer可以结合由多种归因方式（IDFA、IDFV、SKAN、Apple Search Ads等等）产生的数据，为广告主呈现更为全面的投放效果信息。任何归因方式都无法单独反映出完整的应用使用情况。但如果使用多种归因方式，则同一个用户可能会被两种不同的方式归因，因此很难确保用户的记录不出现重复。AppsFlyer的单一可信数据源（SSOT）机制就是专为解决这一痛点而设计的。SSOT能让广告主获得真实且准确的报告和指标，并确保用户不被重复记录。

<Embed title="iOS归因的单一可信数据源（SSOT）指南" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/545isomgo1" providerUrl="https://fast.wistia.com" />

## 单一可信数据源简介——真实的iOS效果数据

iOS 14上线后，AppsFlyer就开始通过多种来源的数据对用户进行归因，这些数据来源包括SKAdNetwork、ATT授权用户、概率模型、增量洞察以及Apple Search Ads的专用API。在没有IDFA的况下结合使用多种归因方式时，几乎无法避免重复数据的出现。

SSOT机制可剔除重复的激活数据，并校正归因结果（即被归为自然用户的非自然用户），为后续相关指标的正确计算打下基础，包括非自然激活量以及对应的eCPI、ROI和ROAS等成本及收入指标。

SSOT机制会标记出同时被SKAN和非SKAN方式重复归因的激活。AF会根据该标记来计算汇总指标，以避免重复计算同一个用户。同理，SKAN原始数据的处理中也同样会用到该标记。

您必须先打开转化值操作台中的SSOT开关，才能对您的数据进行SSOT标记。

<div id="turn-on-single-source-of-truth" />

<Accordion title="启用单一可信数据源（SSOT）机制">

![SSOTControl.png](https://files.readme.io/fd99117e9278ebda3b1f0cc137afb266643e5e45325345ec51aeb58c16d4f13c-31247514683153.png)

**请按以下步骤启用SSOT：**

1. 开始操作之前，请先参阅<Anchor target="_blank" href="https://content.appsflyer.com/ios-hub/billing/">SSOT计费</Anchor>规则。
2. 从AF后台进入**配置** > **SKAN转化值操作台**。
3. 选择**自定义**模式。
4. 打开**单一可信数据源**开关。
5. 完成所需设置。

详情请见<Anchor target="_blank" href="/marketers/zh/docs/skan-conversion-studio">SKAN转化值操作台</Anchor>

</Accordion>

## 数据总览面板的SSOT视图

![SSOTisNowOn.png](https://files.readme.io/8e21fd0c64bb85fb94af752eb037472726d68cd55bf028dc5306b0acb398d199-31247490958225.png)

您可以在数据总览面板中查看SSOT试图，全面掌握非自然量的投放指标。该视图可确保：

* 激活指标的真实性。
* 基于激活数据的eCPI、ARPU和ROAS等成本及收入指标得到正确计算。
* 根据校正后的归因结果调整自然量指标。

本章节重点解释了SSOT视图与其他视图的不同之处及其独特功能。您需要对数据总览面板有一定的了解才能更好地理解这部分内容。

<div id="turn-on-single-source-of-truth-view" />

<Accordion title="启用SSOT视图">

您在转化值操作台中启用SSOT天后，需要等待3-5天方可查看SSOT视图中的数据。

**请按以下步骤启用SSOT视图**：

1. 请事先检查转化值操作台中的<Anchor target="_blank" href="/marketers/zh/docs/skan-conversion-studio#single-source-of-truth">SSOT</Anchor>开关是否已打开。
2. 从AppsFlyer后台进入**面板** > **数据总览面板**。   
   <Image alt="SelectSavedReport.png" src="https://files.readme.io/863a9c66c37e031a1f1b2a7fb3e0c68eb9c29405283214e68a432357c35524dd-31247514684177.png" width="243px" />
3. 点击▼。
4. **选择数据总览轻量版。  
   界面会显示SSOT开关。  
   <Image alt="SSOTviewon.png" src="https://files.readme.io/7b0a664f0882dad46e7239b5363592717358a79d920377dde13aa9c5dfbe84c3-31247514684433.png" width="246px" />**
5. 启用单一可信数据源（SSOT）机制
6. 完成操作后会出现以下两种结果：
   * 界面会显示面板指标和图表，  
     以下几个章节会具体说明其中的可用数据。详情请见下一章节中的数据显示说明。  
     请将该SSOT视图另存为新报告。具体操作如下：  
     1. 点击▼。
     2. 点击 + 保存新报告。
     3. 输入报告名称。
     4. 点击**保存**。
   * 界面不显示数据。请注意，启用SSOT后，需要等待3-5天才能看到数据。请等这段时间过去之后再查看面板。

如果您想要使用SSOT视图中没有的数据维度来查看常规数据，可以随时关闭SSOT开关，  以便对数据进行深剖分析。

</Accordion>

<div id="ssot-view-considerations" />

<Accordion title="SSOT视图的注意事项">

在SSOT视图中：

* **null值**：通过模型推算。我们使用了先进的机器学习技术来建模推算null值，并通过[af\_attribution标记null](/docs/single-source-of-truth-ssot-guide-for-ios-attribution#归因标记字段)值的归因路径（即由AppsFlyer归因还是由SKAN归因）。对于由SKAN归因的null值，其激活后的所有SKAN衡量数据都会显示在SSOT面板中。 <Anchor target="_blank" href="/marketers/zh/docs/skan-modeled-data">详情请见此处说明。</Anchor>
* **重新下载**（Redownloads）：会反映在激活指标中。激活与redownloads之间不作区分。
* **时区**（Timezone）：由AppsFlyer上报的激活和事件按UTC时间或<Anchor target="_blank" href="/marketers/zh/docs/app-settings">应用配置</Anchor>中的指定时区呈现。由SKAN上报的激活和事件按UTC时间呈现，但Meta和Google的SKAN数据除外，这些数据会根据您在对应的Meta和Google账户中所设置的时区来显示。
* **货币**：按USD或<Anchor target="_blank" href="/marketers/zh/docs/app-settings">应用配置</Anchor>中的指定货币显示。
* **收入指标 (D2, D7):** 包括建模数据，以考虑不完整或缺失的SKAN回传（空转换值）

#### 筛选条件的注意事项

请注意筛选条件对数据显示的影响以及各种指标的含义，具体请见下表。

| 筛选条件 | 注意事项 |
| --- | --- |
| 单一可信数据源（SSOT） | 在查看SSOT指标前，请先确认SSOT开关已打开。 |
| 视图类型 | <ul><li>**用户获取：** 最适用于SSOT数据的视图。</li><li>**再营销**：SKAN不支持再营销。</li><li>**统一**：只有拉新广告包含SSOT数据，再营销广告不会受到SSOT影响。</li></ul> |
| 日期 | <ul><li>【推荐】为确保数据准确性，建议选择7天以上且不含最近3天的日期范围</li><li>启用SSOT后一般至少需要3天才能看到数据。最终的数据可用日期取决于AppsFlyer。</li><li>最佳时期范围示例：<ul><li>假设当前日期为2月10日，且SSOT开关于1月29日打开，则最佳日期范围为2月1-7日。</li></ul></li><li>启用SSOT后，部分数据（如收入等）可能需要8天时间才能呈现。</li><li>Google的SKAN激活最多会有45天的上报延迟。</li></ul> |
| 广告筛选条件 | 可用的广告层级筛选条件为：<ul><li>媒体渠道</li><li>广告系列</li></ul> |
| 标题KPI | SSOT面板中的标题KPI包含一下内容：<ul><li>用户获取：自然量和非自然量</li><li>SKAN重复数据</li><li>再营销：再互动和再归因</li><li>成本</li><li>eCPI（有效激活成本）</li></ul>每个KIP都有一个对应的百分比值，表示当前选定时间段内的KPI对比上一个时间段的环比变化。比如本周对比上周的周环比，或您在日期范围选项中设定的任意统计周期对比上一个统计周期的变化。举例来说，如果面板显示激活指标有X%的提升，即表示上一个统计周期的激活与当前统计周期相比少X%。 |
| 图表 | **可用维度：**<ul><li>归因方式：<ul><li>AF模型：由SKAN及非SKAN方式同时匹配到的激活。面板会忽略SKAN记录到的激活，以避免同一次激活的重复统计。在SKAN原始数据中，这类激活的af\_attribution\_flag值为true。</li><li>仅限SKAN：仅限由SKAN匹配到的激活，排除非SKAN方式匹配到的激活。在SKAN原始数据中，这类激活的af\_attribution\_flag值为false。</li></ul></li><li>归因类型</li><li>归因到的广告触达类型</li><li>广告系列</li><li>广告系列ID</li><li>媒体渠道</li><li>数据来源</li><li>应用ID（部分图表）</li><li>国家/地区（SKAN的国家/地区数据通过<Anchor target="_blank" href="/marketers/zh/docs/skan-modeled-data#geo">模型推算</Anchor>得出）</li><li>应用内事件名称（即在SKAN转化值操作台中配置的具体应用内事件的名称）。</li></ul>**指标：**<br /><br />请见下文的指标部分。 |
| 表 | **分组：**<ul><li>【默认】该表格默认按媒体渠道和广告系列分组。</li><li>可用的分组维度包括媒体渠道、转化类型、归因方式、广告系列、广告系列ID、广告互动类型、日期、来源，国家/地区以及这些维度的任意组合。**请注意**：SKAN的国家/地区数据通过<Anchor target="_blank" href="/marketers/zh/docs/skan-modeled-data#geo">模型推算</Anchor>得出。</li><li>如果您选择了只适用于非自然量的分组维度，则自然量的媒体渠道会显示为N/A。</li></ul>**指标：**<br /><br />请见下文的指标部分。 |

</Accordion>

<div id="metrics" />

<Accordion title="指标">

SSOT面板中的可用指标：

| 指标 | 说明及注意事项 |
| --- | --- |
| 分组 | <ul><li>【默认】该表格默认按媒体渠道和广告系列分组。</li><li>可用的分组维度包括媒体渠道、转化类型、归因方式、广告系列、广告系列ID、广告互动类型、日期、来源，以及这些维度的任意组合。</li><li>如果您选择了只适用于非自然量的分组维度，则自然量的媒体渠道会显示为N/A。</li></ul> |
| **SSOT归因** | **SSOT面板的表格中选定时间段内的标题指标（激活、再归因、再互动）深剖。**<ul><li>**非自然量带来用户的广告系列。SSOT机制可确保同一次激活不会被重复记录。**</li><li>**自然量指标。**</li></ul> |
| Total（总计） | 激活、再归因和再互动的数量。 |
| 激活假量 | 激活应用的独立用户数。计算方式如下：由AppsFlyer归因到拉新广告的激活 + 去重后的由SKAN上报的新增激活和redownloads（重新下载）。 |
| 再归因 | 您可以在统一及再营销视图中查看再营销指标。请注意，SKAN不支持再营销数据。 |
| 再互动 | 您可以在统一及再营销视图中查看再营销指标。请注意，SKAN不支持再营销数据。 |
| **其他指标** | **其他各种与SSOT以及投放效果相关的指标** |
| SKAN重复数据 | 带有af\_attribution\_flag=true的SKAN激活数量 |
| Clicks | 由广告平台通过API上报的点击和展示数据。SSOT机制不会影响触点指标。 |
| Impressions | 由广告平台通过API上报的点击和展示数据。SSOT机制不会影响触点指标。 |
| 转化率 | 点击到激活 |
| 成本（美元） | 由广告平台通过API上报的<Anchor target="_blank" href="/marketers/zh/docs/roi360-cost-aggregation-overview">投放成本</Anchor>数据。面板仅显示带来激活的广告投放，SSOT机制不会影响平台上报的总体成本，仅影响基于激活量计算的指标。 |
| 平均eCPI（美元） | 有效激活成本（eCPI）是根据SSOT视图中的激活数据计算的，其中剔除了自然激活量。 |
| CPM | 每千次展示成本。计算方式为：（成本/展示量）* 1000 |
| CPC | 每点击成本。计算方式为：成本/点击量 |
| 点击型归因 | 用户点击广告（CTA）之后发生的转化数量 |
| CTR | 点击率计算方式为：点击量/展示量 |
| 浏览型归因 | <span id="simple-tabpanel-2"></span>用户浏览广告（CTA）之后发生的转化数量 |
| 收入（D2） | <ul><li>包括建模数据，以考虑不完整或缺失的SKAN回传（空转换值）</li></ul>在第1个SKAN窗口期（D2）内由SKAN和传统模式归因到的收入（包括广告收入）：<ul><li>SKAN收入SKAN激活（即af\_attribution\_flag=false/null的激活)所对应的收入。这是根据您在<Anchor target="_blank" href="/marketers/zh/docs/skan-conversion-studio#revenue-component">转化值操作台的收入维度</Anchor>中配置的转化值以及衡量窗口期计算得出的。</li><li>**传统模式的收入：** 传统模式记录到激活应用后，相关用户在SKAN衡量窗口期内带来的收入。</li><li>如果您在转化值操作台中启用了SKAN 4，则该数据为激活后2天内的收入。如果您在转化值操作台中使用SKAN 3，则该数据取决于您设置的SKAN用户行为窗口期，可能是不到/超过2天内的收入。</li><li>比如<ul><li>用户行为窗口期为24小时。</li><li>发生在激活次日（第X+1天），但同时落在24小时用户行为窗口期内的收入事件。<ul><li>SKAN和AF都会记录该收入，因为这些事件的发生时间虽然不是激活当天，但仍属于24小时的窗口期内。</li></ul></li></ul></li></ul>**小贴士**：您可以使用以下方法提升SKAN收入的准确性：<ul><li>按<Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-solution-guide#recording-ad-revenue">SKAN广告收入指南</Anchor>进行配置。</li><li>使用推荐的收入设置。</li></ul> |
| D7收入 | <ul><li>包括建模数据，以考虑不完整或缺失的SKAN回传（空转换值）</li><li>包含SKAN衡量窗口以外的模型推算数据，最多可覆盖激活后7天。<Anchor target="_blank" href="/marketers/zh/docs/skan-modeled-data#revenue-ltv">了解详情</Anchor></li><li>数据建模需要D2的收入数据。</li></ul> |
| D2 ARPU | 平均每位用户累计带来的收入<br /><br />计算方式为：收入/独立用户数<br /><br />如果您在转化值操作台中启用了SKAN 4，则该数据为激活后2天内的收入。如果您在转化值操作台中使用SKAN 3，则该数据取决于您设置的SKAN用户行为窗口期，可能是不到/超过2天内的收入。 |
| D7 ARPU | 包含SKAN衡量窗口以外的模型推算数据，最多可覆盖激活后7天。<Anchor target="_blank" href="/marketers/zh/docs/skan-modeled-data#revenue-ltv">了解详情</Anchor> |
| D2 ROAS | 广告支出回报率（％）<br /><br />计算方式为：收入/成本 * 100<br /><br />如果您在转化值操作台中启用了SKAN 4，则该数据为激活后2天内的收入。如果您在转化值操作台中使用SKAN 3，则该数据取决于您设置的SKAN用户行为窗口期，可能是不到/超过2天内的收入。 |
| D7 ROAS | 包含SKAN衡量窗口以外的模型推算数据，最多可覆盖激活后7天。<Anchor target="_blank" href="/marketers/zh/docs/skan-modeled-data#revenue-ltv">了解详情</Anchor> |
| D2 ROI | 投资回报率（％）<br /><br />计算方式为：（收入 - 成本）/成本 * 100<br /><br />如果您在转化值操作台中启用了SKAN 4，则该数据为激活后2天内的收入。如果您在转化值操作台中使用SKAN 3，则该数据取决于您设置的SKAN用户行为窗口期，可能是不到/超过2天内的收入。 |
| D7 ROI | 包含SKAN衡量窗口以外的模型推算数据，最多可覆盖激活后7天。<Anchor target="_blank" href="/marketers/zh/docs/skan-modeled-data#revenue-ltv">了解详情</Anchor> |
| D2毛利 | 剔除投放成本后的收益<br /><br />计算方式为：收入 - 成本<br /><br />如果您在转化值操作台中启用了SKAN 4，则该数据为激活后2天内的收入。如果您在转化值操作台中使用SKAN 3，则该数据取决于您设置的SKAN用户行为窗口期，可能是不到/超过2天内的收入。 |
| D7毛利 | 包含SKAN衡量窗口以外的模型推算数据，最多可覆盖激活后7天。<Anchor target="_blank" href="/marketers/zh/docs/skan-modeled-data#revenue-ltv">了解详情</Anchor> |
| **应用内事件指标** | **与具体应用内事件（IAE）相关的指标** |
| 事件独立用户（D2） | 完成该事件的独立用户数，通过AppsFlyer传统模式和SKAN归因综合衡量，其中包含根据null值推算的数据。如果您使用的是SKAN 4，该数据是激活后2天内的累计值。如果您使用的是SKAN 3，该数据是激活后指定用户行为窗口期内的累计值。 |
| 事件独立用户（D7） | 完成该事件的独立用户数，综合AppsFlyer传统模式和SKAN归因数据，以此为基础建模推算。包含SKAN衡量窗口以外的模型推算数据，最多可覆盖激活后7天。<Anchor target="_blank" href="/marketers/zh/docs/skan-modeled-data#inapp-event-ltv">了解详情</Anchor><br /><br />请注意：D7的独立用户数中包含D2的独立用户。 |
| 事件eCPA（D2） | 用户行为的有效成本：成本 / 完成事件的独立用户数 |
| 事件eCPA（D7） | 用户行为的有效成本：成本/完成相关事件的独立用户数。包含SKAN衡量窗口以外的模型推算数据，最多可覆盖激活后7天。<Anchor target="_blank" href="/marketers/zh/docs/skan-modeled-data#inapp-event-ltv">了解详情</Anchor> |
| 事件转化率（D2） | 完成相关事件的用户在总体用户中的占比（总体用户包括激活、再互动和再归因用户）。计算方式为：独立用户数/归因到的转化 * 100。 |
| 事件转化率（D7） | 完成相关事件的用户在总体用户中的占比（总体用户包括激活、再互动和再归因用户）。计算方式为：独立用户数/归因到的转化 * 100。包含SKAN衡量窗口以外的模型推算数据，最多可覆盖激活后7天。<Anchor target="_blank" href="/marketers/zh/docs/skan-modeled-data#inapp-event-ltv">了解详情</Anchor> |
| 事件收入（D2） | 在激活后指定天数内通过该事件产生的收入 |
| 事件收入（D7） | 在激活后指定天数内通过该事件产生的收入。包含SKAN衡量窗口以外的模型推算数据，最多可覆盖激活后7天。<Anchor target="_blank" href="/marketers/zh/docs/skan-modeled-data#inapp-event-ltv">了解详情</Anchor> |

</Accordion>

## SSOT机制的作用原理

<div id="understanding-skanaf-modeled-attribution-duplication" />

<Accordion title="SKAN-AF模型的归因重复原理">

SKAN归因和AF模型归因的作用机制不同，且具有不同的特点和局限性，因此每个激活的归因场景有以下三种：

* 仅由SKAN或仅由AF模型归因（独立归因）。
* 同时由SKAN和某个AF模型归因（重复归因）。在这种情况下，SSOT机制会通过af\_attribution\_flag=TRUE来标记出被SKAN重复归因的激活。在SSOT面板中，仅显示一次激活，不会重复显示。
* 既没有被SKAN归因，也没有被AF模型归因，即记录为自然激活。

下图说明了可能出现的SKAN- AF模型归因场景。

![skan_af_model_diagram.png](https://files.readme.io/1b305d053044f79d12b9190d0b6c24dcc7e0bd17e17ef29029ad0b1c3c7d84c0-31247514684689.png)

下表说明了每个归因场景的原理。

| 仅SKAN归因 | 仅AF模型归因 | SKAN和AF模型同时归因 | SKAN和AF模型都不归因 |
| --- | --- | --- | --- |
| <ul><li>渠道是SRN，用户设备的操作系统为iOS 14.5+，且用户未进行ATT双端授权。</li><li>渠道是非SRN，用户设备的操作系统为iOS 14.5+，概率模型不可用，用户未进行ATT双端授权。</li></ul> | <ul><li>用户设备为iOS 14.4及以下。</li><li>渠道不支持SKAN。</li><li>激活来自网页到应用链路（SKAN仅支持应用到应用）。</li><li>激活来自再营销投放（SKAN不支持再营销）。</li></ul> | 不存在归因限制，激活被SKAN和AF模型同时归因。<br /><br />这种情况下会出现重复的激活数据，需要使用SSOT进行去重。 | 用户来自自然激活。 |

</Accordion>

<div id="ssot-mechanism-workings" />

<Accordion title="SSOT机制的作用原理">

下图详细描述了SSOT的作用机制

![SingleSourceOfTruth.png](https://files.readme.io/882527d4828cf3c7156caf183652368de33463a440715c69f7ec39bfd0f655fa-31247514685329.png)

**SSOT机制的作用原理**

SSOT机制在用户设备（即集成到您应用中的AppsFlyer SDK）以及AppsFlyer平台中的作用方式如下：

**用户设备：**

* 用户首次打开应用后，AppsFlyer平台对该用户进行归因，其归因能力取决于投放类型以及用户的ATT授权状态。
* 如果归因成功，则SDK会通过设置转化值（CV）对该归因进行标记。
* 常规的SKAN链路保持不变。也就是说窗口期内的用户行为仍照常通过CV值的设置进行衡量。
* 然后iOS发送回传数据。

**AppsFlyer平台**

* AppsFlyer收到iOS回传后解析CV值，并通过af\_attribution\_flag的值来获取归因标记。

**注意事项**

* 一般情况下，AppsFlyer不统计重装激活。SSOT机制不考虑重装激活状态。也就是说，SSOT分析报告中不会对来自重装激活的SKAN激活进行去重，且此类激活不会影响af\_attribution flag的值。

#### **归因标记字段**

| 转化值中的SSOT标记 | 含义 | af\_attribution\_flag字段 |
| --- | --- | --- |
| 启用 | 转化值操作台中的SSOT开关已打开，且AppsFlyer成功归因到用户。 | True |
| 停用 | 转化值操作台中的SSOT开关已打开，而AppsFlyer未归因到用户。 | 否 |
| -- | 转化值操作台中的SSOT开关未打开 | Null |

**af\_attribution\_flag（归因标记）报告工具有何影响？**

* SKAN面板：仅反映由SKAN回传上报的投放效果数据，因此不考虑af\_attribution flag字段且不做数据去重。
* SKAN<Anchor target="_blank" href="/marketers/zh/docs/skan-aggregated-performance-report-api">汇总效果报告</Anchor>和<Anchor target="_blank" href="/marketers/zh/docs/skan-raw-data-reports">原始数据报告</Anchor>：这些报告中会呈现af\_attribution\_flag。请根据您对报告的具体需求使用该字段。在结合使用SKAN数据和AppsFlyer数据时，您可以通过该标记来做数据去重。该方法对原始数据和汇总数据报告都适用。
* 数据总览面板中的SSOT视图：融合各种归因方式带来的数据，包括SKAN、IDFA、IDFV、Apple Search Ads等等，然后进行去重，并在单一视图中展示去重后的数据。

</Accordion>

<div id="metrics-derived-by-combining-data-from-multiple-attribution-methods" />

<Accordion title="融合多种归因方式得出的指标">

在结合使用SKAN数据和非SKAN数据时，您可以使用af\_attribution\_flag进行数据去重。该方法对原始数据和汇总数据报告都适用。

以下指标可根据af\_attribution\_flag来计算：

* 非自然激活
* Organic installs（自然激活）
* eCPI（有效激活成本）
* 群组收入

上述指标的计算方式：

| 指标说明 | 序号 | 公式 |
| --- | --- | --- |
| 非自然AppsFlyer激活 | A | 由AppsFlyer传统方式归因到的非自然激活 |
| SKAN独立激活 | B | af\_attribution\_flag=false的SKAN激活 |
| 所有的非自然激活 | C | A + B |
| Organic installs（自然激活） | D | 总激活数 - C<br /><br />**请注意**：总激活数指所有由AppsFlyer SDK记录到的激活，忽略归因方式。 |
| 广告eCPI | E | 成本 / C |
| 群组收入 | F | 将以下数据相加：<ul><li>A中的用户所带来的收入，其中包括激活后最初的一段时间内（相当于SKAN衡量窗口期）产生的应用内事件。</li><li>af\_attribution\_flag = false的SKAN收入</li></ul> |
| D2自然收入 | G | 总体D2收入——A类和B类激活的D2收入总和 |
| D2自然IAE独立用户 | H | 总体D2 IAE独立用户——A类和B类激活的D2事件独立用户数总和 |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="特点与局限性">

| 特点 | 说明 |
| --- | --- |
| SSOT视图 | 过去5天内必须至少每天都有一次带`af_attribution_flag=true`的SKAN回传，才能看到SSOT视图。 |
| 总激活量 | 某些情况下，SSOT打开时面板展示的激活反而会比关闭时更多。其原因之一是null值模型推算会影响激活日期的计算，使得相同日期的激活数量之间产生差异。此外，没有null值推算数据时，总体激活数可能会出现虚高，因为这种情况下每个SKAN激活都会被统计为独立激活（带有`af_attribution_flag=false`标记）。 |
| 收入 | 从2022年9月1日起，SSOT将支持收入及其他收入相关的指标（ARPU、ROAS、ROI、毛利润）。 |
| 代理 | 代理用户可以使用数据总览面板中的SSOT视图。 |
| 广告平台 | <ul><li>满足以下条件时，广告平台可以访问数据总览面板中的SSOT视图，查看归因到自身媒体渠道的数据：<ul><li>广告主已在转化值操作台中打开SSOT开关。</li><li>相关广告平台投放SKAN广告。</li><li>广告主已向相关广告平台开放汇总数据的<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#permissions-tab">必要权限</Anchor>。</li></ul></li><li>添加skad\_af\_attribution\_flag字段宏后，广告平台可以就通过SKAN回传获取SSOT signals。<Anchor target="_blank" href="/partners/zh/docs/skan-integration-guide-for-ad-networks#接收appsflyer发送的数据">详情请见此处说明。</Anchor></li></ul> |
| D7（激活后7天）指标 | D7指标在以下情况中可能出现缺失或低于D2指标：<ul><li>从指定日期范围中的某天起到当前为止不满8天。</li><li>模型推算数据不可用，比如相关投放未产生14天的收入数据。 <Anchor target="_blank" href="/marketers/zh/docs/skan-modeled-data#revenue-ltv">详情请见此处说明。</Anchor></li><li>SKAN转化值操作台的配置在过去14天内发生变更。</li><li>某一天的激活数量低于10个。</li></ul> |
| SKAN转化值操作台配置变更 | 变更SKAN转化值操作台配置之后约96小时内，SSOT数据可能会出现不准确的情况。这是因为AppsFlyer会在变更后立即根据新的映射构架来解析SKAN回传，但此时接收到的激活回传仍按变更之前的映射构架编码。 |
| AF上报的数据 | <ul><li>AF上报的数据，有时也称为AF模型数据，是指通过非SKAN的AppsFlyer传统模式归因的激活和事件数据。</li><li>SSOT面板旨在针对同时由SKAN和AppsFlyer传统模式归因的激活和事件进行排重。</li><li>如果您已经启用了SSOT，但想要查看启用前的数据，这时SSOT面板仅显示AF上报的数据。</li></ul> |
| 应用内事件 | 仅符合以下条件的应用内事件及其指标可用作分组维度：<ul><li>在窗口1期间发生的事件</li></ul> |

</Accordion>

> 📄 **相关文档**
>
> * 数据总览面板
> * <Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-solution-guide">SKAN解决方案指南</Anchor>
> * <Anchor target="_blank" href="/marketers/zh/docs/skan-conversion-studio">SKAN转化值操作台</Anchor>
> * 数据总览面板

<div data-zendesk-anchors="how-to-get-true-ios-14-performance-data=%E5%8D%95%E4%B8%80%E5%8F%AF%E4%BF%A1%E6%95%B0%E6%8D%AE%E6%BA%90%E7%AE%80%E4%BB%8B%E7%9C%9F%E5%AE%9E%E7%9A%84ios%E6%95%88%E6%9E%9C%E6%95%B0%E6%8D%AE 01H8TZV6P41Z3ZEZ8VS86DK1J9=%E5%8D%95%E4%B8%80%E5%8F%AF%E4%BF%A1%E6%95%B0%E6%8D%AE%E6%BA%90%E7%AE%80%E4%BB%8B%E7%9C%9F%E5%AE%9E%E7%9A%84ios%E6%95%88%E6%9E%9C%E6%95%B0%E6%8D%AE 01H8TZV6P4G5AF2MJDQB8J6W2M=turn-on-single-source-of-truth overview-dashboard-single-source-of-truth-view=%E6%95%B0%E6%8D%AE%E6%80%BB%E8%A7%88%E9%9D%A2%E6%9D%BF%E7%9A%84ssot%E8%A7%86%E5%9B%BE 01H8TZV6P4ZBJTDH0FQ6F5D6Q9=%E6%95%B0%E6%8D%AE%E6%80%BB%E8%A7%88%E9%9D%A2%E6%9D%BF%E7%9A%84ssot%E8%A7%86%E5%9B%BE 01H8TZV6P47ZE6PMPF7S9GCJ16=turn-on-single-source-of-truth-view 01H8TZV6P4VCC5NRKBRQNJ4NX3=ssot-view-considerations filter-considerations=%E7%AD%9B%E9%80%89%E6%9D%A1%E4%BB%B6%E7%9A%84%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9 01H8TZV6P4QXEXYWSXKDB7B5SV=%E7%AD%9B%E9%80%89%E6%9D%A1%E4%BB%B6%E7%9A%84%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9 01H8TZV6P4YNTFBX5RXVKK8J0F=metrics how-does-ssot-work=ssot%E6%9C%BA%E5%88%B6%E7%9A%84%E4%BD%9C%E7%94%A8%E5%8E%9F%E7%90%86 01H8TZV6P4K8VXNKDR7JHM8PFW=ssot%E6%9C%BA%E5%88%B6%E7%9A%84%E4%BD%9C%E7%94%A8%E5%8E%9F%E7%90%86 01H8TZV6P4QYQJ177E2ZG676MH=understanding-skanaf-modeled-attribution-duplication 01H8TZV6P58E502Y1FDFHC3KHM=ssot-mechanism-workings attribution-flag-field=%E5%BD%92%E5%9B%A0%E6%A0%87%E8%AE%B0%E5%AD%97%E6%AE%B5 01H8TZV6P5SSKDTKV4BV3TTA7D=%E5%BD%92%E5%9B%A0%E6%A0%87%E8%AE%B0%E5%AD%97%E6%AE%B5 01H8TZV6P5AHZD8VRWRS4SPBYW=metrics-derived-by-combining-data-from-multiple-attribution-methods 01H8TZV6P5KN4F24ZN33V0TK7K=traits-and-limitations h_01HE182N43SSBX051E4GK7NFQ8=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />
