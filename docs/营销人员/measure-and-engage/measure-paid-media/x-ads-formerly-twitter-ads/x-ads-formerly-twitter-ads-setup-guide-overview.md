---
title: X 广告（前身为 Twitter 广告）设置指南—概述
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T09:31:36Z'
  edited_at: '2026-10-14T10:03:46Z'
  id: 4410464316049
  locale: zh-cn
  section: X Ads (formerly Twitter Ads)
  section_id: 6551370375569
  url: https://support.appsflyer.com/hc/zh-cn/articles/4410464316049
---
> **概要：** 了解将您的 X 广告账户与 AppsFlyer 集成的背景。

<Image alt="X Ads logo.png" src="https://files.readme.io/cecae90650321943ad1cb6d22b7f27d3d28b0484f1706cb1be1a19099dfbb20d-20375448207377.png" width="167px" />

## 在 X 广告上推广移动应用

X 广告移动应用推广是一种在 X 广告上推广应用的方法。该产品能让广告主使用优质的卡片式设计素材来推广他们的移动应用，从而提升新增激活、应用互动以及深度链接转化。用户可以直接从Twitter的时间线（Timeline）中下载并使用广告主推广的应用，操作十分便捷。

## X 广告用户隐私

Twitter用户可以决定将自己的哪些信息共享给广告主，具体如下：

* 如果用户拒绝与广告主共享其互动信息，则原始数据中会剔除由Twitter带来的激活和应用内事件，但这些激活和事件仍会归因给Twitter。
* AppsFlyer中的汇总归因数据不受Twitter政策的影响，因此会显示准确的归因数据。
* 这样一来，Twitter的汇总数据和原始数据之间就会产生差异。

自2021年7月31日起，Twitter不再向未加入Twitter Advanced Mobile Measurement （高级移动成效衡量，简称AMM）计划的广告主发送任何MACT（移动应用转化跟踪）数据。

广告主可以通过AMM计划获得更为全面的用户级数据，但需要先授权让Twitter进行审核，确保Twitter数据仅用于移动衡量。该计划符合数据保护法以及行业惯例。  
**加入 AMM 计划：** ，然后进入Mobile App, Conversion Tracking & Audience Manager（移动应用、转化跟踪以及受众管理版块）并选择**Advanced Mobile Measurement Program Agreement Form**（AMM计划协议表）。

请注意：加入AMM计划前产生的用户级数据无法导出。

如需进一步了解AMM计划的相关信息，请联系您的Twitter客户经理。

## Twitter Ads与AppsFlyer之间的SKAN互通性

Twitter Ads会通过一个专用的API发送SKAN回传数据。您可以在<Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">SKAN面板</Anchor>中查看来自Twitter Ads的SKAN数据。

Twitter Ads会在SKAN回传中添加以下字段：

* Campaign name
* 广告系列 ID
* 即广告组的名称
* Adset ID

<div data-zendesk-anchors="mobile-app-promotion-on-twitter=%E5%9C%A8-x-%E5%B9%BF%E5%91%8A%E4%B8%8A%E6%8E%A8%E5%B9%BF%E7%A7%BB%E5%8A%A8%E5%BA%94%E7%94%A8 h_01H9QR6TH7M0H5YMXRWVVAYRK9=%E5%9C%A8-x-%E5%B9%BF%E5%91%8A%E4%B8%8A%E6%8E%A8%E5%B9%BF%E7%A7%BB%E5%8A%A8%E5%BA%94%E7%94%A8 twitter-user-privacy=x-%E5%B9%BF%E5%91%8A%E7%94%A8%E6%88%B7%E9%9A%90%E7%A7%81 h_01H9QR6TH74R50K00H7FYN61KC=x-%E5%B9%BF%E5%91%8A%E7%94%A8%E6%88%B7%E9%9A%90%E7%A7%81 twitter-ads-and-appsflyer-skan-interoperation=twitter-ads%E4%B8%8Eappsflyer%E4%B9%8B%E9%97%B4%E7%9A%84skan%E4%BA%92%E9%80%9A%E6%80%A7 h_01H9QR6TH74PKBGM5RC4M118GE=twitter-ads%E4%B8%8Eappsflyer%E4%B9%8B%E9%97%B4%E7%9A%84skan%E4%BA%92%E9%80%9A%E6%80%A7" />
