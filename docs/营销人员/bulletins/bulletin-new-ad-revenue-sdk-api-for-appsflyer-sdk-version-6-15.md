---
title: 公告：适用于AppsFlyer SDK 6.15+版本的新广告收入SDK API
metadata:
  keywords:
    - Premium Feature
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
  created_at: '2024-07-24T08:59:01Z'
  edited_at: '2026-10-14T10:10:55Z'
  id: 26956998859153
  locale: zh-cn
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/zh-cn/articles/26956998859153
---
| **最新动态** | 现在可以通过AdRevenue SDK API获取展示层级广告收入，而不再需要通过广告收入SDK连接器。 |
| --- | --- |
| **开始** | AppsFlyer SDK版本6.15 |
| **重要须知** | <ul><li>到目前为止，展示层级的广告收入一直通过AppsFlyer广告收入SDK**连接器**获取。自生效日期起，对接将通过AppsFlyer**SDK**本身进行（而非连接器），并使用广告收入SDK API。</li><li>广告收入SDK连接器将继续与以下设备配合使用：<ul><li>适用于AppsFlyer Android SDK 6.14.2及更低版本。</li><li>适用于AppsFlyer iOS SDK 6.14.6及更低版本。</li></ul></li></ul> |
| **待办事项** | <ul><li>如果要升级到AppsFlyer SDK 6.15+版本，并且当前已实施广告收入SDK连接器，则需要移除广告收入SDK连接器并对接广告收入SDK API。</li><li>需要开发人员。请参阅开发者<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad-revenue">广告收入SDK API使用指南</Anchor>。</li><li>了解更多关于<Anchor target="_blank" href="/marketers/zh/docs/integrate-the-roi360-ad-revenue-sdk-api">展示层级广告收入SDK API对接的信息</Anchor>。</li></ul> |