---
title: 公告：旧版收据验证已弃用
metadata:
  keywords:
    - Marketers
    - ROI360
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2025-12-21T11:33:45Z'
  edited_at: '2026-10-14T10:01:25Z'
  id: 42133487071121
  locale: zh-cn
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/zh-cn/articles/42133487071121
---
| 板块 | 详情 |
| --- | --- |
| **最新动态** | <ul><li>旧版应用内购买收据验证方案已在AppsFlyer全部SDK中正式弃用。</li><li>自以下SDK版本起，旧版`validateAndLogInAppPurchase`方案将被标记为弃用：<ul><li>Android SDK：v6.17.5</li><li>iOS SDK（原生）：v6.17.8</li><li>插件（Flutter、Unity、React Native等）：v6.17.8</li></ul></li><li>旧版收据验证将在后续SDK版本中移除。</li><li>旧版收据验证产品将于**2026年7月1日**完全下线并停用。</li></ul> |
| **生效日期** | <ul><li>更新日期：24/12/2025</li><li>完全下线日期：2026年7月31日。</li></ul> |
| **重要须知** | <ul><li>在上述SDK版本中，被弃用的`validateAndLogInAppPurchase`仍然存在，但在后续更新中将被移除。</li><li>一旦移除，使用该方案的应用将无法再通过AppsFlyer验证应用内购买。</li><li>AppsFlyer目前提供两种替代方案：<ul><li>**收据验证**。免费解决方案，通过新的`validateAndLog`SDK方案与应用商店进行购买验证。</li><li>**ROI360商店收入**。高级收入衡量解决方案，支持退款追踪、完整订阅周期可视化以及净收入计算。</li></ul></li></ul> |
| **待办事项** | 为避免服务中断并持续通过AppsFlyer进行购买验证，请了解上述两种可用方案，并迁移至其中任一方案。<br /><br />如需更多信息，请参阅<Anchor target="_blank" href="/marketers/zh/docs/purchase-and-subscription-validation-overview">购买和订阅验证 - 概述</Anchor> |