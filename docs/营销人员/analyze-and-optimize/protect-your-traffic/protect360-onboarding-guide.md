---
title: Protect360上手指南
metadata:
  keywords:
    - Marketers
    - Protect360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2025-04-21T09:58:52Z'
  edited_at: '2026-10-14T10:01:58Z'
  id: 34554022072209
  locale: zh-cn
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/zh-cn/articles/34554022072209
---
> **概要：** 按照本指南的分步流程，在6周内快速高效地启用Protect360，为您的营销投入提供最大程度的保护。

<div id="onboarding-timeline-and-what-to-expect" />

## **入驻时间表及预期内容**

本指南涵盖了为期6周的阶段性入驻流程：

* **设置阶段（第1-3周）**：完成Protect360的对接和验证。
* **优化阶段（第3-5周）**：根据初步数据进行优化。
* **核对阶段（第5–6周）**：与广告合作渠道核对作弊数据。
* **进阶防护（第6周起）[可选]**：启用高级作弊防护层。

<div id="about-protect360" />

## **关于Protect360**

Protect360是一款先进的广告作弊防护解决方案，具备对作弊活动的检测、预防与响应能力。它基于AI技术、支持实时检测，能够拦截作弊行为、减少广告预算浪费，并防范点击劫持、虚假激活、机器人作弊等威胁。通过验证规则和作弊防护操作台等功能，Protect360可提供高度可控与完全透明的作弊防护体验。

<div id="setup-weeks-1-3" />

<Accordion title="设置阶段（第1-3周）">

本阶段的重点是将应用内数据发送至AppsFlyer，完成基础的作弊防护设置，并将您的BI术语与AppsFlyer术语进行统一。

**应用内事件数据**

您可以通过以下两种方式将应用内事件数据发送至AppsFlyer：SDK或Server-to-Server（S2S）。根据所使用的方式，可能需要采取不同操作：

* **SDK**：无需操作。
* <strong>Server-to-Server（S2S）</strong>确保事件通过API3发送。<Anchor target="_blank" href="/marketers/zh/docs/bulletin-upgrading-the-appsflyer-s2s-api">点击此处了解具体操作方法。</Anchor>

<div id="note" />

> 📘 **注意事项**
>
> 如果不确定您应使用哪种方式，请与开发团队或营销运营团队确认。

<div id="fraud-protection-studio-settings" />

#### **作弊防护操作台设置**

作弊防护操作台可帮助您了解AppsFlyer各层级作弊防护的功能与影响，包括“作弊检测”和“作弊拦截”的区别。

理解这些差异及选项将有助于您做出更明智的防护决策：

* **已实施**（默认）：实时拦截作弊行为；若在激活后识别出作弊，则标记为“归因后假量”。若您的目标是实时防作弊，这是最理想的设置。
* **已标记**：检测到作弊行为但不阻止归因，仅进行标记，便于后续分析和评估。若您更偏好先进行灵活分析再决定是否拦截，可选择该设置。

<div id="note-1" />

> 📘 **注意事项**
>
> <Anchor target="_blank" href="/marketers/zh/docs/user-management">管理员账号</Anchor>可根据业务目标，随时在**已实施**和**已标记**模式之间进行切换。<Anchor target="_blank" href="/marketers/zh/docs/beta-fraud-protection-studio#key-concepts">点击此处了解详情</Anchor>。

<Image align="center" alt="" src="https://files.readme.io/70bf87550e949fed4898270f731424e948a24f7cf2cff39e81ba44473af94189-35506628777105.png" width="624px" />

提示：在熟悉Protect360的过程中，我们强烈建议您的团队前往作弊防护操作台中的“应用检测评估”（App detection evaluation）卡片，基于应用层级测试并理解各项设置。

<div id="data-connection-setup" />

#### **数据连接设置**

您可以通过三种方式导出Protect360数据：<Anchor target="_blank" href="/marketers/zh/docs/protect360-raw-data-reports#protect360原始数据报告简介">原始数据报告</Anchor>、<Anchor target="_blank" href="/marketers/zh/docs/protect360-raw-data-reports#pull-api">Pull API</Anchor>或<Anchor target="_blank" href="/marketers/zh/docs/protect360-raw-data-reports#data-locker">Data Locker</Anchor>。无论选择哪种方式，请务必正确配置数据连接，以确保作弊数据报告的准确性和分析的有效性。

<Image align="center" alt="" src="https://files.readme.io/d6a96db3fd8ffd3ed6f3f8abb680b4f3778a457142166d69e1ade7fe3263709e-35506660373393.png" width="624px" />

<div id="important" />

