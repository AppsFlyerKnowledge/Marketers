---
title: 将三星与AppsFlyer的对接
metadata:
  keywords:
    - Advertisers
    - Developers
    - CTV
    - Marketers
    - CTV Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - CTV Attribution
  created_at: '2022-05-03T09:19:48Z'
  edited_at: '2026-10-14T10:04:47Z'
  id: 5860544738065
  locale: zh-cn
  section: Promoting CTV apps
  section_id: 15328952633489
  url: https://support.appsflyer.com/hc/zh-cn/articles/5860544738065
---
> **概要： 本文介绍了三星Connected TV (CTV)与AppsFlyer的对接方式。对接完成后，您就可以针对三星Connected TV (CTV)上的广告收集归因和事件数据。**

<div id="about-samsung-ctv-attribution" />

## 关于三星CTV归因

三星的流媒体操作系统Tizen OS应用于所有三星电视。

三星平台上的CTV流媒体应用可通过API接入 AppsFlyer，从而获得归因数据和投放效果指标，了解应用打开和应用内事件的流量来源（自然量合肥自然凉）和带量广告。这些关键信息能够帮助营销人员评估并优化其市场推广工作。

三星API对接适用于：

* 三星智能电视。
* CTV-to-CTV的归因和事件记录。（即在用户的三星设备上进行归因和记录）。

<div id="samsung-attribution-flow" />

### 三星归因流程

<Image align="center" alt="CTV_attribution_flow_-_Samsung__1_.png" src="https://files.readme.io/a1031878e8aced81da5762d06ae0163770cd73b9a7c91224ea7665aa142d2ce8-7215151128209.png" />

<div id="h_01M349521V96NRS5CJKXZKMA6P" />

<div id="integration-procedures" />

## 接入流程

下表列出了三星CTV应用对接到AppsFlyer时需要完成的工作。

| 事项 | 可用操作 | 人员 |
| --- | --- | --- |
| 设置应用 | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">创建一个AppsFlyer帐户</Anchor></li><li><Anchor target="_blank" href="/marketers/zh/docs/user-management">在账户下添加用户，并为其开放必要权限</Anchor></li><li><Anchor target="_blank" href="/marketers/zh/docs/adding-an-app-to-appsflyer">在AppsFlyer中添加您的三星CTV应用</Anchor></li></ul> | 营销人员 |
| 为您的应用配置API对接（通过S2S或SDK） | 对接分为两种不同的方式，即S2S和SDK。<br /><br />如果您使用S2S对接，请在您的应用中<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/pc-console-ctv-api-overview">接入AppsFlyer API</Anchor>，使其向AppsFlyer上报下列事件：<ul><li>首次打开</li><li>应用内事件</li><li>应用打开（Sessions）</li></ul>**请注意**：<ul><li>激活必须在应用内事件和应用打开（session）之前上报。</li><li>通过该API发送事件。请向开发人员说明您需要发送的事件。 对于要发送到AppsFlyer的事件，请务必在配置API时完成这些事件的设置和映射。</li></ul>如需上报自有媒体中的广告互动，请对接<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">impression engagement API</Anchor>。<br /><br />有关 SDK 方法，请参阅开发者中心的<Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-html5-ctv-sdk">三星文档</Anchor>。 | 应用开发人员 |
| 渠道对接 | 在AppsFlyer中添加三星作为广告平台（对接合作伙伴）。<ol><li><Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#a-activate-partner">启用渠道</Anchor></li><li>【可选】启用<Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#e-install-attribution">**浏览型归因**</Anchor>。</li></ol> | 营销人员 |
| 链接设置 | <Anchor target="_blank" href="/marketers/zh/docs/ctv-pc-and-console-platform-direct-attribution-links">了解直接归因链接的创建方式</Anchor> | 营销人员 |
| 报告设置/查看数据 | <Anchor target="_blank" href="/marketers/zh/docs/ctv-pc-and-console-platform-attribution-concepts#数据可用性">了解面板与报告中的数据可用性</Anchor> | 营销人员/数据工程师 |

<div id="traits-and-limitations" />

<Accordion title="特点与局限性">

| 特点 | 说明 |
| --- | --- |
| 再营销 | 目前尚不支持 |
| 成本数据 | 必须使用<Anchor target="_blank" href="/marketers/zh/docs/import-cost-data">成本导入</Anchor>功能，通过邮件上传数据文件，以实现成本数据的发送。 |
| 支持的区域 | 除预装广告系列可在全球范围内投放外，CTV广告系列仅限在美国投放。 |

</Accordion>

> 📄 **相关文档**
>
> <Anchor target="_blank" href="/marketers/zh/docs/ctv-pc-and-console-platform-attribution-concepts">CTV、PC和主机平台简介</Anchor>

<div data-zendesk-anchors="about-samsung-ctv-attribution=%E5%85%B3%E4%BA%8E%E4%B8%89%E6%98%9Fctv%E5%BD%92%E5%9B%A0 01H7Z17A1QPJQH9R5MRBVTMG37=%E5%85%B3%E4%BA%8E%E4%B8%89%E6%98%9Fctv%E5%BD%92%E5%9B%A0 samsung-attribution-flow=%E4%B8%89%E6%98%9F%E5%BD%92%E5%9B%A0%E6%B5%81%E7%A8%8B 01H7Z17A1Q03CEJT848FRFHDPQ=%E4%B8%89%E6%98%9F%E5%BD%92%E5%9B%A0%E6%B5%81%E7%A8%8B integration-procedures=%E6%8E%A5%E5%85%A5%E6%B5%81%E7%A8%8B 01H7Z17A1QQN4FYJXZFS5FP2NY=%E6%8E%A5%E5%85%A5%E6%B5%81%E7%A8%8B 01H7Z17A1QVW58B2FZE7SDJHHJ=traits-and-limitations h_01HE7RG1GE2E37NN4WT1XYG9YX=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />
