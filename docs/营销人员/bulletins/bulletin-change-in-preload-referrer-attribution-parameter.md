---
title: 公告：公告：预装referrer归因参数变更
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-alina-koifman
    - Marketers
    - Mobile Attribution
  created_at: '2023-11-15T10:47:47Z'
  edited_at: '2026-10-14T10:06:07Z'
  id: 20161765461009
  locale: zh-cn
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/zh-cn/articles/20161765461009
---
| **最新动态** | 对于此次更新生效后记录到的新增激活以及归因到新增激活的应用内事件和应用打开（session），其预装referrer归因参数的上报方式会有所变化。<br /><br />预装referrer归因参数将发生以下变更：<ul><li>**attributed\_touch\_type**的值将变为**download**（而不是preload或click\_to\_download）<ul><li>**engagement\_type**的值将变为**preload**（适用于preload\_rfr匹配类型）或**click\_to\_download**（适用于af\_referrer匹配类型）</li></ul></li></ul>此次更新生效前归因到相关激活的应用内事件和应用打开（session）仍保持原有的上报方式：<ul><li>**attributed\_touch\_type**的值为**preload**或**click\_to\_download**<ul><li>**engagement\_type**的值为**空**</li></ul></li></ul> |
| --- | --- |
| **生效日期** | 2024年1月17日 |
| **影响范围** | <ul><li>使用<Anchor target="_blank" href="/marketers/zh/docs/set-up-appsflyer-preload-referrer-attribution">AppsFlyer预装referrer归因</Anchor>的广告主和代理会看到此变更</li><li>原始数据报告和面板中的相关内容会发生变化</li></ul> |