> 🚧 **重要提示！**
>
> 为充分发挥Protect360的价值，请在每月8日导出一次<Anchor target="_blank" href="/marketers/zh/docs/protect360-raw-data-reports#postattribution-reports">归因后报告</Anchor>，以便与广告合作渠道进行核对。

<div id="how-to-display-hijacked-installs-correctly-in-your-bi" />

#### **如何在BI系统中查看被劫持的激活数据**

如需在内部系统中实现更精细化的作弊数据管理，可在BI系统中通过原始数据报告、Pull API或Data Locker准确查看被劫持的激活数据。

<div id="raw-data-report" />

#### **原始数据报告**

如需在BI系统中正确显示被劫持激活数据：

1. 查找字段：**Rejected Reason Value**。
2. 该字段可能包含以下值：
   1. 空白、自然量（orgnaic）、贡献者1(contributor1)、贡献者2(contributor2)等。
3. 请向您的BI团队说明这些值的含义，以便统一术语的解释与使用：

* 空白 - 非劫持激活
* 自然量 - 改归因为自然流量
* Contributor1, contributor2, contributor3 等 - 正确归因到具体媒体渠道

<div id="note-2" />

> 📘 **注意事项**
>
> 若您希望进一步了解**已标记**数据，可查看以下4份原始数据报告：
>
> * 已标记的激活
> * 归因后标记的激活
> * 已标记的应用内事件
> * 归因后标记的应用内事件

<Image align="center" alt="" src="https://files.readme.io/70d33b5c4359f839da8d46c4b07baf277148fc4d5c6ebc7a3e8b2d600bd7c5fc-35506628785169.png" width="624px" />

#### **Pull API**

如需在BI系统中正确显示被劫持激活数据：

4. 查找字段：**Rejected Reason Value**。
5. 该字段可能包含以下值：
   1. 空白、自然量（orgnaic）、贡献者1(contributor1)、贡献者2(contributor2)等。
6. 请向您的BI团队说明这些值的含义，以便术语的统一解释与使用：

* 空白 - 非劫持激活
* 自然量 - 改归因为自然流量
* Contributor1, contributor2, contributor3 等 - 正确归因到具体媒体渠道

#### **Data Locker**

如需在BI系统中正确显示被劫持激活数据：

7. 查找字段：**validation\_reason\_value**。
8. 该字段可能包含以下值：
   1. 空白、自然量（orgnaic）、贡献者1(contributor1)、贡献者2(contributor2)等。
9. 请向您的BI团队说明这些值的含义，以便术语的统一解释与使用：

* 空白 - 非劫持激活
* 自然量 - 改归因为自然流量
* Contributor1, contributor2, contributor3 等 - 正确归因到具体媒体渠道

<div id="validation-rules" />

#### **验证规则**

通过验证规则，您可以基于营销策略设置作弊防护机制，根据不同参数和使用场景灵活设置将哪些激活判定为“有效”，哪些判定为“无效”。

请联系您的客户成功经理或客户经理，获取适用于您所在领域的最佳实践建议。

<div id="note-3" />

> 📘 **注意事项**
>
> 为使验证规则发挥最大效果，建议您检查当前的用户获取策略、营销策略或媒体投放策略，并判断哪些类型的激活或应用事件符合您的业务目标，以便制定拦截规则。例如：如果您未在某个国家/地区（GEO）进行投放，则可以设定规则自动拦截来自该区域的流量。您可创建多个规则，使防护逻辑与营销策略保持一致。

<div id="working-with-dashboards" />

#### **配合面板进行分析**

<Anchor target="_blank" href="/marketers/zh/docs/protect360-dashboard">Protect360面板</Anchor>可为您提供作弊数据的可视化概览，助您深入调查各类作弊行为，更清晰地理解检测机制及其对广告活动的影响。

<Image align="center" alt="" src="https://files.readme.io/4717e1f00d832a9808ac6469d89bf3a87f6701afb24a47f3b4393e4e393111ee-35506628785809.png" width="624px" />

</Accordion>

<div id="optimization-weeks-3-5" />

<Accordion title="优化阶段（第3-5周）">

<div id="campaign-optimization" />

#### **广告投放优化**

在此阶段，您可以开始优化广告活动，以充分发挥Protect360的防护功能。建议您完成以下操作：

