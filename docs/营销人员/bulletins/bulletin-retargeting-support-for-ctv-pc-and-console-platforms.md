---
title: 公告：对 CTV、PC 和主机平台的重定向支持
metadata:
  keywords:
    - Marketers
    - CTV Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - CTV Attribution
  created_at: '2026-07-07T14:08:17Z'
  edited_at: '2026-10-14T10:00:19Z'
  id: 48515925079313
  locale: zh-cn
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/zh-cn/articles/48515925079313
---
| 功能介绍 | AppsFlyer 现在支持扩展（非移动）平台的重定向监测、再互动和再归因：CTV、PC 和游戏机。以前，这些平台仅支持 UA 归因。<br /><br />扩展平台的重定向包括两种转化类型：<ul><li>**再互动**积分活动将现有的、已经安装的用户带回应用程序。</li><li>**再归因**（重定向重装）积分活动可促使流失的用户重新安装并重新打开应用程序。有关更多详情，请参阅<Anchor target="_blank" href="/marketers/zh/docs/measure-reinstalls#reattribution">衡量再归因</Anchor>。</li></ul>这填补了开展生命周期营销的广告商的关键差距，在生命周期营销中，需要进行再互动和再归因才能正确地为可重新激活用户、增加重复消费和减少流失的广告活动提供信贷。它还提高了队列和生命周期的准确性。以前，如果没有重定向支持，后来的应用活动会以最初的安装日期为基准，这会扭曲群组、投资回报率和 LTV 分析。有关 AppsFlyer 一般如何衡量扩展平台的背景信息，请参阅 <Anchor target="_blank" href="/marketers/zh/docs/ctv-pc-and-console-platform-attribution-concepts">CTV、PC 和主机平台</Anchor>归因概念。 |
| --- | --- |
| 生效日期 | 2018 年 8 月 |
| 你应该做什么 | 有三个配置层：应用程序、媒体来源或集成以及归因链接。<ol><li>在<Anchor target="_blank" href="/marketers/zh/docs/app-settings#归因设置">应用程序的设置</Anchor>中，开启**再互动归因**开关。这是应用程序的主开关。如果关闭，则无法在该应用程序的任何媒体来源上启用再互动。</li><li><strong>在活跃集成页面的集成选项卡中，针对您想要进行再营销的每个合作伙伴或媒体来源，开启重新安装归因以启用再归因积分，开启再互动归因以启用再互动积分。</strong>如果你还想**获得浏览积分，也可以开启再互动浏览量归因**，否则只在点击时将其关闭。</li><li>对于非 SRN 网络，`af_campaign_type=retargeting`请添加归因链接。要自动添加此参数，请在<strong>活跃集成页面的归因链接选项卡中开启启用重定向设置。</strong>有关链接创建流程，请参阅<Anchor target="_blank" href="/marketers/zh/docs/retargeting-attribution-guide">重定向归因指南</Anchor><Anchor target="_blank" href="/marketers/zh/docs/ctv-pc-and-console-platform-direct-attribution-links">以及 CTV、PC 和主机平台直接归因链接。</Anchor>在广告活动中使用此链接。</li></ol>**<span id="h_01KX0FSH3GN11MG98MZQAVJ5NC"></span>注意**<br />Roku是目前唯一可用于这些平台的自我报告网络（SRN），仅支持再互动。它不支持再归因，也没有归因链接可供配置。对于 Roku 而言，只要开启开关，任何索赔都有资格进行重定向。 |
| 须知事项 | 在扩展平台上衡量重定向时，请记住以下几点：<ul><li>适配平台扩展平台的重定向适用于任何非安卓、iOS、Windows Phone或网站的平台。实际上，这意味着 CTV、PC 和主机应用程序。</li><li>**范围**此功能仅涵盖非移动平台（CTV、PC、控制台）。不支持移动端的跨平台重定向。例如，仍然不支持推动移动应用程序安装的 CTV 广告。但是，支持导致 PC 应用程序安装的网络广告。</li><li>**SRN 限制：** Roku是当今可用于这些平台的唯一SRN，它仅支持再互动，不支持重新安装或再归因。这可能不适用于将来添加的其他 SRN。</li><li>**可选窗口：** 再互动窗口（默认 30 天）决定了应用内事件主要归因于再互动转化的时间段。不活跃期限（默认为 7 天）决定了用户必须处于非活动状态多长时间才有资格获得重定向。这些窗口的工作方式与在移动设备上的工作方式相同。请参阅<Anchor target="_blank" href="/marketers/zh/docs/retargeting-attribution-guide#归因窗口期">重定向归因指南</Anchor>和<Anchor target="_blank" href="/marketers/zh/docs/set-retargeting-inactivity-window">设置重定向不活跃窗口</Anchor>。</li><li>**结果显示在哪里：** 仅限 “我的控制面板” 和 “数据柜” 高级报告。经典的 Data Locker 报告中没有新的重定向原始数据报告。有关平台特定的仪表板行为，请参阅控制面板概述——用户获取和重定向 LTV。</li></ul> |