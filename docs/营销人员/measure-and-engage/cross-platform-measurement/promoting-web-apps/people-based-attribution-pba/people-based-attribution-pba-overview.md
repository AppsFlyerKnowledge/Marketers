---
title: 基于用户的归因（PBA）简介
metadata:
  keywords:
    - People Based Analysis
    - People Based Attribution
    - People Based Attribution SDK
    - Developers
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2019-08-19T11:53:56Z'
  edited_at: '2026-10-14T10:15:32Z'
  id: 360002274017
  locale: zh-cn
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/zh-cn/articles/360002274017
---
> **概要：概要：基于用户的归因（即PBA）能够为您呈现跨流量入口、跨平台、跨设备的完整用户链路。**

<Image align="center" alt="PBANoSilos_us-en.gif" src="https://files.readme.io/1ac3614eb1b9d4c01bffbe904f1a060d1facd681ff32c274b12f0a15612a2e4a-360009359798.gif" />

<div id="pba-principles" />

## PBA基本原理

* 您可以在PBA面板和原始数据报告中查看PBA数据，并将该数据用于营销分析和投放优化。
* 网页端的访问数据和用户事件数据是通过<Anchor target="_blank" href="/marketers/zh/docs/pba-web-sdk-integration-guide">SDK和/或API</Anchor>得到的。
* 每次产生网页端访问时，AF会判定带来该次访问的媒体渠道，并将之后所有的事件（转化）<Anchor target="_blank" href="/marketers/zh/docs/pba-media-source-attribution-rules">归因</Anchor>到这个渠道。

<div id="pba-analytics-dashboards-and-raw-data" />

### PBA分析面板和原始数据

* PBA数据是通过面板和报告呈现的，其中包括以下信息：
  * 网页广告归因
  * 网页助攻激活
  * 原始数据报告
* 您可以使用移动平台、流量入口、媒体类型等维度对面板中的数据进行<Anchor target="_blank" href="/marketers/zh/docs/using-pba-dashboards">筛选和分组</Anchor>，便于进一步深入剖析。

<div id="website-attribution" />

### <Anchor target="_blank" href="/marketers/zh/docs/pba-website-attribution-dashboard">网页广告归因</Anchor>

<Image align="center" alt="WebsiteAttributionTable_us-en.jpg" src="https://files.readme.io/46f03ee216dc23f3f184663aeef7d6b64ae6fb9a64e7a161ff0482e4d2eab204-360013057757.jpg" />

用于分析哪些网页流量来源和营销投放带来了网页端的访问和转化。可深入到广告层级，分析不同广告的效果差异。PBA支持广告链接中所有的AppsFlyer查询参数，无需让用户跳转到AppsFlyer服务器。

<div id="web-assisted-installs" />

### <Anchor target="_blank" href="/marketers/zh/docs/pba-web-assisted-installs">网页助攻激活</Anchor>

<Image align="center" alt="AppsFlyer-Web-to-App_us.en.gif" src="https://files.readme.io/4a278b57379c999d80fd7f1dfea750049f56c03ed32051f9af92577b2a51742a-360009705058.gif" />

您可以使用网页助攻激活数据考察您的网页端营销投放对移动端应用激活的作用和效果。

* 洞悉各种媒体类型（付费、自有、口碑）、流量入口（直接、社媒、自然搜索）和媒体渠道之间的相互作用关系，了解这些因素对总体拉新效果的推动作用。
* 将自然激活归因到您的网页端营销投放。
* 考察网页端营销投放和非自然激活之间的关系。

<div id="raw-data" />

### <Anchor target="_blank" href="/marketers/zh/docs/pba-raw-data-reports">原始数据</Anchor>

您可以通过Data Locker拉取原始数据报告您可以使用原始数据获得深度洞察信息，其中包括获得归因/为网站带来用户的媒体渠道。

* 网页访问：即网页端的访问量
* 网页事件: 即用户在网页上完成的操作，如订阅或者购买
* 您还可以使用BI工具分析数据，进一步攫取深度洞察。

<div id="see-also" />

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/onboarding-guide-to-people-based-attribution">PBA入门指南</Anchor>

<div data-zendesk-anchors="pba-principles=pba%E5%9F%BA%E6%9C%AC%E5%8E%9F%E7%90%86 01ECF26CMJ8TB4ADT6VN277EMQ=pba%E5%9F%BA%E6%9C%AC%E5%8E%9F%E7%90%86 pba-analytics-dashboards-and-raw-data=pba%E5%88%86%E6%9E%90%E9%9D%A2%E6%9D%BF%E5%92%8C%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE 01ECF26CMJDA1HBC22DGRWY2EA=pba%E5%88%86%E6%9E%90%E9%9D%A2%E6%9D%BF%E5%92%8C%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE website-attribution=%E7%BD%91%E9%A1%B5%E5%B9%BF%E5%91%8A%E5%BD%92%E5%9B%A0 01ECF26CMK0T5C9JKQ0SYMXQVM=%E7%BD%91%E9%A1%B5%E5%B9%BF%E5%91%8A%E5%BD%92%E5%9B%A0 webassisted-installs=%E7%BD%91%E9%A1%B5%E5%8A%A9%E6%94%BB%E6%BF%80%E6%B4%BB 01ECF26CMKDS16XWRBQ1SDAX2Q=%E7%BD%91%E9%A1%B5%E5%8A%A9%E6%94%BB%E6%BF%80%E6%B4%BB raw-data=%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE 01ECF26CMM4KHX9W94DND4BY8C=%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE h_01HE0Y2KTXS06WHN57MQ91AD09=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />
