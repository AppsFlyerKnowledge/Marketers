---
title: AppsFlyer中的PlayStation对接配置
metadata:
  keywords:
    - CTV
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2022-11-03T15:12:14Z'
  edited_at: '2026-10-14T10:10:11Z'
  id: 10342860530961
  locale: zh-cn
  section: Promoting Console apps
  section_id: 15329052471057
  url: https://support.appsflyer.com/hc/zh-cn/articles/10342860530961
---
> **概要： 概要：本文介绍了PlayStation应用与AppsFlyer的对接方式。对接完成后，您就可以针对PlayStation上的广告收集归因和事件数据。**

## PlayStation归因简介

适用于主机和CTV应用的PlayStation操作系统可在所有PlayStation设备中运行。

在PC端运行的应用可以通过S2S API或SDK与AppsFlyer对接，从而获得归因数据和投放效果指标，了解应用打开和应用内事件的流量来源和带量广告。这些关键信息能够帮助营销人员评估并优化其市场推广工作。

PlayStation API对接适用于：

* PlayStation设备。
* PlayStation应用的归因和事件记录（即在用户的PlayStation设备上进行归因和记录）。

### 归因链接示例

下文所示的归因流程重点说明了从广告互动到归因的用户链路中最关键的几个环节。其中还包含AppsFlyer推荐的跨平台落地页。 **请注意**：请注意：虽然我们建议您使用跨平台落地页，但您仍可以选择直接归因链接。

User\_windows.jpg

1. <span id="marketing-touchpoint"></span>营销触点这些营销触点可包括定期/不定期邮件、社交媒体、移动端网页等等。
2. 这个步骤对于UTM及其他URL参数的收集至关重要。有了这些参数，AppsFlyer就能将来自相关点击/激活的用户归因到带量的媒体渠道或广告主的自有媒体。  
   如果您的游戏支持多个平台，可以在落地页中提供跳转到各个平台的链接，比如Xbox、Microsoft商店以及Steam页面等。
4. 游戏激活游戏激活：用户激活游戏时即会触发归因，并开始记录应用内事件和应用打开（session）。

## 对接流程

下表列出了PlayStation应用对接到AppsFlyer时需要完成的工作。

| 事项 | 可用操作 | 人员 |
| --- | --- | --- |
| 设置应用 | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">创建一个AppsFlyer帐户</Anchor></li><li><Anchor target="_blank" href="/marketers/zh/docs/user-management">在账户下添加用户，并为其开放必要权限</Anchor></li><li><Anchor target="_blank" href="/marketers/zh/docs/adding-an-app-to-appsflyer">在AppsFlyer中添加您的PlayStation应用。</Anchor></li></ul> | 营销人员 |
| 为您的应用配置API对接（通过S2S发送数据） | 在您的应用中<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/pc-console-ctv-api-overview">接入AppsFlyer API</Anchor>，使其向AppsFlyer上报下列事件：<ul><li>首次打开</li><li>应用内事件</li><li>应用打开（Sessions）</li></ul>**请注意**：<ul><li>应用首次打开（first app open）必须在应用内事件和应用打开（session）之前上报。</li><li>使用`device_ids`参数时，请选择`custom`类型。<ul><li>通过`custom`customcustom生成的<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_first-open-app-platform-app-id">应用首次打开</Anchor>（first opens）ID应与您的<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_inapp-app-platform-app-id">应用内事件</Anchor>和<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_session-app-platform-app-id">应用打开</Anchor>（sessions）ID一致。</li><li>通过该API发送事件。请向开发人员说明您需要发送的事件。 对于要发送到AppsFlyer的事件，请务必在配置API时完成这些事件的设置和映射。</li></ul></li></ul>如需上报自有媒体中的广告互动，请对接<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">impression engagement API。</Anchor> | 应用开发人员 |
| 跨平台落地页设置 | **推荐**：<br /><br /><Anchor target="_blank" href="/marketers/zh/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">进一步了解跨平台落地页</Anchor><br /><br /><Anchor target="_blank" href="/marketers/zh/docs/cross-platform-landing-pages-with-smart-script">进一步了解跨平台落地页的设置方式</Anchor><br /><br />**请注意**：<ul><li>App ID（应用ID）</li><li>**media\_source**</li></ul>以下参数是可选的，但仍建议您配置：<ul><li>**campaign**</li><li>**ad**</li><li>**ad\_set（广告组）**</li></ul> | 营销人员（可能需要开发人员协助） |
| 链接设置 | 如果您不使用跨平台落地页，可以创建直接归因链接，将其置于广告中。<br /><br /><Anchor target="_blank" href="/marketers/zh/docs/ctv-pc-and-console-platform-direct-attribution-links">了解直接归因链接的创建方式</Anchor> | 营销人员 |
| 报告设置/查看数据 | <Anchor target="_blank" href="/marketers/zh/docs/ctv-pc-and-console-platform-attribution-concepts#数据可用性">了解面板与报告中的数据可用性</Anchor> | 营销人员/数据工程师 |

<div id="traits-and-limitations" />

<Accordion title="特点与局限性">

| 特点 | 说明 |
| --- | --- |
| 再营销 | 目前尚不支持 |
| 成本数据 | 必须通过邮件<Anchor target="_blank" href="/marketers/zh/docs/import-cost-data">上传</Anchor>的方式来发送成本数据。 |

</Accordion>

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/ctv-pc-and-console-platform-attribution-concepts">CTV、PC和主机平台简介</Anchor>

<div data-zendesk-anchors="about-playstation-attribution=playstation%E5%BD%92%E5%9B%A0%E7%AE%80%E4%BB%8B 01H7Z1HPD0AB0VP6REMBF2HCR8=playstation%E5%BD%92%E5%9B%A0%E7%AE%80%E4%BB%8B example-attribution-flow=%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5%E7%A4%BA%E4%BE%8B h_01HP1Q8B11P0Q8F2Z2FRDSPNDE=%E5%BD%92%E5%9B%A0%E9%93%BE%E6%8E%A5%E7%A4%BA%E4%BE%8B 01H7Z19FJ54WZ7XV91Y36EKYQ6=marketing-touchpoint integration-procedures=%E5%AF%B9%E6%8E%A5%E6%B5%81%E7%A8%8B 01H7Z1HPD0VAMPEHBPN8MAT3ST=%E5%AF%B9%E6%8E%A5%E6%B5%81%E7%A8%8B 01H7Z1HPD0CS7CTX2KS2RVD3VA=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />
