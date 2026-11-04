---
title: 广告主入驻指南
metadata:
  keywords:
    - SDK
    - Integration
    - Reports
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2015-01-18T11:03:01Z'
  edited_at: '2026-10-14T10:03:42Z'
  id: 207033486
  locale: zh-cn
  section: Marketer onboarding
  section_id: 6550866490129
  url: https://support.appsflyer.com/hc/zh-cn/articles/207033486
---
> **概要：** 本文重点介绍了与广告主相关的各种设置，详细解释了其中的步骤、时间安排和涉及人员，帮助您将相关应用和团队接入AppsFlyer，充分利用您的AppsFlyer账户。

<Embed title="广告主入驻指南" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/gamcb25kgu" providerUrl="https://fast.wistia.com" />

<div id="introduction" />

## 简介

本文旨在帮助广告主侧（应用所有者）的产品经理**规划并执行AppsFlyer入驻工作**。为此，我们列出了每一项工作的负责人员和预估用时。

请注意：本文中的预估用时是基于我们与大量新客户的合作经验总结得出的，仅供参考。每个广告主、每个应用及其接入情况都会有所不同，因此您的实际用时可能会有出入。

<div id="account-setup" />

## 账户设置

**账户管理员**必须完成以下步骤：

| 步骤 | 用时 | 注意事项 |
| --- | --- | --- |
| 在AppsFlyer平台<Anchor target="_blank" href="https://www.appsflyer.com/get-started/">注册</Anchor> | 5分钟 | 理想情况下，账户管理员会应是AppsFlyer的真实用户，能在必要时接收重要信息。 |
| <Anchor target="_blank" href="/marketers/zh/docs/user-management#creating-users">在账户下添加用户</Anchor>并为其设置权限，以便其使用AppsFlyer面板 | 每个用户1分钟 | <Anchor target="_blank" href="/marketers/zh/docs/user-management#creating-users">满足一定条件时</Anchor>，可以将相关用户添加到多个账号。 |

**结果：** 欢迎！您的AppsFlyer账户已激活，且账户下的用户能够正常使用面板。

<div id="tip" />

> 👍 **提示**
>
> 还不太了解AppsFlyer的产品和服务？让这个<Anchor target="_blank" href="/marketers/zh/docs/welcome-to-appsflyer#appsflyer-能为您提供哪些帮助">6分钟视频</Anchor>带您走近AppsFlyer。

<div id="app-onboarding" />

## 应用入驻

下文所列的**第1-3步是每次在AppsFlyer中添加应用时都必须完成的操作**（指明为“可选”的操作除外）。

您可以按照文本中的文字指南（见下文）或通过应用入驻页面来完成这些操作。应用入驻页面会指导您完成应用归因所必需的基本步骤。即使您选择通过该页面添加应用，仍建议您参考本指南，因为其中涵盖了针对具体业务需求的细节操作说明。

**请按以下方式进入应用入驻页面：**

1. 在菜单栏中点击用户菜单（即面板右上角的邮箱地址下拉菜单）
2. 选择“应用入驻”（App onboarding）

<div id="step-1-app-setup" />

## 第1步：设置应用

对于相关账户下的每一个应用，**账户管理员**都必须完成以下步骤：

| 步骤 | 用时 | 注意事项 |
| --- | --- | --- |
| 在AppsFlyer账户中<Anchor target="_blank" href="/marketers/zh/docs/adding-an-app-to-appsflyer">添加应用</Anchor> | 1分钟 | 应用添加失败一般是因为该应用之前已经被添加到了另一个账户中（通常是与您的市场人员合作的代理账户）。发生这种情况时，请联系您的CSM，或发邮件至hello@appsflyer.com，将该<Anchor target="_blank" href="/marketers/zh/docs/transferring-apps-between-accounts">应用迁移</Anchor>到您的账户中。<br /><br />另请参考添加应用时的<Anchor target="_blank" href="/marketers/zh/docs/adding-an-app-to-appsflyer#故障排查">问题排查</Anchor>指南。 |
| 设置相关应用的<Anchor target="_blank" href="/marketers/zh/docs/adding-an-app-to-appsflyer#填写其他信息不适用于网页端应用">时区和货币</Anchor>，并说明其受众是否包含儿童 | 1分钟 |  |
| 设置应用程序的  <br /><Anchor target="_blank" href="/marketers/zh/docs/set-up-re-attribution-window">再归因窗口</Anchor>（在<Anchor target="_blank" href="/marketers/zh/docs/app-settings#reattribution-window">应用配置页</Anchor>中操作） | 1分钟 | 再归因窗口期从初次激活的日期开始计算，在该窗口期中**同一设备的重装激活不记录**为新增激活。该窗口期默认为90天，您可以根据实际情况调整。 |
| 【可选】将现有用户的信息迁移到AppsFlyer | 2小时 | 如果您已具有数量庞大的现有用户，建议您<Anchor target="_blank" href="/marketers/zh/docs/migration-to-appsflyer-from-other-vendors#设备迁移可选">将其信息迁移到AppsFlyer</Anchor>，以避免为这些用户重复付费。<br /><br />**请注意：** 请让您的AppsFlyer CSM协助您完成这一步，或发邮件至[hello@appsflyer.com](mailto:hello@appsflyer.com))联系技术支持团队寻求协助。 |

