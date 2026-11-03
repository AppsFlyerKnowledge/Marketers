---
title: ROI360上手指南
metadata:
  keywords:
    - ROI
    - cost
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
  created_at: '2024-05-23T08:36:31Z'
  edited_at: '2026-10-14T10:14:59Z'
  id: 25301111725329
  locale: zh-cn
  section: Overview
  section_id: 15173289016593
  url: https://support.appsflyer.com/hc/zh-cn/articles/25301111725329
---
> **概要**：按照本文指南完成相关操作后，您就能开始使用ROI360的成本的收入数据。

![](https://files.readme.io/fa3644980702d735f81d7243f91cb0f0d454bd971e83685ab9759ff7bd925e93-26137252926097.png)

## ROI360简介

ROI360产品套件具有独一无二的成本和收入数据上报功能，以最高的时效性为您呈现最准确的数据。该功能结合了成本和收入两方面的关键信息，能帮助您全面掌握ROAS（广告支出回报率）和ROI（投资回报率），在此基础上进行相应的优化。

请按下文的上手指南完成相关操作，然后您就可以使用ROI360获取成本、广告收入以及应用内购和订阅收入的数据了。ROI360的启用流程需要营销人员、应用开发人员以及BI开发人员协作完成。

**提示**：如需尽快启用ROI360，请选择一个应用优先完成所有配置步骤。您可以将配置重点集中在成本、广告收入或应用内购买和订阅收入，但请先确保针对某一个应用完成启用流程。

<div id="cost-onboarding" />

<Accordion title="启用成本数据上报">

![](https://files.readme.io/0e7102766b3b7cdba3f301ca89c51edf8e4bd2ec88e09bc912ce3c1436c43fcb-26137252929681.png)

开通ROI360成本解决方案后，您就能获得详细的成本数据以及关键的ROI信息，而且这些数据会以每天数次的频率进行更新，帮助您有效管理投放成本并查看各个渠道（广告平台）、广告系列、国家/地区的预算配置。无论您使用的是广告平台、自有媒体或代理，都可使用这一解决方案。

开通成本数据上报后，您就可以：

* 自动整合所有渠道的成本数据，全面掌握最新的总体投放成本
* 根据最准确的激活后成本数据进行数据分析
* 如果您购买了RI360的高阶功能，还能以高达每天四次的频率将成本数据实时传输到您的BI系统
* 管理代理费用，精准监测总体投放成本，实现有效的财务管控并提升信息透明度

| 事项 | 作用 | 操作 | 人员 |
| --- | --- | --- | --- |
| 为所有合作渠道配置Cost API对接 | 从所有对接渠道获取粒度最细的成本数据 | 在AppsFlyer后台为您使用的每个广告平台分别<Anchor target="_blank" href="/marketers/zh/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">启用Cost API</Anchor>。**请注意**：在进行对接之前，请先准备好各平台的登录/证书信息。 | 营销人员 |
| 设置Cost ETL报告。（购买了ROI360高阶功能的广告主可用） | 查看分媒体渠道的投放成本数据。这些数据具有可用范围内最细的颗粒度，且每天最多更新4次。 | 为<Anchor target="_blank" href="/marketers/zh/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl-for-aws-s3">AWS S3</Anchor>或<Anchor target="_blank" href="/marketers/zh/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl-for-gcs">GCS</Anchor>设置Cost ETL 报告。 | 营销/BI开发 |
| 通过成本导入功能上传成本数据 | 适用于下列场景：<ul><li>广告平台不通过API或点击上报成本</li><li>使用OneLink链接进行推广（如网红营销等）</li><li>需要对成本数据进行更正</li></ul> | 使用<Anchor target="_blank" href="/marketers/zh/docs/import-cost-data">成本导入功能</Anchor>上传或通过电子邮件发送成本数据文件。 | 营销人员 |
| 配置代理费用 | 如果您使用代理，可以获得总体投放成本，其中包含针对相关流量按百分比费率计算的代理费 | 为您使用的各家代理创建<Anchor target="_blank" href="/marketers/zh/docs/incorporate-agency-fees-into-campaign-costs">代理计费规则</Anchor> 。 | 营销人员 |

</Accordion>

<div id="ad-revenue-onboarding" />

<Accordion title="启用广告收入上报">

![](https://files.readme.io/877e4abddd466bbe7dfa31f7fffb2f17fe3e6419f3bf6345e9d619253126b0e6-26137252932369.png)

启用ROI360广告收入解决方案后，您就可以获得详细实用的广告收入数据，这些数据以每天数次的频率更新。

广告收入的启用流程包括对接聚合平台或变现平台、部署广告收入的展示级别SDK API，以及与UA渠道共享数据。完成该流程后，您就可以：

* 在AppsFlyer的所有面板和报告中看到准确的最新广告收入数据
* 根据您需要的颗粒度和时效性，将数据实时入库到您的BI系统
* 让UA平台根据广告收入指标优化投放，提升投放效果

| 事项 | 作用 | 操作 | 人员 |
| --- | --- | --- | --- |
| 明确广告收入归因的对接类型 | 了解各类对接的优势，找出最贴合您业务需求的对接类型 | 了解各种<Anchor target="_blank" href="/marketers/zh/docs/roi360-guide-ad-revenue-attribution#integration-types-for-ad-revenue-attribution">广告收入对接类型</Anchor>并选择一种。 | 营销人员 |
| 对接到您使用的所有广告收入聚合和变现平台 | 从您使用的聚合或变现平台获取广告收入数据 | 在AppsFlyer后台<Anchor target="_blank" href="/marketers/zh/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">关联广告收入对接</Anchor>。 | 营销人员 |
| 部署展示层级的广告收入SDK API | <ul><li>适用于SDK层级的对接</li><li>广告收入数据的时效性接近实时</li></ul> | <ol><li>接入<Anchor target="_blank" href="/marketers/zh/docs/integrate-the-roi360-ad-revenue-sdk-api">ROI360 AppsFlyer ad revenue SDK API</Anchor>。</li><li>如需在SKAN面板中查看广告收入数据，请开启<Anchor target="_blank" href="/marketers/zh/docs/skan-conversion-studio#report-events-by-servertoserver-api">SKAdNetwork服务器到服务器支持</Anchor></li></ol> | 开发/营销人员 |
| 与UA渠道共享广告收入数据 | 允许UA广告平台使用广告收入数据优化UA投放 | <ol><li>与UA渠道共享收入数据的方式有两种，详情请见<Anchor target="_blank" href="/marketers/zh/docs/share-ad-revenue-data-with-partners#与ua渠道共享广告收入数据">此文档</Anchor>。</li><li>根据实际需求选择合适的共享方式<Anchor target="_blank" href="/marketers/zh/docs/share-ad-revenue-data-with-partners#配置流程">进行部署</Anchor> 。</li></ol> | 营销人员 |
| 设置Revenue ETL报告（购买了ROI360高阶功能的广告主可用） | 以一天数次的更新频率将可用范围内颗粒度最细的广告收入数据实时传输到您的BI系统 | 设置<Anchor target="_blank" href="/marketers/zh/docs/revenue-etl-reports">Ad revenue ETL报告</Anchor>。 | 营销/BI开发 |

</Accordion>

<div id="revenue-onboarding" />

<Accordion title="启用应用内购买和订阅收入上报">

![](https://files.readme.io/811c90ec42465994455fe42be8400b4ebb94ab6d1a5703bc9a77251aba95ed3b-26137252934545.png)

您可以使用ROI360的收入解决方案对您的收入来源进行前瞻性的管控。

收入数据上报的启用流程包括设置商店通知和接入购买SDK API（分安卓和iOS）。配置完成后，您就可以：

* 对App Store和Google Play的交易设置自动验证和衡量
* 享受流畅准确的收入数据上报，且无需介入开发人员——ROI360会代您处理所有应用内收入事件的记录
* 获取准确的收入衡量数据，有效管理具有战略性增势的产品

| 事项 | 作用 | 操作 | 人员 |
| --- | --- | --- | --- |
| 部署ROI360应用内购买和订购收入解决方案 | 对于通过App Store（iOS）或Google Play（安卓）完成的应用内购买、自动续订及相关事件所产生的收入进行自动验证并衡量 | 请按此文档中的说明完成以下步骤：<ol><li>设置与 Google Play 的对接。</li><li>设置与 iOS 应用商店的对接。</li><li>接入 AppsFlyer purchase SDK connector。</li><li>测试应用内购买（IAP）和订阅收入数据。</li><li>发布包含 SDK connector 的应用版本。</li></ol> | 开发/营销人员 |
| 设置Revenue ETL报告（购买了ROI360高阶功能的广告主可用） | 以一天数次的更新频率将可用范围内颗粒度最细的收入数据实时传输到您的BI系统 | 设置<Anchor target="_blank" href="/marketers/zh/docs/revenue-etl-reports">Revenue ETL报告</Anchor>。 | 营销/BI开发 |

</Accordion>

<div data-zendesk-anchors="overview=roi360%E7%AE%80%E4%BB%8B h_01HKHGX9JJQQCKF9SDZRSCM1XJ=roi360%E7%AE%80%E4%BB%8B h_01HYJ8PSPTFR6QH329TBR73AXM=cost-onboarding h_01HYJ8PSPTKBZ60TF7T0EMSCXW=ad-revenue-onboarding h_01HYJ8PSPTWK4SEGVJWG5J86E2=revenue-onboarding" />
