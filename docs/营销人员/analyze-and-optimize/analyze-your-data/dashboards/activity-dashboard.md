---
title: 活跃数据面板
metadata:
  keywords:
    - activity report
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
  created_at: '2016-01-12T15:50:15Z'
  edited_at: '2026-10-14T10:07:31Z'
  id: 207602503
  locale: zh-cn
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/zh-cn/articles/207602503
---
> **概要：** 您可以在活跃数据面板中查看选定时间范围内的应用使用情况、互动情况以及应用内事件指标。当日指标实时更新。

![ActivityDB.png](https://files.readme.io/8150eafc018c83ae2b1030702129bda12419dfac60eb8664187c2acd66136df3-4420170646289.png)

## 活跃数据面板

* 包含自然量和非自然量数据
* 活跃面板中的日期指的是事件发生的日期，而非<Anchor target="_blank" href="/marketers/zh/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">LTV维度</Anchor>的日期
* 数据时效性：
  * **当日**：<Anchor target="_blank" href="/marketers/zh/docs/about-data-freshness-and-timezone-support#continuous-aka-realtime">持续滚动</Anchor>更新。比如日活（DAU）、应用打开（sessions）、收入
  * **平均：** 每天更新一次。比如月活（MAU）、平均日活（DAU）、平均月活（MAU）
* 筛选条件中的“国家/地区”是指用户激活时所在的位置。

> 👍 **提示**
>
> 如需进一步了解活跃数据面板，我们在<Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7802/play/18621/the-activity-dashboard">AppsFlyer充电站里为您准备了相关课程</Anchor>，视频虽短，但干货满满！

## 面板功能与布局

<div id="metric-definitions" />

<Accordion title="指标定义">

<Table>
  <thead>
    <tr>
      <th>
        指标
      </th>
      <th>
        说明
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="dau"></span>
        日活
      </td>
      <td>
        * 单日活跃用户：一天中打开过相关应用至少一次的独立用户数。
        * 日活的统计以应用打开（sessions）数据为基础。
      </td>
    </tr>
    <tr>
      <td><span id="average-dau"></span>
        平均日活
      </td>
      <td>
        所选时间段内的每日平均活跃用数量。

        示例：平均日活的计算方式

        > 📄
        >
        > |  | 星期日 | 星期一 | 星期二 |
        > | --- | --- | --- | --- |
        > | <span id="daily-active-unique-users"></span>每日活跃独立用户数 | 10 | 12 | 8 |
        >
        >
        >
        > **平均日活** = (10+12+8)/3= 10
      </td>
    </tr>
    <tr>
      <td><span id="mau"></span>
        月活
      </td>
      <td>
        单月活跃用户：

        * **细分：** 在过去31天中打开过相关应用至少一次的独立用户数量（仅统计一次）。
        * **月度：** 以日历为准的当月内打开过相关应用至少一次的独立用户数量（仅统计一次）。
      </td>
    </tr>
    <tr>
      <td><span id="daumau-rate"></span>
        日活/月活比率
      </td>
      <td>
        * 该指标可说明回流用户的占比。如果日活/月活比率超过50%，则表示在过去31天中，用户平均有15天打开了相关应用。
        * 日活/月活比率用于衡量用户粘性，并可让您快速了解用户留存的大致情况。
      </td>
    </tr>
    <tr>
      <td><span id="revenue"></span>
        收入
      </td>
      <td>
        选定时间段内产生的收入。该收入包含应用内收入（若上报）以及广告收入。
      </td>
    </tr>
    <tr>
      <td><span id="arpdau"></span>
        ARPDAU
      </td>
      <td>
        日活用户平均收入  
        计算方式为：（第[n]天收入/第[n]天日活）的总和/天数

        > 📄 **示例：ARPDAU的计算方式**
        >
        > | 第[n]天 | 当日收入（$） | 日活 | 平均每日用户收入（$） |
        > | --- | --- | --- | --- |
        > | <span id="day-1"></span>第1天 | 10 | 5 | 2 |
        > | <span id="day-2"></span>第2天 | 16 | 4 | 4 |
        > | <span id="day-3"></span>第3天 | 30 | 5 | 6 |
        > |  |  | 总计： | 12 |
        > |  <span id="::4eb0b020"></span>|  | 天数 | 3 |
        > |  <span id="::b35cc38c"></span>|  | **ARPDAU** | 4 |
      </td>
    </tr>
    <tr>
      <td><span id="sessions"></span>
        应用打开（Sessions）
      </td>
      <td>
        选定时间段内的应用打开（session）数量（相关应用需上报该数据）
      </td>
    </tr>
    <tr>
      <td><span id="installs"></span>
        激活
      </td>
      <td>
        在选定时间段内产生的激活数量
      </td>
    </tr>
    <tr>
      <td><span id="average-ecpi"></span>
        Average eCPI
      </td>
      <td>
        请注意：
      </td>
    </tr>
    <tr>
      <td><span id="conversion-rate"></span>
        转化率
      </td>
      <td>
        **请注意**：
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="detailed-tab" />

<Accordion title="“细分”选项卡">

细分分析选项卡分为四个部分：主要指标、活跃用户趋势以及活跃数据摘要表。

<table><tbody><tr><td colspan="2"><h4><strong><span id="headline-metrics"></span>主要指标</strong></h4></td></tr><tr><td> </td><td><img alt="ActivityHeadLines_us-en__1_.png" src="https://files.readme.io/a4f1a5316eeacf0f635bbeadf52d490dd0276bb8a1fe9c0e32db7008d11d044b-360012584838.png"/></td></tr><tr><td> </td><td> <strong>平均活跃用户</strong><ul><li>平均日活：指定时间范围内的日活用户数。</li><li>平均月活：指定时间范围内的平均月活用户数。该指标是一个移动平均值，从选定时间段内的每一天各往前推天31天，以此为基础进行计算。请注意，查看某个月（假设是三月）的MAU数据时，需要将指定时间范围的最后一天设置为该月过后的第一天（即4月1日）。</li></ul></td></tr><tr><td> </td><td> <strong>激活总数：</strong>激活数量分为自然激活和非自然激活</td></tr><tr><td> </td><td> <strong>应用打开总数</strong>（sessions）：应用打开（sessions）数量分为自然用户和非自然用户的应用打开</td></tr><tr><td> </td><td> <strong>总收入</strong>：收入分为自然用户和非自然用户产生的收入</td></tr><tr><td colspan="2"><h4> <br/><strong><span id="activity-trends"></span>活跃用户趋势</strong><br/> </h4></td></tr><tr><td> </td><td><p><strong>带有对比功能的趋势图</strong></p><p><img alt="TrendLinWithComp_us-en.png" src="https://files.readme.io/b9edb3e409dc13bc72aebdccdc499fa2dcd9abf4549fb0170bf0cdc7036eee15-360012507997.png"/></p><ul><li>趋势图可呈现KPI或应用内事件相关指标的变化趋势。</li><li>您还可以打开对比功能，在图中添加对比趋势线，只需在右侧选择<strong>对比过去一</strong>天、周、月、季度或年即可。 </li><li>如果您选择了“月”，则该图表会将横轴中的每一天对应上个月的同一天进行对比。 </li></ul><p>可用KPI包括：</p><ul><li><span>日活</span></li><li><span>月活</span></li><li><span>收入</span></li><li><span>ARPDAU</span></li><li><span>应用打开（Sessions）</span></li><li><span>日活/月活比率</span></li></ul><p><span>可用的应用内事件衡量指标包括：</span></p><ul><li><span>数量</span></li><li><span>独立用户数</span></li><li><span>收入</span></li></ul></td></tr><tr><td colspan="2"><h4> <br/><span id="activity-summary-table"></span>活跃数据摘要表  </h4></td></tr><tr><td> </td><td><p>活跃数据摘要表：</p><ul><li>最多可呈现50个媒体渠道及相关的展示、点击和激活数据等。（如需获取所有数据，请使用<a href="./master-api-user-acquisition-metrics-via-api" target="_blank">Master API</a>或<a href="./pivot-table-user-metrics" target="_blank">数据透视表</a>）。 </li><li>按应用打开（session）数量排序。 </li><li>呈现的数据最多可深入到广告系列层级。</li><li>便于查看日活用户中的新老用户数量（老用户 = 日活数 - 激活数）。</li></ul><p><span>请按以下方式使用数据摘要表：</span></p><ul><li><span>使用筛选条件和分组维度调整表格中呈现的数据。</span></li><li><span>可点击表格各列的表头来调整排序维度。</span></li><li>可按<strong>应用内事件</strong>筛选数据，以便查看具体的应用内事件。</li><li>切换不同的视图类型：<ul><li> <strong>摘要：</strong> 选定应用内事件的总数</li><li> <strong>应用内事件：</strong> 按应用内事件细分</li></ul></li></ul></td></tr></tbody></table>

</Accordion>

<div id="highlevel-tab-previous-twelvemonths" />

<Accordion title="月度选项卡：过去12个月">

![ActivityHiLevel.png](https://files.readme.io/42636f5b13dca3a2209ea295c02e784175dfc92a2523c861220b87baed859541-4420194466065.png)

该选项卡中包含过去12个月的历史数据，便于您查看总体的应用使用情况，其中会呈现以下图表：

* 每月毛利润：收入、成本、毛利润

</Accordion>

## 特点与局限性

| 特点 | 说明 |
| --- | --- |
| 数据时效性 | <ul><li>**指标：** 实时更新，详见下图。</li><li>**平均指标**：每天更新一次，详见下图。**请注意**：该面板不对平均指标进行实时计算，这是为了避免天数不完整时的数据造成平均指标失真。如果选定时间段内包含当前日期，会发生以下情况：<ul><li>如果选定时间段仅包含当前日期：面板不显示平均指标</li><li>如果选定时间段是包含当前日期的较长一段时间：面板计算平均指标时不使用来自当前日期的数据。</li></ul></li><li>**广告收入：** <Anchor target="_blank" href="/marketers/zh/docs/roi360-guide-ad-revenue-attribution#data-freshness">数据记录有延时</Anchor>，数据上报归类方式如下：<ul><li>汇总层级数据：归到第1天（即拉取数据的当天）</li><li>用户级数据：规到第0天（即广告展示的日期）。</li></ul></li></ul> |
| 卸载 | 不支持 |
| 再营销 | <ul><li>应用打开总数（sessions）：</li><li>日活</li><li>月活</li><li>日活用户数 DAU/月活用户数 MAU</li><li>ARPDAU</li><li>成本</li><li>点击</li><li>展示</li><li>转化率</li><li>eCPI（有效激活成本）</li></ul> |
| ARPDAU | 活跃数据面板和数据透视表中的ARPDAU可能会有差异。 |
| 历史数据 | <ul><li>3年</li><li>月度选项卡：1年</li></ul> |
| 数据呈现范围 | <ul><li>最多2个月。如果选定时间超过2个月，面板会自动将时间段缩短到2个月，并弹出提示消息。</li></ul> |
| 按国家/地区分组 | <ul><li>最多可显示62个国家/地区（按活跃维度的应用打开数量排序）</li></ul> |
| 按广告系列分组 | 此分组维度仅在选择具体媒体渠道后可用 |
| 维度值 |  |
| 代理 | <Anchor target="_blank" href="/marketers/zh/docs/manage-data-access-permissions">详情请见此处说明。</Anchor> |

<div data-zendesk-anchors="activity-dashboard=%E6%B4%BB%E8%B7%83%E6%95%B0%E6%8D%AE%E9%9D%A2%E6%9D%BF h_01HHYHP1HE8G5VA6GSAVTQDDDN=%E6%B4%BB%E8%B7%83%E6%95%B0%E6%8D%AE%E9%9D%A2%E6%9D%BF h_01HHYHP1HEJHKQKCNC5R26ZE3J=%E6%8F%90%E7%A4%BA dashboard-features-and-layout=%E9%9D%A2%E6%9D%BF%E5%8A%9F%E8%83%BD%E4%B8%8E%E5%B8%83%E5%B1%80 h_01HHYHP1HEBTACW6Q3MJ3QJJ95=%E9%9D%A2%E6%9D%BF%E5%8A%9F%E8%83%BD%E4%B8%8E%E5%B8%83%E5%B1%80 h_01HHYHP1HESQBPYJWK81ZHQDVH=metric-definitions h_01HHYHP1HFZBRTWB8MJ1F6XKZS=%E7%A4%BA%E4%BE%8Barpdau%E7%9A%84%E8%AE%A1%E7%AE%97%E6%96%B9%E5%BC%8F h_01HHYHP1HFF92WQMQAFKWWNDJK=detailed-tab h_01HHYHP1HFNDXC2E55Q7PDE9WY=headline-metrics h_01HHYHP1HFZR9JN2H0RNAG1QTK=activity-trends h_01HHYHP1HFV8AZ2FYKJ300488A=activity-summary-table h_01HHYHP1HF6FCXPS2SHTH0RBXC=highlevel-tab-previous-twelvemonths specifications-and-limitations=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 h_01HHYHP1HFNJF4JJZY4CSVZ3GY=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7" />