* 查看[最佳实践](/docs/protect360-onboarding-guide#最佳实践)
* [检查作弊防护设置](/docs/protect360-onboarding-guide#检查作弊防护设置)
* [设置LVL](/docs/protect360-onboarding-guide#设置lvl)

<div id="best-practices" />

#### 最佳实践

* 结合实时数据与归因后数据，从用户质量（如留存率、应用内事件等）和作弊情况两个维度评估广告活动表现。
* 基于site\_id或subsite\_id进行广告活动优化。
* 分析不同合作渠道的作弊率与作弊类型。

<div id="review-your-fraud-protection-settings" />

#### 检查作弊防护设置

请检查您的[作弊防护操作台](/docs/protect360-onboarding-guide#作弊防护操作台设置)设置，确保其仍与您的业务目标保持一致。

<div id="note-4" />

> 📘 **注意事项**
>
> 已标记的激活（Tagged installs）是“有效激活”的子集。如需根据Protect360的检测结果进行实时拦截，请切换至“已拦截”模式。

#### 设置LVL

请为来自Google Play商店的流量设置LVL（Google License Verification Library）。LVL是Protect360的特有功能，可通过验证每次激活是否来自真实、有授权的Google Play用户，为您的应用提供关键的安全防护。

通过在激活层级进行授权验证，LVL有助于防止未经授权的使用行为，保护您的应用营收，并增强Google Play和AppsFlyer面板间的数据一致性。<Anchor target="_blank" href="/marketers/zh/docs/implement-google-license-verification-library-lvl">了解详情</Anchor>。

</Accordion>

<div id="reconciliation-weeks-5-6" />

<Accordion title="核对阶段（第5–6周）">

<div id="fraud-data-reconciliation" />

#### **欺诈数据核对**

在启用Protect360并积累数周的作弊检测数据后，您可以开始与广告合作渠道核对作弊数据。

这一步至关重要，可确保您与合作渠道在广告活动表现、作弊检测方式和数据准确性方面实现统一。

请下载您的<Anchor target="_blank" href="/marketers/zh/docs/protect360-anti-fraud-guide#postattribution-detection">归因后数据</Anchor>，并与广告合作渠道密切合作，核对并核实作弊指标。此过程有助于识别数据差异、预防争议问题，并提升合作透明度。点击<Anchor target="_blank" href="/marketers/zh/docs/protect360-anti-fraud-guide#fraud-reconciliation-with-ad-networks">此处了解如何与合作渠道核对作弊数据。</Anchor>

</Accordion>

<div id="advanced-protection-setup-week-6--optional" />

<Accordion title="进阶防护（第6周起）[可选]">

<div id="advanced-security-module" />

#### **高级安全模块**

高级安全模块是Protect360的特有功能，专为高流量应用设计。该模块为Android SDK增加了关键防护层，可实时验证平台请求，从而拦截虚假激活和流量。

通过在源头拦截未经授权的信号，该模块有助于减少应用商店数据差异、增强归因准确性，并防止复杂的作弊行为对您的数据造成威胁。

请联系您的CSM或发送邮件至`<hello@appsflyer.com>`。

</Accordion>

<div data-zendesk-anchors="what-to-expect=%E5%85%A5%E9%A9%BB%E6%97%B6%E9%97%B4%E8%A1%A8%E5%8F%8A%E9%A2%84%E6%9C%9F%E5%86%85%E5%AE%B9 h_01JSBWNSH94Q2FBXJ5JSB2JKQ6=%E5%85%A5%E9%A9%BB%E6%97%B6%E9%97%B4%E8%A1%A8%E5%8F%8A%E9%A2%84%E6%9C%9F%E5%86%85%E5%AE%B9 about-protect360=%E5%85%B3%E4%BA%8Eprotect360 h_01JSBWNSHDZ8J3B70KYEG2T03X=%E5%85%B3%E4%BA%8Eprotect360 setup-weeks-1%E2%80%933=setup-weeks-1-3 h_01JSBWJJMHSF6YQ5PDEWE0YTN5=setup-weeks-1-3 h_01JVVK5Z1HWN0TXKZVNNGK1CBV=%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9 fraud-protection-studio-settings=%E4%BD%9C%E5%BC%8A%E9%98%B2%E6%8A%A4%E6%93%8D%E4%BD%9C%E5%8F%B0%E8%AE%BE%E7%BD%AE h_01JSY4SNK5X23DBVD374FV12FG=%E4%BD%9C%E5%BC%8A%E9%98%B2%E6%8A%A4%E6%93%8D%E4%BD%9C%E5%8F%B0%E8%AE%BE%E7%BD%AE h_01JVVK5Z1HZAVV3ZEA1AM7KVAY=%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9-1 data-connection-setup=%E6%95%B0%E6%8D%AE%E8%BF%9E%E6%8E%A5%E8%AE%BE%E7%BD%AE h_01JSY4SNK57K77TBXZB92QPBKA=%E6%95%B0%E6%8D%AE%E8%BF%9E%E6%8E%A5%E8%AE%BE%E7%BD%AE h_01JVVK5Z1H0TZH02S76M7JRKWQ=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA how-to-display-hijacked-installs-correctly-in-your-bi=%E5%A6%82%E4%BD%95%E5%9C%A8bi%E7%B3%BB%E7%BB%9F%E4%B8%AD%E6%9F%A5%E7%9C%8B%E8%A2%AB%E5%8A%AB%E6%8C%81%E7%9A%84%E6%BF%80%E6%B4%BB%E6%95%B0%E6%8D%AE h_01JVVJBVB4FRATEHVZ2Q7EWC54=%E5%A6%82%E4%BD%95%E5%9C%A8bi%E7%B3%BB%E7%BB%9F%E4%B8%AD%E6%9F%A5%E7%9C%8B%E8%A2%AB%E5%8A%AB%E6%8C%81%E7%9A%84%E6%BF%80%E6%B4%BB%E6%95%B0%E6%8D%AE raw-data-report=%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%91%8A h_01JWDAV3K7JF8ATZP88D4NQRW4=%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%91%8A h_01JVVK5Z1HB5AVVF3XV5Q9KNGA=%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9-2 h_01JWDAV8GC5N1859AD1PMEQXH9=pull-api h_01JWDAVEVDAJD47WQYY0FNSPE9=data-locker validation-rules=%E9%AA%8C%E8%AF%81%E8%A7%84%E5%88%99 h_01JSY4SNK5HAG08PAJQEPB7MQ4=%E9%AA%8C%E8%AF%81%E8%A7%84%E5%88%99 h_01JVVK5Z1H05XX8BXECMXAJ4J7=%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9-3 working-with-dashboards=%E9%85%8D%E5%90%88%E9%9D%A2%E6%9D%BF%E8%BF%9B%E8%A1%8C%E5%88%86%E6%9E%90 h_01JSY4SNK50RHSQ95E1E2ZK068=%E9%85%8D%E5%90%88%E9%9D%A2%E6%9D%BF%E8%BF%9B%E8%A1%8C%E5%88%86%E6%9E%90 optimization-weeks-3%E2%80%935=optimization-weeks-3-5 h_01JSBWJJMH4YW52GSBE6639BP4=optimization-weeks-3-5 campaign-optimization=%E5%B9%BF%E5%91%8A%E6%8A%95%E6%94%BE%E4%BC%98%E5%8C%96 h_01JV255GGVBY8XGQS28F0QZRVH=%E5%B9%BF%E5%91%8A%E6%8A%95%E6%94%BE%E4%BC%98%E5%8C%96 best-practices=%E6%9C%80%E4%BD%B3%E5%AE%9E%E8%B7%B5 h_01JV6WFR7MN2X8KTN7RMTXQ5KX=%E6%9C%80%E4%BD%B3%E5%AE%9E%E8%B7%B5 review-your-fraud-protection-settings=%E6%A3%80%E6%9F%A5%E4%BD%9C%E5%BC%8A%E9%98%B2%E6%8A%A4%E8%AE%BE%E7%BD%AE h_01JV6WGDRP200GHN6MJNZJ5MQE=%E6%A3%80%E6%9F%A5%E4%BD%9C%E5%BC%8A%E9%98%B2%E6%8A%A4%E8%AE%BE%E7%BD%AE h_01JVVK5Z1HXPM2G6HAMTYV7MY5=%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9-4 set-up-lvl=%E8%AE%BE%E7%BD%AElvl h_01JV6WGGKTV1GNN9K49YXEYY65=%E8%AE%BE%E7%BD%AElvl reconciliation-weeks-5%E2%80%936=reconciliation-weeks-5-6 h_01JSBWJJMH1481TJW2EQMF118Q=reconciliation-weeks-5-6 fraud-data-reconciliation=%E6%AC%BA%E8%AF%88%E6%95%B0%E6%8D%AE%E6%A0%B8%E5%AF%B9 h_01JV25RP3VAJBCEWWK2TEZFKB2=%E6%AC%BA%E8%AF%88%E6%95%B0%E6%8D%AE%E6%A0%B8%E5%AF%B9 advanced-protection-setup-week-6-%5Boptional%5D=advanced-protection-setup-week-6--optional h_01JSBWJJMHZQNYE1N0W2BSJ37X=advanced-protection-setup-week-6--optional advanced-security-module=%E9%AB%98%E7%BA%A7%E5%AE%89%E5%85%A8%E6%A8%A1%E5%9D%97 h_01JV260Y9M3M6CC48854YHQ01S=%E9%AB%98%E7%BA%A7%E5%AE%89%E5%85%A8%E6%A8%A1%E5%9D%97" />
