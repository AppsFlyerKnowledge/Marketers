---
title: 受众共享入门指南
metadata:
  keywords:
    - Premium
    - Marketers
    - Audience Segmentation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-neama-benhabib
    - Marketers
    - Audience Segmentation
  created_at: '2024-08-05T11:44:00Z'
  edited_at: '2026-10-14T10:11:06Z'
  id: 27276077637649
  locale: zh-cn
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/zh-cn/articles/27276077637649
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要**：本文介绍了如何使用AppsFlyer的受众共享（Audiences）功能创建人群包，并将其连接到渠道平台用于投放，从而充分提升拉新和再营销广告的投放效率。

<Image align="center" alt="53010_Audiences.jpg" src="https://files.readme.io/37aa78c4e885438f7912110a424a9ddbb9ddb7842fcb7239c7e2bc893eb36a50-30778512024081.jpg" />

<div id="about-audiences" />

## 受众共享简介

AppsFlyer的<Anchor target="_blank" href="/marketers/zh/docs/audiences-guide">受众共享产品（Audiences）</Anchor>能帮助您快速完成人群分组，并将其连接到您的自有媒体或付费渠道，实现个性化的广告投放，从而提升用户互动和营销效果。

人群包是根据您所设定的具体标准所细分出来的应用用户，包括现有用户和以往用户。您可以根据个人特征、行为、归因来源、收入生成情况、地理位置、设备类型等各种信息来配置人群包，形成高度定制化的营销策略。

您可以从零开始创建自定义人群包、从您自己的数据库中导入人群包、或从我们的推荐人群包中选择（可自行调整）。该功能不仅能帮助您节省时间，而且其中的人群包都是根据相关行业的最佳实践配置的。然后，您可以将这些人群包连接到您使用的媒体渠道，AppsFlyer的受众共享功能会将人群包中的用户标识符上传到这些渠道，用于渠道侧的人群包搭建。这样，您投放的广告就可以精准定向到您的目标受众。受众共享功能会每天自动更新数据，并以动态方式无缝共享给渠道。此外，相关广告开始投放后，您还可以直接在受众共享面板中直接监测其投放效果指标。

<div id="audiences-onboarding" />

## 初次配置受众共享

**初次使用受众共享时，请按以下方式操作：**

| 事项 | 作用 | 操作 | 人员 |
| --- | --- | --- | --- |
| 1. 购买受众共享产品 |  | 您可以联系负责贵司的AF销售人员，或发送邮件至[hello@appsflyer.com](mailto:hello@appsflyer.com)* | 市场人员 |
| 2. 设置您的帐户层级隐私政策 | 在账户级别设置渠道的用户标识符共享规则。 | 设置您的隐私<Anchor target="_blank" href="/marketers/zh/docs/audiences-user-identifier-policy">政策</Anchor>。 | 市场人员 |
| 3. 创建人群包 |  | 选择您想要创建的人群包类型：<ul><li><Anchor target="_blank" href="/marketers/zh/docs/audiences-guide#create-a-suggested-audience">推荐人群包</Anchor>——根据各行业最佳实践预定义的人群包，您可以自行调整其配置</li><li><Anchor target="_blank" href="/marketers/zh/docs/audiences-guide#create-a-custom-audience">自定义人群包</Anchor>——从零开始创建人群包</li><li><Anchor target="_blank" href="/marketers/zh/docs/audiences-import-audience-segments-from-internal-systems">导入人群包</Anchor>——从您的内部系统（如BI或CRM）导入人群包</li></ul> | 市场人员 |
| 4. 将人群包关联到您的合作渠道 | 将该人群包连接到您的合作渠道，用于在渠道侧创建人群包。人群包数据每天更新一次。 | <ol><li>添加渠道<Anchor target="_blank" href="/marketers/zh/docs/audiences-guide#create-a-new-connection">连接</Anchor>。</li><li>将<Anchor target="_blank" href="/marketers/zh/docs/audiences-guide#connect-an-audience-to-media-partners">人群包关联</Anchor>到您的合作渠道。</li></ol> | 市场人员 |
| **可选操作** |  | <ol><li>对该人群包进行拆分，将其中的用户分到不同渠道和对照组，然后启用<Anchor target="_blank" href="/marketers/zh/docs/run-an-incrementality-for-remarketing-experiment">增量</Anchor>实验（需购买增量分析产品）。</li><li>导入<Anchor target="_blank" href="/marketers/zh/docs/audiences-create-better-audiences-with-user-attribute-data">用户特征</Anchor>。将用户特征共享给AF后，您就可以创建高度定制化的人群包。</li></ol> | 市场人员 |
| 5. 针对该人群包创建适配的广告系列，并在渠道平台中进行操作，将其定向投放到该人群包中的用户。 |  | <ol><li>针对您的目标客群创建适配的广告系列。</li><li>在渠道平台中选择相关人群包。</li><li>将相关广告投放给您的目标客群。</li></ol> | 市场人员 |
| 6. 分析投放效果 |  | 您可以在AppsFlyer<Anchor target="_blank" href="/marketers/zh/docs/audiences-guide#campaign-metrics">受众共享</Anchor>以及其他面板中查看您的广告投放效果。 | 市场人员、数据分析师 |

* 购买受众共享产品后，AppsFlyer会拉取您过去90天的应用内事件数据。整个数据处理流程可能需要1到2周的时间。处理完毕后，我们会想您发出通知，然后您就可以开始创建人群包了。

<div data-zendesk-anchors="overview=%E5%8F%97%E4%BC%97%E5%85%B1%E4%BA%AB%E7%AE%80%E4%BB%8B h_01J2G7RMHSPPXCWJ60W9HZASXX=%E5%8F%97%E4%BC%97%E5%85%B1%E4%BA%AB%E7%AE%80%E4%BB%8B h_01HKHGX9JJQQCKF9SDZRSCM1XJ=%E5%8F%97%E4%BC%97%E5%85%B1%E4%BA%AB%E7%AE%80%E4%BB%8B xyz-onboarding=%E5%88%9D%E6%AC%A1%E9%85%8D%E7%BD%AE%E5%8F%97%E4%BC%97%E5%85%B1%E4%BA%AB h_01J2RJFH0B4R815CWDQNEB2C1P=%E5%88%9D%E6%AC%A1%E9%85%8D%E7%BD%AE%E5%8F%97%E4%BC%97%E5%85%B1%E4%BA%AB" />
