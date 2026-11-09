---
title: OneLink 入职指南
metadata:
  keywords:
    - Marketers
    - set up
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2024-08-21T11:48:39Z'
  edited_at: '2026-10-14T10:07:50Z'
  id: 27699299657617
  locale: zh-cn
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/zh-cn/articles/27699299657617
---
> **概要**：您可以利用OneLink的多种强大功能，为用户打造定制化的跳转体验，实现深度链接，并对您的广告进行跨设备、跨平台、跨流量入口、跨操作系统的归因，充分提升转化和收入。

<Image align="center" alt="53010_Onelink.jpg" src="https://files.readme.io/c0d24ab87126bf765a89a25077b07d8678159cdb6f1b68eddc14a4cd2759b12a-30192941047185.jpg" />

<div id="about-onelink" />

## OneLink简介

<Anchor target="_blank" href="/marketers/zh/docs/onelink-guide">您可以利用AppsFlyer提供的OneLink创建带有归因、跳转和深度链接功能的广告链接，将您自有媒体中的用户转化为应用用户，并为现有用户提供流畅的场景化体验，支持所有设备、平台、操作系统以及流量入口。使用OneLink创建个性化、场景化的用户链路，引导用户进入您的应用，充分提升转化率和收入。该产品可帮助您打造下列各种个性化体验：</Anchor>

* **社媒到应用**： 在社交媒体上吸引用户互动，将流量从社交媒体帖子引导到您的应用。
* **应用到应用**：将用户从其他应用引导到您的应用。
* <Anchor target="_blank" href="/marketers/zh/docs/convert-your-mobile-web-visitors-to-app-users">网页到应用</Anchor>通过智能横幅（Smart Banner）和智能脚本（Smart Script）将移动端网页访客转化为应用用户。
* **二维码到应用**： 通过二维码推动拉新，让用户在线下体验过程的关键环节中扫描二维码。您也可以在PC端、电视或CTV广告中添加二维码，将用户引导到应用。
* **邮件到应用**：通过邮件服务商（ESP）向用户发送邮件，并将他们引导到应用。
* **短信到应用**：创建专用于短信和短消息营销的链接，通过文字消息与用户互动。
* **推荐到应用**：创建用户邀请链接，让用户以及博主邀请其他人使用您的应用或分享应用中的指定内容（如文章）。
* **Custom**：使用多种控件选项创建自定义的用户体验，细致打磨整条链路的方方面面。 不论您的用户来自PC端还是移动端，线上还是线下，自有媒体还是付费媒体，OneLink都能将流量引导到您需要的地方。

<div id="onelink-onboarding" />

## OneLink入门指引

**首次使用OneLink时，请按以下步骤操作：**

<span id="h_01J5WC8Z4J352AHSDTRCEP2W9H"></span>**前期准备**

* 确保您有一个AppsFlyer<Anchor target="_blank" href="https://www.appsflyer.com/sign-up/">账号</Anchor>，且已在该账号中添加至少一个应用。
* 设置OneLink时，您必须具备相关AppsFlyer账号的管理员身份或OneLink模板的添加/修改<Anchor target="_blank" href="/marketers/zh/docs/user-management">权限</Anchor>。
* <Anchor target="_blank" href="/marketers/zh/docs/integrate-the-appsflyer-sdk">您的移动端应用中必须安装AppsFlyer</Anchor> SDK，用于对激活和应用内事件进行归因，并实现深度链接。
  * 若相关应用尚未安装SDK，仍可创建链接并正常完成跳转，但无法进行归因。

