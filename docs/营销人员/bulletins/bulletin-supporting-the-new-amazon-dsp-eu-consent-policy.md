---
title: 公告：支持 Amazon DSP 欧盟意见征求新政
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2026-04-12T09:11:36Z'
  edited_at: '2026-10-14T10:00:16Z'
  id: 45664244736529
  locale: zh-cn
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/zh-cn/articles/45664244736529
---
| 板块 | 详情 |
| --- | --- |
| **最新动态** | 为了配合 Amazon 对《数字市场法案》（DMA）的执行，Amazon Ads 正在更新其欧盟意见征求政策。AppsFlyer正在进行必要调整，以支持Google的政策规定，同时确保广告主能充分发掘Google Ads作为营销渠道的价值。 |
| **生效日期** | June 4, 2025 |
| **重要须知** | **相关对接及受众**所有通过`amazondsp_int` SRN对接与Amazon Ads对接并在欧盟（包括英国和瑞士）有广告活动的广告主。<br /><br />**待办事项**对于欧盟、英国或瑞士境内的用户，请确保向AppsFlyer发送有效的DMA授权信号，用于任何事件（应用打开或应用内事件）。<br /><br />授权信号可以是以下几种：<ol><li>**手动授权：** 唯一的必填字段是手动授权数组中的`ad_user_data_enabled`。Google DMA授权中的其他必填字段与Amazon无关。</li><li>**TCF授权：** 发送由CMP创建的完整TCF授权信息，并确保在授权供应商列表中包括Amazon Ads供应商ID（`793`）。</li><li>**GPP授权字符串：** Amazon支持GPP授权字符串，但AppsFlyer目前不支持。</li></ol>**<span id="h_01KP0FAZ70YDRQ71TDRYFEG120"></span>相关文档**<ul><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/send-consent-for-dma-compliance">如何通过AppsFlyer的SDK发送DMA同意</Anchor></li><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/s2s-events-api3-post">如何通过AppsFlyer的S2S发送DMA授权</Anchor> （搜索 `consent_data`）</li></ul> |