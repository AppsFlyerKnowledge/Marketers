---
title: 公告：扩展广告交互类型的数据可见性
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2024-10-29T15:52:59Z'
  edited_at: '2026-10-14T10:12:30Z'
  id: 29614354758545
  locale: zh-cn
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/zh-cn/articles/29614354758545
---
| **最新动态** | 我们将向所有账号开放扩展广告交互类型（ETT）数据。 |
| --- | --- |
| **具体影响** | <ul><li>对于所有支持ETT的广告平台（包括点击广告平台和SRN），AF都会上报参数。</li><li>深度浏览和深度点击的<Anchor target="_blank" href="/marketers/zh/docs/about-enriched-engagement-types#attribution-model-with-enriched-engagement-types-beta">归因优先级与点击相同</Anchor>，这是为了确保AF能以均等一致的逻辑对所有广告平台进行归因。</li><li>不会影响归因到的转化数量以及激活量。</li></ul><ul><li>您可以在面板中看到**广告交互类型**（Engagement type）这个新增维度。</li><li>如果广告主在“原始数据导出”页面的“报告字段”列表中选择了广告交互类型（Engagement type），则其原始数据报告中就会包含`engagement_type`字段。</li><li>深度浏览通过`attributed_touch_type=impression`参数上报（该参数也适用于Google Ads）</li></ul> |
| **生效日期** | 2020年11月1日 |
| **支持ETT的广告平台** | 目前仅限AppsFlyer认可的广告平台才能向AppsFlyer发送广告交互类型数据。 |
| **须知事项** | 您可以在以下文档中找到有关ETT的所有信息：<ul><li><Anchor target="_blank" href="/marketers/zh/docs/about-enriched-engagement-types">扩展广告交互类型</Anchor></li><li><Anchor target="_blank" href="/partners/zh/docs/enriched-engagement-types-guide-for-ad-networks">广告平台的扩展广告交互类型指南</Anchor></li></ul> |