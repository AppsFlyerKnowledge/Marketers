---
title: Protect360面板
metadata:
  keywords:
    - dashboard
    - Advertisers
    - Protect360
    - protect 360
    - '360'
    - P360
    - Premium
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2020-08-11T09:58:07Z'
  edited_at: '2026-10-14T10:13:47Z'
  id: 360011793077
  locale: zh-cn
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/zh-cn/articles/360011793077
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** Protect360面板针对作弊流量以及按验证规则拦截的激活，提供关键的分析信息。

## Protect360面板简介

Protect360面板具有以下特点：

* 呈现账户层级的汇总假量数据
* 提供以下两种面板视图：
  * 激活（CPI）
  * 应用内事件（CPA）
* 对假量进行归类梳理，包括：
  * 虚假激活和被劫持的激活
  * 实时拦截的假量和归因后识别的假量
  * UA假量和再营销假量
* 您可以使用筛选和分组选项层层深入，剖析激活假量数据。

如需查看Protect360面板，请从AppsFlyer后台进入**优化** > **Protect360**。

<div id="filters-and-groupings" />

<Accordion title="数据筛选和分组">

**筛选和分组窗口**

[![p360_filters_2.png](https://files.readme.io/9fd2afbbfc1bdf671ae0427d75c1020085b36da724e40dcfe57da27943e15b0c-4408431325969.png)](https://files.readme.io/9fd2afbbfc1bdf671ae0427d75c1020085b36da724e40dcfe57da27943e15b0c-4408431325969.png)

Protect360面板提供下列筛选和分组选项：

* 基础筛选条件：
  * 应用名称
  * 流量类型：非自然量和/或自然量
  * 媒体渠道
  * 国家/地区
  * 日期范围（详见<Anchor target="_blank" href="/marketers/zh/docs/about-data-freshness-and-timezone-support#protect360-dashboard">适用时区说明</Anchor>）
  * 归因类型：激活、再归因和/或再互动
  * [应付事件](/docs/protect360-dashboard#payable-events)（详细数据可在应用内事件假量面板中查看）
* 点击日期选择器一行右侧的蓝色加号按钮，界面会展开筛选条件列表，显示下列选项：
  * 代理
  * 广告系列
  * 流量入口（Channel）
* 分组选项——根据实际需求，选择不同的维度对假量数据进行分组，从而获取所需的关键信息：
  * **应用：** 对比各应用的总体假量
  * **媒体渠道**（默认）：对比各渠道所产生的假量
  * **媒体渠道 + 广告系列**：对比所有渠道中投放的广告系列所产生的假量
  * **媒体渠道 + 子渠道**：对比所有渠道的子渠道所产生的假量
  * **媒体渠道 + 子渠道 + 广告系列**：对比所有渠道的子渠道所产生的假量，并将其关联到具体的广告系列名称
  * **媒体渠道 + 国家/地区**（详细数据可在应用内事件假量面板中查看）：对比各渠道所产生的假量，并将其关联到相关的国家
  * **媒体渠道 + 归因类型**：对比各渠道所产生的假量，并将其关联到指定的归因类型（激活、再归因和/或再互动）
  * **国家/地区**：对比来自各个国家的假量

</Accordion>

## 激活假量面板

激活假量面板中呈现LTV维度的数据，也就是说，该面板中的数据与选定日期范围内发生的激活、再归因和再互动有关。

面板功能详见下文各章节的说明。

<div id="installs-headline-metrics" />

<Accordion title="激活假量——标题指标">

您可以在标题指标中看到以下内容：

每个KIP都有一个对应的百分比值，表示当前选定时间段内的KPI对比上一个时间段的环比变化。比如本周对比上周的周环比，或您在日期范围选项中设定的任意统计周期对比上一个统计周期的变化。如果面板显示“预计节省成本”指标有X%的提升，即表示上个统计周期中同一天的激活、再归因和再互动假量比面板显示的当天低X%。

**已识别的作弊转化**

[<Image alt="" src="https://files.readme.io/262403803bd074e4742f63d7998d4642e3b17781e178ed3bc24b35dd958ca262-4408437121297.png" width="100%" />](https://files.readme.io/262403803bd074e4742f63d7998d4642e3b17781e178ed3bc24b35dd958ca262-4408437121297.png)

已识别的总体假量指标用于呈现以下数据：

* 基于各种原因被实时拦截的激活、再归因和再互动假量。
* 归因后被识别为假量的激活、再归因和再互动。

**已拦截的应用内事件**

[<Image alt="" src="https://files.readme.io/ed6692be83cae6a6bee556e5c763d6313c0d32cb577a9587caac41c54b51b378-4403139249809.png" width="100%" />](https://files.readme.io/ed6692be83cae6a6bee556e5c763d6313c0d32cb577a9587caac41c54b51b378-4403139249809.png)

已拦截的应用内事件指标用于显示被AppsFlyer拦截的应用内事件的数量。已拦截的激活所产生的事件以及归因后被标记为可疑的事件都会计入此指标。

[<Image alt="" src="https://files.readme.io/49e705c39b88c243af92c88e33d1939d1ec54b6a83e94724bdef702c9442a6a6-32184720638097.png" width="100%" />](https://files.readme.io/49e705c39b88c243af92c88e33d1939d1ec54b6a83e94724bdef702c9442a6a6-32184720638097.png)

</Accordion>

<div id="installs-charts" />

<Accordion title="激活假量——图表">

#### 已识别的假量趋势图

已识别的假量趋势图按天显示激活、再归因和再互动假量变化，可细分到以下两个维度：

* **检测类型**：被实时拦截的激活以及归因后被识别为假量的激活。
* **归因到的转化类型**激活、再归因、再互动
* **流量类型**：非自然量和自然量

您可以选择曲线图或柱状图来呈现该信息。

#### 被劫持的激活归因更正图表

被劫持的激活归因更正图表用于显示企图窃取归因（激活、再归因和再互动）的媒体渠道以及相应的末次有效助攻渠道。

您可以：

* 按实时识别、归因后识别或通过验证规则识别的归因劫持来筛选数据。
* 设置应获得归因的有效渠道或应纠正归因的劫持渠道。
* 将图表视图改为表格形式，然后以CSV格式下载相关数据。

**请注意：**

* 该图表仅对广告主开放，代理商和广告平台无访问权限。
* 归因劫持行为被实时拦截时，Protect360以外的AppsFlyer面板和报告中也会显示正确的归因结果。但如果相关转化在归因后才被识别为归因劫持，则正确的归因结果仅显示在Protect360原始数据中。
* 该图表可显示从付费渠道纠正**到自然量**的归因，但没有**从自然量**纠正到渠道的数据。

#### 已识别的假量图表

已识别的假量图表会按比例显示您遭遇到的假量类型。该图表可按以下维度对假量进行细分：

* 拦截原因
* <Anchor target="_blank" href="/marketers/zh/docs/protect360-raw-data-reports#激活层级适用于虚假激活的拦截原因">详细拦截原因</Anchor>

* 媒体渠道
* Campaign
* 国家/地区
* 应用

</Accordion>

<div id="installs-table" />

<Accordion title="激活假量——数据表">

#### 已识别的假量细分数据

**已识别的假量细分数据**表会显示以下信息：

* 实时拦截的假量
* 归因后识别并标记的假量
* 按渠道细分的其他作弊迹象

该数据表的格式与数据总览类似，详见下文截屏。

[![p360_main_table.png](https://files.readme.io/15885268068f2b57e9b22b7028a824951690e737a47cb154cd38d1ddf79937b8-4408431449745.png)](https://files.readme.io/15885268068f2b57e9b22b7028a824951690e737a47cb154cd38d1ddf79937b8-4408431449745.png)

该动态数据表具有以下特点：

* 提供可点击的表格设置按钮，用于在表格中添加或移除栏位。  
  对表格进行更改后，请务必点击**保存**按钮。
* 按用户呈现数据。也就是说，相关AppsFlyer账户下每个具有Protect360权限的用户都可以对该表格的结构进行调整，形成自己的定制化数据表。另请查看[其他表格选项](/docs/protect360-dashboard#其他表格选项)。

[![edit_table.jpg](https://files.readme.io/fcde2bc6970c29902dd7585ee92c2bc38edf1d5c56e65de4e3f10df784108e5c-360011641617.jpg)](https://files.readme.io/fcde2bc6970c29902dd7585ee92c2bc38edf1d5c56e65de4e3f10df784108e5c-360011641617.jpg)

#### 已识别的假量细分数据表内容

| 表格栏位 | 说明 |
| --- | --- |
| 分组 | <ul><li>【默认】表格和面板中的数据都按媒体渠道分组。</li><li>选择特定的媒体渠道时，表格会同时按媒体渠道和子渠道进行数据分组。</li><li>可选的分组维度包括广告系列、国家/地区，流量入口（Channel），代理、代理+渠道及上述各项的组合。</li><li>如果您选择了只适用于非自然量的分组维度，则自然量的媒体渠道会显示为N/A。</li></ul> |
| **归因到的转化** | **标题指标细分到实时拦截以及归因后识别的激活假量。** |
| 总计（A） | <ul><li>总体激活数 = 正常（非作弊）激活数 + 已拦截的激活数</li><li>您可以在数据总览面板中查看分渠道的正常激活数据（非自然量）。</li></ul> |
| 已拦截（B） | <ul><li>已拦截的激活总数。</li><li>【默认】表格按此KPI降序排列。</li></ul> |
| 已拦截%（B/A） | 已拦截的激活/激活总数 |
| 归因后（C） | 归因后被判定为假量的激活 |
| 归因后%（C/A） | 归因后被判定为假量的激活/激活总数 |
| 总体激活假量（D） | 作弊的激活数量，涵盖被实时拦截的激活以及归因后被判定为假量的激活。 |
| 激活假量％（D/A） | 激活假量/激活总数 |
| **假量的归因类型细分** | **假量的归因类型可分为激活、再归因和再互动。** |
| 激活 | 来自UA广告的假量。 |
| 再归因 | 来自再营销广告的激活被判定为假量。 |
| 再互动 | 来自再营销广告的再互动被判定为假量。 |
| **虚假激活** | **通过模拟真实用户的行为伪造的激活或再归因，分为实时拦截和归因后识别两类。** |
| 实时拦截 | 被实时拦截的虚假激活 |
| 归因后假量 | 归因后重新被判定为假量的虚假激活。 |
| **被劫持** | **针对真实用户的激活，企图窃取其归因的虚假末次点击，分为实时拦截和归因后识别两类。** |
| 实时拦截 | 被实时拦截激活劫持。 |
| 归因后假量 | 归因后重新被判定为假量的激活劫持。 |
| **验证规则** | **符合验证规则条件的激活。** |
| 已拦截的激活 | 根据验证规则被拦截的激活。 |
| 已拦截的归因 | 根据验证规则而变更的激活归因结果。 |
| **虚假流量细分** | **针对以程序化的方式伪造的虚假激活，将其细分为实时拦截和归因后识别两类。** |
| 已拦截 - 子渠道黑名单 | 由于Protect360将相关子渠道列入了黑名单，因而被拦截的激活 |
| 归因后识别 - 子渠道黑名单 | 由于Protect360在归因后将相关子渠道列入了黑名单，因而被标记为假量的激活 |
| 已拦截的机器人作弊 | 被拦截的由自动化脚本伪造的激活。 |
| 归因后识别的机器人作弊 | 由于归因后识别的自动化脚本而被标记为假量的激活 |
| 已拦截 - 行为异常 | 由于行为异常（用户的应用打开和应用内事件出现异常数据）而被拦截的激活 |
| 归因后识别 - 行为异常 | 由于归因后识别出的行为异常而被标记为假量的激活。 |
| 已拦截 - 激活验证 | 由于未通过商店验证而被拦截的激活总数。 |
| **被劫持的流量细分** | **企图窃取真实激活归因的作弊点击，细分到以下几类。** |
| 已拦截的激活劫持 | 已拦截的被作弊点击渠道劫持的激活。 |
| 归因后识别的激活劫持 | 归因后被判定为激活劫持，因而标记为假量 |
| 已拦截 - CTIT异常 | 由于CTIT异常而被拦截的激活。 |
| 归因后识别 - CTIT异常 | 归因后被判定为CTIT异常，因而标记为假量 |
| 已拦截 - 撞库 | 由于撞库（作弊平台发送大量点击，企图在随机的用户激活之前抢到末次点击）而被拦截的激活。 |
| 归因后识别 - 撞库 | 在归因后被判定为撞库，因而标记为假量 |
| **点击** | **来自相关渠道的点击**<br /><br />**请注意：** 如需在表格中查看点击数据，必须在字段设置微件中的“归因到的转化类型细分”下勾选所有归因类型，否则该指标会显示为“N/A”。请务必根据您的需求调整您的字段设置。 |
| 总计（E） | 相关渠道发送的正常点击和作弊点击总数。 |
| 已拦截 |  |
| **展示** | **来自相关渠道的展示**<br /><br />**请注意：** 如需在表格中查看展示数据，必须在字段设置微件中的“归因到的转化类型细分”下勾选所有归因类型，否则该指标会显示为“N/A”。请务必根据您的需求调整您的字段设置。 |
| 总计 | 相关渠道发送的正常展示和作弊展示总数。 |
| 已拦截 |  |
| **应用内事件** | **来自相关渠道的应用内事件**<br /><br />**请注意：** 这些数据包含由激活产生的应用内事件，不包含再归因和再互动。 |
| 总计（G） | 应用内事件总数 |
| 已拦截（H） | 已拦截的应用内事件 |
| %（H/G） | 已拦截应用内事件数量/应用内事件总数 |
| **设备农场预警指标** | **用于判断设备农场作弊的预警指标。设备农场是指通过设备ID重置以及限制广告追踪（LAT）进行作弊的一种方式。**<br /><br />**请注意：** 这些数据包含激活和再归因，但不包含再互动。 |
| 激活（I） | 从未在AppsFlyer数据库中出现过的全新设备ID所产生的激活。 |
| 激活%（I/A） | 新设备激活/激活总数 |
| 忠实用户% | 用于判断用户真实性的通用KPI。 |
| **点击撞库预警指标** | **根据转化率、助攻率或CTIT时长的异常数据得出的点击撞库指标。** |
| 转化率（%） | 若转化率低于正常水平，表示可能出现了点击撞库。<br /><br />**请注意**：如需在表格中查看转化率数据，必须在字段设置微件中的“归因到的转化类型细分”下勾选所有归因类型，否则该指标会显示为“N/A”。请务必根据您的需求调整您的字段设置。 |
| 助攻％ | 若相关渠道的助攻率高于其他渠道（在数据表上方的字段设置微件中勾选助攻率后可看到具体数据），说明可能出现了点击撞库。 |
| CTIT > 60分钟 | 广告点击和首次应用打开之间的时间间隔超过60分钟的激活、再归因和再互动。该指标仅计算CTIT短于25小时的激活（不涵盖所有激活）。一般情况下，约有30%的首次应用打开会在应用下载的60分钟后发生。 |
| CTIT > 5小时 | 广告点击和首次应用打开之间的时间间隔超过5小时的激活、再归因和再互动。该指标仅计算CTIT短于25小时的激活（不涵盖所有激活）。一般情况下，约有20%的首次应用打开会在应用下载的5小时后发生。 |

#### 其他表格选项

* 点击**导出CSV文件**可下载CSV格式的数据表。
* 点击齿轮图标：
  * 更改表格中的栏位顺序
  * 添加或删除栏位（字段）
  * 添加或删除相关应用下**近期被拦截的应用内事件**。每添加一个应用内事件，数据表就会增加以下各列：

| 表格栏位 | 说明 |
| --- | --- |
| 事件数量（总计） | 特定事件被拦截的次数 |
| 独立用户数 | 已拦截的特定事件的独立用户数 |

请注意：这两个KPI出现异常数据时，不代表一定出现了作弊行为，这是因为很多事件的拦截与归因后被判定为假量的激活有关。

激活面板中的应用内事件数据是LTV维度的，也就是说其中所有的应用内事件都与指定日期范围内发生的激活有关。

</Accordion>

## 应用内事件控制面板

应用内事件假量面板呈现活跃维度的数据，也就是说与这些数据相关的应用内事件发生在您选定的日期范围内，包括在该在此之前发生的激活所产生的事件。

面板功能详见下文各章节的说明。

<div id="inapp-events-headline-metrics" />

<Accordion title="应用内事件——标题指标">

[![](https://files.readme.io/ea33b3ddafc4265eb74b2e1070a77a6afbad429a1aeb20cd1579127f7e8ee605-360012501757.jpg)](https://files.readme.io/ea33b3ddafc4265eb74b2e1070a77a6afbad429a1aeb20cd1579127f7e8ee605-360012501757.jpg)

您可以在标题指标中看到以下内容：

* 预计节省成本
  * 该信息仅在[**应付事件**](/docs/protect360-dashboard#payable-events)启用后才会呈现。
  * 根据您配置的应付事件呈现数据。
* 已识别的应用内事件假量。

</Accordion>

<div id="inapp-events-charts" />

<Accordion title="应用内事件——趋势图">

#### **作弊趋势图**

作弊趋势图显示各天的事件假量，并将其细分到以下几类：

* **实时拦截**：被实时拦截的应用内事件假量
* **归因后**：归因后被识别为假量的应用内事件
* **非作弊**

#### **应用内事件假量最多的媒体渠道图表**

应用内事件（以下简称IAE）假量最多的媒体渠道列表中包含以下信息：

* 前5个IAE假量最多的渠道，以降序排列。
* 图表中的每个柱形代表各渠道所产生的应用内事件，细分到以下三种类型，并以百分比的形式呈现各类事件在事件总数中的占比：
  * **实时拦截**：被实时拦截的应用内事件假量
  * **归因后**：归因后被识别为假量的应用内事件
  * **非作弊**

</Accordion>

<div id="inapp-events-table" />

<Accordion title="应用内事件——数据表">

**应用内事件细分数据**表会显示以下信息：

* 实时拦截的假量
* 归因后识别并标记的假量
* 按渠道细分的其他作弊迹象

该数据表的格式与数据总览类似，详见下文截屏。

[![IAE_fraud_table.jpg](https://files.readme.io/dd57a2508911b3e26268ad8cc4508d5402fa091ac95a77900c7f257486c99aeb-360012839758.jpg)](https://files.readme.io/dd57a2508911b3e26268ad8cc4508d5402fa091ac95a77900c7f257486c99aeb-360012839758.jpg)

该动态数据表具有以下特点：

* 提供可点击的表格设置按钮，用于在表格中添加或移除栏位。  
  对表格进行更改后，请务必点击**保存**按钮。
* 按用户呈现数据。也就是说，相关AppsFlyer账户下每个具有Protect360权限的用户都可以对该表格的结构进行调整，形成自己的定制化数据表。另请查看[其他表格选项](/docs/protect360-dashboard#installs-table)。

[![iae_table_structure.jpg](https://files.readme.io/5b2933e2b254d8fa268e30a72ae53691da391e365d781d55bcdb6cfeb1f40a6a-360012839778.jpg)](https://files.readme.io/5b2933e2b254d8fa268e30a72ae53691da391e365d781d55bcdb6cfeb1f40a6a-360012839778.jpg)

#### 应用内事件假量的细分数据表内容

| 表格栏位 | 说明 |
| --- | --- |
| 分组 | <ul><li>【默认】表格和面板中的数据都按媒体渠道分组。</li><li>选择特定的媒体渠道时，表格会同时按媒体渠道和子渠道进行数据分组。</li><li>可选的分组维度包括广告系列、国家/地区，流量入口（Channel），代理、代理+渠道及上述各项的组合。</li></ul> |
| **应用内事件** | **标题指标细分到实时拦截以及归因后识别的应用内事件假量。** |
| IAE总数（A） | <ul><li>IAE总数 = 正常（非作弊）IAE + 已拦截的IAE + 归因后被识别为假量的IAE。</li><li>您可以在数据总览面板中查看分渠道的正常IAE的数据（非自然量）。</li></ul> |
| 总体IAE假量（B） | <ul><li>已拦截的IAE数量 + 归因后被识别为假量的IAE。</li><li>【默认】表格按此KPI降序排列。</li></ul> |
| 作弊事件％（B/A） | 作弊IAE/总体IAE |
| **实时拦截的虚假IAE** | **被实时拦截IAE假量。** |
| 虚假IAE | 被识别假量并已实时拦截的IAE |
| 虚假激活 | 被识别为假量并已实时拦截的初始激活 |
| 归因后识别的虚假激活 | 初始激活在归因后被判定为假量，而该IAE发生在假量判定之后。 |
| **实时免遭劫持** | **初始激活被作弊渠道劫持后产生的IAE，由AppsFlyer正确归因到最后一个正常的流量来源。** |
| 更正为自然量 | 最后一个正常的流量来源为自然量的激活劫持。 |
| 更正为非自然量 | 最后一个正常的流量来源是非自然媒体渠道的激活劫持。 |
| **归因后识别的IAE假量** | **在归因后被识别为假量的应用内事件。** |
| 虚假激活 | 初始激活在归因后被判定为假量，而该IAE发生在假量判定之前。 |
| 被劫持的激活 | 初始激活被判定为流量劫持，而该IAE发生在劫持判定之前，且无法在归因后更正归因结果。 |
| **验证规则** | **由于符合验证规则的条件而被拦截的IAE。** |
| 已拦截的激活 | 根据验证规则被拦截的激活所产生的IAE。 |
| 已拦截的IAE | 根据验证规则被拦截的IAE。 |
| 更正为自然量 | 最后一个正常的流量来源为自然量的激活劫持。 |
| 更正为非自然量 | 最后一个正常的流量来源是非自然媒体渠道的激活劫持。 |

#### 其他表格选项

* 点击**导出CSV文件**可下载CSV格式的数据表。
* 点击齿轮图标：
  * 更改表格中的栏位顺序
  * 添加或删除栏位（字段）

此处显示的事件数量以活跃维度为基础，而非LTV数据，即指定日期范围内被拦截的实际事件数量。

</Accordion>

<div id="payable-events" />

<Accordion title="应付事件">

应付事件是指带有成本的IAE。启用并配置应付事件后，应用内事件假量面板仅呈现与应付事件有关的数据

**要在应用内活动信息中心中启用应付款事件**：

* **在应用内事件假量面板中的筛选条件一栏中，打开“应付事件”的开关。  
  [![](https://files.readme.io/8162f6f4f6dcef50fbe0fd998b7a95d20deeb658dd53bafc216b75df050c734c-360012576718.jpg)](https://files.readme.io/8162f6f4f6dcef50fbe0fd998b7a95d20deeb658dd53bafc216b75df050c734c-360012576718.jpg)**

**要配置应付事件**：

1. 在应用内事件假量面板中点击**配置应付事件**。

   [![](https://files.readme.io/00b1f4506f0c7ec8e1e1b90c16cc2232d2862b231b2673d2decc7a90b6c6b6af-360012505217.jpg)](https://files.readme.io/00b1f4506f0c7ec8e1e1b90c16cc2232d2862b231b2673d2decc7a90b6c6b6af-360012505217.jpg)

   界面会弹出“配置应付事件”的窗口。

   [![](https://files.readme.io/4643b9d0e0042ca5860d21ec3eb3ff7e4178f92f1f4215db56adda10be41c452-360012580938.jpg)](https://files.readme.io/4643b9d0e0042ca5860d21ec3eb3ff7e4178f92f1f4215db56adda10be41c452-360012580938.jpg)
2. 【可选】如需配置新的应付事件，请点击**添加新事件**。
3. 根据您想要在面板中看到的应付事件，从下拉菜单中选择以下选项：
   * 应用
   * 应用内事件
   * 媒体渠道
   * 广告系列
4. 输入该IAE的CPA。
5. 点击**保存**。
6. 点击**关闭。**

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="特点与局限性">

| 特点 | 说明 |
| --- | --- |
| 再营销 | <ul><li>激活面板会显示AF记录到的广告互动类型，并细分为激活、再归因和再互动。</li><li>应用内事件（CPA）面板显示来自UA激活的事件假量，但不包含再营销激活的事件假量。 **请注意**：AF会实时识别来自再归因的事件假量，并记录在原始数据报告中。</li></ul> |
| 历史数据 | 相关数据从Protect360套餐生效起可用 |
| 数据时效性 | 每日更新。<ul><li>激活（CPI）假量面板每天在UTC时间的16:00更新</li><li>应用内事件（CPA）假量面板每天在UTC时间的21:00更新</li></ul> |

</Accordion>

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/protect360-anti-fraud-guide">Protect360防作弊解决方案</Anchor>
> * <Anchor target="_blank" href="/marketers/zh/docs/protect360-raw-data-reports">原始数据报告</Anchor>

<div data-zendesk-anchors="about-protect360-dashboard=protect360%E9%9D%A2%E6%9D%BF%E7%AE%80%E4%BB%8B 01H8H9GQ17C4PBHCAMXE879BX7=protect360%E9%9D%A2%E6%9D%BF%E7%AE%80%E4%BB%8B 01H8H9GQ173SQ8P29C4DETJRTD=filters-and-groupings installs-dashboard=%E6%BF%80%E6%B4%BB%E5%81%87%E9%87%8F%E9%9D%A2%E6%9D%BF 01H8H9GQ173H3QH1Y5KZ26XMCW=%E6%BF%80%E6%B4%BB%E5%81%87%E9%87%8F%E9%9D%A2%E6%9D%BF installs%E2%80%94headline-metrics=installs-headline-metrics 01H8H9GQ17FJKWE3M2YSZFTQCS=installs-headline-metrics installs%E2%80%94charts=installs-charts 01H8H9GQ18VHMK7FFV3RY409VB=installs-charts identified-fraud-trend-chart=%E5%B7%B2%E8%AF%86%E5%88%AB%E7%9A%84%E5%81%87%E9%87%8F%E8%B6%8B%E5%8A%BF%E5%9B%BE 01H8H9GQ18JDSZ2H8BKZVWGBPV=%E5%B7%B2%E8%AF%86%E5%88%AB%E7%9A%84%E5%81%87%E9%87%8F%E8%B6%8B%E5%8A%BF%E5%9B%BE hijacked-installs-attribution-correction-chart=%E8%A2%AB%E5%8A%AB%E6%8C%81%E7%9A%84%E6%BF%80%E6%B4%BB%E5%BD%92%E5%9B%A0%E6%9B%B4%E6%AD%A3%E5%9B%BE%E8%A1%A8 01H8H9GQ18VXBPQRN55WHM3GG0=%E8%A2%AB%E5%8A%AB%E6%8C%81%E7%9A%84%E6%BF%80%E6%B4%BB%E5%BD%92%E5%9B%A0%E6%9B%B4%E6%AD%A3%E5%9B%BE%E8%A1%A8 identified-fraud-chart=%E5%B7%B2%E8%AF%86%E5%88%AB%E7%9A%84%E5%81%87%E9%87%8F%E5%9B%BE%E8%A1%A8 01H8H9GQ18FW87TXQZCYERHNDE=%E5%B7%B2%E8%AF%86%E5%88%AB%E7%9A%84%E5%81%87%E9%87%8F%E5%9B%BE%E8%A1%A8 installs%E2%80%94table=installs-table 01H8H9GQ18FYXJA7TXQ4RNQGX2=installs-table identified-fraud-breakdown=%E5%B7%B2%E8%AF%86%E5%88%AB%E7%9A%84%E5%81%87%E9%87%8F%E7%BB%86%E5%88%86%E6%95%B0%E6%8D%AE 01H8H9GQ18540JJ8X833E6WF44=%E5%B7%B2%E8%AF%86%E5%88%AB%E7%9A%84%E5%81%87%E9%87%8F%E7%BB%86%E5%88%86%E6%95%B0%E6%8D%AE content-of-the-identified-fraud-breakdown-table=%E5%B7%B2%E8%AF%86%E5%88%AB%E7%9A%84%E5%81%87%E9%87%8F%E7%BB%86%E5%88%86%E6%95%B0%E6%8D%AE%E8%A1%A8%E5%86%85%E5%AE%B9 01H8H9GQ18DMPD7YTPTN2XJMSH=%E5%B7%B2%E8%AF%86%E5%88%AB%E7%9A%84%E5%81%87%E9%87%8F%E7%BB%86%E5%88%86%E6%95%B0%E6%8D%AE%E8%A1%A8%E5%86%85%E5%AE%B9 additional-table-options=%E5%85%B6%E4%BB%96%E8%A1%A8%E6%A0%BC%E9%80%89%E9%A1%B9 01H8H9GQ18PZ8ABG3D51M7J91R=%E5%85%B6%E4%BB%96%E8%A1%A8%E6%A0%BC%E9%80%89%E9%A1%B9 inapp-events-dashboard=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E6%8E%A7%E5%88%B6%E9%9D%A2%E6%9D%BF 01H8H9GQ19CQZV00XA62MGVJ86=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E6%8E%A7%E5%88%B6%E9%9D%A2%E6%9D%BF inapp-events%E2%80%94headline-metrics=inapp-events-headline-metrics 01H8H9GQ19B95MDK2WEHVNEFS5=inapp-events-headline-metrics inapp-events%E2%80%94charts=inapp-events-charts 01H8H9GQ19XEJ0HNY2Y8BMX7A5=inapp-events-charts fraud-trend-over-time-chart=%E4%BD%9C%E5%BC%8A%E8%B6%8B%E5%8A%BF%E5%9B%BE 01H8H9GQ1969AB4KK4ENP8AVQJ=%E4%BD%9C%E5%BC%8A%E8%B6%8B%E5%8A%BF%E5%9B%BE top-iae-fraud-by-media-source-chart=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%81%87%E9%87%8F%E6%9C%80%E5%A4%9A%E7%9A%84%E5%AA%92%E4%BD%93%E6%B8%A0%E9%81%93%E5%9B%BE%E8%A1%A8 01H8H9GQ19Z078PK1HR7VEZHXG=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%81%87%E9%87%8F%E6%9C%80%E5%A4%9A%E7%9A%84%E5%AA%92%E4%BD%93%E6%B8%A0%E9%81%93%E5%9B%BE%E8%A1%A8 inapp-events%E2%80%94table=inapp-events-table 01H8H9GQ19PTNWGJV6YDWR7SH6=inapp-events-table content-of-the-inapp-event-fraud-breakdown-table=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%81%87%E9%87%8F%E7%9A%84%E7%BB%86%E5%88%86%E6%95%B0%E6%8D%AE%E8%A1%A8%E5%86%85%E5%AE%B9 01H8H9GQ19773CS8TGS2QXBRG5=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E5%81%87%E9%87%8F%E7%9A%84%E7%BB%86%E5%88%86%E6%95%B0%E6%8D%AE%E8%A1%A8%E5%86%85%E5%AE%B9 additional-table-options::44e54bfa=%E5%85%B6%E4%BB%96%E8%A1%A8%E6%A0%BC%E9%80%89%E9%A1%B9-1 01H8H9GQ192WA6XFNW7CKGBQ03=%E5%85%B6%E4%BB%96%E8%A1%A8%E6%A0%BC%E9%80%89%E9%A1%B9-1 01H8H9GQ1AVAVQ31ZZA1K024RF=payable-events 01H8H9GQ1BJX0K01NX8VCC0690=traits-and-limitations h_01HE7S2JKX3VMRCF6913S4MCAR=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />
