---
title: 素材优化指南
metadata:
  keywords:
    - Premium
    - Marketers
    - Design team
    - Creative Optimization
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-omer-katzburg
    - Marketers
    - Creative Optimization
  created_at: '2023-09-14T13:32:13Z'
  edited_at: '2026-10-14T10:07:16Z'
  id: 18564718580625
  locale: zh-cn
  section: Creative Optimization
  section_id: 4419063475217
  url: https://support.appsflyer.com/hc/zh-cn/articles/18564718580625
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** 您可以通过素材优化（Creative Optimization）功能获取您广告投放中所有素材资产（asset）的数据，并将其汇总到同一个平台，便于您分析素材效果，找出最高效的素材，利用数据改善营销决策。该面板呈现LTV维度的数据，也就是说其中的指标与相关素材在选定时间段内产生的转化有关。

[![Main image -Default view.jpg](https://files.readme.io/9ef8901b620d54cad031ec142f5dd408406e0a470bae8a0719826777561cd1d1-21362497825169.jpg)](https://files.readme.io/9ef8901b620d54cad031ec142f5dd408406e0a470bae8a0719826777561cd1d1-21362497825169.jpg)

<div id="about-creative-optimization" />

## 素材优化产品简介

**素材优化产品**（Creative Optimization）能够针对您在所有广告投放中用到的全部素材，一站式衡量其投放效果。您可以使用这一产品轻松拉取到所有媒体渠道上的素材资产，并将其统一汇总到AppsFlyer面板，也可以将其入库到您的BI系统，从而根据您指定的维度分析其在各个广告系列、流量入口等方面的投放效果。素材效果优化功能可以帮助您按不同的指标和KPI对数据进行多角度拆解，以便在规划、选取、产出下一批素材之前掌握关键的素材效果信息。

素材优化面板能够衡量视频、图像、HTML和文本素材的效果，并让您了解这些素材在各个渠道中投放一段时间后的变化情况。我们会通过强大的AI算法对每一个素材进行分析、汇总和匹配。也就是说，AppsFlyer能够识别您在不同的广告系列和媒体渠道中使用的相同素材，即使其命名模式、广告ID或其他属性有所不同，也能将其作为同一个素材呈现在面板上。

<Anchor target="_blank" href="/marketers/zh/docs/creative-optimization-overview-dashboard">素材优化总览面板</Anchor>中各种包含大量信息的图表能让您直观地查看数据，同时也提供罗列详细信息的表格，让您掌握优化所需的全部信息，帮助您为各个广告系列选择最合适的素材。

<Anchor target="_blank" href="/marketers/zh/docs/creative-optimization-discovery-ai-dashboard">素材优化解析面板</Anchor>以AI技术为依托，让您无需再靠主观猜测来制作素材。该面板既能让您对所有素材有一个整体的了解，也可以深入分析单个场景和元素的投放效果，帮助您充分发掘关键信息。

<Anchor target="_blank" href="/marketers/zh/docs/creative-optimization-etl-reporting">素材优化ETL</Anchor>工具能让您的数据分析专员获得所有必要信息，帮助其完成素材效果分析。该工具可自动将报告传输到云存储平台，以便您通过程序化的方式将数据入库到您的BI系统。

您可以使用素材优化产品实现以下目标：

* 快速了解有效和无效的素材、场景和元素
* 以数据为依托进行素材优化
* 提升素材效果和ROI
* 打造效果最好的素材
* 针对不同时间段/渠道/广告系列中的素材，检测其投放效果下滑的情况，并做出相应的优化决策
* 以及其他

<div id="creative-assets" />

## 素材资产

本节主要说明了我们衡量的素材资产。

<div id="supported-asset-types" />

<Accordion title="适用资产类型">

素材优化面板支持以下素材资产类型：

* 视频
* 图像
* 轮播（仅限Meta）
* HTML（包括可玩型素材）
* 文本

<div id="notes" />

> 📘 **说明**
>
> * 可在面板中预览的资产类型包括图像、视频和文本。
> * 素材相似度功能尚不支持
>   轮播广告。

</Accordion>

<div id="matching-creatives" />

<Accordion title="素材匹配">

素材优化产品具有独特的素材资产识别能力，即使相同素材在多个不同渠道和广告系列中的命名模式和ID各不相同，也能将其识别出来。这一功能是通过AI技术和计算机视觉算法来实现的，这些技术能够匹配视觉语境、声音和像素。这里需要注意：

* 可成功匹配的素材必须具有相同的长宽比（如竖屏、横屏或方屏）。
* 不同时长的视频视为不同的素材。

</Accordion>

<div id="measuring-creatives-with-multiple-assets" />

<Accordion title="衡量包含多种资产的素材">

**素材优化产品如何衡量包含多种资产的广告素材？**

Meta Advantage+（动态素材）以及Google Universal App Campaigns（UAC）中可使用包含多种资产的广告素材。但AppsFlyer不会按资产来拆分数据。Meta ads提供的数据最细可拆分到**广告层级**，Google数据最多只拆分到**广告组**层级。对于这类广告素材，AppsFlyer会使用数据模型来解析各个资产的效果数据。

<div id="example" />

> 📄 **示例**
>
> 假设您在Facebook上使用了一个包含多种资产的广告素材。Meta共将100个激活归因到自己平台并将其细分到素材资产层级，具体的衡量结果为：**资产A**带来了60个激活，**资产B**带来了40个激活。假设AppsFlyer将50个激活归因到Meta上的这条广告（由于AppsFlyer和<Anchor target="_blank" href="/marketers/zh/docs/self-reporting-networks-srns">SRN</Anchor>之间的核心归因模式不同，因此数据会有差异）。为了分析素材资产层级的投放效果，AppsFlyer会根据这个素材资产层级的指标比例来分配效果数据（展示、点击、激活和成本），具体方式如下图所示：
>
> 上述示例中，**资产A的效果数据分配如下**：
> 资产A带来的60个激活除以Meta归因到的激活总数60+40=0.6，
> 然后再将0.6乘以50（即AppsFlyer归因到的激活数）=30个激活。
>
> **资产B的效果数据分配如下：**
> 资产B带来的40个激活除以Meta归因到的激活总数60+40=0.4，
> 然后再将0.4乘以50（即AppsFlyer归因到的激活数）=20个激活。
>
> AppsFlyer共将50个激活归因到该广告素材，同时会保留Meta侧的素材资产层级细分数据。也就是说在上述示例中，我们可以知道**资产A**产生的激活量大于**资产B**。
> 收入和ROAS等深层漏斗指标也会根据这个比例来计算。
>
> ![Creative_data_example_en-us.png](https://files.readme.io/ca556904829b809238b8b994fd6d762d6cb58ae993c41dd19a7de978f774e8b9-small-18564727253649.png)

</Accordion>

<div id="using-the-dashboard" />

## 使用面板

本节全面介绍了主面板中的各种内容和功能，包括筛选条件及可用指标和维度的的使用方式以及面板视图的保存方式，帮助您获取所需的素材数据并与同事分享关键信息。

[![Filter bar and metrics -Default view.jpg](https://files.readme.io/b68e65ff2cdd2ad2fe0805eb1c2792904af69504d104b6f6ae8a524124272a48-21363121543185.jpg)](https://files.readme.io/b68e65ff2cdd2ad2fe0805eb1c2792904af69504d104b6f6ae8a524124272a48-21363121543185.jpg)

<div id="filter-bar" />

<Accordion title="筛选条件栏">

面板设置的第一步就是选择数据筛选条件。您指定的所有筛选条件会对素材优化总览和解析面板同时生效。

[![filter_bar.jpg](https://files.readme.io/99da48c37938e573af66cf1f46ce3273c3ca010e68070cb59b5e12cbad1981e3-18564730224913.jpg)](https://files.readme.io/99da48c37938e573af66cf1f46ce3273c3ca010e68070cb59b5e12cbad1981e3-18564730224913.jpg)

**面板筛选条件的设置方式如下**：

1. 选择以下各项内容：
   * **应用**
   * **日期范围：** 当选定日期范围内有某个素材的转化数据时，面板就会显示该素材。所有数据均以LTV维度呈现，也就是说面板中的指标与相关素材在选定时间段内产生的转化有关。
   * [视图类型](#view-type)
2. 点击+图标，添加下列任意筛选条件，包括：
   * **维度和指标**
   * 适用于所有指标的**数值型筛选条件**，可用选项如下：
     * 大于——显示指标值大于等于指定值的素材
     * 小于——显示指标值低于指定值的素材

除了[通用指标和维度](/docs/creative-optimization-guide#standard-metrics-and-dimensions)外，素材优化面板还提供各种[专用指标和维度](#unique-metrics-and-dimensions)。

</Accordion>

<div id="view-type" />

<Accordion title="视图类型">

面板分3个视图呈现素材数据，即统一、用户获取（UA）和再营销：

* **统一**——同时显示UA和再营销广告/广告组的所有素材数据。
* **用户获取**——仅显示与UA广告/广告组有关的素材数据。
* **再营销**——仅显示与再营销广告/广告组有关的素材数据。同时也可呈现成本数据。

[![View_types.jpg](https://files.readme.io/e73cc643581e94d6fbc6455e16615eb2e1d8b387cda626d39b17bbe714122611-18564727261585.jpg)](https://files.readme.io/e73cc643581e94d6fbc6455e16615eb2e1d8b387cda626d39b17bbe714122611-18564727261585.jpg)

</Accordion>

<div id="creative-optimization-roi360" />

<Accordion title="素材优化 + ROI360">

如果您购买了ROI360产品，就会在素材优化面板中看到来自ROI360的成本数据。这些信息以广告平台上报的数据为基础，AF对其进行整合及处理并在其中添加其他以成本为基础的指标后将其呈现在面板中。如果没有ROI360，则成本信息仅包含对接渠道自身上报的数据。如需掌握最为全面、最具时效性的成本数据，建议您购买ROI360产品。下表说明了素材优化产品在使用和不使用ROI360时的差异。

| 有ROI360 | 没有ROI360 |
| --- | --- |
| <ul><li><Anchor target="_blank" href="/marketers/zh/docs/roi360-guide-cost-and-revenue-data#成本数据">通过任何ROI360方法报告的数据</Anchor>。</li><li>具备所有的ROI360成本上报功能</li><li>创意ETL包括成本数据（需要ROI360高级订阅）。</li></ul> | <ul><li>成本数据由您的集成合作伙伴直接报告，仅限于创意优化仪表板，而不包括创意ETL。</li></ul> |

进一步了解<Anchor target="_blank" href="/marketers/zh/docs/roi360-guide-cost-and-revenue-data">ROI360</Anchor>。

</Accordion>

<div id="standard-metrics-and-dimensions" />

<Accordion title="通用指标和维度">

面板中可用的通用指标/维度包括：

| 指标/维度 | 说明 |
| --- | --- |
| Impressions | 素材浏览量 |
| Clicks | 带有该素材的广告所产生的点击量 |
| 转化 | <ul><li>激活——激活相关应用的独立用户数</li><li>再互动——与再营销广告互动后打开相关应用的独立用户数</li><li>再归因——与再营销广告互动后重新安装并激活应用的独立用户数</li></ul> |
| 成本 | 素材成本 |
| CTR（点击率） | 点击广告的用户数量在总体展示量中的占比（%），计算方式为：点击量/展示量 *100 |
| CVR（转化率） | 完成点击到归因（包括激活、再互动和再归因）整条链路的用户比例（%），计算方式为：转化量/点击量 * 100 |
| IPM（每千次展示激活量） | 每千次展示激活量（IPM），即相关广告每向用户展示1000次（即广告浏览）所产生的激活数量 |
| eCPI（实际单次激活平均成本） | 计算eCPI时会剔除自然激活，得出每个<Anchor target="_blank" href="/marketers/zh/docs/about-organic-and-non-organic-installs">非自然归因</Anchor>（包括激活、再互动和再归因）的平均成本计算方式为：总体可用成本/非自然转化总量。 |
| CPM（每千次展示成本） | 即1000次广告展示的成本，计算方式为：素材总体消耗/展示次数 * 1000 |
| Platform（系统平台） | 指操作系统（如安卓） |
| Channel | 对某些媒体渠道中的流量进行细分  <br />（如Google下的YouTube，Meta ads下的Instagram等等） |
| Geo（国家/地区） | 国家/地点 |
| ID | <ul><li>Creative</li><li>Ad</li><li>Adset</li><li>Campaign</li></ul> |
| Agency（代理） | 显示选定代理的素材数据 |
| 收入（D0、D1、D3、D7、D14、D30、D60、D90） | 上报到AppsFlyer的群组收入 |
| ROAS（D0、D1、D3、D7、D14、D30、D60、D90） | 群组化的广告支出回报率（％），计算每单位广告消耗所产生的收入。计算方式为：收入/成本 * 100 |
| 独立用户数（D0、D1、D3、D7、D14、D30、D60、D90） | 从激活之日起直到您指定日期内使用过相关应用的群组化独立用户数 |
| 留存（D0、D1、D3、D7、D14、D30、D60、D90） | 在指定时间范围内持续使用您的服务或产品的群组化用户比例（%）<br /><br />**请注意：** 该数据与AppsFlyer的群组分析面板一致。 |

</Accordion>

<div id="unique-metrics-and-dimensions" />

<Accordion title="专用指标和维度">

面板中可用的专用指标/维度包括：

| 指标/维度 | 说明 |
| --- | --- |
| 使用次数 | 显示各渠道中用到某个具体素材的广告系列/广告组/广告的数量 |
| [渠道指标](/docs/creative-optimization-guide#partner-dimensions-and-metrics) | 由对接渠道直接提供的效果数据（非AppsFlyer归因数据） |
| 素材相似度 | 将极为相似（但稍有不同）的素材集中到一起，以便您对比其效果并找出最有效的版本。比如图像一致但画面方向不同（横屏与竖屏）的素材，或内容相同但语言不同的视频等等。该维度仅适用于图像和视频。 |
| 素材使用时长 | 显示相关广告系列中使用某个素材的天数。使用时长根据AppsFlyer收到的首次展示、点击或激活信息来计算（即素材的“First seen”（首次展示）时间戳），不同维度中的使用时长可能会有差异。举例来说，假设您在某天将某个素材上传到某个广告系列，然后又在另一天向另一个广告系列上传该素材，并同时使用广告系列和使用时长维度来筛选数据，面板会根据首次上传来显示使用时长。<br /><br />**请注意：** 如果某个素材在接入素材面板之前就已经用于广告投放，则AppsFlyer显示的数据最多可回溯到接入前的90天。举例来说，假设某个素材在接入面板前已经投放了90多天，这时“素材使用时长”显示为“90”，后续逐天增加。 |
| 素材首次展示 | 根据AF首次接收到效果数据（通常是展示）的时间来呈现素材。“素材使用时长”指标从首次展示的时间戳开始计算。 |
| 时长 | 素材资产的时长，以秒数呈现（适用于视频） |
| 分辨率 | 素材资产的大小，以像素呈现（适用于图像和视频）<br /><br />**请注意：** 这个数据是您的对接渠道实际向用户展示的分辨率，可能与您最初上传到到渠道的分辨率有所差异。 |
| 画面方向 | 素材资产的画面方向，如竖屏、方屏或横屏 |
| 月份 | 月度效果 |
| 周 | 周度效果 |
| 后贴卡片 | 即在视频结束时展示的广告，一般包含与广告中所宣传的应用有关的基本信息。按后贴卡片对素材分组可以进一步提炼出额外的关键信息，用于素材优化。比如对比在不同视频中的同一个后贴卡片，找出效果最好的组合。您可以按下列后贴卡片数据查看素材：<ul><li>后贴卡片名称</li><li>后贴卡片ID</li><li>后贴卡片时长</li><li>后贴卡片分辨率</li><li>后贴卡片画面方向</li><li>后贴卡片类型</li></ul>**请注意：**<ul><li>后贴卡片数据对以下渠道可用：AppLovin、IronSource、Moloco、UnityAds、Snapchat和YouAppi。<ul><li>目前仅有ironSource、Unity Ads和Snapchat这三个平台提供具有唯一性的后贴卡片名称。所有其他渠道的后贴卡片名称都与面板中的素材名称相同。</li></ul></li></ul> |

</Accordion>

<div id="custom-metrics" />

<Accordion title="自定义指标">

您还可以创建自定义指标，以最贴合您需求的方式衡量素材效果。

**请按以下方式创建自定义指标：**

1. 1. 点击面板右上角的下拉菜单，选择**自定义指标**。  
   **![Custom_metric_select.jpg](https://files.readme.io/99ca0ee30d09e42ef2798188e8d95fc4cf56ee31ad055209efadc47c9df8a859-18564742772625.jpg)**
2. **填写表格：**
   * **名称** - 填写指标名称，不能与其他指标的名称重复
   * **类型** - 在数值、百分比或货币类型中任选一个
   * **说明** - 填写简短说明（可选）
   * **指标计算公式** - 点击 **+添加计算公式**，创建公式。   
     * *指标*包括展示、点击、激活、CTR、CVR、CPM、IPM、成本、eCPI、再归因、再互动、收入、ROAS、留存、独立用户、广告数量、渠道指标
     * 结合使用各种*运算符、数字*和/或*应用内事件*
     * 您可以从下拉菜单中选择具体的应用内事件，并针对每个应用内事件分别添加各种指标，以得出极为具体的分析信息，如af\_purchase revenue + af\_login count（购买收入+登录次数）。  
       <Image alt="" src="https://files.readme.io/2b8bdaa8c1fb47c7e78b59e7e24f37aa3248800c7a3ed5cc821c2e11622a93fe-30129836915729.png" width="892px" />
3. 点击**保存**。  
   完成以上步骤后，您自定义的新指标即创建成功，会显示在筛选条件栏以及表格设置选项中，一旁标有“自定义”字样。

**请注意：**

* 您在一个账户下最多可以创建30个自定义指标。
* 您可以将鼠标悬浮在表格设置中的“自定义”标签上，查看相关说明。

您也可以修改或删除自定义指标。

**修改方式如下：**

1. 点击**编辑现有自定义指标**下拉菜单（位于**自定义指标**表格中），选择您需要修改的指标。  
   <Image alt="" src="https://files.readme.io/b792e08152482bed11ea8ce5ea5795c3df961c257d07397b5b4d787f40a8ea2e-30129836916369.png" width="892px" />
2. 根据实际需求进行修改，然后点击**保存**。  
   **请注意：** 您也可以点击**另存为**，将其保存为新的自定义指标。

**删除方式：**

* 从下拉菜单中选择您需要删除的自定义指标后，点击删除图标。  
  <Image alt="" src="https://files.readme.io/8370c5bfec23ef2ac15e266e98be357e496aef51fa14ca5b4c853b0b38910a10-30129810517393.png" width="546px" />

</Accordion>

<div id="partner-dimensions-and-metrics" />

<Accordion title="渠道维度和指标">

渠道指标是指由您的对接渠道直接提供的效果数据（非AppsFlyer归因数据）。每个渠道提供的指标有所不同，可包含展示、点击、转化、成本和视频观看时长比率等指标。您可以在筛选条件中选择这些指标、在面板和报告中查看这些指标，也可以将其添加到表格中。

下表列出了所有素材优化渠道，及其在以下各方面的数据颗粒度：

* 维度
* 由广告平台上报的指标
* 支持的功能及其特征

下载文件：<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTQLUxhNMmBPTlm1_KsfLTupNL6tgZeqAt5OFwzLJUmhSXZ7K18aX6enuV4ST1mUVarUV-KPrUnMYS6/pub?output=csv">CSV</Anchor>、<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTQLUxhNMmBPTlm1_KsfLTupNL6tgZeqAt5OFwzLJUmhSXZ7K18aX6enuV4ST1mUVarUV-KPrUnMYS6/pub?output=xlsx">XLS</Anchor>

<div id="to-set-up-partner-metrics" />

#### **请按以下方式设置渠道指标：**

只需添加一个新的<Anchor target="_blank" href="/marketers/zh/docs/creative-optimization-partner-integrations">渠道对接</Anchor>，适配渠道的指标就会自动同步到素材优化面板（**Unity Ads除外，详见特别说明**）。设置完毕后，这些指标一旁会标有“渠道”字样。

![partner metrics image.jpg](https://files.readme.io/074948fd8e4707c1353b6f8ce387e76e04801eeef397e94a604619bc8a0ad420-18564730240145.jpg)

**特别说明及注意事项：**

<div id="applovin-metrics" />

<Accordion title="AppLovin指标">

**请注意：**

* 由于AppLovin API的限制，历史数据最多仅可回溯45天。一般情况下，AppsFlyer最多可以呈现90天的历史数据，但AppLovin的历史数据可用性受这一限制影响，最多只有45天。
* AppsFlyer的素材优化数据与AppLovin的概率报告（非计费报告）数据一致。

</Accordion>

<div id="google-ads-metrics" />

<Accordion title="Google Ads指标">

**请注意：**

* Google Ads上报的激活数量会与AppsFlyer的数据有所差异，这是因为两个平台的归因逻辑不同。
* 所有指标的Google数据和AppsFlyer数据之间都会有差异，这是因为Google的渠道指标根据Google的素材资产浏览数据计算，而AppsFlyer的指标则根据Google的广告组浏览数据计算。两者对于其他效果指标所呈现的数据也不会完全一致，比如某个广告组下的素材资产总体展示次数会与该广告组上报的总体展示量有所差异。
* 素材优化产品与Google AdWords平台之间有也有差异；在对比Googl和AppsFlyer之间的素材资产浏览数据时，您可能会发现两者之间有细微的差别，这是因为：1. 时区不同（素材优化产品的时区为UTC+0）。2. 数据时效性不同（事件发生时间vs.平台提供相关数据的时间）。

</Accordion>

<div id="meta-ads" />

<Accordion title="Meta Ads指标">

**请注意：**

* Meta ads上报的激活数量会与AppsFlyer的数据有所差异，这是因为两个平台的归因逻辑不同。
* Meta不上报iOS中素材资产级别的激活数据，因此该数据在素材面板中不可用。

</Accordion>

<div id="unity-ads-metrics" />

<Accordion title="Unity Ads指标">

**如需获取Unity Ads**

1. 点击素材优化面板右上方的⋮图标，进入**素材对接**部分。  
   ![icon for creative integrations.jpg](https://files.readme.io/5af3cc395743cf305a9d19dca41dc53c7cbf82e18434d2eb335c9e58a4245456-21366803702033.jpg)
2. 点击 **+新对接**。
3. 在**渠道**下拉列表中选择**Unity Ads**。  
   ![New integration - Unity Ads.jpg](https://files.readme.io/8a03c4b50287768cd95217af142ec551c8526b2cf5f7f7af06c04704a868093d-18564745005073.jpg)
4. 输入用于该对接的Unity **Key ID**、 **Secret Key**以及**Organization Core ID**（请参考Unity对接说明，了解获取这些信息的方式）。
5. 在**渠道指标**部分输入Unity的**API Key**以及**Organization ID**。您可以按照下文说明来获取这些证书信息。**请注意：** 如果您有Unity Ads的ROI360成本对接，也可以使用其中的证书完成上述操作。
   * **API key的获取方式如下：**
     1. 登入您的Unity Gaming Service账号。
     2. 点击侧边栏中的**Products**，然后点击**Grow**。  
        ![Unity Org ID step 1.jpg](https://files.readme.io/79d445c8588ef6fa7b34ad8983d068b80a7ab733e7dd9906ad079fa647b3e10b-20348482802833.jpg)
     3. 点击**Unity Ads User Acquisition**。  
        <Image alt="Unity Org ID step 2.jpg" src="https://files.readme.io/1e0efbece8777100ac7046f09c52887f52bc5fba2e28c724298340afe78ba8f4-20348466710545.jpg" width="312px" />
     4. 点击**API management**。  
        ![Unity-from API mngmt, get API key w arrow.jpg](https://files.readme.io/c617593d5935fbe8072d9fac0146fb3257c395c8dcf173130b97cc2a4a043285-20348783332881.jpg)
     5. 复制该API key。
   * **Organization ID的获取方式如下：**
     1. 进入Unity Ads后台，点击侧边栏中的**Products**，然后点击**Grow**。  
        <Image alt="Unity Org ID step 1.jpg" src="https://files.readme.io/79d445c8588ef6fa7b34ad8983d068b80a7ab733e7dd9906ad079fa647b3e10b-20348482802833.jpg" width="583px" />
     2. 点击**Unity Ads User Acquisition**。
     3. <Image alt="Unity Org ID step 2.jpg" src="https://files.readme.io/1e0efbece8777100ac7046f09c52887f52bc5fba2e28c724298340afe78ba8f4-20348466710545.jpg" width="336px" />
     4. 点击**Settings**。  
        ![Get Organization ID instructions 2 arrows.jpg](https://files.readme.io/7514d25a8c9a7a9f64e7e5b6f9008c649cb949eff7d25c49a1693f806518e07d-20348948474897.jpg)
     5. 复制该**Organization ID**。

<div id="note" />

> 📘 **注意**
>
> 建议您在设置新的渠道对接时就输入相关的渠道指标证书，但这不是必须完成的操作。您可以先保存对接，之后再添加证书信息。但这里需要注意，我们会从渠道对接创建之时起拉取90天内的渠道数据，这时如果您未提供渠道指标证书，可能会导致数据缺失。

</Accordion>

</Accordion>

<div id="save-and-share-views" />

<Accordion title="保存并分享面板视图">

筛选条件选择完毕后，您可以保存您选定的配置，便于您快速在面板中查看所需信息，无需在每次登入时重新设置筛选条件。保存后的视图会同时对素材优化总览和解析面板生效。您可以将面板视图保存为私人视图或共享视图。共享视图对帐户下的其他用户可见，您也可以通过链接分享面板视图。

**请注意**：如果您更改面板设置后没有保存，当前视图名称右侧就会出现橘色圆点，以示提醒。

<div id="save-private-dashboard-view" />

#### **保存私人面板视图**

**请按以下方式保存私人面板视图（即仅对自己可见）：**

1. 点击当前所示面板顶部的下拉菜单图标，选择菜单中的私人图标，然后点击 **+保存为新的私人面板**。  
   ![](https://files.readme.io/c1ed2ac6917fa105641f054623ad87a562f4b80042379301c8736bffaa57a22e-25381406386065.png)
2. 为您的面板命名，然后点击**保存**。
3. 后续您可以使用菜单图标编辑或删除面板视图、更改共享设置（将“私人”切换为“共享”），或收藏视图使其在登入时默认呈现。

<div id="save-shared-dashboard-view" />

#### **保存共享面板视图**

**请按以下方式保存共享面板视图（对账户下的其他用户可见）：**

1. 点击当前所示面板顶部的下拉菜单图标，选择菜单中的共享图标，然后点击 **+保存为新的共享面板**。  
   **![](https://files.readme.io/d4a7f206d49ddea230883ee6e119caab119164fa3bee9d0c3f02d487c9cf8a36-25381406390033.png)**
2. 为您的面板命名，然后点击**保存**。  
   保存完毕后，该视图会出现在账户下所有其他用户的面板视图列表中。
3. 后续您可以使用菜单图标编辑或删除面板视图、更改共享设置（将“共享”切换为“私人”），或收藏视图使其在登入时默认呈现。

<div id="share-view-url" />

#### **分享视图链接**

**请按以下方式与账户下的其他用户分享视图链接：**

* 点击面板右上方的“复制页面链接”图标，便可分享该页面。  
  <Image alt="Copy_page_URL_with_cursor.jpg" src="https://files.readme.io/2d1cc2f9585850c1d9c723f959be96e953fe6cc90b6b2a31ac8c16bf4e7b4b8f-18564702245777.jpg" width="121px" />  
  **请注意**：即使是私人面板，也可以通过链接进行分享。当其他人打开您的私人面板链接时，报告名称会显示为“未保存的报告”。

</Accordion>

<div id="custom-tags" />

## 自定义标签

您可以根据您上传的标签或素材文件名中的标识符对素材进行分组和分析。本节介绍了创建自定义标签的各种方式，这些标签会以维度选项的形式出现在数据筛选条件中，供您在面板各部分查看。

<div id="custom-dimensions" />

<Accordion title="通过CSV文件创建自定义标签">

您可以通过CSV文件在面板中添加自定义维度以及带有相关标签的素材，并使其与在投广告中使用的素材一致。该功能可让您按照最贴合实际需求的任意自定义维度查看、梳理、排列并筛选素材。

<div id="create-and-manage-custom-dimensions" />

<Accordion title="创建并管理自定义维度">

自定义维度的创建和管理流程包含以下3个步骤：

1. 从素材优化面板中下载一个包含现行素材的CSV文件。
2. 创建新的维度或更改现有维度和标签。CSV文件中的标题列即自定义维度的名称（如“Color”）。某一列中的所有素材都会带有对应自定义维度的标签，并会呈现在面板中的相应标签下。您也可以通过CSV文件添加或更改任何自定义维度或标签。**请注意**：新的CSV不需要包括之前创建的自定义标签和维度；只需包括您想要编辑或添加的标签。
3. 将更改完毕的CSV文件上传到素材优化面板。相关数据会在大约30分钟后准备就绪。

CSV文件的下载和上传流程如下：

**如需从面板下载含有当前素材信息的CSV文件，请按以下方式操作：**

1. 单击仪表板右上角的<Image alt="3_dots_icon.png" src="https://files.readme.io/e958f262f824e2d6d259f123f550697f2916628c71cde515697e51af832d2410-18564718539665.png" width="16px" />菜单。  
   ![Main menu highlighted.jpg](https://files.readme.io/be14a3ab1a9aba6dc20816e53ad692b1697d15a185053cf523d2ae8451842350-21367268248465.jpg)
2. 点击**下载自定义标签文件**。
3. 选择该文件中需要包含的素材（可包含所有素材，或仅包含面板当前呈现的素材——即剔除不符合筛选条件的素材）。
4. 点击**下载**。

根据需要添加或修改文件内容并保存，然后将其重新上传到面板。

**向素材优化面板上传CSV文件的方式如下：**

1. 单击仪表板右上角的<Image alt="3_dots_icon.png" src="https://files.readme.io/e958f262f824e2d6d259f123f550697f2916628c71cde515697e51af832d2410-18564718539665.png" width="16px" />菜单。
2. 点击**上传自定义标签文件**。
3. 选择一个文件，将其上传。  
   请务必先了解上传CSV文件时需要考虑的各种[特点和局限性](/docs/creative-optimization-guide#traits-and-limitations)。
4. 点击**上传到面板**。

相关数据会在上传完毕后的30分钟内准备就绪。

</Accordion>

<div id="example-csv" />

<Accordion title="CSV文件样例">

下方展示了自定义维度CSV文件的样例（可从面板下载该文件）。各标题列（第1行）即自定义维度的名称（如“Theme”和“Variant”）。您可以添加其他维度或更改现有维度，也可以添加或更改标签（如“3 Moves”或“DarkPalette”）。

[![Screen_Shot_2022-08-08_at_16.25.23.png](https://files.readme.io/33137d3c8eab51069a3863a2af193d2192cd28546442abcaf8b74073e737c63e-18564702296977.png)](https://files.readme.io/33137d3c8eab51069a3863a2af193d2192cd28546442abcaf8b74073e737c63e-18564702296977.png)

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="自定义维度的特点和局限性">

* 自定义维度会在筛选条件和表格中以“自定义”字样标出。

<Image alt="Custom_tag.png" src="https://files.readme.io/f8003396943a406dec2b825f4a4725aeb2f0ea3b23f3c67643cc0c096321b401-18564730363025.png" width="477px" />

* 您最多可以在素材优化面板中添加15个自定义维度。
* 上传的文件不能超过1 MB。
* 如需更改现有维度和标签的名称，只需修改并重新上传相关CSV文件即可。**请注意**：每次上传仅可更新或添加一个维度。
* CSV文件中的自定义维度会在账户层级生效，也就是说该账户下的所有应用和用户都可以使用这些维度。
* 每个素材的各维度下可各含一个标签。举例来说，假设自定义维度是“Color”，这时仅可使用一种颜色作为标签，比如red（红色）。
* 创建或编辑自定义维度时，切勿更改creative\_id字段，避免数据被覆盖或出现差异。

</Accordion>

</Accordion>

<div id="name-convention-tags" />

<Accordion title="命名模式标签">

您可以根据您的素材资产命名模式来创建自定义标签。这些自定义标签会以维度选项的形式出现在数据筛选条件中，供您在面板各部分查看。

这一功能尤其适用于营销和素材团队，因为这两个团队对于素材的命名方式往往带有特定的用意，会在名称中设定一些具有唯一性的标识符。AppsFlyer会根据这些内置的标识符自动为素材打标，并对其进行分组，用于分析和优化。

<div id="create-and-manage-name-convention-tags" />

<Accordion title="创建和修改命名模式标签">

**命名模式标签的创建方法如下：**

1. 点击面板右上方的 ⋮ 图标，选择**命名模式标签**。  
   界面会显示**管理命名模式标签**的窗口。  
   <Image alt="Name convention tags main window.jpg" src="https://files.readme.io/e59721daabccd23ae7735d3e8cca68194983a3c28453daf00bf0ab39ad76fa98-18564727397393.jpg" width="795px" />
2. 在**创建新的命名模式类型**下输入以下信息：
   * **名称**——为新的命名模式类型赋予具有唯一性的名称。
   * **分隔符**——用于分隔名称各段的字符，比如在名为“enUS\_bluegalaxy\_launch.mp4”的素材中，其名称的各段以“\_”分隔，这时“\_”即为分隔符。
   * **分段总数**——比如在名为“enUS\_bluegalaxy\_launch.mp4”的素材中，共有3个以“\_”分隔的分段。  
     **请注意：** 文件类型不能作为标签。
   * **应用**（可选）——您可以让标签对所有应用的素材生效，或仅对与具体应用相关的素材生效。
   * **媒体渠道**（可选）——您可以让标签对所有媒体渠道上的素材生效，或仅对在具体渠道上投放的素材生效。
3. 添加自定义标签信息：
   * **分段编号**——选择该标签所对应的名称分段编号。
   * **自定义标签名称**——点击 **+创建新的自定义标签**创建标签名称，或从现有名称中选择一个。
   * **格式** - 选择相关标签在表格/面板中的呈现方式：大写、小写或原始格式（即按素材名称原样保存）。  
     您还可以点击 **+添加自定义标签**，添加其他自定义标签。
4. 保存标签之前，您还可以点击**下载预览文件**，预览自定义标签在素材中的生效方式（可选）。预览文件中包含所有与该命名模式类型相匹配的素材，且均按新建的标签打标。
5. 点击**保存**。  
   保存后这些标签即会生效，您在数小时内便可在面板中查看这些标签。

**命名模式标签的更改方法如下：**

1. 点击面板右上方的 ⋮ 图标，选择**命名模式标签**。
2. 点击**编辑命名模式类型**，在下拉菜单中选择您要修改的类型。
3. 根据需要修改标签，然后点击**保存**。

**命名模式类型的删除方法如下：**

1. 点击**编辑命名模式类型**，在下拉菜单中选择您要删除的类型。
2. 将鼠标悬停在您选定的选项右侧，点击<Image alt="Delete icon.jpg" src="https://files.readme.io/a4bb54fefcdd474edbb897dc334b8219c36273fd5e4f45a03e1b39091856e137-18564742905873.jpg" width="19px" />图标。  
   **请注意：** 删除命名模式类型后，您的素材将不再带有相关的自定义标签。该变更会在数小时后生效。

<div id="name-tag-traits-and-limitations" />

<Accordion title="名称标签的特点和局限性">

* 您最多可以创建10个不同的命名模式类型（以及与其相关联的自定义标签）。
* 如果通过CSV文件上传的自定义标签与您创建的命名模式标签之间有冲突，则CSV上传标签会覆盖命名模式标签，对素材生效。

</Accordion>

</Accordion>

</Accordion>

<div id="additional-information" />

## 其他相关信息

<div id="h_01HA282W8WHHNDG75XZNSV2QQF" />

<Accordion title="特点与局限性">

| 特点 | 说明 |
| --- | --- |
| 数据来源 | 素材优化面板中的效果数据（除渠道指标外）都来源于AppsFlyer的归因模型。**请注意**：该归因模型与各类广告平台和移动广告业相关平台所使用的归因模型有本质上的不同，因此上报的数据会有所差异。 |
| 多资产素材 | 对于包含多种素材资产的素材，仅显示一种素材资产（在有视频的情况下，一般会显示视频）。 |
| 数据时效性 | 素材优化总览和解析面板每天的更新时间为在UTC+10，每次更新覆盖最近90天内的所有素材数据。也就是说，每天更新的当地时间取决于您所在的地理位置，您可以根据“**0 UTC + 10 + 当地时区**”来计算更新的当地时间。<br /><br />**示例：**  <br />纽约：0 UTC + 10 - 5 = 5:00  <br />柏林：0 UTC + 10 + 1 = 11:00  <br />上海：0 UTC + 10 + 8 = 18:00<br /><br />**请注意**：素材优化面板与AppsFlyer数据总览面板之间可能会有一些数据差异，这是因为这两个面板的数据时效性有所不同（素材优化面板每天更新一次，数据总览面板每天更新数次）。 |
| 货币 | 素材优化产品中的所有货币指标都以美元（USD）为单位。 |

</Accordion>

<div data-zendesk-anchors="overview=%E7%B4%A0%E6%9D%90%E4%BC%98%E5%8C%96%E4%BA%A7%E5%93%81%E7%AE%80%E4%BB%8B 01H7SZ8R9ZWZ81WHV26P00YAYP=%E7%B4%A0%E6%9D%90%E4%BC%98%E5%8C%96%E4%BA%A7%E5%93%81%E7%AE%80%E4%BB%8B creative-assets=%E7%B4%A0%E6%9D%90%E8%B5%84%E4%BA%A7 01H7SZ8RA14Q5D32EY5J0WMVYA=%E7%B4%A0%E6%9D%90%E8%B5%84%E4%BA%A7 01H7SZ8RA1C863VRG1P10CJHTR=supported-asset-types h_01HMXES26N1X3KAFRKKCC9NFXW=%E8%AF%B4%E6%98%8E 01H7SZ8RA1D9JVG1145CAXEZFX=matching-creatives 01H7SZ8RA191221K683N1Z9R69=measuring-creatives-with-multiple-assets 01H7SZ8RA1KRPFF9AW5P4QKQXH=%E7%A4%BA%E4%BE%8B creative-dashboard=%E4%BD%BF%E7%94%A8%E9%9D%A2%E6%9D%BF 01H7SZ8RA1JX2TCQHB5XW21EK8=%E4%BD%BF%E7%94%A8%E9%9D%A2%E6%9D%BF 01H7SZ8RA1ATSBZPMFJC0T7HRG=filter-bar 01H7SZ8RA1RT91HKKD0R93T2TA=view-type h_01HJDKZWTQVTPSJXP2HWSMD8W6=creative-optimization-roi360 h_01H9JS005MCGMPJM7NYTW2HCAF=standard-metrics-and-dimensions 01H7SZ8RA222QS1AXDKT49DEK3=unique-metrics-and-dimensions 01H7SZ8RA23SCGJ435B4V32CP1=custom-metrics 01H7SZ8RA2R9N2NC6JXNZZ7C5Z=partner-dimensions-and-metrics partner-table=%E8%AF%B7%E6%8C%89%E4%BB%A5%E4%B8%8B%E6%96%B9%E5%BC%8F%E8%AE%BE%E7%BD%AE%E6%B8%A0%E9%81%93%E6%8C%87%E6%A0%87 01H7SZ8RA2VJ9466WSMN3WHR90=%E8%AF%B7%E6%8C%89%E4%BB%A5%E4%B8%8B%E6%96%B9%E5%BC%8F%E8%AE%BE%E7%BD%AE%E6%B8%A0%E9%81%93%E6%8C%87%E6%A0%87 01H8GHNPQKS7REZ9RPH0ZYEBHE=applovin-metrics 01H8GHNPQKCKMDS8AYETEDDZKH=google-ads-metrics 01H8H1GTRV7VNJDKFEF35HCNKY=meta-ads 01H7SZ8RA28T63K3NASWC92R0F=unity-ads-metrics 01H7W4JTRSJJ2R45JQVYHMYGX2=%E6%B3%A8%E6%84%8F 01H7SZ8RA3TPD6ED2HJZGTVRMS=save-and-share-views save-private-dashboard-view=%E4%BF%9D%E5%AD%98%E7%A7%81%E4%BA%BA%E9%9D%A2%E6%9D%BF%E8%A7%86%E5%9B%BE h_01HYT77DSHZ6FE0MSQS83FRGW0=%E4%BF%9D%E5%AD%98%E7%A7%81%E4%BA%BA%E9%9D%A2%E6%9D%BF%E8%A7%86%E5%9B%BE save-shared-dashboard-view=%E4%BF%9D%E5%AD%98%E5%85%B1%E4%BA%AB%E9%9D%A2%E6%9D%BF%E8%A7%86%E5%9B%BE 01HYT89BRYKRG44AT9MZWKZJNY=%E4%BF%9D%E5%AD%98%E5%85%B1%E4%BA%AB%E9%9D%A2%E6%9D%BF%E8%A7%86%E5%9B%BE share-view-url=%E5%88%86%E4%BA%AB%E8%A7%86%E5%9B%BE%E9%93%BE%E6%8E%A5 h_01HYT8GXVJV8Q6GKBDHTTJ1SM2=%E5%88%86%E4%BA%AB%E8%A7%86%E5%9B%BE%E9%93%BE%E6%8E%A5 custom-tags=%E8%87%AA%E5%AE%9A%E4%B9%89%E6%A0%87%E7%AD%BE h_01H9J4Z9V9SJBTE63C358FME95=%E8%87%AA%E5%AE%9A%E4%B9%89%E6%A0%87%E7%AD%BE h_01H9J4R9MTMGF9F1PNZRT2QZ1W=custom-dimensions 01H7SZ8RA3GW927GJBKKR4582T=create-and-manage-custom-dimensions 01H7SZ8RA3P8VQFH268G453FKM=example-csv 01H7SZ8RA307CBMA0533M3VGWK=traits-and-limitations h_01H9J67GSXXZ20W56NDVW2XDJC=name-convention-tags h_01H9J6PCQNVAB88ZCKRT3MVJEH=create-and-manage-name-convention-tags h_01H9J6PCQN6MV2KPYNFF7SB44Q=name-tag-traits-and-limitations additional-information=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF h_01J1VPMV85CT5ZJNN3BW4FCW0D=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF" />
