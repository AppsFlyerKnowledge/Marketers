---
title: ROI360—成本与收入数据
metadata:
  keywords:
    - cost
    - Advertisers
    - Premium
    - Marketers
    - revenue
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2022-11-10T13:52:03Z'
  edited_at: '2026-10-14T10:15:25Z'
  id: 10515748254609
  locale: zh-cn
  section: Overview
  section_id: 15173289016593
  url: https://support.appsflyer.com/hc/zh-cn/articles/10515748254609
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要**:本文介绍了成本和收入数据的获取方式，帮助您了解总体的ROI和ROAS。

![M_emptyState.png](https://files.readme.io/5eec5be77bf0b72afdd95b1957642cc67ba509000bc756ac68d87da5e96ed08e-11832563913489.png)

## 速览

ROI360产品套件具有独一无二的成本和收入数据上报功能，为您呈现最准确、最新鲜的数据。

该功能结合了成本和收入两方面的关键信息，能帮助您全面掌握ROAS（广告支出回报率）和ROI（投资回报率）。

### 成本数据

ROI360成本功能的前身是Xpend，用于成本数据的汇总和上报。下表列出了所有用于成本数据的工具和功能。您可以点击各个工具的名称，以进一步了解其对应的功能。

<table><thead><tr><th>工具</th><th>说明</th></tr></thead><tbody><tr><td><a href="./roi360-cost-aggregation-overview" target="_blank">归因成本</a></td><td><p><span>关联到归因、点击和展示的成本数据。该工具提供可用范围内粒度最细的数据。</span></p><p><span>客户可以使用80多个API对接，快速连接到全球或本地的广告平台。</span></p></td></tr><tr><td><a href="./import-cost-data" target="_blank">文件导入</a></td><td><p><span>使用成本导入功能记录不通过API传输的成本数据。</span></p></td></tr><tr><td><a href="./incorporate-agency-fees-into-campaign-costs" target="_blank">代理费</a></td><td><p><span>用于计算成本中的代理费用。</span></p></td></tr><tr><td><a href="./set-up-and-use-roi360-cost-etl-reports" target="_blank">Cost ETL\*</a></td><td><span>用于传输投放成本数据，每天更新4次，写入您的AWS S3或GCS数据存储桶，以入库到BI。</span></td></tr><tr><td colspan="2"><span>\* 购买ROI360高级套餐后可用</span></td></tr></tbody></table>

**请注意**：但该方法仅适用于CPI模式，CPA、CPC及CPM等其他模式均不适用。

### 收入数据

ROI360收入专用工具可汇总并上报收入数据，包括应用内购买、订阅和广告收入，并将税费和商店抽成也纳入收入指标的计算。 下表列出了该产品的全线套件，您可以点击各个工具的名称，以进一步了解其对应的功能。

<table><thead><tr><th>工具</th><th>说明</th></tr></thead><tbody><tr><td>应用内购买</td><td><p><span>自动上报已验证的应用内购买，包括后续的交易数据（如退款或取消订单等）。</span></p></td></tr><tr><td>订阅收入</td><td><p><span>自动上报订阅，包括订阅的更改、取消以及全家共享型订阅。</span></p></td></tr><tr><td><a href="./roi360-guide-ad-revenue-attribution" target="_blank">广告收入</a></td><td><p>提供20多个广告收入平台的API或SDK对接，可实现优异的数据准确性和时效性。</p></td></tr><tr><td> <a href="./revenue-etl-reports" target="_blank">Revenue ETL</a>\*</td><td><span>可将收入数据传输到您的AWS S3或GCS数据存储桶，以入库到BI。</span></td></tr><tr><td colspan="2"><span>\* 购买ROI360高级套餐后可用</span></td></tr></tbody></table>

**请注意**：ROI360中不包括部分基础收入衡量工具。这些工具与ROI360的不同之处在于它们需要广告主侧的开发人员完成大量的配置工作。

* <Anchor target="_blank" href="/marketers/zh/docs/legacy-receipt-validation-for-in-app-purchases">应用内购买收据验证</Anchor>
* 订阅收入衡量
* <Anchor target="_blank" href="/marketers/zh/docs/roi360-revenue-attribution-overview">通过自定义应用内事件记录收入。</Anchor>

<div data-zendesk-anchors="overview=%E9%80%9F%E8%A7%88 h_01HKHGX9JJQQCKF9SDZRSCM1XJ=%E9%80%9F%E8%A7%88 cost-tools=%E6%88%90%E6%9C%AC%E6%95%B0%E6%8D%AE h_01HKHGX9JJRWDP9PMYP9CFA7MQ=%E6%88%90%E6%9C%AC%E6%95%B0%E6%8D%AE revenue-tools=%E6%94%B6%E5%85%A5%E6%95%B0%E6%8D%AE h_01HKHGX9JJFQ9ZM6J3B2D5G6C5=%E6%94%B6%E5%85%A5%E6%95%B0%E6%8D%AE" />
