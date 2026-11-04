---
title: 解决AppsFlyer面板和报告中的数据差异问题
metadata:
  keywords:
    - dashboard
    - activity
    - Advertisers
    - ltv
    - life time value
    - lifetime value
    - lifetime
    - Agencies
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
  created_at: '2017-11-07T12:42:27Z'
  edited_at: '2026-10-14T10:08:18Z'
  id: 115005600889
  locale: zh-cn
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/zh-cn/articles/115005600889
---
> **概要：** 在对比不同面板和报告的数据时，您可能会发现数据存在差异。这类差异往往是由于数据类型不同所致：有些反映的是LTV（用户终身价值），而另一些反映的则是活跃维度数据。LTV数据与特定日期范围内的激活有关，而活跃数据与特定日期范围内发生的事件有关。

<div id="about-data-differences-and-discrepancies" />

## 关于数据差异

在对比不同面板和报告的数据时，出现数据差异的常见原因可能是您对比的并不是同一类型的数据。请根据以下速查清单，确保您比较的是相同维度的数据：

* 应用平台是否相同（Android、iOS、CTV等）？
* 应用ID是否相同？
* 面板或报告中使用的过滤条件是否一致？
* 货币是否相同？
* 时区是否相同？
* <Anchor target="_blank" href="/marketers/zh/docs/about-data-freshness-and-timezone-support">数据时效性</Anchor>（更新时间）是否一致？
* 数据是<Anchor target="_blank" href="/marketers/zh/docs/aggregated-and-analytics-reporting-overview#toolapi-comparison">汇总数据</Anchor>还是<Anchor target="_blank" href="/marketers/zh/docs/raw-data-reporting-overview">原始数据</Anchor>？
* 数据类型是LTV还是活跃维度数据？

造成数据差异最常见的原因之一是将LTV面板或报告与活跃数据面板或报告进行对比。 有关LTV与活跃数据的更多区别，请参见下文说明。

<div id="ltv-vs-activity" />

## 区分LTV数据与活跃数据

用户事件数据的分析方式分为两种。事件数据与用户激活后的行为相关，比如应用内购买、注册、完成关卡等等。AppsFlyer对于事件数据提供两种分组维度，即获客日期以及事件发生日期。

* 我们将按获客日期分组的激活后事件数据称为用户生命周期价值（LTV）维度的数据，
* 同时将按事件日期分组的激活后事件数据称为活动。

**请注意**：激活数据既不是LTV维度也不是活跃维度。

这两种数据广告主都会用到，但是用途不同。因此我们同时提供两种数据。

<div id="ltv-data" />

### LTV数据

* LTV数据是指在特定时间段内转化/激活应用的用户在其生命周期中所完成的事件。该日期范围针对的是在此期间内激活的用户，用于衡量他们作为“客户”期间所带来的价值。如果某用户在指定日期之前就已完成转化或激活，即使其在该日期范围内发生了事件，相关数据也不会显示在LTV面板和报告中。
* LTV数据用于评估不同媒体渠道的**用户质量**。在优化广告投放时，需要依赖LTV数据。

<div id="activity-data" />

### 活跃数据

* 活跃数据展示的是用户在指定日期范围内的行为数据，即已激活用户在该时间段内触发了哪些事件。在这种数据维度下，用户是否在日期范围内完成转化/激活并不重要。
* 由于活跃数据中呈现的是按时间顺序细分的事件，因此适用于衡量特定时间段内相关媒体渠道的总体效果。比如您可以通过活跃数据来考察所有应用用户在某个月内所完成的购买事件数量。
* 您还可以使用或活跃数据来分析用户行为的月环比情况。

<div id="the-train-analogy" />

> 📄 **关于火车的类比**
>
> 我们拿火车来做类比，帮助您更直观地理解活跃数据和LTV数据之间的区别。
>
> **活跃数据：** 假设一列火车从您眼前驶过。在这列火车的行驶过程中，您只能看到车上乘客在某一瞬间的行为。这就好比是活跃维度的数据。
>
> <Image alt="activity_data.jpg" src="https://files.readme.io/70a37d5dc16f0817d137f9011be9af5360bd7c4d2469a8abf9430fe69b2671c3-360002436957.jpg" width="400px" />
>
> **LTV数据**：假设您登上了这列火车，观察内部情况。这列火车分为多节车厢。
>
> * 您在出发站台跟其他乘客一起登上这列火车（用户激活应用）。
> * 在这趟行程中，您可以看到车厢内乘客的所有行为。您对车厢内乘客的观察到乘客下车为止（用户卸载应用）。
> * 您无法观察到其他车厢内的乘客，因为他们上车的时间与您不同。这就好比是LTV维度的数据。
>
> <Image alt="ltv_data.jpg" src="https://files.readme.io/78925644f263b6d5ea5630a09e0b2155d153ce2c4b3060be5c8d7cb9ba0ce4e6-360002436977.jpg" width="400px" />

<div id="appsflyer-dashboards-and-reportsltv-or-activity" />