| 事项 | 作用 | 操作 | 人员 |
| --- | --- | --- | --- |
| 1. 创建一个OneLink模板 | OneLink 模板是您将创建的链接重定向逻辑所需的基础。 | <ul><li>市场人员/产品经理：在AppsFlyer后台设置一个<Anchor target="_blank" href="/marketers/zh/docs/create-a-onelink-template">OneLink模板</Anchor>。</li><li>安卓开发人员：配置现有用户的应用打开方式（使用安卓App Link和URI scheme）</li><li>iOS开发人员：配置现有用户的应用打开方式（使用iOS Universal Link和URI scheme）。</li></ul><Anchor target="_blank" href="/marketers/zh/docs/create-a-onelink-template#add-redirection-logic-for-existing-app-users">开发人员相关说明</Anchor> | 市场人员和开发人员 |
| 2. 创建OneLink链接 | 在新模板的基础上创建一条OneLink，用于您的广告投放。 | <ul><li>市场人员/产品经理：在AppsFlyer后台设置一条<Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#创建onelink链接">OneLink链接</Anchor>，选择您要提供的用户体验，并添加所需的归因和深度链接参数。</li><li>安卓和iOS开发人员：设置<Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">深度链接</Anchor>（如有需要）。</li></ul> | 市场人员和开发人员 |
| 3. 设置跳转白名单 | 为了保障用户的数据安全，您通过AppsFlyer创建的链接仅会跳转到含有加白域名的网址。 | 更新您的<Anchor target="_blank" href="/marketers/zh/docs/set-up-your-domain-redirect-allowlist">跳转白名单</Anchor>，确保其中包含您想让用户跳转的所有域名。 | 市场人员 |
| 4. 测试新链接 | 测试并验证该链接是否能成功完成跳转：<ul><li>未安装应用的新用户</li><li>已安装应用的现有用户</li></ul> | <Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#testing">测试</Anchor>新创建的链接。 | 市场人员 |
| 5. 在您的广告中使用该链接，并衡量投放效果 |  | <ol><li>将新链接添加到您的广告中，投放到目标客群。</li><li>在AppsFlyer的数据总览面板中查看相关广告投放的效果（需按广告系列筛选数据）。</li></ol>完成上述操作后，您已完成OneLink的初始设置。 | 市场人员、数据分析师 |
| **可选功能** |  | 完成初始设置后，您可以探索OneLink的其他功能，包括：<ul><li>网页到应用：将网页用户转化为应用用户，并衡量网页到应用的转化漏斗。</li><li><Anchor target="_blank" href="/marketers/zh/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">OneLink API</Anchor>和<Anchor target="_blank" href="/marketers/zh/docs/perform-onelink-bulk-actions-via-csv">批量链接创建</Anchor>：同时铺开投放多个广告系列，快速、轻松地创建上千个OneLink链接。<ul><li>OneLink API对购买了Enterprise企业套餐的客户开放。</li></ul></li><li><Anchor target="_blank" href="/marketers/zh/docs/export-onelink-urls">导出OneLink URL：下载您在AppsFlyer中创建的OneLink URL。</Anchor></li><li><Anchor target="_blank" href="/marketers/zh/docs/measuring-push-notification-re-engagement-campaigns">衡量消息推送型再互动广告</Anchor>：您可以结合OneLink使用推送通知进行推广，衡量用户的再互动行为。</li><li><Anchor target="_blank" href="/marketers/zh/docs/cross-promotion-attribution-for-marketers">交叉推广归因</Anchor>：现有用户是您在推广新应用时的优质资源，他们是最有可能安装新应用的人群。具体请查阅如何通过SDK方式创建并衡量交叉推广广告。</li><li><Anchor target="_blank" href="/marketers/zh/docs/understand-onelink-short-vs-long-urls">长链</Anchor>：您可以在OneLink自定义链接中添加参数，或通过简单的工作表公式生成大量OneLink自定义链接。</li></ul> | 市场人员和开发人员 |

如果您在初次使用OneLink时需要任何帮助，请联系负责贵司的AF销售，或发邮件至[hello@appsflyer.com](mailto:hello@appsflyer.com)。

<div id="traits-and-limitations" />

## 特点与局限性

| 特点 | 说明 |
| --- | --- |
| iPad Safari 中的自有媒体归因 | 当用户在使用 Safari 浏览器的 iPad 上点击自有媒体链接时，浏览器可能会报告一个 **类似 Macintosh 的用户代理**，而不是 iPad 设备型号。因此，AppsFlyer 将点击识别为来自 Mac 设备，而应用安装则被识别为来自 iPad。由于概率归因依赖于点击和安装之间设备特征的匹配，这种不匹配会阻止归因，并可能导致未归因的安装或延迟深度链接失败。此限制仅适用于使用 Safari 的 iPad 设备上的自有媒体流量。 |

<div data-zendesk-anchors="overview=onelink%E7%AE%80%E4%BB%8B h_01J2G7RMHSPPXCWJ60W9HZASXX=onelink%E7%AE%80%E4%BB%8B h_01HKHGX9JJQQCKF9SDZRSCM1XJ=onelink%E7%AE%80%E4%BB%8B xyz-onboarding=onelink%E5%85%A5%E9%97%A8%E6%8C%87%E5%BC%95 h_01J2RJFH0B4R815CWDQNEB2C1P=onelink%E5%85%A5%E9%97%A8%E6%8C%87%E5%BC%95 traits-and-limitations=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 h_01KFAG3N0X0W0RCJXK00KX038E=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7" />
