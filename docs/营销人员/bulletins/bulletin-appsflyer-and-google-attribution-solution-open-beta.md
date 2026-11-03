---
title: 公告：AppsFlyer 和 Google 归因解决方案
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2025-08-06T13:24:32Z'
  edited_at: '2026-10-14T10:01:48Z'
  id: 37857301293457
  locale: zh-cn
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/zh-cn/articles/37857301293457
---
<Embed title="YouTube视频播放器" typeOfEmbed="youtube" url="https://www.youtube.com/embed/5u2sK5dfrR4?si=6TpIQXP1YU93MmI6" providerUrl="https://www.youtube.com" />

| 板块 | 详情 |
| --- | --- |
| **最新动态** | Google的集成转化测量（ICM）解决方案将适用于所有使用Google Ads来测量安装和再归因的客户。 |
| **生效日期** | <ul><li>**iOS：** 25/09/25</li><li>**安卓：** 25/09/25</li></ul> |
| **重要须知** | <ul><li>通过 ICM，AppsFlyer 可以使用隐私至上的方法将安装归因到 Google Ads，而无需设备 ID。</li><li>Google会向AppsFlyer发送非确定性安装声明。<br />如果通过AppsFlyer的数据验证，这些索赔将用于归因。有关更多信息，请参阅使用高级数据共享的<Anchor target="_blank" href="/marketers/zh/docs/google-ads-adwords-integration-setup-for-advertisers#google-ads-归因流程与高级数据共享">Google Ads归因流程</Anchor>。</li></ul> |
| **待办事项** | <ul><li>**SDK要求：**<ul><li>**iOS：** 需要AppsFlyer <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-release-notes">iOS SDK版本6.17.5</Anchor>或更高版本*，以及*Google <Anchor target="_blank" href="https://github.com/firebase/firebase-ios-sdk/releases">Firebase SDK版本11.14.0</Anchor>或更高版本，或独立的<Anchor target="_blank" href="https://support.google.com/google-ads/answer/16384720">Google ODM SDK</Anchor>。</li><li>**安卓：** 无需SDK更新。</li></ul></li><li>**高级数据共享开关：** iOS 和 Android `googleadwords_int`对接下的新设置：<ul><li>**启用**后：即使没有设备ID，AppsFlyer也会将所有安装事件发送到Google。</li><li>**禁用**时：只有具有可用设备ID或GCLID的安装事件才会被共享，从而限制了ICM的有效性。</li></ul></li><li><strong>重要提示！</strong>iOS 端 ICM 目前**不适用**于欧盟用户。</li></ul> |