### AppsFlyer面板和报告——LTV数据 or 活跃数据？

营销人员可以利用AppsFlyer面板来优化其非自然流量。AppsFlyer中的大部分面板和报告都以LTV维度来呈现数据，这是因为营销人员一般需要从LTV维度评估的投放效果。所有汇总数据报告都是LTV维度的数据，而所有原始数据报告都是活跃数据。

下表显示哪些面板和报告显示的是LTV数据，哪些是活跃数据。

| 数据来源 | 数据类型 |
| --- | --- |
| 数据总览面板 | LTV |
| My Dashboards | LTV |
| SKAN总览面板 | LTV |
| Protect360激活 | LTV |
| Protect360应用内事件 | 活跃 |
| 活跃数据面板 | 活跃 |
| 事件面板 | LTV |
| 留存 | LTV |
| 群组 | LTV |
| 汇总数据效果报告 | LTV |
| 原始数据报告 | 活跃 |
| 再营销报告 | LTV |
| Protect360防作弊报告 | 活跃 |
| Master API——投放效果KPI | 两者皆有 |
| 数据透视表 | 两个维度同时呈现 |

<div id="compare-data-between-different-dashboards-and-reports" />

## 不同面板和报告之间的数据对比

以下内容为您说明了如何在对比不同面板和报告数据时，有效规避和排查数据差异问题。

<div id="compare-ltv-and-activity-data-in-appsflyer" />

<Accordion title="在AppsFlyer中对比LTV数据与活跃数据">

在对比AppsFlyer中的LTV数据与活跃数据时，需要注意以下两点关键差异：

1. 活跃数据中包含**在选定时间段之前激活**的用户所产生的事件。
2. LTV数据中包含**在选定时间段之后发生**的事件 。

为了确保数据之间的可比性，在进行对比分析时需要先消除这些差异。您可以从活跃数据中选取LTV数据，或从LTV数据中选取活跃数据，来达成此目的。**请注意**：类型相近的数据之间也可能会有轻微的差异，这是由于报告生成的时间不同而造成的。

<div id="to-retrieve-ltv-data-out-of-raw-activity-data" />

#### 从原始活跃数据中检索LTV数据：

1. 从AppsFlyer后台的侧边栏中选择**报告**>**原始数据导出**。
2. 将**当前日期设置为日期范围的最后一天** （解决差异2）。
3. 下载应用内事件的原始数据报告。
4. 使用**激活时间**字段来筛选数据，剔除起始日期之前发生的激活（解决差异1）。

<div id="compare-inapp-event-raw-data-with-the-activity-view" />

<div id="reconcile-raw-data-with-activity-event-metrics" />

<div id="to-retrieve-activity-data-out-of-ltv-data" />

#### 从LTV数据中选取活跃数据：

1. **在AppsFlyer中，选择在指定日期范围内开始发送激活的媒体渠**道（解决差异1）。  
   这是为了确保活跃数据中不包含这段时间之前激活的用户在此时段内完成的事件。
2. 将**当前日期设置为日期范围的最后一天** （解决差异2）。   
   这是为了确保LTV数据中不包含这段时间内激活的用户在此时段外完成的事件。

</Accordion>

<div id="compare-different-appsflyer-aggregated-data-dashboards-and-reports" />

<Accordion title="对比AppsFlyer汇总数据面板和报告中的数据">

在对比AppsFlyer各类汇总数据面板和报告时，出现数据差异的原因之一可能是LTV数据与活跃数据间的维度差异。

按照国家/地区（geo）进行数据汇总时，出现差异的另一个原因可能是：在AppsFlyer面板中，geo指的是激活发生所在的地区；而在原始数据报告中，geo则指事件发生所在的地区。

除此之外也可能存在其他导致数据差异的因素。<Anchor target="_blank" href="/marketers/zh/docs/aggregated-and-analytics-reporting-overview#toolapi-comparison">建议参考汇总报告方式对比以了解更多详细信息</Anchor>

</Accordion>

<div id="compare-appsflyer-data-with-external-data" />

<Accordion title="将 AppsFlyer 数据与外部数据进行比较">

绝大部分提供数据的平台，包括Google和Apple等，都呈现活跃数据，而非LTV数据。因此，如需对AppsFlyer的数据与其他平台的数据进行对比，您一般需要使用Appsflyer原始数据报告中的活跃数据。

请注意：Meta Ads提供不完整的LTV数据，仅提供激活后28天的数据。

除此之外也可能存在其他导致数据差异的因素。相关文档

