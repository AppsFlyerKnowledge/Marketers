---
title: 群组与留存面板
metadata:
  keywords:
    - Cohort
    - Cohort Report
    - Advertisers
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2015-12-24T10:20:01Z'
  edited_at: '2026-10-14T10:15:08Z'
  id: 207040496
  locale: zh-cn
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/zh-cn/articles/207040496
---
> **概要：** 群组与留存面板（简称“群组面板”）会根据激活日期将用户分组，并对用户整个生命周期（LTV）内的投放效果进行分析。您可以通过该面板深入了解投放差异对效果指标的影响。

[![cohort main (2).png](https://files.readme.io/5a9307f4220a5bc41b5cebefe345a9b93165ac3874dd4faaed184d0309e92615-small-32127933337873.png)](https://files.readme.io/5a9307f4220a5bc41b5cebefe345a9b93165ac3874dd4faaed184d0309e92615-small-32127933337873.png)

<div id="cohort-and-retention-dashboard" />

## 群组与留存面板

相关文档： <Anchor target="_blank" href="/marketers/zh/docs/aggregated-and-analytics-reporting-overview#cohort-flavors">群组功能各种形式之间的差异</Anchor>

您只需要选择一个或个多应用的用户，并将其按转化时间分组，可用的群组指标包括收入、ROI和事件转化率等。您可以将相关用户群组按广告系列或媒体渠道等维度进行拆分，以便对比分析。这有助于您发现用户或广告系列的生命周期内出现的某些规律或变化。详情请见<Anchor target="_blank" href="https://www.appsflyer.com/blog/cohort-report-mobile-marketing-kpis/?utm_campaign=Blog%20Subscription%2003-2019&utm_source=hs_email&utm_medium=email&utm_content=76370689&_hsenc=p2ANqtz-8SX49xuEw2WX_Vrlh11_zxlDFvlfMpBzSQm1I-nFhc0WbZDf0ACC-VEi4qmKhesHCsUNdhU50Oinl-urwnGAOZMwwHSTp6UgdChCi7ARayJFUFTus&_hsmi=76370689">群组功能的使用场景</Anchor>。

<div id="tip" />

> 👍 **提示**
>
> 如需进一步了解群组报告，我们在<Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7804/play/18625/your-users-journey-with-retention-and-cohort-reports">AppsFlyer充电站里为您准备了相关课程</Anchor>，视频虽短，但干货满满！

<div id="using-cohort" />

## 群组面板使用指南

<div id="setting-up-an-analysis" />

<Accordion title="设置分析报告">

1. 从AppsFlyer后台的侧边栏中选择**分析** > **群组与留存**。  
   界面会打开群组面板，并显示颗粒度和转化日期范围的选项。  
   ![mceclip0__1_.png](https://files.readme.io/4113fd619422979d6a26004a55c009ebc48eef59d10ddc7c3e5becd2a758e6d4-32127949494417.png)
2. 选择[群组周期颗粒度](/docs/cohort-and-retention-dashboard#cohort-periods)：
   * 小时数
   * 天数
   * 周
   * 月
3. 设置归因时间段（用户获取或再营销互动）。如果您选择的日期离当前日期很近，可能会出现[数据不完整](/docs/cohort-and-retention-dashboard#partial-data)的情况，在图标和表格中会以破折号来标记。
4. 点击**编辑群组**。  
   界面会打开群组设置窗口。  
   <Image alt="CohortSetup.jpg" src="https://files.readme.io/f09cc190770d16a2ddf60e1f210f458114ac43d4c19fc5507fb50b0d1d2f5c77-32127949495825.jpg" width="365px" />
5. 请设置以下各项内容：
   * [**面板视图类型**](/docs/cohort-and-retention-dashboard#view-types)：
     * **用户获取**
     * **再营销**
     * **统一：** 同时包含拉新和再营销的应用内事件。**请注意**：再营销事件的优先级高于拉新事件，也就是说报告显示的是<Anchor target="_blank" href="/marketers/zh/docs/raw-data-reporting-overview">is\_primary\_attribution=true</Anchor>的事件。
   * [**趋势类型**](/docs/cohort-and-retention-dashboard#trend-types)：
     * **用户生命周期内的投放效果**
     * **基于归因时间的KPI趋势**
   * **用户范围**：选择一个或多个应用。若选择**所有**应用，则覆盖您账户中最靠前的100个应用。**请注意**：代理商只能选择一个应用。
   * **分组维度**： 选择一个或多个[维度](/docs/cohort-and-retention-dashboard#list-of-dimensions-for-grouping-and-filtering)进行分组（默认 分组维度为媒体渠道）。
   * **最小群组体量**：设置最小群组体量，以避免您的报告中出现过多因体量太小而无统计意义的群组（默认为1）。
   * 可选设置：
     * **筛选条件**： 选择一个或多个[维度](/docs/cohort-and-retention-dashboard#list-of-dimensions-for-grouping-and-filtering)进行筛选。筛选条件没有默认设置。
6. 点击**应用更改**。
7. 选择您想要进行群组分析的相关指标（KPI）。对于应用内事件，您需要同时指定相关的应用内事件以及指标。
8. 选择您要查看的群组周期。及转化后的第几个小时、第几天、第几周或第几个月。可供选择的群组周期数量取决于您选定的趋势类型。
9. 选择是否要包含**不完整数据**，还是仅显示**完整数据**（即已完结的群组周期的数据）详情请见不完整数据与完整数据的对比说明。
10. 选择让面板显示**累计**或**当天**（小时/天/周/月）数据：
    * **累计**：意为该指标的累计总和或流水总计。也就是说群组3会显示群组周期0-3的总和。
    * **当天**：仅显示相关指标在当天的值。也就是说，群组3仅显示群组周期3内的指标值，不计入之前周期的数据。
11. 选择是否显示**热力图**。
12. 选择数据呈现方式：表格或图表。如果您选择了表格，还可以选择表格中包含的数据行数，分别有25、50、100和200这四个选项。
13. 【可选】[管理已保存的群组报告](/docs/cohort-and-retention-dashboard#using-my-reports-save-and-select-reports)。

</Accordion>

<div id="using-my-reports-save-and-select-reports" />

<Accordion title="“我的报告”使用指南">

* 您可以通过“我的报告”保存当前的面板设置，以便后续使用。
* 选择已保存的报告后，面板会基于该报告的设置显示最新的群组数据。
* 您可以保存一个或多个报告。
* 只有您本人可以查看“我的报告”。

| 功能 | 说明 |
| --- | --- |
| 我的报告 | ![MyReports.png](https://files.readme.io/8f49c0e6dee55427bf3a64149ac48f67547967b8cd24aa8de3e34b760708f992-32127933340305.png)<br /><br />选择报告，查看相关的最新数据 |
| 保存更改 | 保存报告。请注意：这会覆盖当前选定的报告设置。 |
| 操作选项（![Elipse.png](https://files.readme.io/14b74dc6e733867bd16b6a3594f5f0856d7437462b2e0cf7c12adf11cfa295b3-32127949499409.png)） | <ul><li>**另存为新报告**<ul><li>以新的报告名称保存该报告。</li><li>【可选】将该报告设为默认报告</li></ul></li><li>**重命名**： 更改报告名称</li><li>**设为默认**： 将该报告设为默认报告（您打开群组面板时看到的报告）</li><li>**删除**：删除该报告</li></ul> |

</Accordion>

<div id="export-the-cohort-to-a-csv-file" />

<Accordion title="导出CSV格式的群组报告">

* 您可以导出CSV格式的群组报告。
* 列名称中的[partial前缀相当于面板图表和表格中显示的破折号](/docs/cohort-and-retention-dashboard#partial-data)

**请按以下步骤导出CSV格式的群组报告：**

* 点击群组报告窗口右上方的导出图标<Image alt="Download.png" src="https://files.readme.io/50af9c6cde00dada58a1bb89a9eb3e566f316c0e7336af68f4ce403584047a5b-32127933341969.png" width="21px" />。  
  完成CSV群组报告的下载。

</Accordion>

<div id="cohort-concepts" />

## 群组概念

<div id="cohort-periods" />

<Accordion title="群组周期">

群组周期的原理如下：转化发生的当前周期为第0期，如第0个小时（Hour 0）、第0天（Day 0）、第0周（Week 0）或第0个月（Month 0）；下一个周期即为第1期，如第1个小时（Hour 1）、第1天（Day 1）、第1周（Week 1）或第1个月（Month 1），以此类推。

可用的周期数量取决于您选定的周期颗粒度：

* 以小时为单位时，最多可以显示转化后72小时内的数据。
* 以天为单位时，最多可以显示转化后180天内的数据。
* 以周为单位时，最多可以显示156周内的数据。
* 以月为单位时，最多可以显示36个月内的数据。

**请注意**：AppsFlyer平台中的群组周期不考虑具体的激活时间戳，而是对群组小时数就近取整，群组天数、周数和月数则以公历日期为准。对于根据具体激活时间戳判定群组周期（1小时为激活时间戳后的60分钟，1天为激活时间戳后的24小时，以此类推）的平台，这一逻辑可能会使其群组数据与AppsFlyer之间产生一定差异。

</Accordion>

<div id="view-types" />

<Accordion title="视图类型">

群组面板提供以下3种类型的视图：

* **统一**：
  * 用户获取和再营销广告的综合投放效果（包括成本及收入）。
  * 如果某个事件同时归因为两种转化类型，则仅将其记为再营销事件。也就是说，面板会根据实际发生的末次触达渠道来生成报告，这样的事件在原始数据中表达为<Anchor target="_blank" href="/marketers/zh/docs/raw-data-reporting-overview">is\_primary\_attribution=true</Anchor>。
* **用户获取：** 来自激活（不含重装激活，除非<Anchor target="_blank" href="/marketers/zh/docs/measure-reinstalls#attributed-to-the-first-install">额外开通</Anchor>）的效果数据
* **再营销**：来自再归因（重装激活）或再互动（应用打开）的效果数据

[![OV.png](https://files.readme.io/738bf91c1a12671b32b088993c43d4103498907a8bbe15821ddc53a0b071b876-32127949500305.png)](https://files.readme.io/738bf91c1a12671b32b088993c43d4103498907a8bbe15821ddc53a0b071b876-32127949500305.png)

</Accordion>

<div id="trend-types" />

<Accordion title="趋势类型">

群组面板提供以下2种类型的趋势：

* **用户全生命周期表现**
* **以归因时间查看KPI**

<div id="user-lifetime-performance" />

#### **用户全生命周期表现**

* 表格中的每一列以及图表中的每一个点分别代表一个单独的群组周期（小时/天/周/月）。转化发生的当前周期为群组第0期，如第0个小时（Hour 0）、第0天（Day 0）、第0周（Week 0）或第0个月（Month 0）；转换后的第一个周期即为群组第1期，如第1个小时（Hour 1）、第1天（Day 1）、第1周（Week 1）或第1个月（Month 1），以此类推。这样，您就能从转化发生的当前周期开始，对用户转化后的效果指标进行对比分析。
* 您可以通过选择群组周期来指定面板数据的范围，可用的周期数取决于您选定的群组周期颗粒度（小时/天/周/月）。

<div id="kpi-by-attribution-time" />

#### **以归因时间查看KPI**

* 表格中的每一列以及图表中的每一个点分别代表选定日期范围内一个单独的群组周期（小时/天/周/月）。从而评估一段时间内的投放效果变化，并查看基于转化日期的投放KPI。
* 您在指定面板数据的范围时最多可以选择5个群组周期。
* 如果您选择以图表而非表格的形式查看数据，相关图表进显示1个群组周期（所选范围内的最小周期数）。

<div id="example-user-lifetime-performance-trend-vs-kpi-by-attribution-time-trend" />

#### 示例：用户生命周期内的投放效果趋势 vs 基于归因时间的KPI趋势

在此示例中，面板基于相同的原始数据生成了两种不同的群组趋势图。原始数据表中包含了A、B、C、D四位用户的归因事件。这些用户与某个广告互动后下载了应用，并在激活后完成了一次或多次购买事件。用户激活当天即同类群组第0天。

[![CohortExample_en-us.jpg](https://files.readme.io/7542605e2bb3972dc90fb12c9d6a328ff52ec65f0694a79752380d548e72e286-32127949500817.jpg)](https://files.readme.io/7542605e2bb3972dc90fb12c9d6a328ff52ec65f0694a79752380d548e72e286-32127949500817.jpg)

</Accordion>

<div id="partial-data" />

<Accordion title="不完整数据与完整数据">

如果自转化日期起到转化日期范围内的某一天少于同类群组天数，则该同类群组日中包含不完整数据。也就是说，只要同类群组天数 > 当前日期-转化日期时，就会出现不完整数据。

使用不完整/完整数据选项来选择数据显示模式：

* 【默认】**不完整数据**：
  * 归因数据实时滚动更新，包括收入数据。
  * 成本数据每天更新6次，平均每4小时更新一次。
  * 包含不完整数据（在表格和图表中以破折号标记）。
* **完整数据：** 数据每天更新，且在零点过后的几分钟内就会反应到面板上。未完结日期的数据不显示。

</Accordion>

<div id="list-of-dimensions-for-grouping-and-filtering" />

<Accordion title="分组及筛选维度">

| 维度 | 注意事项 | 分组维度 | 筛选 |
| --- | --- | --- | --- |
| <span id="ad"></span>广告 |  | ✓ | ✓ |
| <span id="ad-id"></span>广告ID |  | ✓ | ✓ |
| <span id="adset"></span>广告组 |  | ✓ | ✓ |
| <span id="adset-id"></span>广告组ID |  | ✓ | ✓ |
| <span id="agency"></span>代理 |  | ✓ | ✓ |
| <span id="apps"></span>应用 | 报告包含多个应用时适用 | ✓ | **x** |
| <span id="attributed-touchtype"></span>归因到的触点类型 | 可能出现的值为：click（点击）、impression（展示）或NA（即自然量） | ✓ | ✓ |
| <span id="campaign"></span>广告系列 |  | ✓ | ✓ |
| <span id="campaign-id"></span>广告系列ID |  | ✓ | ✓ |
| <span id="channel"></span>流量入口 |  | ✓ | ✓ |
| <span id="conversion-type"></span>转化类型 | 群组类型取决于以下因素：<ul><li>**用户获取**：激活</li><li>**再营销**：再互动、再归因</li></ul> | ✓ | ✓ |
| <span id="country-geo"></span>国家/地区 | 根据用户的IP地址得出 | ✓ | ✓ |
| <span id="time-in-the-case-of-daily-granularity-is-the-date-hourly-granularity-is-the-hour-of-the-day-weekly-granularity-is-the-week-of-the-year-monthly-granularity-is-the-month-of-the-year"></span>时间，分为以下颗粒度：<ul><li>以天为单位时：日期</li><li>以小时为单位时：一天中小时数</li><li>以周为单位时：一年中的周数</li><li>以月为单位时：月份</li></ul> | 群组类型取决于以下因素：<ul><li>**用户获取及统一**：用户首次打开应用的时间。</li><li>**再营销**：用户与再营销广告互动后首次打开应用的时间。</li></ul> | ✓ | **x** |
| <span id="install-app-store"></span>带来激活的应用商店 | 适用于使用安卓<Anchor target="_blank" href="/marketers/zh/docs/set-up-multi-store-android-attribution">多商店归因的应用。</Anchor> 如需启用该维度，请联系您的CSM。 | ✓ | ✓ |
| <span id="keywords"></span>关键词 | 由对接渠道提供的搜索关键词 | ✓ | ✓ |
| <span id="media-source"></span>媒体渠道 |  | ✓ | ✓ |
| <span id="revenue-type"></span>收入类型 | 分为应用内购买和广告收入 | **x** | ✓ |
| <span id="site-id"></span>子渠道ID |  | ✓ | ✓ |
| <span id="sub-param-1"></span>可配置参数1 |  | ✓ | ✓ |

</Accordion>

<div id="metrics-available" />

<Accordion title="可用指标">

| 指标 | 说明 |
| --- | --- |
| 激活 | 选定时间范围内的激活数量 |
| 再营销转化 | 选定时间范围内的再营销转化（再归因和再互动） |
| 归因触点 | 选定时间范围内的激活、再互动和再归因数量 |
| 成本 | <ul><li>通过点击或API上报到AppsFlyer的投放成本</li><li>成本指标在以下情况中不可用：<ul><li>视图类型为“再营销”时。</li><li>颗粒度为小时数时。</li></ul></li></ul> |
| Average eCPI | 平均有效激活（归因到的转化）成本：成本 / 归因数量 |
| 收入 | 上报到AppsFlyer的收入（累计或当天，具体取决于您的设置） |
| 收入事件数 | 收入事件的发生次数（累计或当天，具体取决于您的设置） |
| ARPU | 每用户平均收入：收入/独立用户数 |
| 平均收入事件数 | 上报到AppsFlyer的平均收入事件数量（累计或当天，具体取决于您的设置） |
| Session数（累计） | 应用打开、在前台运行或其他埋点（具体取决于开发侧）的累计触发次数 |
| 平均session数（累计） | 应用打开、在前台运行或其他埋点（具体取决于开发侧）的每用户平均触发次数（累计） |
| Session数（当天） | 应用打开、切到前台运行或其他埋点（具体取决于开发侧）的当天触发次数 |
| 平均session数（当天） | 应用打开、在前台运行或其他埋点（具体取决于开发侧）的每用户平均触发次数（当天） |
| 留存 | 留存率：当天打开相关应用的独立用户数 / 转化量 *100 |
| ROI | <ul><li>投资回报率：（收入-成本）/成本 * 100</li><li>成本指标在以下情况中不可用：<ul><li>视图类型为“再营销”时。</li><li>颗粒度为小时数时。</li></ul></li></ul> |
| ROAS | <ul><li>广告支出回报率：收入/成本 * 100</li><li>成本指标在以下情况中不可用：<ul><li>视图类型为“再营销”时。</li><li>颗粒度为小时数时。</li></ul></li></ul> |
| 卸载数量 | <ul><li>激活后卸载相关应用的用户数（仅适用于用户获取）</li><li>成本指标在以下情况中不可用：<ul><li>视图类型为“再营销”或“统一”。</li><li>颗粒度为小时数时。</li></ul></li></ul> |
| 平均卸载数量 | <ul><li>激活后卸载应用的平均用户数（仅适用于用户获取）</li><li>成本指标在以下情况中不可用：<ul><li>视图类型为“再营销”或“统一”。</li><li>颗粒度为小时数时。</li></ul></li></ul> |
| IAE数量 | 相关应用内事件的完成次数（（累计或当天，具体取决于您的设置） |
| 平均IAE数量 | 相关应用内事件的平均完成次数（累计或当天，具体取决于您的设置） |
| IAE收入 | 应用内事件产生的收入（累计或当天，具体取决于您的设置） |
| 平均IAE收入 | 应用内事件产生的平均收入（累计或当天，具体取决于您的设置） |
| IAE独立用户 | 完成相关应用内事件的独立用户数（累计或当天，具体取决于您的设置） |
| IAE转化量（累计） | 应用内事件转化率：完成相关IAE的累计独立用户数 / 转化量 * 100 |
| IAE转化量（当天） | 应用内事件转化率：当天完成相关IAE的独立用户数 / 转化量 * 100 |
| eCPA | 实际单次事件成本：成本/完成该事件的累计独立用户数。 |

</Accordion>

<div id="additional-information" />

## 其他相关信息

<div id="cohort-for-agencies" />

<Accordion title="代理商的群组面板使用指南">

* 广告主需向代理商开放群组面板使用权限。
  * 如需为代理开通权限，广告主须按完成以下操作：
    1. 从AppsFlyer的侧边栏中选择**协作** > **活跃对接**。
    2. 选择代理商。
    3. 在授权选项卡中选择**允许代理商访问您的留存及群组报告**。
* 代理只能查看由其自身带来的流量所产生的相关数据，看不到自然量或其他来源的非自然量产生的数据。

</Accordion>

<div id="use-cases" />

<Accordion title="使用场景">

<div id="revenue-sum-by-geo" />

#### 按国家/地区加总的收入

**图表：用户人均累计收入**

[![Screenshot 2023-10-31 at 16.56.31.png](https://files.readme.io/cde4e25a051e159cd4e1a1f192eda79df1d3df6f5891fcda2c24a01e0baa462b-small-32127949501201.png)](https://files.readme.io/cde4e25a051e159cd4e1a1f192eda79df1d3df6f5891fcda2c24a01e0baa462b-small-32127949501201.png)

**表格：每日收入**

[![cohort use case 2.2.png](https://files.readme.io/be3949a33cdf489eb7735acbf06c7abbecfd46f84a20d463e50ddfe815cc3368-small-32127949501969.png)](https://files.readme.io/be3949a33cdf489eb7735acbf06c7abbecfd46f84a20d463e50ddfe815cc3368-small-32127949501969.png)

<div id="in-app-event-conversion" />

#### 应用内事件转化

如果广告主将某个应用内事件定义为af\_purchase，群组数据表就会显示该群组中完成购买事件的用户占比。以下图为例，根据图中数据表可知：在第10天时，归因到Facebook Ads的群组用户中有36.27%完成了购买[。](https://files.readme.io/e365c6b930d765d97155b1fd4384a608cb7eb0339b2b61e4598ee2d5d17d3249-32127949502481.png)

[![cohort use case 3.png](https://files.readme.io/d2709ec30a9f6cc3fe55503af557153b6a2677948d0ca0b9a477af9e47746c33-small-32127933347089.png)](https://files.readme.io/d2709ec30a9f6cc3fe55503af557153b6a2677948d0ca0b9a477af9e47746c33-small-32127933347089.png)

</Accordion>

<div id="faq" />

<Accordion title="常见问题解答">

| 问题 | 答案 |
| --- | --- |
| 能否查看Apple Search Ads的<Anchor target="_blank" href="/marketers/zh/docs/apple-ads-integration-setup#analyze-keyword-cost">关键词成本与ROI</Anchor>？ | 可以。  <br />Apple Search Ads会向AF上报每个关键词每天的成本，并可细分到广告系列/广告组/广告。**请注意：** 无法按地理位置/国家细分成本。 |
| 为什么有些媒体渠道会在报告中多次出现？ | <ul><li>如果同一个广告系列名称对应了多个广告系列ID，那么报告中会多次出现该系列名称</li><li>建议广告系列ID与广告系列名称一一对应</li><li>广告系列名称变更后，数据会对应到最近使用的广告系列名称。</li></ul> |
| 能否查看自然用户数据？ | 群组报告默认包含自然量数据。<br /><br />**如仅需在群组报告中查看自然量数据，请完成以下操作：**<ol><li>点击**群组面板**中的**编辑群组**按钮。</li><li>在群组设置窗口中，将**筛选条件**下的**媒体渠道**设置为**自然流量**，如下图所示：[![cohort_setup_filtered_by_media_source_is_organic.png](https://files.readme.io/ba95397eac2b66a365a2aabb2f56587e78624be5ecd06dd6c0463e19dfe9e26a-32127949503889.png)](https://files.readme.io/ba95397eac2b66a365a2aabb2f56587e78624be5ecd06dd6c0463e19dfe9e26a-32127949503889.png)</li><li>点击**应用更改**</li></ol> |
| 激活被删除后还能再看到相关数据吗？ | 为了遵守SRN平台的数据保留规定或GDPR等规章条例，我们会定期删除相关的激活数据，这些数据一旦删除后就不会再出现在群组面板中。<br /><br />详情请见<Anchor target="_blank" href="/marketers/zh/docs/user-level-data-retention#渠道的数据保留期限">此文档</Anchor>。 |
| 能否将日度数据与周度或月度数据进行比对？ | 日度数据与周度或月度数据的可比性较差，这是因为群组的LTV不一致。<br /><br />查看日度群组数据时，**第0天**展示的是激活当天的数据，第1天是激活次日，第2天是激活日起2天后，以此类推。<br /><br />查看周度群组数据时，**第0周**展示的是这一周内发生的所有激活的数据，第1周是激活后一周，第2周是激活后2周，以此类推。<br /><br />查看月度群组数据时，**第0月展示**的是这一个月内发生的所有激活的数据，第1个月是激活后一个月，第2个月是激活后2个月，以此类推。<br /><br />综上可以看出，这几个视图的LTV时间节点不一致。假设您要查看1月9日-15日的数据，如果您使用日度视图，则**第0天**的数据是**1月9日-15日之间所有激活的首日信息，第6天**的数据是**1月9日-15日**之间发生的所有激活在激活后最初6天内的数据。但如果您使用的是**周度视图**，则**第0周**的数据是**1月9日到15日间**发生的所有激活在**整个一周内**产生的数据。因此，对于**1月9日**发生的激活，其周度数据相当于**第6天**的数据，但是对于**1月15日**发生的激活，其周度数据则相当于**第0天**的数据。 |
|  |  |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="特点与局限性">

| 特点 | 说明 |
| --- | --- |
| 广告平台的群组报告权限 | 不可用 |
| 代理访问权限 | 可用：<ul><li>仅限一个应用。</li><li>混合型账户无法使用群组面板。</li><li>需要获取具体应用的权限。</li><li>无法选择多个应用。</li><li>无法访问自然量数据。</li></ul> |
| 代理数据透明化 | 2021年1月10日起可用 |
| 应用层级的指定时区 | <ul><li>可用</li><li>例外情况：在以下场景中，AppsFlyer会使用默认时区UTC +0，并忽略应用层级的指定时区：<ul><li>群组报告中包含多个应用的数据，且这些应用的指定时区不一致。</li><li>所有应用的指定时区一致，但在群组报告时段内至少有一个应用的时区有变化。报告时段的计算方法如下：<ul><li>开始日期：转化日期范围的第一天</li><li>结束日期：转化日期范围的最后一天加上显示时长的总天数。假设转化日期范围的最后一天为2019年1月1日，报告时长为30天，结束日期：2019年1月31日。</li></ul></li><li>周度和月度数据按UTC时间显示。</li></ul></li></ul> |
| 成本 | <ul><li>只有在出现相关转化（激活、再互动或再归因）的情况下，群组面板才会显示成本数据。也就是说，如果您投放的广告按点击量和展示量计费，但该广告没有带来转化，则群组报告中不会显示成本数据。报告中的所有广告层级都按照这个规则来显示成本数据。</li><li>AppsFlyer的群组报告或群组API不上报包含大写字母的关键词成本数据。</li></ul> |
| 应用配置中的指定货币 | <ul><li>可用</li><li>请注意：在多应用场景中，所有应用都必须使用同一种货币货币不统一时自动使用美元（USD）为单位。</li></ul> |
| 下载CSV文件 | <ul><li>最多包含1万行数据。</li><li>仅可下载用户生命周期内的投放效果报告。基于归因时间的KPI趋势不能以CSV格式导出。</li><li>每个用户每分钟最多可导出10个CSV文件，每天最多100个。</li></ul> |
| 图表 | 无论您选择了哪个维度，图表都会显示群组中用户人数最多的前5或10个结果。 |
| 表格 | 表格最多显示200行数据。无论您选择了哪个指标，表格始终会显示激活、再营销转化或归因（具体取决于群组视图类型）、成本和平均eCPI（实际单次激活成本）。 |
| 重装激活 | <ul><li>如果重装激活发生后的事件被记录为未归因的自然量：<ul><li>2024年5月26日之后的报告不呈现该数据。<Anchor target="_blank" href="/marketers/zh/docs/bulletin-cohort-data-includes-unattributed-sessions-and-events">详情请见此处说明。</Anchor></li><li>激活时间以<Anchor target="_blank" href="/marketers/zh/docs/raw-data-field-dictionary#device-info::dfd9504e">device\_download\_time</Anchor>字段的值为准。</li><li>不计入独立用户数和留存指标。</li></ul></li><li>如果重装激活后发生的事件被归因到首次激活，则报告中总是包含该数据。<Anchor target="_blank" href="/marketers/zh/docs/unique-users">详情请见此处说明。</Anchor></li></ul> |
| 数据查询（Data Queries） | 每个用户每分钟最多可查询数据20次，每天最多500次。更改时间范围、分组维度、KPI等也视为一次新的查询。 |
| 自然量数据 | 包含 |
| 非自然量数据 | 包含 |
| 数据时效性 | <ul><li><Anchor target="_blank" href="/marketers/zh/docs/about-data-freshness-and-timezone-support#eod">实时</Anchor></li><li>例外：<ul><li>每天更新的群组数据：<ul><li>成本、广告收入和卸载指标每天更新一次。</li><li>卸载数据每天计算一次（以UTC为准）。</li></ul></li><li>每周和每月更新的群组数据：<ul><li>实时数据不可用。数据仅在收集完成后（即指定那一周/月的周末/月末）才会呈现。<br />但如果相关数据中的激活数据已收集完毕（即部分数据已准备就绪），但其他数据尚未完成，这样的数据也会呈现在面板中。</li></ul></li></ul></li></ul> |
| 历史数据 | <ul><li>日度群组数据：2年。</li><li>周度/月度群组数据：3年</li></ul> |
| 国家/地区 | <ul><li>可用</li><li>地理位置未知时（N/A），按地理位置分组的报告不显示广告收入数据。</li></ul> |
| 应用打开次数 | 再营销视图中第0天的应用打开次数（session count）可能会低于用户数。<br />这种情况可由多种因素造成，其中最常见的原因如下：<ul><li>session先被归因到初始流量来源，之后才记录到是再互动。这种情况下，该session不会归因到再营销广告。</li><li>如果您按**session间最短间隔时间**等其他设置筛选数据，则AF会记录再互动，但筛除部分session，不记录这部分数据。</li></ul> |
| 再营销和统一视图的数据 | 2021年9月1日之前的月度session数据不可用 |
| 广告收入 | <ul><li>以小时为单位查看群组数据时不可用。</li><li>群组面板和总览面板的广告收入金额之间可能有差异。如果变现平台按UTC时间上报收入，而相关应用在AF后台配置的时区不是UTC，就会产生这样的差异。</li><li>对于af\_ad\_revenue事件，独立用户指标在以下汇总类型中不可用：<ul><li>“累计”</li><li>2022年10月5日到2023年2月16日之间的“当天”维度</li></ul></li></ul> |
| 周度和月度数据 | <ul><li>月度和周度数据仅在群组面板中呈现</li><li>如果数据中包含2022年11月之前的激活，则**独立用户数**、**留存**和**转化率**指标不可用。</li><li>2021年及之前的历史数据不可用。</li><li>激活后的天数：如果群组中包含2021年1月到2022年12月期间激活的用户，则该群组可用的激活后数据时限最多为一年（即52周或12个月）。如果群组中的用户激活日期在此之后，则最多有3年的激活后数据可用（即156周或36个月）。</li></ul> |
| 群组周期 | <ul><li>转化发生的当前周期为第0期，如第0个小时（Hour 0）、第0天（Day 0）、第0周（Week 0）或第0个月（Month 0）；下一个周期即为第1期，如第1个小时（Hour 1）、第1天（Day 1）、第1周（Week 1）或第1个月（Month 1），以此类推。</li><li>AppsFlyer平台中的群组周期不考虑具体的激活时间戳，而是对群组小时数就近取整，群组天数、周数和月数则以公历日期为准。对于根据具体激活时间戳判定群组周期（1小时为激活时间戳后的60分钟，1天为激活时间戳后的24小时，以此类推）的平台，这一逻辑可能会使其群组数据与AppsFlyer之间产生一定差异。</li><li>不同群组周期颗粒度的可查询时间范围上限分别为： 天-60天；小时-60小时；月-12个月；周-26周。</li></ul> |
| 应用内事件名称 | 建议：选择具有描述性的字词为您的应用内事件命名，不要仅使用“Revenue”等过于笼统的名称。如果将某个事件命名为“Revenue”，可能会与其他收入指标混淆，造成数据污染。 |
| 筛选条件 | 按广告系列筛选数据时，最多可选择100个值。 |
| 不完整数据 |  |
| 事件 |  |

</Accordion>

<div data-zendesk-anchors="cohort-dashboard=%E7%BE%A4%E7%BB%84%E4%B8%8E%E7%95%99%E5%AD%98%E9%9D%A2%E6%9D%BF 01H7T5AGP75A36TVWSM7H81E8P=%E7%BE%A4%E7%BB%84%E4%B8%8E%E7%95%99%E5%AD%98%E9%9D%A2%E6%9D%BF 01H7T5AGP7SGPZNK8VTDYBTY2B=%E6%8F%90%E7%A4%BA using-cohort=%E7%BE%A4%E7%BB%84%E9%9D%A2%E6%9D%BF%E4%BD%BF%E7%94%A8%E6%8C%87%E5%8D%97 01H7T5AGP7XDKN85TR0J4V8TP3=%E7%BE%A4%E7%BB%84%E9%9D%A2%E6%9D%BF%E4%BD%BF%E7%94%A8%E6%8C%87%E5%8D%97 01H7T5AGP7FDZNVM9PDBQJPMA0=setting-up-an-analysis using-my-reports%E2%80%94save-and-select-reports=using-my-reports-save-and-select-reports 01H7T5AGP8KRZ9207DCYGRGGC0=using-my-reports-save-and-select-reports 01H7T5AGP84HVD2BQ9Z8S13D5K=export-the-cohort-to-a-csv-file cohort-concepts=%E7%BE%A4%E7%BB%84%E6%A6%82%E5%BF%B5 01H8K817ZPJTRBP1KK90FVV57T=%E7%BE%A4%E7%BB%84%E6%A6%82%E5%BF%B5 01H8K817ZPZTG476KZ83F6Z460=cohort-periods h_01JJH967X8P2NF3AFBSNMBD7B4=view-types 01H8K817ZPBVTGT5R18XGQHYT2=trend-types user-lifetime-performance=%E7%94%A8%E6%88%B7%E5%85%A8%E7%94%9F%E5%91%BD%E5%91%A8%E6%9C%9F%E8%A1%A8%E7%8E%B0 01H8VNMYN0149T418BXM8RGBN9=%E7%94%A8%E6%88%B7%E5%85%A8%E7%94%9F%E5%91%BD%E5%91%A8%E6%9C%9F%E8%A1%A8%E7%8E%B0 kpi-by-attribution-time=%E4%BB%A5%E5%BD%92%E5%9B%A0%E6%97%B6%E9%97%B4%E6%9F%A5%E7%9C%8Bkpi 01H8VNRGMWS8SSDM5KX08EDAS2=%E4%BB%A5%E5%BD%92%E5%9B%A0%E6%97%B6%E9%97%B4%E6%9F%A5%E7%9C%8Bkpi example-user-lifetime-performance-trend-vs-kpi-by-attribution-time-trend=%E7%A4%BA%E4%BE%8B%E7%94%A8%E6%88%B7%E7%94%9F%E5%91%BD%E5%91%A8%E6%9C%9F%E5%86%85%E7%9A%84%E6%8A%95%E6%94%BE%E6%95%88%E6%9E%9C%E8%B6%8B%E5%8A%BF-vs-%E5%9F%BA%E4%BA%8E%E5%BD%92%E5%9B%A0%E6%97%B6%E9%97%B4%E7%9A%84kpi%E8%B6%8B%E5%8A%BF 01H8K98XE9T23QGB440GHRB8E8=%E7%A4%BA%E4%BE%8B%E7%94%A8%E6%88%B7%E7%94%9F%E5%91%BD%E5%91%A8%E6%9C%9F%E5%86%85%E7%9A%84%E6%8A%95%E6%94%BE%E6%95%88%E6%9E%9C%E8%B6%8B%E5%8A%BF-vs-%E5%9F%BA%E4%BA%8E%E5%BD%92%E5%9B%A0%E6%97%B6%E9%97%B4%E7%9A%84kpi%E8%B6%8B%E5%8A%BF 01H7T5AGP8PN12P2C4RGGQ0R95=partial-data 01H7T5AGP8XNG1CW2FPJSEEJ45=list-of-dimensions-for-grouping-and-filtering time-in-the-case-of%0A%20%20%0A%20%20daily-granularity-is-the-date%0A%20%20hourly-granularity-is-the-hour-of-the-day%0A%20%20weekly-granularity-is-the-week-of-the-year%0A%20%20monthly-granularity-is-the-month-of-the-year=time-in-the-case-of-daily-granularity-is-the-date-hourly-granularity-is-the-hour-of-the-day-weekly-granularity-is-the-week-of-the-year-monthly-granularity-is-the-month-of-the-year 01H7T5AGP708H7JGTS1RJ07H27=metrics-available information=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF 01H7T5AGP8J9AQ1BREYZ0JWWZ4=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF 01H7T5AGP83FRX1H9WVMS485MT=cohort-for-agencies 01H7T5AGP8JF0EAX8WEFNSEKM9=use-cases revenue-sum-by-country=%E6%8C%89%E5%9B%BD%E5%AE%B6%E5%9C%B0%E5%8C%BA%E5%8A%A0%E6%80%BB%E7%9A%84%E6%94%B6%E5%85%A5 01H7T5AGP8R6913GPXWM6DGASF=%E6%8C%89%E5%9B%BD%E5%AE%B6%E5%9C%B0%E5%8C%BA%E5%8A%A0%E6%80%BB%E7%9A%84%E6%94%B6%E5%85%A5 inapp-event-conversion=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E8%BD%AC%E5%8C%96 01H7T5AGP80W5J1VEZ40MHGPPF=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E8%BD%AC%E5%8C%96 01H7T5AGP85T7H25863GXJCVCW=faq 01H7T5AGP90NADB7YXTFEMTSAX=traits-and-limitations" />
