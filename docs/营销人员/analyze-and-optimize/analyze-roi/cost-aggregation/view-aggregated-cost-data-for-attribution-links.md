---
title: 通过归因链接上报的广告成本
metadata:
  keywords:
    - eCPI
    - clicks
    - ROI
    - Advertisers
    - Agencies
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Marketers
    - Agencies
    - ROI360
  created_at: '2020-05-20T10:50:58Z'
  edited_at: '2026-10-14T10:04:58Z'
  id: 360008981698
  locale: zh-cn
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/zh-cn/articles/360008981698
---
> **概要：** 如果广告平台通过归因链接上报每个点击的广告成本，广告主可以在AppsFlyer中查看这些成本的汇总数据。

<div id="basic-cost-reporting" />

## 基础的成本上报方式

成本数据可通过以下方式发送到AppsFlyer：

* 广告平台：每当有用户点击某条广告时向AppsFlyer发送成本数据。广告主可以在AppsFlyer面板中查看投放成本，进而衡量其ROI并作出相应的预算分配决策。
  * 按CPI计价模式（每激活成本）通过<Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters">归因链接</Anchor>上报成本。
  * 向相关广告平台发送归因链接时，请确保该平台在其中<Anchor target="_blank" href="/partners/zh/docs/cost-reporting-on-the-attribution-link-for-ad-networks">添加成本上报参数</Anchor>。
* <Anchor target="_blank" href="/marketers/zh/docs/roi360-cost-aggregation-overview">高级汇总成本</Anchor>的传输方式包括API和成本导入（CSV文件上传）。

  * 除了CPI之外，成本汇总还支持渠道使用的其他成本模型，包括CPA、CPC和CPM。

<div id="viewing-ad-cost-by-click" />

<Accordion title="查看通过归因链接上报的广告成本">

AppsFlyer会对归因链接中上报的成本数据进行汇总，并通过面板、投放效果报告以及原始数据报告实时呈现这些数据（最多会在点击后有2个小时的延迟）。

*数据总览面板中的汇总效果报告*包含成本、点击、展示、ROI和平均eCPI数据。

<Image align="center" alt="CostReporting.jpg" src="https://files.readme.io/5d4dbe5dc74fd0915924518f76c63e379f0b072b5d5dbb7a7f92455b83e33a12-17313191631633.jpg" />

AppsFlyer还提供可<Anchor target="_blank" href="/marketers/zh/docs/raw-data-reporting-overview">下载</Anchor>的效果数据和原始数据报告。

</Accordion>

<div id="ad-networks-providing-cost-by-click-data" />

<Accordion title="通过归因链接提供成本数据的广告平台">

对于通过归因链接上报成本的广告平台，AppsFlyer中的数据分组可支持链接所包含的维度。

**下列广告平台通过归因链接上报成本：**

* AdAction
* Aura from Unity
* Blind Ferret
* Chartboost
* Cross Install
* Digital Turbine
* Fyber
* HangMyAds
* ironSource
* Criteo DSP (Manage)
* Mintegral
* TikTok for Business
* Vungle
* <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTMPZ9anfZoFBelK2bsBUoHG9n4YE3WxpXOayDF_wI8vyYClM6_6yXelFCZ3khwhd9Z_5Louxd4VVgx/pub?gid=0&single=true&output=csv">如需查看所有支持归因链接上报成本的广告平台，请点击下载此列表。</Anchor>

</Accordion>

<div id="limitations" />

<Accordion title="局限性">

通过归因链接上报成本的方式具有以下局限性：

* 仅可使用CPI计价模式（每激活成本）上报成本，不支持CPA、CPC和CPM等其他计价模式。
* <Anchor target="_blank" href="/marketers/zh/docs/self-reporting-networks-srns">自归因平台</Anchor>（SRN）不在归因链接中上报成本。
* 通过归因链接上报的成本数据不可更改。也就是说，即使在数据上报有误的情况下，只要这类成本数据被记录到AppsFlyer平台，就无法进行更改。

</Accordion>

<div data-zendesk-anchors="basic-cost-reporting=%E5%9F%BA%E7%A1%80%E7%9A%84%E6%88%90%E6%9C%AC%E4%B8%8A%E6%8A%A5%E6%96%B9%E5%BC%8F h_01HX954Y5X7ZP2VMB5W2XAMCR0=%E5%9F%BA%E7%A1%80%E7%9A%84%E6%88%90%E6%9C%AC%E4%B8%8A%E6%8A%A5%E6%96%B9%E5%BC%8F h_01HX954Y5XTRRQV4JHA5XX1AQ0=viewing-ad-cost-by-click h_01HX954Y5XV8M2R2VDAV34641R=ad-networks-providing-cost-by-click-data h_01HX954Y5X84BM7F8TGQRDPBTS=limitations" />