* <Anchor target="_blank" href="/marketers/zh/docs/google-analytics-integration-discrepancies">Google Analytics差异</Anchor>
* <Anchor target="_blank" href="/marketers/zh/docs/meta-ads-discrepancies">Meta ads数据差异</Anchor>
* <Anchor target="_blank" href="/marketers/zh/docs/snapchat-integration-discrepancies">Snapchat差异</Anchor>
* <Anchor target="_blank" href="/marketers/zh/docs/google-ads-adwords-faq-and-discrepancies">Google Ads数据差异</Anchor>
* <Anchor target="_blank" href="/marketers/zh/docs/x-ads-formerly-twitter-ads-faq-and-discrepancies">X ads数据差异</Anchor>
* <Anchor target="_blank" href="/marketers/zh/docs/attribution-discrepancies-between-tiktok-for-business-and-appsflyer">TikTok差异</Anchor>
* <Anchor target="_blank" href="/marketers/zh/docs/resolve-appsflyer-app-stores-discrepancies">应用商店差异</Anchor>
* <Anchor target="_blank" href="/marketers/zh/docs/discrepancies-between-appsflyer-and-third-party-platforms">第三方平台差异</Anchor>

</Accordion>

<div data-zendesk-anchors="ltv-vs-activity=%E5%85%B3%E4%BA%8E%E6%95%B0%E6%8D%AE%E5%B7%AE%E5%BC%82 h_01HKA0R42YZMAM5Y20B7T2JCDZ=%E5%85%B3%E4%BA%8E%E6%95%B0%E6%8D%AE%E5%B7%AE%E5%BC%82 h_01J5WGZ13WPMNSB1NA0SMA77WJ=%E5%8C%BA%E5%88%86ltv%E6%95%B0%E6%8D%AE%E4%B8%8E%E6%B4%BB%E8%B7%83%E6%95%B0%E6%8D%AE ltv-data=ltv%E6%95%B0%E6%8D%AE h_01HKA0R42YQ2CJS67MDQSJHKEW=ltv%E6%95%B0%E6%8D%AE activity-data=%E6%B4%BB%E8%B7%83%E6%95%B0%E6%8D%AE h_01HKA0R42Y987PJRM70M7DFJ98=%E6%B4%BB%E8%B7%83%E6%95%B0%E6%8D%AE h_01J5WGZ13W5W8NJ1CRZQPHY939=%E5%85%B3%E4%BA%8E%E7%81%AB%E8%BD%A6%E7%9A%84%E7%B1%BB%E6%AF%94 appsflyer-dashboards%E2%80%94ltv-or-activity=appsflyer%E9%9D%A2%E6%9D%BF%E5%92%8C%E6%8A%A5%E5%91%8Altv%E6%95%B0%E6%8D%AE-or-%E6%B4%BB%E8%B7%83%E6%95%B0%E6%8D%AE h_01HKA0R42Y558BQ45Y9MFZHZM0=appsflyer%E9%9D%A2%E6%9D%BF%E5%92%8C%E6%8A%A5%E5%91%8Altv%E6%95%B0%E6%8D%AE-or-%E6%B4%BB%E8%B7%83%E6%95%B0%E6%8D%AE compare-data-between-different-dashboards-and-reports=%E4%B8%8D%E5%90%8C%E9%9D%A2%E6%9D%BF%E5%92%8C%E6%8A%A5%E5%91%8A%E4%B9%8B%E9%97%B4%E7%9A%84%E6%95%B0%E6%8D%AE%E5%AF%B9%E6%AF%94 h_01J5WKA06A7XYFN07V60VQ4FY5=%E4%B8%8D%E5%90%8C%E9%9D%A2%E6%9D%BF%E5%92%8C%E6%8A%A5%E5%91%8A%E4%B9%8B%E9%97%B4%E7%9A%84%E6%95%B0%E6%8D%AE%E5%AF%B9%E6%AF%94 h_01J5WHVQSNEA2WK83RBRDM1GT3=compare-ltv-and-activity-data-in-appsflyer retrieving-ltv-data-out-of-raw-activity-data=%E4%BB%8E%E5%8E%9F%E5%A7%8B%E6%B4%BB%E8%B7%83%E6%95%B0%E6%8D%AE%E4%B8%AD%E6%A3%80%E7%B4%A2ltv%E6%95%B0%E6%8D%AE h_01HKA0R42Z3ZSMEM7T5F0V3VM7=%E4%BB%8E%E5%8E%9F%E5%A7%8B%E6%B4%BB%E8%B7%83%E6%95%B0%E6%8D%AE%E4%B8%AD%E6%A3%80%E7%B4%A2ltv%E6%95%B0%E6%8D%AE retrieving-activity-data-out-of-ltv-data=%E4%BB%8Eltv%E6%95%B0%E6%8D%AE%E4%B8%AD%E9%80%89%E5%8F%96%E6%B4%BB%E8%B7%83%E6%95%B0%E6%8D%AE h_01HKA0R42ZHFM4RHG78GE51XK3=%E4%BB%8Eltv%E6%95%B0%E6%8D%AE%E4%B8%AD%E9%80%89%E5%8F%96%E6%B4%BB%E8%B7%83%E6%95%B0%E6%8D%AE h_01J5WK0AEN2N6J4P06CC3DMWPJ=compare-different-appsflyer-aggregated-data-dashboards-and-reports h_01J5WHVQSNZW66CQ4VGQGAKZB1=compare-appsflyer-data-with-external-data" />
