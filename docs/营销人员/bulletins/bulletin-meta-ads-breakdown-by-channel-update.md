---
title: 公告：Meta 广告按渠道细分更新
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2026-08-04T08:33:09Z'
  edited_at: '2026-10-23T12:56:51Z'
  id: 49465306965393
  locale: zh-cn
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/zh-cn/articles/49465306965393
---
| 部分 | 详情 |
| --- | --- |
| **最新动态** | 自 2026 年 8 月 6 日起，Meta 现要求广告账户单独启用 `impression_device` （展示设备）细分功能。由于 Meta 的报告 API 无法在同一查询中同时返回按地理位置和渠道细分的成本数据，因此，未启用此选项的账户可能会出现不完整的数据：<ul><li>默认的 My Dashboards 视图中可能缺少渠道层级的成本数据</li><li>成本 ETL 中可能缺少 Meta 数据</li></ul>以上限制也会影响按渠道细分的素材效果数据。 |
| **生效日期** | 2026 年 8 月 6 日 |
| **重要需知** | Meta 会自动为 AppsFlyer 客户账户启用此选项。在 8 月 6 日之前，您无需采取任何操作。<ul><li>如果在 8 月 6 日之后，您发现按渠道细分的成本数据或广告素材效果数据依然缺失，说明 Meta 尚未为您的账户自动启用此功能。</li></ul> |
| **待办事项** | 请完成以下操作：<ol><li>在 8 月 6 日之后，请检查您按渠道细分的成本数据（My Dashboards）以及按渠道细分的素材表现数据。</li><li>如果您发现数据缺失，请直接联系 Meta 咨询如何启用此功能，或联系您的 AppsFlyer 代表寻求帮助。</li><li>为您的账户启用此功能后，系统会在随后不久自动回填历史数据，补齐缺失的数据。</li><li>您也可以直接在 Ads Manager 中检查该账户是否已启用 Impression Device（展示设备）。步骤请参见下方的 [在 Ads Manager 中检查展示设备](#在-ads-manager-中检查展示设备)。</li></ol> |

## 在 Ads Manager 中检查展示设备

如需检查广告账户是否已启用“展示设备”：

1. 前往 <Anchor target="_blank" href="https://adsmanager.facebook.com/">Ads Manager</Anchor>，然后选择 **设置**。

[![广告管理工具栏，显示「设置」按钮](https://files.readme.io/64c9ac8d571e88bfd098b542456886cc64d6320bf3856721335a077c4f19e5b5-49469436208529.png)](https://files.readme.io/64c9ac8d571e88bfd098b542456886cc64d6320bf3856721335a077c4f19e5b5-49469436208529.png)

2. 在“创建”视图面板中，选择 **Delivery（投放）**。
3. 在 Delivery（投放）下，找到 **Additional Breakdowns（其他细分维度）**。
4. 在 Additional Breakdowns （其他细分维度）下，检查 **展示设备** (`impression_device`) 旁边的加号是否已选中。如果已选中，说明该账户已启用此功能。

[![Ads Manager 中的其他细分维度面板，显示 Time of Day（时段）、Impression Device（展示设备）和 Frequency Value（频次值）旁的加号图标](https://files.readme.io/71eb7c75a3f49a82e98522fcf418acbc6ef378eeda5f093535a168aa8505ade1-49469462456081.png)](https://files.readme.io/71eb7c75a3f49a82e98522fcf418acbc6ef378eeda5f093535a168aa8505ade1-49469462456081.png)

<div data-zendesk-anchors="check-impression-device-in-ads-manager=%E5%9C%A8-ads-manager-%E4%B8%AD%E6%A3%80%E6%9F%A5%E5%B1%95%E7%A4%BA%E8%AE%BE%E5%A4%87 h_01KZ63J08GPADE2AH0KV9NNESC=%E5%9C%A8-ads-manager-%E4%B8%AD%E6%A3%80%E6%9F%A5%E5%B1%95%E7%A4%BA%E8%AE%BE%E5%A4%87" />