**结果：完成上述步骤后**，您的应用在AppsFlyer面板中即已设定完毕。

<div id="step-2-sdk--api-integration" />

## 第2步：SDK / API对接

对于在[第1步：应用设置](/docs/getting-started-onboarding-for-marketers#第1步设置应用)中添加到AppsFlyer后台的每一个应用，请完成以下操作：设置应用：

| 步骤 | 负责人 | 用时 | 注意事项 |
| --- | --- | --- | --- |
| 在可选范围内根据实际需求选择<Anchor target="_blank" href="/marketers/zh/docs/sdk-integration-overview">SDK功能</Anchor> | 产品经理 | 1小时 | <ul><li>基础归因功能以外的一些考量：<ul><li>您需要在广告中将用户深度链接到应用中吗？</li><li>您是否需要<Anchor target="_blank" href="/marketers/zh/docs/basic-sdk-integration-guide#拉取归因和深度链接数据">拉取该应用的归因或延迟深度链接数据</Anchor>？</li><li>是否要让AppsFlyer数据中带有<Anchor target="_blank" href="/marketers/zh/docs/basic-sdk-integration-guide#integrate-unique-identifiers-from-your-bi-system-with-appsflyer">CUID</Anchor>（客户用户ID）以作参考？</li><li>您计划如何<Anchor target="_blank" href="/marketers/zh/docs/basic-sdk-integration-guide#configure-app-tracking-transparency-att-support">针对iOS 14+设备设置隐私保护</Anchor>？您是否计划衡量卸载、投放交叉推广广告等等？</li></ul></li><li>CTV应用开发者请查阅<Anchor target="_blank" href="/marketers/zh/docs/ctv-pc-and-console-platform-attribution-concepts">CTV概览</Anchor>。</li></ul> |
| 选择要记录的<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview">应用内事件</Anchor> | 产品经理 | 1小时 | 记录用户在激活后的应用内行为能帮助您对用户**质量**有更清晰的了解。<br /><br />访问[应用内事件生成器](https://evgen.appsflyer.com/)使用我们为各垂类准备的完整推荐清单，其中包含推荐的<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview#recommended-events-by-business-vertical">应用内事件</Anchor>和参数。您也可以添加自定义事件和参数。  <br />点击**Code**按钮可查看并复制自动生成的代码，方便开发人员使用。 |
| 选择归因/深度链接数据的拉取方式 | 产品经理 | 30分钟 | 请点击以下链接，深入了解各种数据拉取<Anchor target="_blank" href="/marketers/zh/docs/basic-sdk-integration-guide#拉取归因和深度链接数据">方式</Anchor>：<ul><li><Anchor target="_blank" href="/marketers/zh/docs/pull-api-raw-data">Pull API</Anchor></li><li><Anchor target="_blank" href="/marketers/zh/docs/push-api-streaming-raw-data">Push API</Anchor></li><li><Anchor target="_blank" href="/marketers/zh/docs/create-a-onelink-template">Unified Deep Linking API</Anchor></li><li><Anchor target="_blank" href="/marketers/zh/docs/conversion-data-payloads-and-scenarios">获取转化数据</Anchor></li></ul> |
| 向开发人员交接 | 产品经理 | 5分钟 | 向您的开发人员发送一封电子邮件，包含以下指示和任务：<ul><li>SDK / API对接</li><li>应用内事件映射</li></ul>您可以在添加应用向导的<Anchor target="_blank" href="https://hq1.appsflyer.com/onboarding/apps">对接SDK</Anchor> 选项卡中找到这些内容。 |
| 开发人员接入SDK | 应用开发人员 | 3小时 | 接收投放运营人员发送的邮件，其中包含SDK对接和应用内事件映射的相关指南和任务说明。<br /><br />可通过<Anchor target="_blank" href="https://dj.dev.appsflyer.com/?utm_source=dashboard&utm_medium=app-onbrd-mail-a">AppsFlyer开发对接路径</Anchor>在Android和iOS上自动实现，或使用下方链接手动实现。<br /><br />AppsFlyer为开发人员提供下列资源：<ul><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk">安卓</Anchor></li><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk">iOS</Anchor></li><li>Unity</li><li><Anchor target="_blank" href="/marketers/zh/docs/windows-sdk-integration-for-developers">Windows Phone</Anchor></li><li><Anchor target="_blank" href="/marketers/zh/docs/other-platforms">其他平台</Anchor></li></ul> |
| <Anchor target="_blank" href="/marketers/zh/docs/testing-the-sdk-integration-for-marketers">对接测试</Anchor> | 产品经理/  <br />应用开发人员 | 1小时 | 应用上架前后都可以测试SDK对接。您可以使用联调软件防止测试影响您的应用数据。<br /><br />仅适用于Android和iOS应用：请务必<Anchor target="_blank" href="/marketers/zh/docs/registering-test-devices">为您的测试设备加白</Anchor>。 |
| 上线新版应用 | 产品经理 | 1小时 | <Anchor target="_blank" href="/marketers/zh/docs/preparing-for-the-app-store-review-nutrition-labels">为iOS App Store的审核做好准备</Anchor>。 |

**结果：** 完成上述步骤后，您就可以对相关应用进行激活归因、应用内事件衡量并使用其他不涉及开发的AppsFlyer功能。

<div id="step-3-attribution-setup" />

## 第3步：归因设置

对于在[第1步：应用设置](/docs/getting-started-onboarding-for-marketers#第1步设置应用)中添加到AppsFlyer后台的每一个应用，请完成以下操作：设置应用：

| 步骤 | 负责人 | 用时 | 注意事项 |
| --- | --- | --- | --- |
| 在AppsFlyer后台设置**付费**媒体，用于归因 | 产品经理/  <br />营销人员 | 每个渠道15分钟 | 建议详细了解<Anchor target="_blank" href="/marketers/zh/docs/self-reporting-networks-srns">自归因平台</Anchor>（即SRN），尤其是以下平台：<ul><li><Anchor target="_blank" href="/marketers/zh/docs/google-ads-adwords-integration-setup-for-advertisers">Google Ads</Anchor></li><li><Anchor target="_blank" href="/marketers/zh/docs/meta-ads-integration-setup">Meta ads</Anchor></li><li><Anchor target="_blank" href="/marketers/zh/docs/apple-ads-integration-setup">Apple Search Ads</Anchor></li><li>GMP（Doubleclick）</li></ul>请点击以下链接，深入了解非SRN平台：<ul><li><Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner">其他对接渠道</Anchor></li><li>AppsFlyer<Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters">归因链接</Anchor>的结构及参数</li></ul> |
| 使用OneLink对**自有**媒体（移动端网站、社交媒体、用户邀请等等）进行归因 | 产品经理 | 1小时 | 深入了解<Anchor target="_blank" href="/marketers/zh/docs/onelink-guide#其他选项">基于OneLink的解决方案</Anchor>在自有媒体中的使用场景 |
| 自有媒体的开发侧配置 | 应用开发人员 | 0-6.5小时（具体取决于您选用的方案） | 开发人员指南：<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/getting-started-1">深度链接入门指南</Anchor> |
| 设置归因窗口 | 产品经理 | 每个渠道2分钟 | 了解更多<Anchor target="_blank" href="/marketers/zh/docs/set-up-lookback-windows">点击和浏览回溯窗口详解</Anchor> |
| 【可选】启用再营销功能 | 产品经理 | 2分钟 | <Anchor target="_blank" href="/marketers/zh/docs/app-settings#reengagement-attribution">在应用配置页面中打开再营销开关</Anchor>。<br /><br />了解更多<Anchor target="_blank" href="/marketers/zh/docs/retargeting-attribution-guide">再营销指南</Anchor> |

**结果：** 完成上述步骤后，所有为您的应用带量的媒体渠道会在吸引到新老用户与其互动时得到归因。

<div id="step-4-additional-setup" />

## 第4步：其他设置

对于在[第1步：应用设置](/docs/getting-started-onboarding-for-marketers#第1步设置应用)中添加到AppsFlyer后台的每一个应用，请完成以下操作：设置应用。

部分操作在有些情况下是必须完成的，具体取决于您的业务目标。

| 步骤 | 负责人 | 相关资源 |
| --- | --- | --- |
| 记录收入以优化拉新投放 | 产品经理/  <br />应用开发人员 | <ul><li><Anchor target="_blank" href="/marketers/zh/docs/legacy-receipt-validation-for-in-app-purchases">应用内购验证</Anchor></li><li><Anchor target="_blank" href="/marketers/zh/docs/roi360-guide-ad-revenue-attribution">广告变现</Anchor></li><li>用户订阅</li></ul> |
| 了解成本数据的汇总及查看方式 | 产品经理 | <Anchor target="_blank" href="/marketers/zh/docs/roi360-cost-aggregation-overview">ROI360—成本汇总解决方案</Anchor> |
| 设置其他的<Anchor target="_blank" href="/marketers/zh/docs/3rd-party-platforms">第三方合作平台</Anchor> | 产品经理/  <br />应用开发人员 | <ul><li><Anchor target="_blank" href="/marketers/zh/docs/mparticle-integration-with-appsflyer">mParticle</Anchor></li><li><Anchor target="_blank" href="/marketers/zh/docs/segment-integration">Segment</Anchor></li><li><Anchor target="_blank" href="/marketers/zh/docs/mixpanel-integration-with-appsflyer">Mixpanel</Anchor></li><li><Anchor target="_blank" href="/marketers/zh/docs/amplitude-integration-with-appsflyer">Amplitude</Anchor></li><li><Anchor target="_blank" href="/marketers/zh/docs/adobe-analytics-integration-with-appsflyer">Adobe Analytics</Anchor>（Omniture）</li><li><Anchor target="_blank" href="/marketers/zh/docs/braze-formerly-appboy-integration-with-appsflyer">Braze</Anchor></li></ul> |
| 了解AppsFlyer高阶功能帮助您节省时间和预算 | 产品经理 | <ul><li><Anchor target="_blank" href="/marketers/zh/docs/audiences-guide">受众共享（Audiences）</Anchor></li><li><Anchor target="_blank" href="/marketers/zh/docs/pivot-table-user-metrics">数据透视表</Anchor></li><li><Anchor target="_blank" href="/marketers/zh/docs/data-locker-for-marketers">Data Locker</Anchor></li></ul> |
| 屏蔽假量并避免误伤 | 产品经理 | <ul><li><Anchor target="_blank" href="/marketers/zh/docs/protect360-anti-fraud-guide">Protect360—防作弊解决方案</Anchor></li><li>使用<Anchor target="_blank" href="/marketers/zh/docs/implement-validation-rules-to-prevent-fraud">验证规则</Anchor>以确保正常投放不会遭到误伤</li></ul> |
| 使用S2S API上报在应用外部发生的事件 | 产品经理/  <br />应用开发人员 | <Anchor target="_blank" href="/marketers/zh/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S REST API</Anchor> |
| 衡量媒体渠道的卸载率 | 产品经理/  <br />应用开发人员 | 卸载衡量 |
| 跨流量入口、跨平台、跨设备梳理整合用户链路 | 产品经理/  <br />应用开发人员 | <Anchor target="_blank" href="/marketers/zh/docs/people-based-attribution-pba-overview">基于用户的归因（PBA）</Anchor> |
| 确保隐私合规：GDPR、CCPA等 | 产品经理/  <br />应用开发人员 | 允许用户<Anchor target="_blank" href="/marketers/zh/docs/apply-privacy-preserving-sdk-methods">拒绝授权</Anchor>进行归因 |

<div id="enrich-your-knowledge" />

## 扩展知识点

建议所有AppsFlyer用户都了解以下信息：

| 步骤 | 用时 |
| --- | --- |
| 了解AppsFlyer数据总览面板 | 15分钟 |
| 在AppsFlyer面板中查看<Anchor target="_blank" href="/marketers/zh/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">LTV维度与活跃维度数据之间的差异</Anchor>（了解为什么应用内事件总结在数据总览面中和在活跃面板中有所不同） | 15分钟 |
| 了解AppsFlyer<Anchor target="_blank" href="/marketers/zh/docs/appsflyer-attribution-model">归因模型</Anchor> | 30分钟 |
| 了解<Anchor target="_blank" href="/marketers/zh/docs/aggregated-and-analytics-reporting-overview">汇总报告及分析工具</Anchor> | 30分钟 |
| 了解<Anchor target="_blank" href="/marketers/zh/docs/raw-data-reporting-overview">原始数据报告</Anchor> | 30分钟 |

<div id="related" />

## 相关信息

<div id="tip-1" />

> 👍 **提示**
>
> 刚开始接触UA（用户获取）？<Anchor target="_blank" href="https://www.appsflyer.com/resources/ecommerce/getting-started-user-acquisition-apps-complete-guide/">这篇文档</Anchor>将帮助您了解用户获取的规划、执行和持续优化过程中最棘手的难题和最关键的要素。

<div id="note" />

> 📘 **注意**
>
> 非广告主如何使用AppsFlyer？无需担心！
> 我们为各个参与方提供了相应的入门指南：
>
> * <Anchor target="_blank" href="/partners/zh/docs/getting-started-agency-onboarding">代理商入门指南</Anchor>
> * <Anchor target="_blank" href="/partners/zh/docs/getting-started-onboarding-guide-for-ad-networks">广告平台入驻指南</Anchor>

<div data-zendesk-anchors="introduction=%E7%AE%80%E4%BB%8B 01H8BD2FJ6TQ5FP9625MNP2B3Z=%E7%AE%80%E4%BB%8B step-1-account-setup=%E8%B4%A6%E6%88%B7%E8%AE%BE%E7%BD%AE 01H8BD2FJ6E8KZW41V04SBDQPQ=%E8%B4%A6%E6%88%B7%E8%AE%BE%E7%BD%AE 01H8BD2FJ6A39JB8J0PQ3EY52N=%E6%8F%90%E7%A4%BA app-onboarding=%E5%BA%94%E7%94%A8%E5%85%A5%E9%A9%BB 01H8V6FS97NTTF1VPQQDZQT973=%E5%BA%94%E7%94%A8%E5%85%A5%E9%A9%BB step-2-app-setup=%E7%AC%AC1%E6%AD%A5%E8%AE%BE%E7%BD%AE%E5%BA%94%E7%94%A8 01H8BD2FJ61S3Z22CD01H6F39E=%E7%AC%AC1%E6%AD%A5%E8%AE%BE%E7%BD%AE%E5%BA%94%E7%94%A8 step-3-sdk-integration=%E7%AC%AC2%E6%AD%A5sdk--api%E5%AF%B9%E6%8E%A5 01H8BD2FJ6CY53QXVB5QC98KTT=%E7%AC%AC2%E6%AD%A5sdk--api%E5%AF%B9%E6%8E%A5 step-4-attribution-setup=%E7%AC%AC3%E6%AD%A5%E5%BD%92%E5%9B%A0%E8%AE%BE%E7%BD%AE 01H8BD2FJ6Q8R83FV0XS5B93B3=%E7%AC%AC3%E6%AD%A5%E5%BD%92%E5%9B%A0%E8%AE%BE%E7%BD%AE step-5-additional-setup=%E7%AC%AC4%E6%AD%A5%E5%85%B6%E4%BB%96%E8%AE%BE%E7%BD%AE 01H8BD2FJ76WD0MRCJXZH8XABN=%E7%AC%AC4%E6%AD%A5%E5%85%B6%E4%BB%96%E8%AE%BE%E7%BD%AE enrich-your-knowledge=%E6%89%A9%E5%B1%95%E7%9F%A5%E8%AF%86%E7%82%B9 01H8BD2FJ7ZV0ZYHQZ8DBTTFFK=%E6%89%A9%E5%B1%95%E7%9F%A5%E8%AF%86%E7%82%B9 related=%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF 01H8BD2FJ748GFC4VJWWYGGN1K=%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF 01H8BD2FJ712NGA534TCSWQGR8=%E6%8F%90%E7%A4%BA-1 01H8BD2FJ7PRJAA1K8MESRK7VA=%E6%B3%A8%E6%84%8F" />
