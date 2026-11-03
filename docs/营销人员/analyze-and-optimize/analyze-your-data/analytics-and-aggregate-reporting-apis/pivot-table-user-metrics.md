---
title: 数据透视表——用户指标
metadata:
  keywords:
    - Pivot
    - Advertisers
    - 透视表
    - Premium
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2017-03-16T13:11:23Z'
  edited_at: '2026-10-14T10:03:25Z'
  id: 115001421846
  locale: zh-cn
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/zh-cn/articles/115001421846
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要**：您可以使用数据透视表查看各类用户指标——包括LTV维度、活跃维度、Protect360以及留存数据，并以CSV文件的形式下载查询结果，用于相关数据的BI入库。数据透视表支持一次查询多个应用的数据。您还可以使用该面板生成Master API接口。

![](https://files.readme.io/890612985a8346e6b5dcdd66d3e7ad47ac4e46b5b98bf7457b19e328cd9b6c1f-51911409860369.gif) altFull\_Funnel.gif

## 关于透视报告页面

您可以使用数据透视表面板生成包含UA指标的自定义报告。该面板提供多种预定义报告，您可以将其作为一个模板，在此基础上创建您的自定义报告。由账户下的某个用户创建的报告对其他所有用户都可见。

我们提供下列预定义数据透视报告：

* 媒体渠道（按日期）
* 全层级
* 成本分析

**请注意**：要在透视中查看活动数据，活动必须有安装。

## 数据透视面板的使用方式

您可以在面板中创建并修改现有的数据透视表。具体操作流程请见下文各章节的说明。

**数据透视表的使用方式如下**：

* 从AppsFlyer后台的侧边栏中选择**分析** > **数据透视表**。  
  界面会显示现有报告的列表。

<div id="pivot-page-controls-and-options" />

<Accordion title="数据透视表面板——控件和选项">

<Table>
  <thead>
    <tr>
      <th>
        列标题/选项
      </th>
      <th>
        说明
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        名称
      </td>
      <td>
        选择一个报告名称，查看相关的数据透视表。
      </td>
    </tr>
    <tr>
      <td>
        点击列标题
      </td>
      <td>
        您可以点击部分列标题，调整表格的排序方式（具体取决于界面提示）。
      </td>
    </tr>
    <tr>
      <td>
        上次修改时间
      </td>
      <td>
        上次修改报告结构的时间。
      </td>
    </tr>
    <tr>
      <td>
        修改人
      </td>
      <td>
        修改了数据透视表的用户名称。
      </td>
    </tr>
    <tr>
      <td>
        应用名称
      </td>
      <td>
        * 若透视表中仅包含一个应用：显示该应用的名称
        * 若透视表中包含多个应用：显示应用数量
      </td>
    </tr>
    <tr>
      <td>
        操作
      </td>
      <td>
        | 操作 | 说明 |
        | --- | --- |
        | 复制 | 复制现有的数据透视报告 |
        | 重命名 | 更改报告名称 |
        | 查看历史日志 | 查看报告结构的经手人、具体处理方式以及处理时间。 |
        | 复制Master API链接 | 生成一个URL链接，通过<Anchor target="_blank" href="/marketers/zh/docs/master-api-user-acquisition-metrics-via-api">Master API</Anchor>拉取数据。如需使用Master API，请先获取<Anchor target="_blank" href="/marketers/zh/docs/managing-appsflyer-tokens">API token</Anchor>（需要管理员权限），将其用于认证头（authentication header）中。 |
        | 删除 | 删除选定的数据透视表。 |
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="add-a-pivot-report" />

<Accordion title="添加数据透视报告">

**添加数据透视报告的方法如下**：

1. 点击**添加数据透视表。  
   界面会打开新建数据透视表的窗口。**
2. 输入该数据透视表的名称。
3. 点击**提交**。  
   界面会打开添加数据透视表的窗口。
4. 选择所需的应用、维度和指标，并设置筛选条件以及数据显示方式。

| 板块 | 说明 |
| --- | --- |
| 应用 | 选择该数据透视表所覆盖的应用。 |
| 维度 | [<Image alt="" src="https://files.readme.io/9b0fda106b5de3401a71ceaeb45bac5cc4215b164e263a1422bf6097a9320553-360002246845.png" width="221px" />](https://files.readme.io/9b0fda106b5de3401a71ceaeb45bac5cc4215b164e263a1422bf6097a9320553-360002246845.png)<br /><br />您可以使用这些维度对数据透视表的分组方式、结构和排序进行调整。<br /><br />**请按以下方式选择维度**：<ol><li>点击**维度**。</li><li>选择一个维度，将其拖曳到所需板块内。在各板块中的维度设置分别会对透视表起到下列作用：<ul><li>**行**：“行”板块中的维度设置决定了报告的分组层级。</li><li>**列**：“列”板块中所选的各维度在表格中单独成列，因此“列”中的维度越多，数据表就会扩展得越大。</li></ul></li></ol> |
| KPI | [<Image alt="" src="https://files.readme.io/6b210b1bdc38ee96ef8b73dcacbac3389b914aaef76a680604e41d4becbad807-360000640109.png" width="294px" />](https://files.readme.io/6b210b1bdc38ee96ef8b73dcacbac3389b914aaef76a680604e41d4becbad807-360000640109.png)<br /><br />KPI按以下类别分组<ul><li>LTV</li><li><Anchor target="_blank" href="/marketers/zh/docs/activity-dashboard#特点与局限性">活跃数据</Anchor></li><li>留存：留存天数、留存率。 **请注意**：在留存板块中向下滚动可，可看到留存率选项及Protect360部分（对启用了Protect360的账户开放）。</li><li><Anchor target="_blank" href="/marketers/zh/docs/master-api-user-acquisition-metrics-via-api#kpis">指标说明</Anchor></li></ul>大多数情况下，建议将KPI拖曳到“值”板块。您也可以根据实际需求将KPI用作一个维度。<br /><br />将KPI拖曳到所需板块。 |
| 值 | 选择一个运算符，为各个KPI设置计算方式：<ul><li>加总</li><li>计数</li><li>最大值</li><li>最小值</li><li>比率</li><li>平均值</li></ul> |
| 筛选条件 | 将所需筛选条件拖曳到筛选条件板块。选择筛选条件的设置方式:<ul><li>文本</li><li>多选</li></ul> |

</Accordion>

<div id="view-a-pivot-report" />

<Accordion title="查看数据透视报告">

[![](https://files.readme.io/cb549ba9b17e75f05d723cdb56335232dd40c419ebfe7ecad08b80a71be46296-360002246865.png)](https://files.readme.io/cb549ba9b17e75f05d723cdb56335232dd40c419ebfe7ecad08b80a71be46296-360002246865.png)

**数据透视报告的查看方式**：

* 在数据透视表面板中选择一个报告后，界面就会展示该报告。
* 您可以使用下列报告显示选项：

| 板块 | 说明 |
| --- | --- |
| (1) 选定维度 | 第一列是您选定的报告分组维度。这些维度按数据透视表编辑页面中显示的顺序进行分组。在上图示例中，数据表的主要维度为应用名称，其次是媒体渠道，最后为激活日期。 |
| （2）指标 | 其余各列是您在数据透视表编辑页面的**值**板块中选择的KPI。在上图示例中，第一个KPI是展示量，之后为点击、激活等等。 |
| （3）筛选条件 | 您在数据透视表编辑页面中为该报告设置的筛选条件会显示在此处。您可以输入字符串，或在下拉菜单中选择多个选项。<br /><br />[**![](https://files.readme.io/e7f16a6e848b8e9f6942615dd14257b3c0e358cefabbdcfe86c498612fcaae26-115004149786.png)**](https://files.readme.io/e7f16a6e848b8e9f6942615dd14257b3c0e358cefabbdcfe86c498612fcaae26-115004149786.png) |
| （4）选定日期 | 使用日期选择器将查询范围缩小到特定日期。您可以使用预先设定的日期范围按钮，也可以选择自定义的日期范围。 |
| （5）操作 | [报告列表](/docs/pivot-table-user-metrics#view-a-pivot-report)中各报告的可用操作可能有所不同，点击具体报告一行中的操作图标后即可查看可用操作。 |

</Accordion>

## 特点与局限性

<div id="traits-and-limitations::e6883df" />

<Accordion title="特点与局限性">

| 特点 | 说明 |
| --- | --- |
| 广告平台对报告的访问权限 | 否 |
| 代理访问权限 | 否 |
| 代理数据透明化 | 是 |
| 应用配置中设定的本地时区 | 是<br /><br />例外情况：在以下场景中，AppsFlyer会使用默认时区UTC +0，并忽略相关应用的本地时区：<ul><li>报告中包含多个应用的数据，且这些应用中设定的本地时区不一致。</li><li>所有应用的指定时区一致，但在报告周期内至少有一个应用的时区有变化。报告时段的计算方法如下：<ul><li>起始日期：转化日期范围的第一天。</li><li>截止日期：转化日期范围的最后一天加上报告所显示的时间范围的总天数。举例来说，转化日期范围的最后一天为2019年1月1日，报告时长为30天，此时报告周期的截止日期为2023 年1月31日。</li></ul></li></ul> |
| 应用配置中设定的本地货币 | 总是以美元（USD）为单位返回查询结果。 |
| 自然量数据 | 包含 |
| 非自然量数据 | 包含 |
| 数据时效性 | 数据时效性：每天更新一次，与<Anchor target="_blank" href="/marketers/zh/docs/master-api-user-acquisition-metrics-via-api">Master API</Anchor>的时效性一致。 |
| 账户下的用户是否可访问 | 是 |
| 再营销收入 | 包含 |
| 广告系列名称变更 | 广告系列名称发生变更后，数据透视表不会将相关的成本数据全部显示到新名称下，也就是说每个广告系列名称下都会有一个对应的成本。 |
| 再营销数据 | <ul><li>一般来说，使用 <Anchor target="_blank" href="/marketers/zh/docs/cohort-and-retention-dashboard">群体</Anchor> 来查看重定向数据。</li><li>2025年2月1日之后的流量活动KPI包括统一数据（UA和重定向数据一起）。</li></ul> |
| 成本数据 | AppsFlyer主要通过Cost API从对接渠道处拉取成本数据。<Anchor target="_blank" href="/marketers/zh/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">另请参考各对接渠道支持的数据维度。</Anchor> |
| 留存率 | 如需查看留存率，请在报告中添加激活指标 |
| 报告行数上限 | 20万 |
| 历史数据 | <ul><li>LTV数据：5年</li><li>活跃数据：3年</li></ul> |

</Accordion>

<div data-zendesk-anchors="pivot-reports-page=%E5%85%B3%E4%BA%8E%E9%80%8F%E8%A7%86%E6%8A%A5%E5%91%8A%E9%A1%B5%E9%9D%A2 h_01HJR8389QPFKR9X6V52N7PHMM=%E5%85%B3%E4%BA%8E%E9%80%8F%E8%A7%86%E6%8A%A5%E5%91%8A%E9%A1%B5%E9%9D%A2 pivot-procedures=%E6%95%B0%E6%8D%AE%E9%80%8F%E8%A7%86%E9%9D%A2%E6%9D%BF%E7%9A%84%E4%BD%BF%E7%94%A8%E6%96%B9%E5%BC%8F h_01HJR8389QPNRX8Y26VQWN0ZXP=%E6%95%B0%E6%8D%AE%E9%80%8F%E8%A7%86%E9%9D%A2%E6%9D%BF%E7%9A%84%E4%BD%BF%E7%94%A8%E6%96%B9%E5%BC%8F pivot-page%E2%80%94controls-and-options=pivot-page-controls-and-options h_01HJR8389QDDWR8ZKCSDZGVAGP=pivot-page-controls-and-options h_01HJR8389R2C1E42JN9NFMS4CJ=add-a-pivot-report h_01HJR8389SQ40HZ8EXQME4807S=view-a-pivot-report traits-and-limitations=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 h_01HJR8389SPJZG6AYGABB17V1N=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 h_01HJR8389S19TVMVR60ZYAJMAA=traits-and-limitations::e6883df" />
