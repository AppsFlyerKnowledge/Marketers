---
title: 【Beta】启用AppsFlyer网页归因
metadata:
  keywords:
    - Attribution
    - Agencies
    - Web Attribution
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Web Attribution
    - Agencies
  created_at: '2026-02-04T19:35:31Z'
  edited_at: '2026-10-14T10:00:50Z'
  id: 43529798016401
  locale: zh-cn
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/zh-cn/articles/43529798016401
---
> **概要：** 请按照本指南中的入驻指南设置AppsFlyer Web归因。设置完毕后，您就可以对网站访问量和网页事件进行衡量，并将其归因到相应的营销渠道，了解哪些因素促成了有意义的网站效果，并支持跨平台衡量。

<div id="set-up-network-integrations-postbacks-and-cost-measurement" />

<div id="create-a-web-app-in-appsflyer" />

<div id="about-web-performance-measurement" />

## AppsFlyer网页归因简介

<Embed title="【Beta】启用AppsFlyer网页归因" typeOfEmbed="youtube" url="https://www.youtube.com/embed/tJ_LoaQinzY" providerUrl="https://www.youtube.com" />

AppsFlyer 网页归因功能可帮助您将网站中的访问和网页事件与相应的营销渠道联系起来。也就是说，面板会显示哪些媒体渠道和营销活动将用户带到您的网站，并影响他们下一步的行动，以便您衡量绩效并优化投资回报率。

如需在AppsFlyer中衡量网站访问量和网页事件，请按照下方AppsFlyer网页归因设置清单中的启用步骤进行操作。

<div id="web-performance-measurement-setup-checklist" />

## AppsFlyer网页归因设置清单

下表列出了AppsFlyer后台收集网页端访问和网页端事件时需要完成的关键设置任务，以及需要完成的操作和顺序。

| 事项 | 操作 | 在哪里学习 | 人员 |
| --- | --- | --- | --- |
| 1.创建一个 Web 应用 | 前往应用设置页面<ul><li>复制 **Web SDK ID** 并将其分享给您的开发人员。</li><li>设置报告**时区**和**货币**。</li><li>选择**排除域**。</li></ul> | <ul><li><Anchor target="_blank" href="/marketers/zh/docs/adding-an-app-to-appsflyer#web">配置网页应用设置</Anchor></li></ul> | 营销人员 |
| 2. （可选）创建跨平台LTV产品线 | 如需启用跨平台归因和 LTV 用户链路衡量，请创建一个产品线实体，并将相关应用/网页属性关联到一起，或将您的网页应用添加到现有产品线中。 | <ul><li><Anchor target="_blank" href="/marketers/zh/docs/product-line-group-apps-for-cross-platform-attribution">创建产品线</Anchor></li></ul> | 营销人员 |
| 3.安装并配置Web SDK | 将AppsFlyer Web SDK接入您的网站。 | <ul><li><Anchor target="_blank" href="/marketers/zh/docs/integrate-appsflyer-web-sdk">将Web SDK集成到您的网站</Anchor></li></ul> | 开发者 |
| 4.配置网页应用归因设置。 | 在**应用设置**页面中，配置网页应用归因设置，如回溯窗口期和用户获取事件。   <br />**注意：** 自定义用户获取事件只有在Web SDK集成到您的网站后才能选择。 | <ul><li><Anchor target="_blank" href="/marketers/zh/docs/configure-web-performance-measurement-settings">配置网页应用归因设置</Anchor></li></ul> | 营销人员 |
| 5.为AppsFlyer网页归因创建URL | 使用正确的归因参数创建URL，以获得最准确、最细颗粒度的归因结果。 | <ul><li><Anchor target="_blank" href="/marketers/zh/docs/choose-attribution-parameters-for-landing-page-urls">为落地页URL选择归因参数</Anchor></li></ul> | 营销人员 |
| 6.设置与适用渠道的对接 | 激活渠道并设置回传数据。<br />适用渠道：<ul><li>Google Ads</li><li>Meta Ads</li><li>TikTok Ads</li><li>Snapchat Ads</li></ul> | 使用以下功能为网站应用创建网页广告系列：<ul><li><Anchor target="_blank" href="/marketers/zh/docs/google-ads-adwords-create-web-campaigns-for-website-apps">Google Ads</Anchor></li><li><Anchor target="_blank" href="/marketers/zh/docs/meta-ads-create-web-campaigns-for-website-apps">Meta Ads</Anchor></li><li><Anchor target="_blank" href="/marketers/zh/docs/tiktok-for-business-create-web-campaigns-for-website-apps">TikTok Ads</Anchor></li><li><Anchor target="_blank" href="/marketers/zh/docs/snapchat-create-web-campaigns-for-website-apps">Snapchat Ads</Anchor></li></ul> | 营销人员 |
| 7.从Data Locker导出AppsFlyer网页归因数据 | 为AppsFlyer网页归因原始数据报告配置**Data Locker**，以便BI和分析工具分析网页旅程。 | <ul><li><Anchor target="_blank" href="/marketers/zh/docs/export-web-performance-measurement-report-data-from-data-locker">从Data Locker导出AppsFlyer网页归因数据</Anchor></li></ul> | 市场人员/BI工程师 |
| 24/12/2025衡量网站广告成本<br /><br />**（仅适用于ROI360）** | 将您的网页应用连接到支持自归因平台（SRN）的**成本设置**中的成本对接：Google、Meta（Facebook）、Snapchat和Twitter。  <br />  <br />连接完成后，网页广告的成本、点击和展示会近乎实时地呈现在Cost ETL报告和My Dashboard中。  <br />  <br />如需使用**ROI360高级套餐**，请在Cost ETL配置页面中将相关网页端应用添加到适配应用列表中。  <br />  <br />**注意：** 归因链接必须在落地页URL中包含广告系列ID | 将您的网页应用连接到成本对接：<ul><li><Anchor target="_blank" href="/marketers/zh/docs/google-ads-adwords-create-web-campaigns-for-website-apps#通过网络成本测量网络归因数据">Google Ads</Anchor></li><li><Anchor target="_blank" href="/marketers/zh/docs/meta-ads-create-web-campaigns-for-website-apps#使用网络成本衡量网络归因数据">Meta Ads</Anchor></li><li><Anchor target="_blank" href="/marketers/zh/docs/snapchat-create-web-campaigns-for-website-apps#用网络成本衡量网络归属数据">Snapchat Ads</Anchor></li><li><Anchor target="_blank" href="/marketers/zh/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl">设置Cost ETL</Anchor></li></ul> | 市场人员/BI工程师 |

<div data-zendesk-anchors="about-appsflyer-web-attribution=appsflyer%E7%BD%91%E9%A1%B5%E5%BD%92%E5%9B%A0%E7%AE%80%E4%BB%8B h_01KGN43TYPKCQ7H3SRRHHPT387=appsflyer%E7%BD%91%E9%A1%B5%E5%BD%92%E5%9B%A0%E7%AE%80%E4%BB%8B appsflyer-web-attribution-setup-checklist=appsflyer%E7%BD%91%E9%A1%B5%E5%BD%92%E5%9B%A0%E8%AE%BE%E7%BD%AE%E6%B8%85%E5%8D%95 h_01KGN43TYP1EV5KFQ37FC4SM0C=appsflyer%E7%BD%91%E9%A1%B5%E5%BD%92%E5%9B%A0%E8%AE%BE%E7%BD%AE%E6%B8%85%E5%8D%95" />
