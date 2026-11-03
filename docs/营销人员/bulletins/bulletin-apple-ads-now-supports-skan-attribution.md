---
title: 公告：Apple Ads现已支持SKAN归因
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2025-04-15T08:21:59Z'
  edited_at: '2026-10-14T10:02:02Z'
  id: 34395758837137
  locale: zh-cn
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/zh-cn/articles/34395758837137
---
| **最新动态** | AppsFlyer现已全面接收、处理并展示来自Apple Ads（AA）的SKAN回传数据，为营销人员提供与其他广告平台一致、符合隐私规范的归因衡量能力。 |
| --- | --- |
| **更新日期** | 10/04/2025 |
| **重要须知** | **<span id="where-to-find-aa-skan-data"></span>在哪里查看AA SKAN数据**<ul><li>**2025年4月10日 – 2025年5月26日:** 可在Data Locker中的<Anchor target="_blank" href="/marketers/zh/docs/skan-raw-data-reports#postback::315d5a62">SKAN原始回传副本报告</Anchor>中查看。</li><li>**2025年5月27日起:** 数据已全面接入所有SKAN面板、API、Data Locker导出及SSOT</li></ul>**归因变化**：在SKAN归因机制下，原本归因给其他渠道的部分激活现在可能会被归因至AA。<br /><br />**<span id="data-granularity"></span>数据颗粒度：**<ul><li>SKAN回传中仅包含标准字段，以下字段将**为空值（NULL）**：campaign、adset、ad、geo 和 creative enrichment。</li><li>**广告位映射（通过** **skad\_campaign\_id**）:</li><li>10 -> Search Results</li><li>20 -> Search Tab</li><li>30 -> Today Tab</li><li>40 -> Product Pages</li></ul>**<span id="h_01JXYJ6B8FP8N79CVF84VNYQCR"></span>注意**<br />Apple仅提供广告展示位置信息，并会通过SKAN回传中的Campaign ID字段来对应四种广告展示位置（搜索结果页、搜索标签页、Today页面和产品详情页）。因此，回传中不包含实际的Campaign ID以及Campaign层级的归因数据。<ul><li>media\_source为**Apple Search Ads**，skad\_ad\_network\_id为**com.apple.ads**。</li></ul>**<span id="skan-versions-supported"></span>支持的SKAN版本**<br /><br />AA当前仅支持SKAN 1.0至3.0中的点击归因（click-through），暂不支持浏览归因（view-through）和SKAN 4及以上版本。<br /><br />**对SSOT的影响**不会对现有去重逻辑产生影响。未被AppsFlyer传统归因方式识别的AA回传数据将被纳入，其余则在SSOT中进行去重处理。 |
| **待办事项** | 如需在AppsFlyer中启用AA SKAN数据，请确保你的App已设置将苹果的SKAN回传数据直接转发至AppsFlyer。<ul><li>若已完成该配置，则无需额外操作。</li></ul>注意：此功能仅支持iOS 15以上版本。Apple的数据显示，超过95%的用户设备已满足此条件。 |

<div data-zendesk-anchors="h_01JXYJ7NFNJP83Z2J43841ZENJ=where-to-find-aa-skan-data h_01JXYJ7S61RSK8SV11Y7QGQ9XE=data-granularity h_01JXYJ7Z0ERWPH70A291CEFMH6=skan-versions-supported" />
