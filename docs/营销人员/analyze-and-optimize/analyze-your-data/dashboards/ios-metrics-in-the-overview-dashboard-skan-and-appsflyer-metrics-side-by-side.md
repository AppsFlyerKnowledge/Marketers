---
title: 数据总览面板中的iOS指标（SKAN与AppsFlyer指标并列显示）
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
  created_at: '2021-08-02T07:18:18Z'
  edited_at: '2026-10-14T10:06:46Z'
  id: 4404976682257
  locale: zh-cn
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/zh-cn/articles/4404976682257
---
> **概要**：概要：您可以在数据总览面板中并列查看由SKAdNetwork（SKAN）和AppsFlyer归因模型产出的指标，看看哪个归因框架产出的投放效果指标最适合您，进而多加利用，以获得有效洞察并优化投放。

**数据总览面板2.0版中并列显示的归因指标**

![SBSDB.png](https://files.readme.io/550c465c329eac484d2b2e5a65c8f48831c350c3c4b967315e3b2059ab95a36d-4409263804049.png)

<div id="finding-the-best-ios-14-campaign-performance-metrics" />

## 找到最理想的iOS 14+投放效果指标

从iOS 14+开始，SKAN归因和<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-attribution-model">AF模型归因</Anchor>都能产出投放效果指标。这两种框架的归因方式不同，特点和局限性也不同，因此两者之间经常会有数据差异。比如SKAN不包含ASA和自有媒体上的广告投放指标，而AF模型的SRN指标则不包含未授权用户的激活信息。此外，SKAN仅在用户激活后的1-3天内衡量其使用情况，而AppsFlyer则会衡量用户整个生命周期内的数据（即LTV数据）。

通过并列显示两种归因框架的指标，您可以看到两组投放效果数据，便于您对两者进行对比，并选出最能体现真实投放效果的指标。

<mark>如果面板中未显示SKAN指标，您需要更新[表格设置](/docs/ios-metrics-in-the-overview-dashboard-skan-and-appsflyer-metrics-side-by-side#display-skan-metrics-in-the-table)。</mark>

并列视图能让您深入考察投放指标。您可以利用该视图从以下各方面来评估投放效果指标：

* [精确度](/docs/ios-metrics-in-the-overview-dashboard-skan-and-appsflyer-metrics-side-by-side#campaign-precision)：
  * 某个广告系列带来了多少个激活？
  * 为什么SKAN指标与AF指标之间有差异？
* 投放效率有多少转化用户？ROI如何？

本指南是基于我们对市场的了解以及对数据解读和洞察攫取方式的观察所编写的。由于每个应用面对的市场格局各不相同，请根据您自己的应用有取舍地参考本文内容。

**概念定义**

* **转化**：
  * AppsFlyer：
  * SKAN：SKAN：新增激活和重新下载（redownloads）。
* 实际：指即使在数据不完整的情况下，仍最能体现实际数据的指标。
* 授权用户 授权用户：在流量侧应用（publisher app）和广告主应用（advertised app）中都同意ATT授权/strong>的iSO 14+用户。

<div id="campaign-precision" />

<Accordion title="数据精确度">

| 问题 | 某个广告系列带来了多少实际激活？ |
| --- | --- |
| 问题描述 | 两种归因框架所产出的激活指标不同。两个框架分别统计了部分激活，其中可能有重复统计的数据，也可能有差异。 |
| 解决方式 | <ul><li>在广告系列层级对比两个框架的激活指标。</li><li>激活数最多的框架指标最为精确，即使该指标未覆盖到所有激活的归因。</li></ul> |
| 示例 | ![S2Sinstalls.png](https://files.readme.io/9599ef8ac37aa1bc0da46112c1a7d6b4c42f3ff82efda0d0e4b47b8bddc6b52a-4406110225425.png)<br /><br />上表中标出了激活数最多的框架。圈出的数字即为相应广告系列实际带来的激活数。 |
| 提示 | 您可以使用@max功能和带条件的格式设置来标出激活数上报最多的框架，将表格导入Excel表，就能自动选出数值更高的那个指标。 |

| 问题 | 为什么SKAN指标与AF指标之间有差异？ |
| --- | --- |
| 问题描述 | 激活指标有差异 |
| 说明 | <ul><li>AppsFlyer框架根据AppsFlyer的<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-attribution-model">归因模型</Anchor>来判定激活数量，其中包括多种广告系列类型以及归因方式，而SKAN是根据付费的应用到应用广告来衡量激活的。</li><li>一般情况下，对于SRN广告带来的激活，其SKAN指标会高于AppsFlyer指标，因为AppsFlyer仅记录授权用户的激活。</li><li>对于非SRN广告平台（即点击平台）带来的激活，这两种指标之间的差异会小很多。</li></ul> |

</Accordion>

<div id="campaign-effectiveness" />

<Accordion title="投放效果">

| 问题 | 有多少转化用户？ROI如何？ |
| --- | --- |
| 注意事项 | <ul><li>要判定收入和转化率就需要对用户行为进行更长期的衡量。</li><li>SKAN将衡量窗口期限制在12-72内，而AppsFlyer的衡量窗口是无限制的。</li><li>AppsFlyer归因仅包含授权用户的指标。</li></ul> |
| 解决方式 | 您需要自行判断AppsFlyer的归因指标是否能准确体现所有用户（包括通过SKAN上报的用户）的使用情况。如果能够准确体现，那么您就可以使用AppsFlyer的归因指标来推算ROI和转化率等投放效果指标。<br /><br />请按以下方式计算转化用户数：<ol><li>使用AppsFlyer转化率指标（分事件）。</li><li>把转化率与实际用户数（按“数据精确度”部分所述方法取数）相乘。</li></ol>请按以下方式计算收入和ROI：<ol><li>按“数据精确度”部分所述方法取得实际用户数（a）。</li><li>使用AppsFlyer归因框架所产出的ARPU（b）指标</li><li>收入计算公式：a * b</li><li>使用面板中显示的投放成本。</li><li>ROI = （收入 - 投放成本）/（投放成本 * 100）</li></ol> |
| 示例 | **ROI计算方式**<br /><br />![SBSCost.png](https://files.readme.io/052c862e0a93c4e938f84b22e04e8b088bf50acbf047b821ca6cd20f5b9eae57-4409270882577.png)<br /><br />广告系列a的ROI计算方式如下：<ol><li>假设用户数量为2000</li><li>面板中的ARPU指标为：$0.76</li><li>该广告系列的收入 = 2000 * $0.76 = $1520</li><li>该广告系列的投放成本：$905.88</li><li>ROI= ($1520 - $905.88) / ($905.88 * 100) = 68%</li></ol> |
| 提示 | 建议您使用您的BI产品分析工具，对比授权用户和整体用户之间的投放效果数据。如果结果有差异，您需要调整解决方式中所述的计算方法，以体现该差异。 |

</Accordion>

<div id="campaign-efficiency" />

<Accordion title="投放效率">

| 问题 | 广告投放的eCPI是多少？ |
| --- | --- |
| 问题描述 | eCPI等投放成本相关的指标具有误导性，因为这类数据的计算依赖于精确的用户数。 |
| 解决方式 | <ol><li>按“数据精确度”部分所述方法取得实际用户数（a）。</li><li>eCPI计算公式：eCPI = 成本 /（a）</li></ol> |
| 示例 | ![mceclip1.png](https://files.readme.io/98fc80d1e995ba8ef0cce267fa12f22d48a77d7e25db4add1108144c6de7136d-4406111715217.png)<ul><li>实际激活数为激活数较高的归因框架所产出的激活指标。</li><li>eCPI计算公式：成本/激活数。</li></ul> |

</Accordion>

<div id="using-side-by-side" />

## 并列视图的使用方式

<div id="principles" />

<Accordion title="原理">

* 该视图同时包含两种归因框架所产出的激活数据。
* 请使用数据总览2.0面板中的统一视图，显示某个广告系列的所有可用数据，确保没有使用筛选条件过滤掉任何数据。
* SKAN数据与SKAN面板中的可用数据一致。
* 建议按以下方式在面板中设置一个日期范围，以减少两个归因框架之间因时间不同而造成的数据差异：
  * 时长：
  * 最近日期：
    * 当前日期的3—5天前。具体范围取决于您的用户行为窗口期。
    * 如果您在Google Ads上投放广告，那么最早日期必须为当前日期前8天。

</Accordion>

<div id="display-skan-metrics-in-the-table" />

<Accordion title="在表格中查看SKAN指标">

**请按以下步骤在表格中查看SKAN指标**：

1. 点击⚙（表格设置图标）。   
   打开指标选择窗口。

   ![SelectSkan.png](https://files.readme.io/6b60fa8e2d10a1b61b1bfb4b7a968adb5ee16086d80c9cc8bc097b8e8ed77b51-4408473842833.png)
2. 点击SKAN归因。
3. 点击SKAN激活。
4. 点击SKAN收入。
5. 【可选】请按以下方式添加或移除应用内事件：
   1. 选择应用内事件。
   2. 添加或删除相关的应用内事件。
6. 点击启用。   
   显示所选指标和应用内事件。

</Accordion>

<div id="timerelated-differences" />

<Accordion title="时间相关的数据差异">

<table><thead><tr><th>数据差异</th><th>AppsFlyer</th><th>SKAN</th></tr></thead><tbody><tr><td>历史数据</td><td><p>可用；无限制</p></td><td><p>可用；无限制 </p></td></tr><tr><td>时区</td><td><p>应用层级的指定时区</p></td><td>UTC </td></tr><tr><td>数据时效性 </td><td>持续滚动更新，最多会有60分钟延迟</td><td><p><span>在每天的UTC时间08:00之前更新。</span></p><p>具体的延迟取决于用户行为窗口期的时长。默认默认：2-5天；Google Ads广告：最长13天。</p></td></tr><tr><td>Install date</td><td>激活发生的日期。 </td><td>根据回传接收时间推算。(1) </td></tr><tr><td>衡量时长</td><td>无限制；LTV维度</td><td><p>用户行为窗口期限长12-72小时，默认为24小时。</p></td></tr><tr><td>Attribution lookback window</td><td><ul><li>由广告主或SRN设定</li><li>7天</li></ul></td><td><ul><li>由Apple设定</li><li>点击下载30天</li><li>60天</li></ul></td></tr><tr><td colspan="3"><p>说明</p><p>（1）Google Ads数据更新最长会有13天的延迟。</p></td></tr></tbody></table>

</Accordion>

<div id="cost-clicks-and-impressions" />

<Accordion title="成本、点击和展示">

广告平台会向AppsFlyer提供成本、点击和展示指标。这些指标是两种归因框架都会用到的，不会按归因框架区隔开来。

成本指标遵循以下规律：

* 每天更新6次，平均每4小时一次。
* AppsFlyer会记录与某广告系列相关的首次互动（点击或展示），然后呈现与该互动相关的投放成本。
* 由于SKAN激活是在应用首次打开后的72—120小时内上报的，因此您会在成本关联到激活前数天就看到成本指标。
* Google Ads带来的激活最长会有13天的延迟。

</Accordion>

<div id="data-scope-differences" />

<Accordion title="数据范围差异">

| 数据差异 | AppsFlyer | SKAN |
| --- | --- | --- |
| Platform（系统平台） | 所有 | iOS |
| 归因触点类型 | <ul><li>激活假量</li><li>再互动</li><li>再归因</li></ul> | <ul><li>激活假量</li><li>重新下载（redownloads）</li></ul> |
| 广告收入 | 可用 | <Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-solution-guide#recording-ad-revenue">有限制；具体取决于聚合渠道</Anchor>。 |
| Apple Search Ads | 可用 | 不适用于SKAN归因 |
| 自有媒体 | 可用 | 不适用于SKAN归因 |
| 网页到应用 | 可用 |  |
| 货币 | 应用配置中的指定货币 | USD |

</Accordion>

<div id="matching-considerations" />

<Accordion title="数据匹配注意事项">

<table><thead><tr><th>注意事项</th><th>AppsFlyer</th><th>SKAN</th></tr></thead><tbody><tr><td>代理数据透明化</td><td>支持</td><td><p>激活会被归因到带来该激活的媒体渠道。代理商可以让媒体渠道在广告系列名称中设置对应的<em><a href="/partners/zh/docs/getting-started-agency-onboarding" target="_blank">prt</a></em>前缀，以便识别出代理带来的流量。</p></td></tr><tr><td>广告系列名称变更</td><td><ul><li>支持</li><li>AF会使用广告平台最近一次上报的广告系列名称，来标记与该广告系列ID有关的所有激活，包括之前已经记录到的激活。 </li></ul></td><td><ul><li>不支持</li><li>SKAN使用的是用户激活应用时所上报的广告系列名称，之后不会再有任何变更。也就是说，如果您更改了广告系列名称，就会出现多个广告系列名称对应同一个广告系列ID的现象。 </li></ul></td></tr><tr><td>适用维度</td><td>没有限制</td><td><p>可用</p><p><strong>代理：</strong></p><p>如果您选择的维度不可用，SKAN数据会显示为“none”。</p></td></tr><tr><td>SRN激活指标</td><td>仅限授权用户。因此，AppsFlyer上报的指标会低于SKAN及SRN上报的指标。 </td><td>包括所有由SKAN归因到的激活，通常会高于AppsFlyer的指标。 </td></tr><tr><td>隐藏的SKAN投放数据</td><td colspan="2"><p>面板表格中可显示的数据行数有限，无法显示的各行会合并成一行，标识为<em>其他</em>。</p><p>如需查看“其他”行的完整数据，请将整个表格导出到Excel表中。 </p></td></tr></tbody></table>

</Accordion>

<div id="dimensions-available" />

<Accordion title="可用维度">

并列视图的可用维度如下：

* 媒体渠道
* 即广告系列的名称
* 即广告系列的ID
* Date
* 归因类型

</Accordion>

<div data-zendesk-anchors="finding-the-best-ios-14-campaign-performance-metrics=%E6%89%BE%E5%88%B0%E6%9C%80%E7%90%86%E6%83%B3%E7%9A%84ios-14%E6%8A%95%E6%94%BE%E6%95%88%E6%9E%9C%E6%8C%87%E6%A0%87 h_01HYAQAR84BP9MRRXP7BPPDJ4N=%E6%89%BE%E5%88%B0%E6%9C%80%E7%90%86%E6%83%B3%E7%9A%84ios-14%E6%8A%95%E6%94%BE%E6%95%88%E6%9E%9C%E6%8C%87%E6%A0%87 h_01HYAQAR856G6VARSH746SJB5Z=campaign-precision h_01HYAQAR856JT2JX28SE3QY7VZ=campaign-effectiveness h_01HYAQAR85GZN1RZYNV2MV7DAP=campaign-efficiency using-sidebyside=%E5%B9%B6%E5%88%97%E8%A7%86%E5%9B%BE%E7%9A%84%E4%BD%BF%E7%94%A8%E6%96%B9%E5%BC%8F h_01HYAQAR85FY6K8R574GWFQW91=%E5%B9%B6%E5%88%97%E8%A7%86%E5%9B%BE%E7%9A%84%E4%BD%BF%E7%94%A8%E6%96%B9%E5%BC%8F h_01HYAQAR85Z09SXSE8JGTG5AMF=principles h_01HYAQAR85V6CD29T9AY9XYX0Z=display-skan-metrics-in-the-table h_01HYAQAR85QSTB8QZPGMEV6MR9=timerelated-differences h_01HYAQAR85A03KNAHC5TEAZAZK=cost-clicks-and-impressions h_01HYAQAR85SPYQKDFP3CRGW5FN=data-scope-differences h_01HYAQAR85FSAXQ25X16N6XQEW=matching-considerations h_01HYAQAR85XF7CEG6F7PC44F1C=dimensions-available" />
